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
