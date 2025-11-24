# SuperSecureStoreAngelitoBellaco Proyecto E-commerce Seguro - SSSAB



Una tienda super segura basada en el mítico AngelitoBellaco. La plataforma está construida sobre WordPress y WooCommerce, con múltiples capas de hardening aplicadas a nivel de servidor, aplicación y base de datos.

## !!! Cuentas
<details>
<summary>Clic para reverla la info</summary>
Cuenta admin: adminotepppppp3p3p <br>
Email admin: correoadminonaoiharioai@correoanadoisdao.com<br>
Contraseña admin: PiUPbKm0j3dMPatWqV*@geit<br>
---<br>
Cuenta usuario: jofixi7963<br>
Contraseña usuario: SiT9zryNT9Zqw510U2OVjIxb<br>
</details>

## !!! Info para hacer compras:
<details>
<summary>Clic para reverla la info</summary>
N° de Tarjeta de credito para compras<br>
4032038181397310<br>
10/2030<br>
CVC 3 digitos cualquiera que quieran poner<br><br>
Cupon de bienvenida: BIENVENIDO
</details>
  
## Prerrequisitos

  

Antes de comenzar, asegúrese de tener instalado el siguiente software en su sistema:

  

*   **Laragon:** Un entorno de desarrollo local universal para Windows. [Descargar aquí](https://laragon.org/download/).

*   **Git:** El sistema de control de versiones. [Descargar aquí](https://git-scm.com/downloads).

*   **Editor de Código:** Se recomienda Visual Studio Code. [Descargar aquí](https://code.visualstudio.com/).

  

## Guía de Instalación y Despliegue Local

  

Siga estos pasos en orden para replicar el entorno de desarrollo y ejecutar el proyecto correctamente.

  

### Paso 1: Clonar el Repositorio

  

1.  Abra la terminal de Laragon (`Menú > Terminal`).

2.  Navegue al directorio raíz de proyectos de Laragon.

    ```bash

    cd C:\laragon\www

    ```

3.  Clone este repositorio. Esto creará una carpeta llamada `SSSAB`.

    ```bash

    git clone [URL_DE_SU_REPOSITORIO_GITHUB] SSSAB

    ```

  

### Paso 2: Configuración del Entorno Laragon

  

Laragon necesita ser configurado para servir el proyecto correctamente sobre HTTPS y con los parámetros de PHP necesarios.

  

1.  **Iniciar Servicios:** Abra la aplicación de Laragon y haga clic en **"Iniciar todo"**. Esto debería iniciar los servicios de Apache y MySQL.

  

2.  **Habilitar SSL:** Para que el sitio funcione sobre `https://`, debe habilitar SSL en Laragon.

    *   Haga clic derecho sobre el icono de Laragon en la bandeja del sistema.

    *   Navegue a `Apache > SSL`.

    *   Haga clic en **"Habilitado"**.

    *   Laragon instalará automáticamente un certificado SSL para `sssab.test`.

    *   **Reinicie Apache** para que los cambios surtan efecto (`Menú > Apache > Reiniciar`).

  

3.  **Configurar `php.ini`:** Se requiere una modificación en la configuración de PHP para limitar el tamaño de los archivos subidos, una medida de seguridad para prevenir ataques de denegación de servicio.

    *   Haga clic derecho sobre el icono de Laragon.

    *   Navegue a `PHP > php.ini`.

    *   Busque y modifique las siguientes directivas a los valores indicados:

        upload_max_filesize = 2M

        post_max_size = 8M

    *   Guarde y cierre el archivo.

    *   **Reinicie Apache** nuevamente para aplicar esta configuración.

  

### Paso 3: Configuración de la Base de Datos

  

El proyecto incluye un archivo de volcado SQL que contiene la estructura y los datos de la base de datos.

  

1.  **Acceder a HeidiSQL:** Desde el menú de Laragon, haga clic en el botón **"Base de datos"**. Esto abrirá HeidiSQL, el gestor de bases de datos.

  

2.  **Importar el Archivo SQL:**

    *   Una vez en HeidiSQL, vaya al menú `Archivo > Cargar archivo SQL...`.

    *   Navegue a la carpeta del proyecto y seleccione el archivo de la base de datos: `C:\laragon\www\SSSAB\BD\exportacion_completa.sql` (o el nombre que le haya dado).

    *   Asegúrese de que la codificación esté en `UTF-8`.

    *   Haga clic en el botón **"Ejecutar"** (el icono de play azul).

    *   El script se encargará de crear la base de datos (`tienda_segura_db`), el usuario (`app_user_x9z`) y de importar todas las tablas y datos necesarios.

    *   Puede cerrar HeidiSQL una vez que el proceso finalice sin errores.

  

### Paso 4: Acceder al Sitio

  

¡La configuración está completa!

  

1.  Abra su navegador web y navegue a la URL local del proyecto:

    **`https://sssab.test/`**

  

2.  La primera vez que acceda, su navegador puede mostrar una advertencia de seguridad porque el certificado SSL es autofirmado. Debe aceptar el riesgo y continuar.

  

3.  Para acceder al panel de administración, utilice la URL de acceso segura

    **`https://sssab.test/wp-admin/`**