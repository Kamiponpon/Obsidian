23/oct
son sistemas dedicados a discoduro
# ¿que es un archivo?

un conjunto de *Datos* y *Meta-datos*
- Meta-Datos
es informacion para el S.O., tienen nombres, fechas ->(Creacion, modificacion, acceso) y Permisos -> (de escritura, lectura, ejecuccion) y **ACL**
-> ¿que es ACL?
tambien hay *tipo* de archivo, los ".[algo]" .rar, .doc, .exe
antes, en los metadato estaba el tipo de archivo, ahi estaba el "magic number": son 2 bytes para mostrar el tipo de archivo

_meta datos tambien le dicen *headers*_

meta datos esta en alguna parte del S.O, no está en el mismo archivo por si, es un segmento aparte. por lo tanto diferentes S.O tienen distintos Meta-datos

en linux existe "wine", un tipo de software, hace un espacio en linux que deja vivir a programas hechos para windows u otros

de igual manera, actualmente no se usa el magic number primariamente para saber que programa abre que archivo y esa pega la hace:


# GUI: Grafic User Interface

carcara del kernel, asocia una extension a un programa, desde aqui hay distintos tipos de de "coordinadores" (?) que se encargan o de abrir termiales o de asociar extensiones