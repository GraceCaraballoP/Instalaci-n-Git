# Configuración básica de Git

Una vez tenemos la versión de GIT que queremos pasaremos a configurarlo para que muestre información básica sobre nosotros cada vez que creemos un proyecto.    
Para ello usaremos el comando **git** config a continuación configuraremos nuestro nombre y nuestro email.
```
git config --global user.name "Your Name"
```
<div align="center">
  <img src="Captura22.png">
</div>

```
git config --global user.email "youremail@domain.com"
```
<div align="center">
  <img src="Captura.png">
</div>

Podemos ver los datos de configuración creados si escribimos lo siguiente:
```
git config --list
```
<div align="center">
  <img src="Captura.png">
</div>

Con esto queda finalizada la configuración básica de nuestro Git.
