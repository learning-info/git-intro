# Introducción a GIT

## Comandos de configuración

### Establecer el nombre de usuario
```sh
git config --global user.name "Your-Full-Name"
```

### Establecer el email de usuario
```sh
git config --global user.email "your-email-address"
```

### Mostrar las configuraciones establecidas
```sh
git config --list
```
---

## Crear nuevo repositorio local

Este comando crea crea una nueva carpeta con el nombre del repositorio, que a su vez contiene otra carpeta oculta llamada `.git` que contiene la base de datos donde se registran los cambios en el repositorio.

```sh
git init <nombre-repositorio>
```

## Estados del ciclo de vida de archivos Git

### Archivos untracked
- Archivos que no viven adentro de Git, solo en el disco duro.
- Nunca han sido afectados por el comando git add.
- Git no tiene registros de su existencia.

### Archivos unstaged
- Archivos que viven dentro de Git.
- No han sido afectados por el comando git add ni git commit.
- Git tiene un registro desactualizado de estos archivos.
- Sus últimas versiones solo están guardadas en el disco duro.

### Archivos staged
- Archivos en staging.
- Viven dentro de Git.
- Hay registros de ellos por que han sido afectados por el comando ** git add** (no, los últimos cambios).
- Git ya sabe de la existencia de los últimos cambios, pero aún no se han guardado en el repositorio por que falta ejecutar el comando git commint.

### Archivos traked
- Son los archivos que viven dentro de Git.
- No tienen cambios pendientes.
- Sus ultimas actualizaciones se han guardado en el repositorio por medio de comandos git add y git comment.

## Añadir cambios a la zona de intercambio temporal (staged)

```sh
git add
```
- `git add <fichero>` añade los cambios en el chero <fichero> del directorio de trabajo a la zona de intercambio temporal.
- `git add <carpeta>` añade los cambios en todos los cheros de la carpeta `<carpeta>` del directorio de trabajo a la zona de intercambio temporal.
- `git add .` añade todos los cambios de todos los cheros no guardados aún en la zona de intercambio temporal.

## Añadir cambios al repositorio
```sh
git commit
```
- `git commit -m "mensaje"` conrma todos los cambios de la zona de intercambio temporal añadiéndolos al repositorio y creando una nueva versión del proyecto. "mensaje" es un breve mensaje describiendo los cambios realizados que se asociará a la nueva versión del proyecto.
- `git commit --amend -m "mensaje"` cambia el mensaje del último commit por el nuevo mensaje "mensaje".

## Mostrar el estado de un repositorio

```sh
git status
```
`git status` muestra el estado de los cambios en el repositorio desde la última versión guardada. En particular, muestra los cheros con cambios en el directorio de trabajo que no se han añadido a la zona de intercambio temporal y los cheros en la zona de intercambio temporal que no se han añadido al repositorio.

## Ramas

```sh
git branch
```
`git branch` podemos ver en la rama actual que se encuentra nuestra área de trabajo.
`git branch <rama>` crea una nueva rama con el nombre <rama> en el repositorio a partir del último commit.

### Cambio entre ramas
```sh
git checkout
```
- git checkout <rama> actualiza los cheros del directorio de trabajo a la última versión del repositorio correspondiente a la rama <rama>, y la activa, es decir, pasa a apuntar al último commit de esta rama.
- git checkout -b <rama> crea una nueva rama con el nombre <rama> y la activa
