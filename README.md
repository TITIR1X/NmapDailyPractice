## 1. ESPECIFICACIÓN DE OBJETIVO:

### **`nmap -iL targets.txt scanme.nmap.org`**
> Este comando lee una lista de sistemas o redes del archivo especificado en targets.txt y los utiliza como objetivos para el escaneo en scanme.nmap.org.

**Dato curioso:**
Puedes crear un archivo de texto con una lista de objetivos y utilizarlo como entrada para realizar escaneos en múltiples sistemas o redes de manera conveniente.

**Para qué:**
Este comando es útil cuando deseas realizar un escaneo en varios objetivos diferentes y no quieres especificarlos manualmente en el comando.

**Casos de uso:**
Puedes utilizar este comando para escanear una lista predefinida de sistemas o redes, como un grupo de servidores en una infraestructura de red.

&nbsp;

### **`nmap -iR 10 scanme.nmap.org`**

> Este comando selecciona al azar 10 objetivos y los utiliza para el escaneo en scanme.nmap.org.

**Dato curioso:**
La opción -iR permite seleccionar objetivos al azar, lo que puede ser útil para realizar escaneos en un conjunto diverso de sistemas o redes de forma aleatoria.

**Para qué:**
Este comando es útil cuando deseas realizar escaneos en objetivos seleccionados al azar para fines de pruebas o evaluaciones de seguridad.

**Casos de uso:**
Puedes utilizar este comando para realizar escaneos en una muestra aleatoria de sistemas o redes dentro de una organización, para evaluar su seguridad y detectar posibles vulnerabilidades.

&nbsp;

### **`nmap --exclude 192.168.0.1,192.168.0.2 scanme.nmap.org`**

> Este comando realiza un escaneo en scanme.nmap.org, excluyendo los sistemas o redes especificados (en este caso, 192.168.0.1 y 192.168.0.2).

**Dato curioso:**
La opción --exclude te permite excluir sistemas o redes específicos del escaneo, lo cual puede ser útil cuando deseas evitar ciertos objetivos o segmentos de red.

**Para qué:**
Este comando es útil cuando deseas realizar un escaneo en scanme.nmap.org, pero deseas excluir ciertos sistemas o redes específicas de ese escaneo.

**Casos de uso:**
Puedes utilizar este comando para realizar escaneos en una red que contiene sistemas o segmentos de red que no deseas incluir en el análisis, como sistemas críticos o redes aisladas.


&nbsp;

### **`nmap --excludefile excluded.txt scanme.nmap.org`**

> Este comando realiza un escaneo en scanme.nmap.org, excluyendo los sistemas o redes especificados en el archivo excluded.txt.

**Dato curioso:**
La opción --excludefile te permite especificar un archivo que contiene una lista de sistemas o redes a excluir del escaneo, lo cual proporciona flexibilidad en la configuración de exclusiones.

**Para qué:**
Este comando es útil cuando deseas excluir múltiples sistemas o redes del escaneo en scanme.nmap.org y prefieres mantener esa lista de exclusión en un archivo separado.

**Casos de uso:** Puedes utilizar este comando para realizar escaneos en scanme.nmap.org, excluyendo una lista específica de sistemas o redes que están definidos en el archivo excluded.txt. Esto es especialmente útil cuando tienes una lista extensa de exclusiones o cuando deseas reutilizar la lista en diferentes escaneos.

&nbsp;




## 2. DESCUBRIMIENTO DE HOSTS:

### **`nmap -sL scanme.nmap.org`**
> Este comando simplemente lista los objetivos a analizar sin realizar un escaneo real.

**Dato curioso:**

El sondeo de lista es útil para obtener una visión general de los objetivos sin realizar un escaneo real.

**Para qué:**

Este comando es útil para verificar y seleccionar los objetivos adecuados antes de realizar un escaneo completo.

**Casos de uso:**

Puede ser utilizado para identificar rápidamente los objetivos disponibles en una red y decidir qué objetivos escanear con mayor detalle.


&nbsp;

### **`nmap -sP scanme.nmap.org`**
> Este comando realiza un escaneo de ping para determinar qué objetivos están activos sin realizar un escaneo de puertos.

**Dato curioso:**

El escaneo de ping es útil para descubrir qué sistemas o redes están en línea y disponibles para el escaneo posterior de puertos.

**Para qué:**

Este comando es útil cuando deseas identificar rápidamente los sistemas activos en una red sin realizar un escaneo exhaustivo de puertos.

**Casos de uso:**

Puede ser utilizado para mapear rápidamente la disponibilidad de sistemas en una red y determinar qué sistemas son accesibles para escaneos posteriores.


&nbsp;

### **`nmap -P0 scanme.nmap.org`**
> Este comando realiza un escaneo sin enviar pings de descubrimiento, asumiendo que todos los objetivos están activos.

**Dato curioso:**

El uso de la opción -P0 suprime el escaneo de ping y asume que todos los objetivos están activos, lo cual puede ser útil en casos donde el filtrado ICMP o la respuesta a pings está deshabilitada.

**Para qué:**

Este comando es útil cuando deseas realizar un escaneo completo de puertos sin depender de la respuesta a pings para determinar la disponibilidad del objetivo.
Casos de uso: Puede ser utilizado cuando los sistemas o redes objetivo no responden a pings o cuando el filtrado ICMP está activo y deseas realizar un escaneo de puertos sin depender de la respuesta a pings.


&nbsp;

### **`nmap -PS/PA/PU -p <puerto> scanme.nmap.org`**
> Estos comandos realizan un escaneo TCP SYN/ACK/UDP para el puerto especificado en scanme.nmap.org.

**Dato curioso:**

Los escaneos TCP SYN/ACK/UDP son técnicas de escaneo de puertos específicas que permiten determinar el estado de los puertos (abiertos, cerrados, filtrados) utilizando diferentes tipos de paquetes.

**Para qué:**

Estos comandos son útiles cuando deseas determinar el estado de un puerto específico en un objetivo y obtener información sobre si está abierto, cerrado o filtrado.
Casos de uso: Puedes utilizar estos comandos para identificar el estado de un puerto específico en un sistema objetivo y evaluar la seguridad y configuración de los servicios que se ejecutan en ese puerto.


&nbsp;

### **`nmap -PE/PP/PM scanme.nmap.org`**
> Estos comandos realizan un escaneo ICMP Echo Request (ping) para el descubrimiento de sistemas activos en scanme.nmap.org.

**Dato curioso:**

Los escaneos ICMP Echo Request son útiles para determinar qué sistemas están activos en la red y disponibles para escaneos posteriores.

**Para qué:**

Estos comandos son útiles cuando deseas realizar un escaneo de descubrimiento para identificar sistemas activos mediante el envío de pings y obtener respuestas ICMP.

**Casos de uso:**

Puedes utilizar estos comandos para descubrir sistemas activos en una red y recopilar información sobre su disponibilidad antes de realizar escaneos más exhaustivos.


&nbsp;

### **`nmap -n scanme.nmap.org`**
> Este comando realiza un escaneo sin resolución de DNS inversa para no obtener los nombres de host de los objetivos.

**Dato curioso:**

La opción -n desactiva la resolución de DNS inversa, lo cual puede acelerar el escaneo y reducir la cantidad de solicitudes DNS realizadas durante el proceso.

**Para qué:**

Este comando es útil cuando deseas realizar un escaneo rápido y no necesitas obtener los nombres de host asociados a las direcciones IP delos objetivos escaneados.

**Casos de uso:** Puedes utilizar este comando cuando deseas obtener resultados de escaneo más rápidos al omitir la resolución de DNS inversa, especialmente en escenarios donde la resolución de nombres de host no es relevante para tu análisis.


&nbsp;

### **`nmap -R scanme.nmap.org`**
> Este comando realiza un escaneo con resolución de DNS inversa, intentando obtener los nombres de host asociados a las direcciones IP de los objetivos.

**Dato curioso:**

La opción -R activa la resolución de DNS inversa, lo cual puede proporcionar información adicional sobre los nombres de host de los objetivos escaneados.

**Para qué:**

Este comando es útil cuando deseas obtener los nombres de host asociados a las direcciones IP de los objetivos escaneados, lo que puede ayudar en la identificación y el análisis posterior.

**Casos de uso:**

Puedes utilizar este comando cuando deseas obtener información detallada sobre los nombres de host asociados a las direcciones IP de los objetivos, lo que puede ser útil para el análisis de la infraestructura de red y la identificación de sistemas específicos.


&nbsp;

### **`nmap --dns-servers <servidores DNS> scanme.nmap.org`**
> Este comando realiza un escaneo utilizando servidores DNS personalizados en lugar de los servidores DNS predeterminados del sistema.

**Dato curioso:**

La opción --dns-servers te permite especificar los servidores DNS a utilizar durante el escaneo, lo cual puede ser útil para escenarios donde deseas utilizar servidores DNS específicos o evitar la resolución DNS predeterminada.

**Para qué:**

Este comando es útil cuando deseas utilizar servidores DNS personalizados durante el escaneo, lo que te brinda control sobre la resolución de nombres de host y la interacción con los servidores DNS.

**Casos de uso:**

Puedes utilizar este comando cuando deseas realizar escaneos utilizando servidores DNS específicos o cuando necesitas evitar la resolución de nombres de host utilizando los servidores DNS predeterminados del sistema.


&nbsp;

### **`nmap --system-dns scanme.nmap.org`**
> Este comando realiza un escaneo utilizando los servidores DNS predeterminados del sistema para la resolución de nombres de host.

**Dato curioso:**

La opción --system-dns utiliza los servidores DNS configurados en el sistema operativo para la resolución de nombres de host durante el escaneo.

**Para qué:**

Este comando es útil cuando deseas utilizar los servidores DNS predeterminados del sistema para la resolución de nombres de host durante el escaneo, en lugar de especificar servidores DNS personalizados.

**Casos de uso:**

Puedes utilizar este comando cuando deseas utilizar los servidores DNS configurados en el sistema operativo para la resolución de nombres de host durante el escaneo, lo que te permite aprovechar la configuración DNS existente en el sistema.

&nbsp;




## 3. TÉCNICAS DE ANÁLISIS:

### **`nmap -sS/sT/sA/sW/sM scanme.nmap.org`**
> Estos comandos realizan diferentes tipos de escaneos TCP SYN, TCP Connect, TCP ACK, TCP Window, y TCP Maimon.

**Dato curioso:** Cada opción (-sS, -sT, -sA, -sW, -sM) representa un tipo de escaneo TCP diferente, que tiene sus propias características y finalidades.

**Para qué:** Estos comandos son útiles para realizar diferentes tipos de escaneos TCP y obtener información específica sobre los puertos y servicios en los objetivos.

**Casos de uso:** Puedes utilizar estos comandos para evaluar la seguridad de los sistemas y servicios en una red y descubrir posibles vulnerabilidades o configuraciones incorrectas.

&nbsp;

### **`nmap -sN/sF/sX scanme.nmap.org`**
> Estos comandos realizan diferentes tipos de escaneos TCP Null, TCP FIN, y TCP Xmas.

**Dato curioso:** Cada opción (-sN, -sF, -sX) representa un tipo de escaneo TCP específico que envía paquetes sin establecer banderas TCP.

**Para qué:** Estos comandos son útiles para realizar escaneos TCP sin establecer banderas TCP específicas y evaluar la respuesta de los sistemas objetivo.

**Casos de uso:** Puedes utilizar estos comandos para identificar cómo los sistemas objetivo responden a paquetes sin banderas TCP establecidas, lo cual puede revelar información sobre la configuración y la protección de los sistemas.

&nbsp;

### **`nmap --scanflags <indicador> scanme.nmap.org`**
> Este comando permite especificar banderas TCP personalizadas para el escaneo.

**Dato curioso:** La opción --scanflags te permite establecer banderas TCP específicas en los paquetes enviados durante el escaneo.

**Para qué:** Esta opción es útil cuando deseas personalizar las banderas TCP utilizadas en el escaneo y evaluar la respuesta de los sistemas objetivo a configuraciones específicas de banderas TCP.

**Casos de uso:** Puedes utilizar esta opción para simular diferentes escenarios de configuración de banderas TCP y evaluar cómo los sistemas objetivo responden a ellos.

&nbsp;

### **`nmap -sI <sistema zombi[:puerto_sonda]> scanme.nmap.org`**

> Este comando realiza un escaneo utilizando un sistema zombi como intermediario para ocultar la identidad del escáner.

**Dato curioso:** El uso de un sistema zombi como intermediario puede ayudar a ocultar la identidad del escáner y evitar la detección o el bloqueo por parte **
de los sistemas** objetivo.

**Para qué:** Este comando es útil cuando deseas realizar un escaneo sin revelar tu propia identidad y utilizar un sistema intermediario para enviar los paquetes de escaneo.

**Casos de uso:** Puedes utilizar este comando en situaciones donde necesites mantener el anonimato durante el escaneo y evitar ser bloqueado o detectado por los sistemas objetivo.

&nbsp;

### **`nmap -sO scanme.nmap.org`**
> Este comando realiza un escaneo de detección de protocolos para identificar los protocolos admitidos por los sistemas objetivo.

**Dato curioso:** El escaneo de detección de protocolos permite identificar los protocolos de capa 3 (IP) y capa 4 (TCP, UDP) que los sistemas objetivo admiten.

**Para qué:** Este comando es útil cuando deseas obtener información sobre los protocolos que los sistemas objetivo admiten y evaluar la configuración de red.

**Casos de uso:** Puedes utilizar este comando para descubrir y evaluar los protocolos de red utilizados en una red objetivo, lo que puede ser útil para fines de auditoría o resolución de problemas.

&nbsp;

### **`nmap -b <servidor ftp rebote> scanme.nmap.org`**
> Este comando realiza un escaneo utilizando un servidor FTP rebote como intermediario para enviar los paquetes de escaneo.

**Dato curioso:** El uso de un servidor FTP rebote permite enviar los paquetes de escaneo a través de un servidor FTP y ocultar la identidad del escáner.

**Para qué:** Este comando es útil cuando deseas realizar un escaneo utilizando un servidor FTP rebote y ocultar tu propia identidad durante el escaneo.

**Casos de uso:** Puedes utilizar este comando en situaciones donde necesites mantener el anonimato durante el escaneo y utilizar un servidor FTP como intermediario para enviar los paquetes de escaneo.

&nbsp;




## 4. ESPECIFICACIÓN DE PUERTOS Y ORDEN DE ANALISIS:

**`nmap -p <rango de puertos> scanme.nmap.org`**

> Esta opción permite especificar un rango de puertos a sondear en el objetivo. Puedes indicar un solo puerto, un rango de puertos separados por guiones o una combinación de ambos.

**Dato curioso:** Nmap utiliza por defecto los 1000 puertos más comunes, conocidos como "puertos bien conocidos". Sin embargo, existen más de 65,535 puertos posibles en un sistema, por lo que esta opción te permite personalizar el análisis y enfocarte solo en los puertos de interés.

**Para qué:** Utilizar esta opción es útil cuando deseas escanear una lista específica de puertos en lugar de todos los puertos posibles. Puede ayudarte a identificar servicios específicos que podrían estar en ejecución en esos puertos y evaluar la seguridad de los servicios correspondientes.

**Casos de uso:**

Identificar puertos abiertos en un objetivo para realizar una auditoría de seguridad.
Verificar si un puerto específico está abierto o cerrado en un sistema remoto.
Analizar la configuración de firewall o enrutadores al escanear puertos específicos.

&nbsp;

**`nmap -F scanme.nmap.org`**

> Esta opción realiza un escaneo rápido de puertos. Analiza los 100 puertos más comunes en lugar de los 1000 puertos por defecto.

**Dato curioso:** La opción -F es una forma rápida de obtener una visión general de los puertos más comúnmente utilizados en un objetivo. Puede ahorrar tiempo al realizar un escaneo inicial y proporcionar información relevante sobre los servicios disponibles.

**Para qué:** Utilizar esta opción puede ser útil cuando deseas realizar un análisis rápido de los servicios más comunes en un objetivo y obtener una idea general de su configuración de seguridad. Es especialmente útil cuando se dispone de poco tiempo o se necesita un escaneo rápido.

**Casos de uso:**

Realizar un escaneo inicial de puertos en un objetivo desconocido.
Obtener una visión general rápida de los servicios expuestos en una red.
Identificar posibles vulnerabilidades en los servicios más comunes.

&nbsp;

**`nmap -r scanme.nmap.org`**

> Esta opción activa la resolución inversa DNS durante el escaneo. Intenta determinar los nombres de host asociados a las direcciones IP encontradas.

**Dato curioso:** La resolución inversa DNS es el proceso de encontrar el nombre de host asociado a una dirección IP. Nmap utiliza esta opción para proporcionar información adicional sobre los objetivos escaneados, lo que puede ayudar a identificar mejor los sistemas y su ubicación.

**Para qué:** La opción -r es útil cuando se desea obtener información adicional sobre los objetivos escaneados, como los nombres de host asociados a las direcciones IP. Esto puede ser útil para reconocimiento de red, análisis de infraestructura y mapeo de sistemas.

**Casos de uso:**

Obtener una lista de nombres de host asociados a direcciones IP en una red.
Identificar sistemas y su ubicación geográfica mediante resolución inversa DNS.
Realizar análisis de infraestructura y mapeo de sistemas más detallado.

















&nbsp;


> https://svn.nmap.org/nmap/docs/nmap.usage.txt:
```
Uso: nmap [Tipo(s) de Análisis] [Opciones] {especificación de objetivos} 
ESPECIFICACIÓN DE OBJETIVO:
  Se pueden indicar nombres de sistema, direcciones IP, redes, etc.  
  Ej: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
  -iL <archivo_entrada>: Lee una lista de sistemas/redes del archivo.
  -iR <número de sistemas>: Selecciona objetivos al azar
  --exclude <sist1[,sist2][,sist3],...>: Excluye ciertos sistemas o redes 
  --excludefile <fichero_exclusión>: Excluye los sistemas indicados en el fichero
DESCUBRIMIENTO DE HOSTS: 
  -sL: Sondeo de lista - Simplemente lista los objetivos a analizar
  -sP: Sondeo Ping     - Sólo determina si el objetivo está vivo
  -P0: Asume que todos los objetivos están vivos 
  -PS/PA/PU [listadepuertos]: Análisis TCP SYN, ACK o UDP de los puertos indicados
  -PE/PP/PM: Solicita un análisis ICMP del tipo echo, marca de fecha y máscara de red
  -n/-R: No hacer resolución DNS / Siempre resolver [por omisión: a veces]
  --dns-servers <serv1[,serv2],...>: Especificar servidores DNS específicos
  --system-dns: Utilizar la resolución del sistema operativo
TÉCNICAS DE ANÁLISIS: 
  -sS/sT/sA/sW/sM: Análisis TCP SYN/Connect()/ACK/Window/Maimon 
  -sN/sF/sX: Análisis TCP Null, FIN, y Xmas 
  --scanflags <indicador>: Personalizar los indicadores TCP a utilizar
  -sI <sistema zombi[:puerto_sonda]>: Análisis pasivo («Idle», N. del T.)
  -sO: Análisis de protocolo IP 
  -b <servidor ftp rebote>: Análisis por rebote FTP 
ESPECIFICACIÓN DE PUERTOS Y ORDEN DE ANÁLISIS: 
  -p <rango de puertos>: Sólo sondear los puertos indicados 
    Ej: -p22; -p1-65535; -p U:53,111,137,T:21-25,80,139,8080 
  -F: Rápido - Analizar sólo los puertos listados en el archivo nmap-services 
  -r: Analizar los puertos secuencialmente, no al azar. 
DETECCIÓN DE SERVICIO/VERSIÓN: 
  -sV: Sondear puertos abiertos, para obtener información de servicio/versión
  --version-intensity <nivel>: Fijar de 0 (ligero) a 9 (probar todas las sondas)
  --version-light: Limitar a las sondas más probables (intensidad 2)
  --version-all: Utilizar todas las sondas (intensidad 9)
  --version-trace: Presentar actividad detallada del análisis (para depurar)
 DETECCIÓN DE SISTEMA OPERATIVO 
  -O: Activar la detección de sistema operativo (SO)
  --osscan-limit: Limitar la detección de SO a objetivos prometedores 
  --osscan-guess: Adivinar el SO de la forma más agresiva
TEMPORIZADO Y RENDIMIENTO:
  -T[0-5]: Seleccionar plantilla de temporizado (los números altos son más rápidos)
  --min-hostgroup/max-hostgroup <tamaño>: Paralelizar los sondeos
  --min-parallelism/max-parallelism <numsondas>: Paralelización de sondeos
  --min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <msegs>: Indica 
    el tiempo de ida y vuelta de la sonda
  --max-retries <reintentos>: Limita el número máximo de retransmisiones de las
    sondas de análisis de puertos
  --host-timeout <msegs>: Abandonar un objetivo pasado este tiempo
  --scan-delay/--max-scan-delay <msegs>: Ajusta el retraso entre sondas
EVASIÓN Y FALSIFICACIÓN PARA CORTAFUEGOS/IDS:
  -f; --mtu <valor>: fragmentar paquetes (opc. con el MTU indicado) 
  -D <señuelo1,señuelo2[,ME],...>: Disimular el análisis con señuelos 
     N. del T.: «ME» es «YO» mismo.
  -S <Dirección_IP>: Falsificar la dirección IP origen 
  -e <interfaz>: Utilizar la interfaz indicada 
  -g/--source-port <numpuerto>: Utilizar el número de puerto dado 
  --data-length <num>: Agregar datos al azar a los paquetes enviados 
  --ttl <val>: Fijar el valor del campo time-to-live (TTL) de IP
  --spoof-mac <dirección mac/prefijo/nombre de fabricante>: Falsificar la dirección MAC
  --badsum: Enviar paquetes con una suma de comprobación TCP/UDP falsa
SALIDA: 
  -oN/-oX/-oS/-oG <file>: Guardar el sondeo en formato normal, XML, 
     s|<rIpt kIddi3 (n3n3b4n4n4), y Grepeable (para usar con grep(1), N. del T.), 
     respectivamente, al archivo indicado. 
  -oA <nombre_base>: Guardar en los tres formatos principales al mismo tiempo
  -v: Aumentar el nivel de mensajes detallados (-vv para aumentar el efecto)
  -d[nivel]: Fijar o incrementar el nivel de depuración (Tiene sentido hasta 9)
  --packet-trace: Mostrar todos los paquetes enviados y recibidos 
  --iflist: Mostrar interfaces y rutas (para depurar) 
  --append-output: Agregar, en vez de sobreescribir, a los archivos indicados con -o. 
  --resume <archivo>: Retomar un análisis abortado/detenido
  --stylesheet <ruta/URL>: Convertir la salida XML a HTML según la hoja de estilo
      XSL indicada
  --webxml: Referenciar a la hoja de estilo de Insecure.Org para tener un XML más portable
  --no-stylesheet: No asociar la salida XML con ninguna hoja de estilos XSL
MISCELÁNEO:
   -6: Habilitar análisis IPv6 
   -A: Habilita la detección de SO y de versión 
   --datadir <nombreDir>: Indicar la ubicación de los archivos de datos Nmap 
     personalizados.
   --send-eth/--send-ip: Enviar paquetes utilizando tramas Ethernet o paquetes IP 
     "crudos"
   --privileged: Asumir que el usuario tiene todos los privilegios 
   -V: Muestra el número de versión 
   -h: Muestra esta página resumen de la ayuda. 
EJEMPLOS: 
   nmap -v -A scanme.nmap.org 
   nmap -v -sP 192.168.0.0/16 10.0.0.0/8 
   nmap -v -iR 10000 -P0 -p 80
```
