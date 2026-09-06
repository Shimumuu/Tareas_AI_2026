# Tarea Nº 1 — Inteligencia Artificial

Universidad Diego Portales · Facultad de Ingeniería y Ciencias

Repositorio con el desarrollo de la Tarea 1 del curso de Inteligencia Artificial.
El trabajo se entrega en un único Jupyter Notebook: `Tarea 1 - IA.ipynb`.

## Integrantes

- Magdalena Correa
- Martin Melo

## Requisitos

**Python 3.13** (obligatorio).

No usar Python 3.14 o superior: la librería `hmmlearn` no publica wheels
precompilados para esas versiones, por lo que `pip` intenta compilarla desde
el código fuente y la instalación falla si no se cuenta con Microsoft Visual
C++ Build Tools.

Verificar la versión disponible, ya que hay que tener el py 3.13.15 por el HMMlearn:

```powershell
py -0p
```

Si Python 3.13 no aparece en la lista, descargarlo desde
[python.org/downloads](https://www.python.org/downloads/). Puede convivir con
otras versiones sin necesidad de desinstalarlas.

## Instalación

### Windows (PowerShell)

```powershell
py -3.13 -m venv mi_entorno
.\mi_entorno\Scripts\Activate.ps1
pip install -r requirements.txt
```

Si PowerShell bloquea la activación del entorno con el mensaje
`la ejecución de scripts está deshabilitada en este sistema`, ejecutar una
sola vez:

```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

### macOS / Linux

```bash
python3.13 -m venv mi_entorno
source mi_entorno/bin/activate
pip install -r requirements.txt
```

### Verificación

Con el entorno activado:

```
python --version     # debe indicar 3.13.x
pip list             # debe incluir pgmpy y hmmlearn
```

## Ejecución

1. Abrir la carpeta del repositorio en VS Code.
2. Abrir `Tarea 1 - IA.ipynb`.
3. Seleccionar el kernel correspondiente al entorno `mi_entorno`
   (esquina superior derecha del notebook). En VS Code también puede
   usarse `Ctrl+Shift+P` → *Python: Select Interpreter*.
4. Ejecutar las celdas en orden, o usar **Run All**.

Los datos se leen mediante rutas relativas desde la carpeta `Dataset/`, por
lo que el notebook se ejecuta sin ninguna modificación una vez clonado el
repositorio.

## Estructura del repositorio

```
.
├── Dataset/
│   ├── energydata_complete.csv    # Appliances Energy Prediction
│   ├── diabetic_data.csv          # Diabetes 130-US hospitals
│   └── IDS_mapping.csv            # Diccionario de códigos
├── Tarea 1 - IA.ipynb             # Desarrollo de la tarea
├── requirements.txt               # Dependencias con versiones fijadas
├── .gitignore
└── README.md
```

El entorno virtual (`mi_entorno/`) está excluido del repositorio mediante
`.gitignore` y debe crearse localmente siguiendo los pasos de instalación.

## Datos

| Archivo | Dataset | Fuente |
|---|---|---|
| `energydata_complete.csv` | Appliances Energy Prediction | [UCI 374](https://archive.ics.uci.edu/dataset/374/appliances+energy+prediction) |
| `diabetic_data.csv` | Diabetes 130-US hospitals (1999–2008) | [UCI 296](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008) |
| `IDS_mapping.csv` | Diccionario de códigos de admisión y alta | [UCI 296](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008) |

Los archivos están incluidos en el repositorio para garantizar la
reproducibilidad de la ejecución sin depender de descargas externas.

## Dependencias

| Librería | Versión | Uso |
|---|---|---|
| `pgmpy` | 1.1.2 | Redes bayesianas |
| `hmmlearn` | 0.3.3 | Modelos ocultos de Markov |
| `pandas` | 3.0.5 | Manipulación de datos |
| `numpy` | 2.5.2 | Operaciones numéricas |
| `matplotlib` | 3.11.1 | Visualizaciones |
| `ipykernel` | 7.3.0 | Ejecución del notebook |
| `ucimlrepo` | 0.0.7 | Acceso al repositorio UCI |

Las versiones están fijadas en `requirements.txt`. Esto es relevante en el
caso de `pgmpy`, cuya API cambió entre las versiones 0.x y 1.x: el código de
este repositorio utiliza la nomenclatura de la versión 1.x
(`DiscreteBayesianNetwork` en lugar de `BayesianModel`, entre otros).

## Uso de herramientas generativas

Uso de Claude para poder dejar listo el entorno para poder empezar a realizar la tarea ya que hubo complicaciones al intentar instalar el HMMlearn y que por sugerencia que se recibio antes de empezar, se realizo un entorno para mantener seguro el sistema operativo.
Asi mismo se utilizo para poder tener el readme de instalación ya que no se como lograr una mejor explicación de lo que se realizo sobre el entorno y los problemas que se presentaron ante el HMMlearn con la version 3.14. Lo que termino obligando a usar una version anterior con ayuda externa.
