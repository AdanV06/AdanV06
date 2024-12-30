

## Creación de un repositorio de Git local mediante VS Code
1. En VS Code, abra una carpeta de proyecto de Power BI Desktop
2. Para inicializar un repositorio de Git, seleccione **Control de código fuente**>**Inicializar repositorio**
3. Realice una confirmación inicial y escriba un mensaje

>[!NOTE]
>A partir de ahora, los cambios realizados en Power BI Desktop cambian un archivo en la carpeta a la que realiza el seguimiento el Git local. Por ejemplo, en Power BI Desktop, al cambiar una fórmula DAX para una medida y, a continuación, guardarla, se desencadenará una diferencia de Git en el archivo model.bim.

# Usos de git
## Nuevas ramas:
1. Para crear una nueva rama y cambiar a esta, se utuliza el comando: `git checkout -b`.
  * Ej: **git checkout -b name_rama**.
2. Para crear una nueva rama y mantenernos en la rama actual se utiliza el comando `git branch`.
  + Ej: **git branch name_rama**.

> [!Note]
> Para el cambio de rama se utiliza el comando `git checkout name_rama`.

## Hacer commit:
1. Para subir los cambios primero se debe de seleccionar la rama.
2. Nombrar Commit
3. Pulsar boton commit

> [!Note]
> Cuando no hemos publicado la rama antes de hacer el commit, aparecera un boton **Publish Branch**, luego de pulsar en el la subiremos al repsitorio en GitHub.

## Pull requests:
Utiliamos pull requests para meclar los cambios realizados, con la rama **main**.
1. Primero abrimos el repositorio en Github
2. Seleccionamos la opcion `Pull Request`
3. Presionamos el boton `New Pull Request`
4. Seleccionamos las ramas que se compararan para mezclarse
5. Presionamos el boton `Create Pull Requests`
