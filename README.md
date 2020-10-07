# crypt_dev

ejecutar Makefile  con el comando "make clean && make"

luego ejecutar el comando "sudo insmod char_device.ko"

despues , crear un dispisitivo con : "sudo mknod -m 666 /dev/char_dev_cryp c 999 0"   

usar  echo "mensaje a encriptar" >> /dev/char_dev_cryp     (para encriptar el mensaje)

usar cat /dev/char_dev_cryp  (para leer el mensaje encriptado)


para borrar todo de forma segura :

sudo rm /dev/char_dev_cryp

sudo rmmod char_device

make clean (en la carpeta donde se encuentren los archivos char_device.c y Makefile)



Problemas sin solucionar  : al usar cat el mensaje encrptado aparece mal ubicado en la terminal ( ejem : mensaje alumno@alumno-virtualbox:~$   )

********
mknod : para crear dispisitvo

-m 666 : para dar permisos de escritura y lectura a todos

/dev/char_dev_cryp : lugar donde va a estar el archivo y nombre del archivo

c : va a ser de tipo caracter

999 : mayor number , sirve para comunicarse con el driver

0 : minor number , sirve como identificador cuando hay mas de un dispositivo del mismo Mayor number
*****
