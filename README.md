# Configuración entorno Karate

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
  winget install Oracle.JDK.24 -e
  ```
  Para verificar la instalación de Java (y su JDK):
  Java:
  ```bash
  java --version
  ```
  ![Versión Java](https://github.com/user-attachments/assets/aa6cea9b-c24c-4ccc-9eb4-c00a61a2b615)

  JDK:
  ```bash
  javac --version
  ```
  ![Versión JDK](https://github.com/user-attachments/assets/c9588594-9477-4baa-876b-e40485670d41)

- Maven 🪶:
  Para instalar maven, usaremos `scoop`:
  ```bash
  scoop install main/maven
  ```
