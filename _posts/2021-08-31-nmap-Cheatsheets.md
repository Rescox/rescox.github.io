---
layout: post
author: Resco
---


## Comandos de Nmap que utilizo al hacer un reto CTF:
### Escaneo básico

```bash
#!/usr/bin/bash

nmap -p- --open -T5 -v -n $IP

```

- -p- Indicamos el rango de puertos
- --open Le decimos a nmap que detecte solo los puertos con estado "open"
- -T{0-5} Del 0 al 5 indicamos la agresividad del escaneo (0 minimo, 5 máximo)
- -v Para que muestre más información sobre el escaneo o -vvv si queremos que muestre aún más que con -v
- -n Para evitar que haga resolución DNS

### Escaneo de los servicios ejecutandose en los puertos

```bash
#!/usr/bin/bash

nmap -sV -p{puertos a explorar} $ip -oN targeted


```

- -sV Para sondear puertos abiertos y obtener información sobre el servicio y versión del mismo.

- -p Para especificar los puertos a analizar

- -oN Para que se produzca la salida del comando a un archivo


### Escaneo básico (en caso de que el primero vaya lento)

```bash
#!/usr/bin/bash

nmap -p- --open -sS --min-rate 5000 -vvv -n -Pn $Ip -oG allPorts


```

- -sS: Opción para realizar una conexión TCP Syn/Connect()
- --min-rate Para enviar paquetes que no vayan más lentos de x segundos 
- -Pn Para evitar que se haga descubrimiento de host

