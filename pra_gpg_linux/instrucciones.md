# Práctica BRS: GPG usando Linux

## Requisitos previos

- PC con acceso a Internet
- Máquina virtual con [Kali Linux](https://www.kali.org/get-kali/#kali-virtual-machines) (o cualquier otra distribución)
- Software [MobaXterm](https://mobaxterm.mobatek.net/download-home-edition.html)

## Proceso

### 1. Creación llaves GPG

- Ejecutaremos el comando `gpg --gen-key` en la terminal de nuestra máquina Linux. Nos pedirá nuestro nuestro nombre e email y nos pedirá que confirmemos los datos.
  ![1731006615430](image/instrucciones/1731006615430.png)
- Una vez hecho, nos pedirá una `passphrase` (**pandora27** en mi caso) para proteger las claves.
  ![1731006573046](image/instrucciones/1731006573046.png)
- Tras darle a `OK` y esperar un poco, nos generará las claves y nos mostrará un breve resumen de lo que hemos hecho.
  ![1731006635875](image/instrucciones/1731006635875.png)
- Para ver todas las claves que tenemos usaremos el comando `gpg --list-keys`
  ![1731007168211](image/instrucciones/1731007168211.png)

### 2. Exportar la claves

- Usaremos el comando `cd ~/.gnupg` para irnos al directorio oculto donde se encuentran las claves GPG de nuestro sistema (se almacenan ahí por defecto)
  ![1731007315621](image/instrucciones/1731007315621.png)
- Ejecutamos el comando `gpg --export -a nombreAsignado > mi-clave-publica.key`, siendo `nombreAsignado` el nombre que hayamos introducido al crear la clave. En mi caso `Alejandro Rios`
  ![1731007719193](image/instrucciones/1731007719193.png)
- Con el comando `gpg --export-secret-key -a nombreAsignado > mi-clave-publica.key` haremos exactamente lo mismo, pero exportaremos la clave privada.
  ![1731007969074](image/instrucciones/1731007969074.png)
- Nos pedirá la contraseña que introdujimos anteriormente y tras darle a `OK` se exportará clave.
  ![1731007835776](image/instrucciones/1731007835776.png)
  ![1731008024981](image/instrucciones/1731008024981.png)

### 3. Importar una clave pública
Usaremos el software [MobaXterm](https://mobaxterm.mobatek.net/download-home-edition.html).
![1731009135743](image/instrucciones/1731009135743.png)
- Crearemos una conexión SSH con la máquina virtual (debe tener **SSH** habilitado)
![1731008885532](image/instrucciones/1731008885532.png)
- Le daremos a `OK` y tras eso nos pedirá una contraseña maestra (**NO COMPARTIR ESTA CONTRASEÑA**). Una vez introducida le daremos a `OK`
![1731008931899](image/instrucciones/1731008931899.png)
- Nos pedirá la contraseña de la máquina (en mi caso `kali`)
![1731009046901](image/instrucciones/1731009046901.png)
![1731009192211](image/instrucciones/1731009192211.png)
![1731009251161](image/instrucciones/1731009251161.png)
![1731009476143](image/instrucciones/1731009476143.png)
![1731009513574](image/instrucciones/1731009513574.png)
![1731011287788](image/instrucciones/1731011287788.png)
![1731011336030](image/instrucciones/1731011336030.png)
pide passphrase
![1731011384335](image/instrucciones/1731011384335.png)
![1731011420534](image/instrucciones/1731011420534.png)
### 4. Encriptación simétrica
![1731011982018](image/instrucciones/1731011982018.png)
pide contraseña cualquiera
![1731011739575](image/instrucciones/1731011739575.png)
![1731012193153](image/instrucciones/1731012193153.png)