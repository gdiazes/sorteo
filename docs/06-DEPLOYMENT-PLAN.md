# 6. Plan de Despliegue

## 6.1 Estrategia de Despliegue
> El despliegue de la aplicación se realizará de forma **automatizada utilizando Git** desde la rama `main` del repositorio de GitHub.

## 6.2 Pasos de Despliegue
> Se configurará un webhook en GitHub que notificará al servidor de hosting (vía cPanel/Plesk). El servidor se encargará de clonar la última versión y ejecutar los comandos de actualización:
> ```bash
> # Poner la web en modo mantenimiento
> php artisan down
> 
> # Obtener el código más reciente
> git pull origin main
> 
> # Instalar dependencias de PHP y JS
> composer install --no-dev --optimize-autoloader
> npm install && npm run build
> 
> # Ejecutar migraciones de la base de datos y limpiar caché
> php artisan migrate --force
> php artisan config:cache
> php artisan route:cache
> 
> # Salir del modo mantenimiento
> php artisan up
> ```

## 6.3 Plan de Rollback (Reversión)
> En caso de un despliegue fallido, se ejecutará un plan de **reversión manual rápida**.
> 1.  El desarrollador se conectará al servidor vía SSH.
> 2.  Navegará al directorio de la aplicación.
> 3.  Revertirá el código al commit anterior funcional usando comandos de Git (ej. `git reset --hard HEAD~1`).
> 4.  Ejecutará de nuevo los comandos de post-despliegue si es necesario.
```
