# Configuración entorno Karate 🥋

Para configurar el entorno de Karate Framework se necesita:
- Java (JDK)
- Maven
- Gradle
- IDE (En nuestro caso: **JetBrains: Intellij**)
- Git (Opcional, pero recomendado)

> [!IMPORTANT]
> Para la mayoría de las instalaciones, usaremos algunos gestores de paquetes para la mayoría de los programas y/o utilidades que necesitamos para adecuar nuestro entorno de **Karate Framework**.
> Estos gestores son: [winget](https://learn.microsoft.com/es-es/windows/package-manager/winget/) y [scoop](https://scoop.sh/)
> (Winget ya viene instalado por defecto en computadores con Windows 11, y algunos con Windows 10 desde su versión **22H2**)

## Instalación 🚀

- scoop:
Desde una terminal de **Powershell** (no **CMD**). También es válido la aplicación de [Windows Terminal](https://apps.microsoft.com/detail/9n0dx20hk701?hl=es-ES&gl=co).  
```bash
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```
```bash
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```
Para verificar que `scoop` se instaló correctamente:
```bash
scoop -h
```
![scoop funcional](https://github.com/user-attachments/assets/26452353-ae11-44a3-8ab8-cdc0f2d48581)

- Java 🍵:
  Para instalar java, usaremos `winget`:
  ```bash
  winget install Microsoft.OpenJDK.17 -e
  ```
  Para verificar la instalación de Java (y su JDK):
  Java:
  ```bash
  java --version
  ```
  ![Versión Java](https://github.com/user-attachments/assets/9a4e47bc-e8d9-45be-ac4e-eb73323c70f1)

  JDK:
  ```bash
  javac --version
  ```
  ![Versión JDK](https://github.com/user-attachments/assets/8df3c5f8-8c7f-44e9-85e9-2eca652fc5ae)

- Maven 🪶:
  Para instalar maven, usaremos `scoop`:
  ```bash
  scoop install main/maven
  ```
  Para verificar la instalación:
  ```bash
  mvn --version
  ```
  ![Versión Maven](https://github.com/user-attachments/assets/e5f358fb-404e-4595-9d3d-7e3ae71e599f)

- Gradle 🐘:
  Para instalar gradle, usaremos `scoop`:
  ```bash
  scoop install gradle
  ```
  Para verificar la instalación:
  ```bash
  gradle --version
  ```
  ![Versión Gradle](https://github.com/user-attachments/assets/ab8122e5-3f21-4d33-8c46-e4acfd879e9d)
> [!NOTE]
> Hacer caso omiso cuando se menciona "(no JDK specified, using current Java home)" en la línea de **Daemon VM**, ya que al no especificar que versión de Java usará Gradle, usará la versión que esté identificada en la variable de entorno `JAVA_HOME` (Para uso de esta guía: Java 24).
  
- IDE: Jetbrains IntelliJ 👩🏿‍💻👨🏿‍💻
    - Para instalar, acceder al link: [IntelliJ-Descargas](https://www.jetbrains.com/idea/download/?section=windows)
    - Buscar la opción de **IntelliJ IDEA Community Edition**.
    - Click en download.
    - Ejecutar el archivo descargado (el archivo debería tener el nombre de: `ideaIC-2025.2.exe`.
    - En la ventana de `installation options`, habilitar:
      - ![check IntelliJ](https://github.com/user-attachments/assets/ced19437-22c3-449f-b2b6-899a58a1b9e7)
    - Una vez instalado, click en **plugins**, buscar `Karate` e instalar.
      ![Plugin Karate](https://github.com/user-attachments/assets/9b56e614-c8b2-45f7-bc0e-249a4a666cfd)

- Git (opcional):
  Para instalar Git, usaremos `winget`:
  ```bash
  winget install Git.Git
  ```

## Verificación y ejecución `sample-project` karate 🥋:
Para verificar que la instalación de todas las herramientas ha sido exitosa, haremos uso de un `sample-project` de karate:
- Crearemos una carpeta donde se tendrá el proyecto de `sample-project`, esta carpeta puede ser en cualquier lugar, para uso de esta guía se usará la ruta de: `C:\Users\YOUR-USERNAME\Documents\Testing`.
- Una vez situados en esta carpeta, abriremos una terminal que nos sitúe en la ruta anteriormente mencionada:
  - ![Click derecho - terminal](https://github.com/user-attachments/assets/dd7489dd-3f53-49e9-91d8-4d11310aa461)
- Ejecutamos el siguiente comando que importará el proyecto de prueba para verificar nuestra configuración del entorno de Karate:
```bash
& 'mvn' archetype:generate "-DarchetypeGroupId=io.karatelabs" "-DarchetypeArtifactId=karate-archetype" "-DarchetypeVersion=X.X.X" "-DgroupId=YOUR.GROUPIDHERE" "-DartifactId=YOUR-ARTIFACT-ID-HERE" "-DinteractiveMode=false"
```
Donde, se debe reemplazar:
- `DarchetypeVersion=X.X.X`, por la versión deseada de karate, en esta guía se usó la versión `1.5.1`.
- `DgroupId=YOUR.GROUPIDHERE`, por el nombre de ID de grupo que desee, por ejemplo: `QR.JohnDoe`.
- `DartifactId=YOUR-ARTIFACT-ID-HERE`, por el nombre de ID de artefacto que desee, por ejemplo: `karateSample`.

- Deberiamos tener algo como:
  ![comando sample project](https://github.com/user-attachments/assets/464220b1-bb01-4f51-a10d-1359358149d6)
- Abrir el programa **IntelliJ** y abrir el proyecto:
  ![IDE1](https://github.com/user-attachments/assets/1ee5e94a-9588-4951-96d8-583bc7bf83af)
  ![IDE2](https://github.com/user-attachments/assets/d31e604d-70f3-4799-bf1c-3595905d2d4f)
- Una vez abierto el proyecto, podremos ejecutarlo de las siguientes maneras:
  - Terminal: Desde una terminal situados en la carpeta donde esta el proyecto, ejecutar el siguiente comando:
    ```bash
    mvn clean test
    ```
    ![mvn clean test1](https://github.com/user-attachments/assets/4b4a62c4-d171-4a53-9a38-434fd52bf46a)
    ![mvn clean test2](https://github.com/user-attachments/assets/8b1585cd-c675-4a04-9a7c-65b515f74058)
  - IntelliJ - IDE: Ir al archivo `C:\Users\YOUR-USERNAME-HERE\Documents\Testing\YOUR-ARTIFACT-ID-HERE\src\test\java\examples\ExamplesTest.java`, y ejecutarlo:
> [!NOTE]
> Si bien no es necesario especificar el JDK (ya que usará el JDK que esté por defecto en la variable de entorno `JAVA_HOME`), se puede especificar el JDK en el IDE dando click en `Setup SDK`):
> ![SDK1](https://github.com/user-attachments/assets/b8d06f01-b466-40e5-9ac9-9abb1b9a7317)
> ![SDK2](https://github.com/user-attachments/assets/87b93549-c7ef-407a-b2b1-d771f01e6233)

![Run-IDE1](https://github.com/user-attachments/assets/3b578704-700e-43c7-86b0-550edfa40498)
![Run-IDE2](https://github.com/user-attachments/assets/a6c9104a-ecd3-45fc-b76c-28c34d16d910)
- Al ejecutarlo (independientemente de las opciones que se usó) nos indicará por cuantos test se ejecutaron, cuantos fallaron entre otras estadisticas.
- Además, nos brindará un archivo `.html` en el que podremos ver el reporte de los tests ejecutados de manara más visual y amigable, este archivo puede ser visualizado en cualquier navegador web:
  - Terminal:
    ![reporte-terminal](https://github.com/user-attachments/assets/1d5d1ea8-3c16-4a0e-82ea-7f07418a7697)
  - IntelliJ - IDE:
  - ![reporte-IDE](https://github.com/user-attachments/assets/3abad91f-e52b-47c5-8fee-097ec73221e3)
- El reporte muestra información importante al tester como:
  - Número de test.
  - Cuantos fueron exitosos y cuantos fallaron.
  - Features.
  - Entre otra información.
![Reporte-WEB-Karate1](https://github.com/user-attachments/assets/e273775d-2c6e-4233-8f87-6835698cd3bd)
![Reporte-WEB-Karate2](https://github.com/user-attachments/assets/a4888dec-3370-4c41-9182-2e6cb6c3d6f3)

# Si llegaste hasta aquí, ¡felicidades!, ya tienes tu entorno de karate completo y funcional. 🥳🥳🥳
## Alguna información de utilidad.
- [Documentación oficial Karate.](https://karatelabs.github.io/karate/)
- [Repositorio oficial Karate.](https://karatelabs.github.io/karate/)
- [Tutorial Karate Framework - Español](https://youtube.com/playlist?list=PLeo6Q1inqlOfQbhHyPDwCygeU8JELFidl&si=LPSSC1Uw2xEZ3nkG), Créditos: https://www.youtube.com/@JulianMesaAutomation
- [Turorial Karate Framework - Inglés](https://youtube.com/playlist?list=PLlsKgYi2Lw72TXZxTNVvRn7A8IznAJcz2&si=xcNcn3ml1d4xpjAv), Créditos: https://www.youtube.com/@RahulRathore41
