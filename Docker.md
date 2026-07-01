### Instrucciones Docker para CC-0C2

Guía práctica para construir y ejecutar el entorno reproducible del curso con Docker usando imágenes separadas para **CPU** y **GPU**.

> En este proyecto la carpeta del curso se llama **`CC-0C2`**, pero las imágenes Docker recomendadas se construirán con los nombres **`entorno_nlp_cpu`** y **`entorno_nlp_gpu`**.

#### 1. Estructura recomendada

```text
CC-0C2/
├── Dockerfile
├── requirements-base.txt
├── requirements-opcional.txt
├── Docker.md
├── verificacion_entorno.ipynb
├── .dockerignore
└── Semana1/
    ├── Cuaderno1-CC0C2.ipynb
    └── Enlaces.md
```

#### 2. Qué hace este Dockerfile

El `Dockerfile` de este proyecto:

- usa `python:3.11-slim`
- copia `requirements-base.txt` y `requirements-opcional.txt`
- instala primero la base y luego, si corresponde, los paquetes opcionales
- instala PyTorch según el argumento `TORCH_FLAVOR`
- permite construir una imagen para **CPU** o para **GPU NVIDIA**
- descarga recursos de `nltk`
- descarga el modelo `es_core_news_sm` de `spaCy`
- expone `JupyterLab` en el puerto `8891`

#### 3. Cómo elegir CPU o GPU

El parámetro `TORCH_FLAVOR` controla qué variante de PyTorch se instala:

- `cpu`: instala PyTorch para CPU
- `cu121`: instala PyTorch con CUDA 12.1
- `cu124`: instala PyTorch con CUDA 12.4

Uso recomendado:

- si la computadora **no tiene GPU NVIDIA**, construye la imagen CPU
- si la computadora **sí tiene GPU NVIDIA**, construye la imagen GPU y ejecuta el contenedor con `--gpus all`

#### 4. Tags recomendados

Para evitar confusión entre máquinas, usa dos tags distintos:

- **`entorno_nlp_cpu`** para la PC sin GPU
- **`entorno_nlp_gpu`** para la PC con GPU NVIDIA

Así el mismo proyecto mantiene un solo `Dockerfile`, pero dos imágenes distintas según el equipo.

#### 5. Construcción de imágenes

##### 5.1 Build base en CPU

```bash
docker build --no-cache \
  --build-arg INSTALL_opcional=false \
  --build-arg TORCH_FLAVOR=cpu \
  -t entorno_nlp_cpu .
```

##### 5.2 Build completa en CPU

```bash
docker build --no-cache \
  --build-arg INSTALL_opcional=true \
  --build-arg TORCH_FLAVOR=cpu \
  -t entorno_nlp_cpu .
```

##### 5.3 Build completa con GPU NVIDIA

```bash
docker build --no-cache \
  --build-arg INSTALL_opcional=true \
  --build-arg TORCH_FLAVOR=cu121 \
  -t entorno_nlp_gpu .
```

Si necesitas CUDA 12.4:

```bash
docker build --no-cache \
  --build-arg INSTALL_opcional=true \
  --build-arg TORCH_FLAVOR=cu124 \
  -t entorno_nlp_gpu .
```

##### 5.4 Verificar imágenes

```bash
docker images | grep entorno_nlp
```

#### 6. Ejecutar el contenedor

##### 6.1 Linux/macOS/Git Bash en CPU

```bash
docker run -it --rm \
  --name entorno_nlp_container \
  -p 8891:8891 \
  -v "$(pwd)":/workspace \
  entorno_nlp_cpu
```

##### 6.2 Linux/macOS/Git Bash con GPU NVIDIA

```bash
docker run -it --rm \
  --gpus all \
  --name entorno_nlp_container \
  -p 8891:8891 \
  -v "$(pwd)":/workspace \
  entorno_nlp_gpu
```

##### 6.3 Windows PowerShell en CPU

```powershell
docker run -it --rm `
  --name entorno_nlp_container `
  -p 8891:8891 `
  -v "${PWD}:/workspace" `
  entorno_nlp_cpu
```

##### 6.4 Windows PowerShell con GPU NVIDIA

```powershell
docker run -it --rm `
  --gpus all `
  --name entorno_nlp_container `
  -p 8891:8891 `
  -v "${PWD}:/workspace" `
  entorno_nlp_gpu
```

##### 6.5 Windows CMD en CPU

```bat
docker run -it --rm --name entorno_nlp_container -p 8891:8891 -v %cd%:/workspace entorno_nlp_cpu
```

##### 6.6 Windows CMD con GPU NVIDIA

```bat
docker run -it --rm --gpus all --name entorno_nlp_container -p 8891:8891 -v %cd%:/workspace entorno_nlp_gpu
```

#### 7. Abrir JupyterLab

Al iniciar el contenedor, abre en el navegador:

```text
http://localhost:8891/lab
```

Si Jupyter muestra token, cópialo desde los logs del contenedor.

#### 8. Qué sucede específicamente en Ubuntu

En Ubuntu hay una diferencia importante:

- **Docker Desktop para Linux** usa una **máquina virtual** y normalmente trabaja con el contexto `desktop-linux`
- por eso, aunque Docker Desktop puede servir para tareas normales, **no es la ruta recomendada para esta práctica con GPU en Ubuntu**
- para usar GPU en Ubuntu, conviene usar el **daemon local del host**, es decir, el contexto `default`, junto con **NVIDIA Container Toolkit**

En otras palabras:

- si estás en Ubuntu y solo quieres CPU, puedes usar Docker normalmente
- si estás en Ubuntu y quieres GPU, evita trabajar con `desktop-linux` para esta práctica y usa `default`

##### 8.1 Ver el contexto actual

```bash
docker context ls
```

Si ves algo como esto:

```text
default           Current DOCKER_HOST based configuration   unix:///var/run/docker.sock
desktop-linux *   Docker Desktop                            unix:///home/USUARIO/.docker/desktop/docker.sock
```

entonces tus comandos están yendo a Docker Desktop.

##### 8.2 Cambiar al contexto correcto en Ubuntu

```bash
docker context use default
```

Después verifica otra vez:

```bash
docker context ls
```

Debería quedar:

```text
default *
```

##### 8.3 Requisito para GPU en Ubuntu

Además del driver NVIDIA, necesitas tener instalado **NVIDIA Container Toolkit** en el host.

Prueba rápida recomendada:

```bash
docker run --rm --runtime=nvidia --gpus all ubuntu nvidia-smi
```

Si ese comando muestra la GPU dentro del contenedor, entonces Docker ya tiene acceso correcto a la GPU en Ubuntu.

##### 8.4 Paso a paso completo en Ubuntu con GPU

1. entra a la carpeta del proyecto:

```bash
cd ~/CC-0C2
```

2. cambia al contexto correcto:

```bash
docker context use default
```

3. construye la imagen GPU:

```bash
docker build --no-cache \
  --build-arg INSTALL_opcional=true \
  --build-arg TORCH_FLAVOR=cu121 \
  -t entorno_nlp_gpu .
```

4. ejecuta el contenedor con acceso a GPU:

```bash
docker run --gpus all -it --rm \
  --name entorno_nlp_container \
  -p 8891:8891 \
  -v "$(pwd)":/workspace \
  entorno_nlp_gpu
```

5. abre JupyterLab en el navegador:

```text
http://localhost:8891/lab
```

6. valida dentro del contenedor o en una terminal de Jupyter:

```bash
python -c "import torch; print(torch.__version__); print('cuda:', torch.cuda.is_available()); print('count:', torch.cuda.device_count()); print(torch.cuda.get_device_name(0) if torch.cuda.is_available() else 'sin GPU')"
```

Si todo está bien, deberías ver `cuda: True` y el nombre de la GPU.

##### 8.5 Resumen práctico para Ubuntu

##### Caso A. Ubuntu en una PC sin GPU NVIDIA

Usa:

- build con `TORCH_FLAVOR=cpu`
- imagen `entorno_nlp_cpu`
- `docker run` sin `--gpus all`

##### Caso B. Ubuntu en una PC con GPU NVIDIA

Usa:

- `docker context use default`
- NVIDIA Container Toolkit instalado
- build con `TORCH_FLAVOR=cu121` o `cu124`
- imagen `entorno_nlp_gpu`
- `docker run --gpus all ...`

#### 9. Paso a paso con Docker Desktop

##### 9.1 En Windows

Docker Desktop sí es una ruta práctica para CPU y, cuando aplica, GPU según soporte de Windows + WSL2.

##### 9.2 En Ubuntu

Puedes tener Docker Desktop instalado, pero para esta práctica con GPU conviene usar la terminal del host con el contexto `default`.

Si Docker Desktop deja activo `desktop-linux`, cambia a:

```bash
docker context use default
```

#### 10. Uso de requirements fuera de Docker

##### Opción A. Solo base

```bash
pip install -r requirements-base.txt
```

Luego instala PyTorch según tu caso.

Para CPU:

```bash
pip install torch==2.4.1 torchvision==0.19.1 torchaudio==2.4.1 --index-url https://download.pytorch.org/whl/cpu
```

Para GPU con CUDA 12.1:

```bash
pip install torch==2.4.1 torchvision==0.19.1 torchaudio==2.4.1 --index-url https://download.pytorch.org/whl/cu121
```

Para GPU con CUDA 12.4:

```bash
pip install torch==2.4.1 torchvision==0.19.1 torchaudio==2.4.1 --index-url https://download.pytorch.org/whl/cu124
```

##### Opción B. Base + opcional

```bash
pip install -r requirements-base.txt
pip install -r requirements-opcional.txt
```

Luego instala PyTorch con la variante que corresponda.

#### 11. Qué instala cada archivo

- `requirements-base.txt`: núcleo del entorno, ciencia de datos, NLP clásico y moderno, `transformers`, `datasets`, `evaluate`, `spaCy`, `NLTK` y utilidades generales
- `requirements-opcional.txt`: retrieval, embeddings, PEFT, alignment ligero, multimodalidad, demos y servicios simples
- `Dockerfile`: instala PyTorch aparte para que el mismo proyecto pueda construirse en CPU o GPU

#### 12. Validar el entorno

Abre `verificacion_entorno.ipynb` en JupyterLab y ejecuta todas las celdas.

La validación debería comprobar, como mínimo:

- versión de Python
- imports principales
- disponibilidad de `torch`
- disponibilidad de `torch.cuda.is_available()`
- carga de tokenizer de Hugging Face
- carga de un dataset pequeño
- funcionamiento básico de spaCy y NLTK

#### 13. Comprobación rápida de CPU o GPU

Dentro del contenedor puedes verificar así:

```bash
python -c "import torch; print(torch.__version__); print('cuda:', torch.cuda.is_available()); print('count:', torch.cuda.device_count()); print(torch.cuda.get_device_name(0) if torch.cuda.is_available() else 'sin GPU')"
```

Y dentro del cuaderno de PyTorch puedes usar:

```python
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
print(device)
```

#### 14. Problemas comunes

##### El build sigue fallando

Reconstruye sin caché:

```bash
docker build --no-cache --build-arg INSTALL_opcional=false --build-arg TORCH_FLAVOR=cpu -t entorno_nlp_cpu .
```

Si la build base funciona y la build completa falla, revisa `requirements-opcional.txt`.

##### La GPU no aparece dentro del contenedor

Verifica estos puntos:

1. estás en Ubuntu con `docker context use default`
2. construiste con `TORCH_FLAVOR=cu121` o `cu124`
3. ejecutaste con `--gpus all`
4. el host detecta la GPU con `nvidia-smi`
5. Docker la detecta con:

```bash
docker run --rm --runtime=nvidia --gpus all ubuntu nvidia-smi
```

Si construyes con `TORCH_FLAVOR=cpu`, el contenedor solo usará CPU aunque la máquina tenga GPU.

##### El puerto 8891 está ocupado

Usa otro puerto del host, por ejemplo `8892`:

```bash
docker run -it --rm -p 8892:8891 -v "$(pwd)":/workspace entorno_nlp_cpu
```

En ese caso abre:

```text
http://localhost:8892/lab
```

##### spaCy no descarga el modelo

Dentro del contenedor:

```bash
python -m spacy download es_core_news_sm
```

#### 15. Comandos mínimos recomendados

##### PC sin GPU

```bash
docker build --no-cache --build-arg INSTALL_opcional=true --build-arg TORCH_FLAVOR=cpu -t entorno_nlp_cpu .
docker run -it --rm --name entorno_nlp_container -p 8891:8891 -v "$(pwd)":/workspace entorno_nlp_cpu
```

##### PC con GPU en Ubuntu

```bash
docker context use default
docker build --no-cache --build-arg INSTALL_opcional=true --build-arg TORCH_FLAVOR=cu121 -t entorno_nlp_gpu .
docker run --gpus all -it --rm --name entorno_nlp_container -p 8891:8891 -v "$(pwd)":/workspace entorno_nlp_gpu
```

##### Verificación rápida en Ubuntu con GPU

```bash
docker run --rm --runtime=nvidia --gpus all ubuntu nvidia-smi
python -c "import torch; print(torch.__version__); print('cuda:', torch.cuda.is_available())"
```