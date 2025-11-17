
no me quedo claro, pero entiendo que existe un buffer que esta entre el kernel y el hardware

en un sistema de archivos, todo lo que sea dispositivo de bloques *Guarda* datos
dispositivos de bloques = pendrive, ssd, hdd

estos bloques guardan informacion en *sectores* pero ser transferidos se agarran de grupos de "bloques"

entonces, cuando muevo un archivo a al computador estoy moviendo un bloque de sectores donde los sectores tienen los datos que busco

# Dispositivos de almacenamiento

protocolos y dispositivos con distintos tipos de almacenamiento
intefaz -> protocolo
Paralel ATA -> IDE 
Serial ATA -> AHCI
PCIexpress -> NVMe 

cualquier dispositivo tiene una ID, un identificador unico:
linux -> /dev/a,b,c,d

el hardware, o el dispositivo que guarda cosas, es mapeao al SO como una carpetita