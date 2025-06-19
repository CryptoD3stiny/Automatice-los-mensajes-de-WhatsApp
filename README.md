# Automatice-los-mensajes-de-WhatsApp
Automatice los mensajes de WhatsApp con Python usando el módulo Pywhatkit
![image](https://github.com/user-attachments/assets/80d3bc64-48d2-4bf8-be62-be44bee15b76)
Podemos automatizar un script de Python para enviar mensajes de WhatsApp. En este artículo, aprenderemos las formas más fáciles de usar el módulo pywhatkit que utiliza el sitio web web.whatsapp.com para automatizar el envío de mensajes a cualquier número de WhatsApp.

Instalación del módulo pywhatkit:
pywhatkit es un módulo de python para enviar mensajes de Whatsapp en un momento determinado. Para instalar el módulo pywhatkit, escriba el siguiente comando en su IDE/compilador:

pip install pywhatkit
Este comando descargará el módulo pywhatkit. Causará algún retraso, ya que también descargará algunos módulos relacionados.

Usando el módulo pywhatkit:
Para usar esta biblioteca de python para enviar mensajes automáticamente en WhatsApp en ciertos momentos, necesitamos un navegador Chrome y debes tener tu WhatsApp conectado al sitio web de web.whatsapp.com.

Si no tiene un navegador Chrome, puede seguir los siguientes pasos:

Descargue y extraiga la versión estable actual del controlador de Chrome desde aquí (https://chromedriver.chromium.org/).
Abra el archivo descargado y busque una aplicación llamada unidad de cromo, copie su ruta, para Windows, debería verse así: C:/Usuarios/.../chromedriver.exe.
Luego llame a la función pywhatkit.add_driver_path(ruta) y pase la ruta copiada como argumento, si la ruta es válida, se abrirá y cerrará una ventana negra junto con Chrome.
A continuación, llame a la función pywhatkit.load_QRcode() y escanee el código QR.
A continuación se muestra la implementación:

import pywhatkit


pywhatkit.sendwhatmsg("+57xxxxxxxxx", 
                      "Geeks For Geeks!", 
                      18, 30)

                      

                      Explicación:
En el script anterior, hemos especificado el número de teléfono del destinatario al que queremos enviar el mensaje, luego el mensaje que se enviará y luego la hora a la que se debe enviar el mensaje. Esta función sigue el formato de tiempo de 24 horas, por lo tanto, la hora de las 18:30 es 06:30 PM.
Además, debe proporcionar al menos 2-3 minutos de tiempo futuro de la hora actual mientras ejecuta el script, porque si establece el tiempo 1-2 minutos de la hora actual, entonces el módulo dará un error.
Antes de ejecutar el script, asegúrese de haber iniciado sesión en WhatsApp web en Google Chrome. Para iniciar sesión en WhatsApp web, vaya a este enlace y escanee el código QR con el teléfono móvil en el que está usando WhatsApp.

![image](https://github.com/user-attachments/assets/1d113be8-1d01-4376-8e11-5c9e8492be69)

Ahora sólo tienes que ejecutar el script final para enviar un mensaje de WhatsApp. Después de ejecutar el script, le permitirá saber después de cuántos segundos se abrirá su WhatsApp y a qué hora en particular se enviará su mensaje. Después de esa cantidad de segundos, este script abrirá automáticamente WhatsApp y enviará el mensaje al destinatario especificado.

Por ejemplo


En 51 segundos se abrirá web.whatsapp.com y después de 20 segundos se entregará el mensaje


Algunos mensajes de error que puede encontrar durante la ejecución:
1. Al instalar el módulo Pywhatkit, es posible que encuentre este mensaje de error:


"No se pudieron encontrar los encabezados o los archivos de biblioteca para zlib, una dependencia necesaria cuando se compila Pillow desde el código fuente".


Solución: Mejora la pipa y la almohada. Ejecute los siguientes códigos por separado:

2. Especifique el argumento de los minutos comenzando con 0. Por ejemplo, 6:08 PM como 18, 08. Obtendrá un error de sintaxis:


"SyntaxError: no se permiten ceros a la izquierda en literales enteros decimales; use un prefijo 0o para números enteros octales".


Solución: Comience el argumento de los minutos con un número que no sea 0.

3. Si el número de teléfono del destinatario al que desea enviar un mensaje no tiene un código de país. Obtendrá este error:


"CountryCodeException("Falta el código de país en el número de teléfono")"


"pywhatkit.mainfunctions.CountryCodeException: Falta el código de país en el número de teléfono"


Solución: Incluya el código de país de cada número de teléfono. Por ejemplo, +234, +44, +1.

4. Cuando tenga Internet lento, su mensaje no se enviará. Recibirás este mensaje de error:


"raise Warning("INTERNET ES LENTO, la extracción de información puede llevar más tiempo")"


"Advertencia: INTERNET ES LENTO, la extracción de información puede llevar más tiempo"


Solución: Utilice una conexión a Internet sólida.


