# LABORATORIO: Decrypt an encrypted message

## Lugar de realización y enlace de la actividad
**[Qwiklabs](https://www.qwiklabs.com/)**

**[Enlace a la actividad](https://www.cloudskillsboost.google/focuses/42747591)**  

## Certificado y curso
**[Google Cybersecurity Certificate](https://www.coursera.org/professional-certificates/google-cybersecurity)**

**Enlace al curso:**  
[Assets, Threats, and Vulnerabilities](https://www.coursera.org/learn/assets-threats-and-vulnerabilities)

## Descripción de la Actividad
Se debe completar una serie de tareas para desencriptar un archivo protegido mediante cifrado. Se trabajara con archivos en el directorio personal, identificando archivos ocultos y aplicando técnicas de descifrado para recuperar información.

## Pasos Realizados

1. **Exploración del directorio personal:**  
    Utilicé el comando `ls` para listar los archivos en el directorio `/home/analyst`, identificando los archivos `Q1.encrypted`, `README.txt` y el subdirectorio `caesar`. Luego, con `cat README.txt`, leí las instrucciones que indicaban la existencia de un archivo oculto en el subdirectorio `caesar`.

2. **Identificación y análisis de archivos ocultos:**  
    Accedí al subdirectorio con `cd caesar` y utilicé `ls -a` para listar todos los archivos, incluyendo los ocultos. Encontré el archivo `.leftShift3`, cuyo contenido estaba cifrado con un cifrado César. Usé `cat .leftShift3` para visualizar el texto cifrado y comprendí que debía aplicar un desplazamiento de tres posiciones hacia la izquierda para descifrarlo.

3. **Descifrado de archivos y recuperación de datos:**  
    Apliqué el comando `cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"` para descifrar el mensaje y obtener el comando necesario para recuperar el archivo encriptado. Volví al directorio principal con `cd ~` y ejecuté `openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute` para desencriptar el archivo. Finalmente, utilicé `cat Q1.recovered` para leer el mensaje recuperado.

Estos pasos demuestran la aplicación de técnicas de análisis y descifrado en un entorno real de ciberseguridad.

## Comandos Usados y Explicación

| Comando | Descripción | Ejemplo de uso |
|---------|-------------|---------------|
| `ls` | Lista los archivos y directorios en el directorio actual. Permite identificar archivos relevantes. | `ls` |
| `cat` | Muestra el contenido de un archivo en la terminal. Se usó para leer instrucciones y archivos cifrados. | `cat README.txt` |
| `cd` | Cambia el directorio de trabajo actual. Se utilizó para navegar entre directorios. | `cd caesar` |
| `ls -a` | Lista todos los archivos, incluidos los ocultos (que comienzan con un punto). | `ls -a` |
| `tr` | Traduce o reemplaza caracteres en el texto. Se usó para descifrar el cifrado César. | `cat .leftShift3 \| tr "d-za-cD-ZA-C" "a-zA-Z"` |
| `openssl` | Herramienta para operaciones criptográficas. Se usó para desencriptar el archivo protegido. | `openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute` |

## Resultados Obtenidos
Al ejecutar los comandos, logré identificar y descifrar un archivo oculto protegido con cifrado César, y posteriormente desencripté el archivo `Q1.encrypted` utilizando la clave proporcionada. El archivo recuperado contenía el mensaje esperado, demostrando la efectividad del proceso.

![Ventana de terminal que muestra una sesión de shell de Linux donde un usuario lista archivos, lee instrucciones de README.txt, encuentra un archivo oculto en el directorio caesar y utiliza comandos para descifrar un archivo encriptado. La terminal muestra comandos como ls, cat, cd, tr y openssl, junto con sus salidas. El mensaje descifrado confirma la desencriptación exitosa del texto cifrado clásico y la recuperación de la clave de cifrado. El entorno es una terminal de tema oscuro centrada en tareas de ciberseguridad y recuperación de archivos. El tono es técnico e instructivo.](recursos/Lab9_image.png)

## Conclusiones
Este laboratorio permitió reforzar habilidades en la identificación de archivos ocultos, el uso de comandos de Linux y la aplicación de técnicas de descifrado clásicas y modernas. Para futuras actividades, podría automatizar algunos pasos mediante scripts para agilizar el proceso y minimizar errores.