# EJERCICIOS GIT, GITHUB Y MARKDOWN
Repositorio de la asignatura DATA SCIENCE TOOLKIT.

## 2.1 REPOSITORIO CAMPUSCIFF (I)
### 1. Crear un repositorio en vuestro GitHub llamado campusciff.

## 2.2 REPOSITORIO CAMPUSCIFF (II)
### 1. Clonar vuestro repositorio en local.
~~~
carlospaz@Carlos-MacBook-Pro:~$ git clone git@github.com:cpazsantos/campusciff.git
~~~

## 2.3 README
### 1. Crear (si no lo habéis creado ya) en vuestro repositorio local un documento README.md. 
README.md ya creado al inicializar el repositorio en GitHub.

## 2.4 COMMIT INICIAL
### 1. Añadir al README.md los comandos utilizados hasta ahora y hacer un commit inicial con el mensaje commit inicial.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git add .
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git commit -m 'Commit inicial.'
~~~

## 2.5 PUSH INICIAL
### 1. Subir los cambios al repositorio remoto.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git push origin master 
~~~

## 2.6 IGNORAR ARCHIVOS (I)
### 1. Crear en el repositorio local un fichero llamado privado.txt.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ touch privado.txt
~~~
### 2. Crear en el repositorio local una carpeta llamada privada.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ mkdir privada
~~~

## 2.7 IGNORAR ARCHIVOS (II)
### 1. Realizar los cambios oportunos para que tanto el archivo como la carpeta sean ignorados por git.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ echo -e "privado.txt \nprivada/" > .gitignore
carlospaz@Carlos-MacBook-Pro:~/campusciff$ cat .gitignore 
privado.txt 
privada/
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git add .gitignore 
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git commit -m "Creado .gitignore"
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git push origin master 
~~~

## 2.8 AÑADIR FICHERO 1.TXT
### 1. Añadir fichero 1.txt al repositorio local.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ touch 1.txt
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git add 1.txt 
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git commit -m "Creado 1.txt"
~~~

## 2.9 CREAR EL TAG V0.1
### 1. Crear un tag v0.1.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git tag -a v0.1 -m "Creado tag v0.1"
~~~

## 2.10 SUBIR EL TAG V0.1
### 1. Subir los cambios al repositorio remoto.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git push --tag origin master
Counting objects: 4, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 464 bytes | 0 bytes/s, done.
Total 4 (delta 0), reused 0 (delta 0)
To git@github.com:cpazsantos/campusciff.git
   bd7b4d5..4dd6aab  master -> master
 * [new tag]         v0.1 -> v0.1
 ~~~


## 2.11 CREAR UNA RAMA V0.2
### 1. Crear una rama v0.2.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git branch v0.2
~~~

### 2. Posiciona tu carpeta de trabajo en esta rama.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git checkout v0.2
~~~

## 2.12 AÑADIR FICHERO 2.TXT
### 1. Añadir un fichero 2.txt en la rama v0.2.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ touch 2.txt
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git add .
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git commit -m "Creado 2.txt y actualizado README.md"
~~~

## 2.13 CREAR RAMA REMOTA V0.2
### 1. Subir los cambios al reposiorio remoto.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git push origin v0.2
~~~

## 2.14 MERGE DIRECTO
### 1. Posicionarse en la rama master.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git checkout master
~~~

### 2. Hacer un merge de la rama v0.2 en la rama master.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git merge v0.2 -m "Merge de la rama v0.2 en la rama master"
~~~

## 2.15 MERGE CON CONFLICTO (I)
### 1. En la rama master poner Hola en el fichero 1.txt y hacer commit.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ echo "Hola" > 1.txt 
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git add .
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git commit -m "Actualizado 1.txt"
~~~

## 2.16 MERGE CON CONFLICTO (II)
### 1. Posicionarse en la rama v0.2 y poner Adios en el fichero "1.txt" y hacer commit.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git checkout v0.2
carlospaz@Carlos-MacBook-Pro:~/campusciff$ echo "Adios" > 1.txt 
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git add .
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git commit -m "Actualizado 1.txt con Adios"
~~~

## 2.17 MERGE CON CONFLICTO (III)
### 1. Posicionarse de nuevo en la rama master y hacer un merge con la rama v0.2
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git checkout master
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git merge v0.2 -m "Merge con conflicto de la rama v0.2 en la rama master"
~~~

## 2.18 LISTADO DE RAMAS
### 1. Listar las ramas con merge y las ramas sin merge.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git branch --merged
* master
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git branch --no-merged
  v0.2
~~~

## 2.19 ARREGLAR CONFLICTO
### 1. Arreglar el conflicto anterior y hacer un commit.
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ cat 1.txt 
<<<<<<< HEAD
Hola
=======
Adios
>>>>>>> v0.2

# Arreglamos el conflicto
carlospaz@Carlos-MacBook-Pro:~/campusciff$ cat 1.txt 
Adios
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git add .
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git commit -m "Arreglado coflicto rama v0.2"
~~~

## 2.20 BORRAR RAMA
### 1. Crear un tag v0.2
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git tag -a v0.2 -m "Creado tag v0.2"
~~~

### 2. Borrar la rama v0.2
~~~
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git branch -d v0.2
~~~

## 2.21 LISTADO DE CAMBIOS
### 1. Listar los distintos commits con sus ramas y sus tags.
~~~
# Creamos un alias list
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git config --global alias.list 'log --oneline --decorate --graph -all'
carlospaz@Carlos-MacBook-Pro:~/campusciff$ git list
*   85310ce (HEAD -> master, tag: v0.2, origin/master, origin/HEAD) Arreglado coflicto rama v0.2
|\  
| * 9935b96 Actualizado 1.txt con Adios
* | 412db99 Actualizado 1.txt
|/  
* c34ee52 (origin/v0.2) Creado 2.txt y actualizado README.md
* d147e42 Actualizado README.me con los comandos utilizados.
* 4dd6aab (tag: v0.1) Creado 1.txt
* bd7b4d5 Actualizado README.me con los comandos utilizados.
* 9beb4fc Creado .gitignore
* 059711d Commit inicial.
* c74fcbc Initial commit
~~~
