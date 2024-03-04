Aprendiendo PROLOG - Instalación
================================
### Representación del conocimiento
### Lógica proposicional
### Lógica de primer orden 
### Agentes (inteligentes) lógicos

La idea es disponer del entorno SWI-Prolog para ejecutarlo desde línea de comandos en tu sistema operativo o desde el entorno que proporciona el programa.

Una vez instalado, usaremos Jupyter Notebooks con un kernel SWI-Prolog (Herculog), para que realizar los ejercicios propuestos en la carpeta [notebooks](./notebooks/) en el navegador.

## 1. Instalación de SWI-Prolog

Sigue las instrucciones necesarias para instalar SWI-Prolog en tu sistema operativo. 

Descarga la [versión estable SWI-Prolog](https://www.swi-prolog.org/download/stable).

Aquí también las de [desarrollo](https://www.swi-prolog.org/Download.html).

Si es MacOSX, consulta conmigo los detalles de la configuración final de las variables de entorno:

```zsh
% swipl --dump-runtime-variables

PLBASE="/Applications/SWI-Prolog.app/Contents/swipl";
SWIPL_PACK_PATH="";
PLARCH="x86_64-darwin";
PLBITS="64";
PLVERSION="90200";
PLSOEXT="so";
PLSOPATH="DYLD_LIBRARY_PATH";
PLLIBDIR="/Applications/SWI-Prolog.app/Contents/swipl/lib/x86_64-darwin";
PLLIB="-lswipl";
PLLIBSWIPL="/Applications/SWI-Prolog.app/Contents/Frameworks/libswipl.9.2.0.dylib";
PLSHARED="yes";
PLTHREADS="yes";
```

Presta atención a:

```zsh
PLLIBDIR="/Applications/SWI-Prolog.app/Contents/swipl/lib/x86_64-darwin";
PLLIBSWIPL="/Applications/SWI-Prolog.app/Contents/Frameworks/libswipl.9.2.0.dylib";
```

Edita tu fichero `.zshrc` o `.bashrc` en tu `home` para que incluya esta configuración de variables de entorno:

```zsh
PATH="/Applications/SWI-Prolog.app/Contents/MACOS/:${PATH}"
export DYLD_FALLBACK_LIBRARY_PATH="/Applications/SWI-Prolog.app/Contents/Frameworks/"
export PATH
```


## 2. Instalación del kernel Prolog - Herculog para jupyter notebook

### Desde la distribución Herculog

Aquí el repo:

https://github.com/hhu-stups/prolog-jupyter-kernel

https://pypi.org/project/prolog-kernel/

Es necesario seguir la instalación en el orden indicado pineando[^1] las versiones de las dependencias Prolog:

[Instruccciones instalación](https://github.com/hhu-stups/prolog-jupyter-kernel/blob/master/README.md#installation)

Aquí un ejemplo de [jupyter notebook con kernel Prolog: sintaxis e instrucciones](https://github.com/hhu-stups/prolog-jupyter-kernel/blob/master/notebooks/feature_introduction/swi/using_jupyter_notebooks_with_swi_prolog.ipynb)

### Desde este repo

Clona el proyecto en tu máquina:

`mkdir prolog; cd prolog`

`git clone https://github.com/dfleta/prolog-for-IA.git` 

Crea el entorno virtual y actívalo:

`python -m venv venv`

`source venv/bin/activate`

Las dependencias de primer nivel testeadas en el repo de Herculog están pineadas en el fichero [requirements.in](./requirements.in), pero para instalar todas las dependencias has de utilizar el fichero [requirements.txt](./requirements.txt): 

`pip install -r requirements.txt`

El fichero [requirements-updated.txt](./requirements-updated.txt) contiene las versiones actualizadas de las dependencias de primer nivel con las que el kernel Herculog funciona para esta versión de SWI-Prolog:

``` zsh
% swipl --version 
SWI-Prolog version 9.2.0 for x86_64-darwin
```

## 3. Ejercicios propuestos Prolog

En el directorio de este repo [notebooks](./notebooks/) encontrarás los _notebooks_ con los ejercicios propuestos.

Echa un ojo a las [soluciones](./notebooks_solucion/).

Una vez que completes la instalación de SWI-Prolog y el kernel Herculog para Jupyter ejecuta:

`source venv/bin/activate`

`jupyter-lab`

Accede con tu navegador al localhost:

`http://localhost:8888/`

y abre el notebook seleccionando el kernel `Prolog`.

## 4. Cómo aprender Prolog

En el directorio [doc](./doc) encontrarás mis apuntes del libro [_Prolog, programming for Artificial Intelligence_ de Ivan Bratko.](https://drive.google.com/file/d/19RQO9T4452kuj-iK5ynsuafZ5opRIWOn/view?usp=drive_link) 

Iré publicando mis resúmenes de los capítulos según los necesitemos.

Empléalos para completar los ejercicios propuestos.

----------------------------------------------------------------------------------------------------
[^1]: Consulta el fichero `requirements.in` y mi [tutorial sobre cómo especificar las versiones de las dependencias](https://github.com/dfleta/ollivanders?tab=readme-ov-file#dependencias) de tu proyecto Python.