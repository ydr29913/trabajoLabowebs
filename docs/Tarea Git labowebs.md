# Tarea Git labowebs

> Realizado por: Dani Gayol Rodriguez

[TOC]



## Trabajo en Local

1. **Inicializa un nuevo repositorio Git en una carpeta llamada  "labowebs" y agrega los  archivos proporcionados en el aula virtual. Renombra la rama master a  main, si es  necesario. Realiza el primer commit. Muestra el log del repositorio.**

```bash
git init
git branch -m master main
git add .
git commit -m "Primer commit"
```

<img src="C:\Users\alumno\AppData\Roaming\Typora\typora-user-images\image-20241114085727581.png" alt="image-20241114085727581" style="zoom:80%;" />

<img src="C:\Users\alumno\AppData\Roaming\Typora\typora-user-images\image-20241114085917916.png" alt="image-20241114085917916" style="zoom:80%;" />



2. **Incluye un fichero  .gitignore para que  los ficheros  README.md,  LICENCE.txt y  passwords.txt sean ignorados por el control de versiones. Realiza el commit y muestra  los logs del repositorio en una línea.**

```bash
touch .gitignore
nano .gitignore
git add .gitignore
git commit -m "Añadir fichero .gitignore"
git log --oneline
```

<img src="C:\Users\alumno\AppData\Roaming\Typora\typora-user-images\image-20241114090527217.png" alt="image-20241114090527217" style="zoom:80%;" />



3. **En el repositorio, crea los archivos   README.md,  LICENCE.txt y  passwords.txt con  algún contenido. Muestra el estado del repositorio. Muestra el listado de archivos  ignorados.**

```bash
echo "Tarea labowebs Dani Gayol" > README.md
echo "Realizado por Dani Gayol" > LICENCE.txt
echo "user : dani" > passwords.txt
git status
git status --ignored
```

<img src="./Tarea Git labowebs.assets/image-20241114091524687.png" alt="image-20241114091524687" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241114091551530.png" alt="image-20241114091551530" style="zoom:80%;" />



4. **Crea una rama  feature-estilos. Cámbiate a ella. **
   * Modifica el archivo  estilos.css:  
     * propiedad color del  body y de h2:  #2a2a2a 
     * propiedad background-color de  header y  footer: #2a75ff 
   * Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el  mensaje "actualizados estilos a azules"

```bash
git checkout -b feature-estilos
git status
git add .
git commit -m "Actualizados estilos a azules"
```

<img src="./Tarea Git labowebs.assets/image-20241114093025127.png" alt="image-20241114093025127" style="zoom:80%;" />



5. **Vuelve a la rama  main. En el archivo  index.html añade un comentario donde se indique  tu nombre como autor de la página. Comprueba el estado del repositorio. Añade los  cambios, realiza un commit con el mensaje ' añadido autor en index'. Muestra los logs del  repositorio en una línea, gráficamente y con 'decoración'**

```bash
git checkout main
git status
git add .
git commit -m "Añadido autor en index"
git log --oneline --graph --decorate
```

<img src="./Tarea Git labowebs.assets/image-20241114094032847.png" alt="image-20241114094032847" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241114094159109.png" alt="image-20241114094159109" style="zoom:80%;" />



6. **Fusiona la rama  feature-estilos en la rama  main . Muestra los logs del repositorio en  una línea, gráficamente y con 'decoración'**

```bash
git merge feature-estilos
git log --oneline --graph --decorate
```

<img src="./Tarea Git labowebs.assets/image-20241114094741019.png" alt="image-20241114094741019" style="zoom:80%;" />





## Trabajo en Remoto

1. **Continúa con el repositorio  labowebs.  Añade el repositorio a Sourcetree.**

<img src="./Tarea Git labowebs.assets/image-20241114095623122.png" alt="image-20241114095623122" style="zoom:80%;" />



2. **Crea un repositorio remoto y sube al remoto los ficheros de tu repositorio local. Debes  subir todas las ramas.**

```bash
git remote add origin https://github.com/ydr29913/trabajoLabowebs.git
git branch -M main
git push -u origin main
git push -u origin feature-estilos
```

<img src="./Tarea Git labowebs.assets/image-20241114100051297.png" alt="image-20241114100051297" style="zoom:80%;" />



3. **Crea una rama  feature-index.  Añade el siguiente código dentro de la "<"section class = "about">" . Añade los cambios y crea un commit. Sube los cambios al remoto.**

<img src="./Tarea Git labowebs.assets/image-20241114100422588.png" alt="image-20241114100422588" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241114100827352.png" alt="image-20241114100827352" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241114100919067.png" alt="image-20241114100919067" style="zoom:80%;" />



4. **En el repositorio local, fusiona la rama  feature-index en la rama  main.**

<img src="./Tarea Git labowebs.assets/image-20241114101557568.png" alt="image-20241114101557568" style="zoom:80%;" />



5. **Edita el fichero  contacto.html. Borra unas líneas. Muestra los ficheros con cambios  pendientes y las diferencias. Añade los cambios y haz un commit.**

<img src="./Tarea Git labowebs.assets/image-20241114102021334.png" alt="image-20241114102021334" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241114102127287.png" alt="image-20241114102127287" style="zoom:80%;" />



6. **Te das cuenta del error. Deshaz el commit anterior. Captura el estado actual del  repositorio.**

<img src="./Tarea Git labowebs.assets/image-20241114102227670.png" alt="image-20241114102227670" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241114102244694.png" alt="image-20241114102244694" style="zoom:80%;" />



7. **Crea una rama  feature-mapa . Incluye este código en el archivo  contacto.html. Añade  los cambios. Realiza un commit. Sube los cambios al remoto. Muestra en el remoto los  cambios del archivo  contacto.html en la rama  feature-mapa.**

<img src="./Tarea Git labowebs.assets/image-20241120104957366.png" alt="image-20241120104957366" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120105424290.png" alt="image-20241120105424290" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120110141692.png" alt="image-20241120110141692" style="zoom:80%;" />



8. **En GitHub,  en la rama  main, fusiona la rama  feature-mapa. Baja los cambios del remoto  a local. Deja los dos repositorios sincronizados.**

<img src="./Tarea Git labowebs.assets/image-20241120120422784.png" alt="image-20241120120422784" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120120457248.png" alt="image-20241120120457248" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120120542702.png" alt="image-20241120120542702" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120120646894.png" alt="image-20241120120646894" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120120716326.png" alt="image-20241120120716326" style="zoom:80%;" />





## Conflictos

1. **Crea una rama  hotfix-js. Cámbiate a ella. Añade este código en el fichero  Confirma el cambio y haz un commit.**

<img src="./Tarea Git labowebs.assets/image-20241120123023122.png" alt="image-20241120123023122" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120123307085.png" alt="image-20241120123307085" style="zoom:80%;" />



2. **Vuelve a la rama  main. En el fichero  script.js en las mismas líneas que en la cuestión  anterior, añade el código siguiente. Confirma el cambio y haz un commit.**

<img src="./Tarea Git labowebs.assets/image-20241120123558766.png" alt="image-20241120123558766" style="zoom:80%;" />



3. **Fusiona la rama  hotfix-js en  main. Debe producirse un conflicto. Resuélvelo. Cuando  termines la resolución del conflicto sube los cambios al remoto.**

<img src="./Tarea Git labowebs.assets/image-20241120123953547.png" alt="image-20241120123953547" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120124052426.png" alt="image-20241120124052426" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120124403836.png" alt="image-20241120124403836" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120124434810.png" alt="image-20241120124434810" style="zoom:80%;" />

<img src="./Tarea Git labowebs.assets/image-20241120124509854.png" alt="image-20241120124509854" style="zoom:80%;" />





## URL Github

[URL Github]: https://github.com/ydr29913/trabajoLabowebs.git

https://github.com/ydr29913/trabajoLabowebs.git