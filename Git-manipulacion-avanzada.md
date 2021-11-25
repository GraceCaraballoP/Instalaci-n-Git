# Manipulación avanzada de repositorios en GIT

Veremos algunos comandos avanzados para manejar archivos en GIT. Lo haremos en una máquina con Ubuntu 20.04 a través de la terminal. Si no tenemos aún instalado GIT podemos hacerlo siguiendo los pasos de [**Instalación de GIT en Linux**](Git-defecto.md) y también deberemos seguir los pasos de la [**Configuración de Git**](Git-configuracion.md).  
Para comenzar con las pruebas debemos hacer un clon de un repositorio remoto, podéis utilizar el siguiente repositorio https://github.com/GraceCaraballoP/Repositorio-de-pruebas para realizar las pruebas de a través del siguiente comando:
```
git clone URL
``` 
A continuación nos posicionaremos en el directorio clonado llamado **libro** en mi caso, en el tuyo si utilizas mi repositorio será Repositorio-de-pruebas.
```
cd libro
``` 

## Ejercicio 1
Comenzaremos mostrando el historial de cambios del repositorio:
```
git log
```

Crearemos una carpeta llamada Capitulos:
```
mkdir capitulos
```

Dentro de esta carpeta crearemos el fichero **capitulo1.txt** con el siguiente texto:
```
Git es un sistema de control de versiones ideado por Linus Torvalds.
```
Lo haremos con **cat** y cuando ya lo tengamos preparado lo cerramos con **Ctrl+D**.
```
cat > capitulos/capitulo1.txt
Git es un sistema de control de versiones ideado por Linus Torvalds.
```

A continuación añadiremos este fichero a la zona de intercambio.
```
git add
``` 
Una vez en la zona de intercambio solo nos quedará hacer un **commit** con el mensaje **Añadido capítulo 1**.
```
git commit -m "Añadido capítulo 1."
``` 
Ahora volveremos a ver el historial de cambios del repositorio con:
```
git log
``` 

## Ejercicio 2
Crearemos un nuevo fichero **capitulo2.txt** con el siguiente texto:
```
El flujo de trabajo básico con Git consiste en: 
1- Hacer cambios en el repositorio. 
2- Añadir los cambios a la zona de intercambio temporal. 
3- Hacer un commit de los cambios.
```
Lo haremos con **cat** y cuando ya lo tengamos preparado lo cerramos con **Ctrl+D**.
```
cat > capitulos/capitulo2.txt
El flujo de trabajo básico con Git consiste en:
1- Hacer cambios en el repositorio.
2- Añadir los cambios a la zona de intercambio temporal.
3- Hacer un commit de los cambios
``` 

Añadiremos este fichero a la zona de intercambio.
	git add
 
Una vez en la zona de intercambio solo nos quedará hacer un **commit** con el mensaje **Añadido capítulo 2**.
```
git commit -m "Añadido capítulo 2."
``` 
 
Ahora veremos las diferencias de la última versión del repositorio comparada con dos versiones anteriores:
```
git diff HEAD~2..HEAD
```  

## Ejercicio 3
Crearemos el fichero **capitulo3.txt** con el siguiente texto:
```
Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.
```
Lo haremos con **cat** y cuando ya lo tengamos preparado lo cerramos con **Ctrl+D**.
```
cat > capitulos/capitulo3.txt
Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.
``` 
A continuación añadiremos este fichero a la zona de intercambio.
```
git add
```

Una vez en la zona de intercambio solo nos quedará hacer un **commit** con el mensaje **Añadido capítulo 3**.
```
git commit -m "Añadido capítulo 3."
```

Ahora veremos la diferencia entre los repositorios la primera versión y la última con:
```
git diff <codigo hash de la primera version>..HEAD
```

## Ejercicio 4
Crearemos el fichero **índice.tx** con el siguiente texto:
```
Índice de los capítulos, con conceptos avanzados de git
```
Lo haremos con **cat** y cuando ya lo tengamos preparado lo cerramos con **Ctrl+D**.
```
cat > capitulos/índice.txt
Índice de los capítulos, con conceptos avanzados de git.
```
A continuación añadiremos este fichero a la zona de intercambio.
```
git add
``` 
Una vez en la zona de intercambio solo nos quedará hacer un **commit** con el mensaje **Índice de los capítulos, con conceptos avanzados de git**.
```
git commit -m "Índice de los capítulos, con conceptos avanzados de git."
``` 
Se añade **“Índice de los capítulos, con conceptos avanzados de git”** a **indice.txt**:
```
echo “Índice de los capítulos, con conceptos avanzados de git” >> índice.txt
``` 
Lo añadimos a la zona de intercambio con:
```
git add .
```

Una vez en la zona de intercambio hacemos un **commit** con el mensaje **“Añadido el índice”**.
```
git commit –m “Añadido el índice”
``` 
Ahora veremos quien ha realizado los cambios  en el fichero **índice.txt**:
```
git annotate indice.txt
``` 

## Ejercicio 5
Crearemos una nueva **rama** o **branch bibliografía**:
```
git branch bibliografia
``` 
Mostraremos los **branch** del repositorio.
```
git branch -av
``` 

## Ejercicio 6
Dentro de esta carpeta crearemos el fichero **capitulo4.txt** con el siguiente texto:
```
En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.
```

Lo haremos con **cat** y cuando ya lo tengamos preparado lo cerramos con **Ctrl+D**.
```
cat > capitulos/capitulo4.txt
En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.
```

A continuación añadiremos este fichero a la zona de intercambio.
```
git add
``` 
Una vez en la zona de intercambio solo nos quedará hacer un **commit** con el mensaje **Añadido capítulo 4**.
```
git commit -m "Añadido capítulo 4."
``` 
Ahora veremos el historial del repositorio incluidas sus ramas:
```
git log --graph --all --oneline
``` 

## Ejercicio 7
Pasaremos al branch bibliografía.
```
git checkout bibliografia
``` 
Dentro de esta carpeta crearemos el fichero **bibliografia.txt** con el siguiente texto:
```
Chacon, S. and Straub, B. Pro Git. Apress.
```

Lo haremos con **cat** y cuando ya lo tengamos preparado lo cerramos con **Ctrl+D**.
```
cat > bibliografia.txt
Chacon, S. and Straub, B. Pro Git. Apress
``` 
A continuación añadiremos este fichero a la zona de intercambio.
```
git add
``` 
Una vez en la zona de intercambio solo nos quedará hacer un **commit** con el mensaje **Añadida primera referencia bibliográfica**.
```
git commit -m "Añadida primera referencia bibliográfica."
``` 
Ahora veremos el historial del repositorio incluidas sus ramas:
```
git log --graph --all --oneline
```

## Ejercicio 8
Nos posicionaremos en el **branch main**
```
git checkout main 
``` 
Luego **fusionaremos** la bibliografia.
```
git merge bibliografia
``` 
A continuación mostraremos el historial del repositorio incluyendo sus branch:
```
git log --graph --all –oneline
``` 
Ahora para **eliminar** el branch bibliografía lo haremos así:
```
git branch -d bibliografia
``` 
Volvemos a mostrar el historial del repositorio incluyendo sus branch.
```
git log --graph --all –oneline
``` 

## Ejercicio 9
Crearemos el **branch bibliografia**:
```
git branch bibliografia
```
Nos posicionaremos dentro del anterior branch.
```
git checkout bibliografia
```
Modificaremos el archivo **bibliografía.txt** para que contenga:
```
Scott Chacon and Ben Straub. Pro Git. Apress.
Ryan Hodson. Ry’s Git Tutorial. Smashwords (2014)
```
Una vez terminado de modificar lo cerraremos con **Ctrl+D**.
```
cat > bibliografia.txt
Scott Chacon and Ben Straub. Pro Git. Apress.
Ryan Hodson. Ry's Git Tutorial. Smashwords (2014)
```

Haremos un **commit** con el siguiente mensaje **"Añadida nueva referencia bibliográfica."**:
```
git commit -a -m "Añadida nueva referencia bibliográfica."
``` 
Cambiaremos al **branch main**:
```
git checkout main
``` 
Modificar el archivo **bibliografia.txt** para que contenga lo siguiente:
```
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
```
Una vez finalizada la modificación cerraremos con **Ctrl+D**.
```
cat > bibliografia.txt
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O'Reilly.
``` 
Lo añadiremos a la zona de intercambio.
```
git add .
```

A continuación haremos un **commit** con el mensaje **“Añadida nueva referencia bibliográfica.”**:
```
git commit -a -m "Añadida nueva referencia bibliográfica."
``` 
Fusionaremos el branch bibliografía con el branch main.
```
git merge bibliografía
``` 
Resolveremos el conflicto modificando **bibliografía.txt** para que contenga:
```
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
Hodson, R. Ry’s Git Tutorial. Smashwords (2014)
```
Una vez finalizada la modificación cerraremos con **Ctrl+D**.
```
cat > bibliografia.txt
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O'Reilly.
Hodson, R. Ry’s Git Tutorial. Smashwords (2014)
``` 
Lo añadiremos a la zona de intercambio.
```
git add .
```
A continuación haremos un **commit** con el mensaje **“Solucionado conflicto bibliografía."**
```
git commit -a -m "Solucionado conflicto bibliografía."
```
 
Finalizaremos mostrando el historial del repositorio incluyendo los branch.
```
git log --graph --all –oneline
```
