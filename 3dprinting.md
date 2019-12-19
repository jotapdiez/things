# 3D Printing things

## Security (printables and non printables)
- XT60
- Firmware (thermal runaway/protection)

## Slicers
- Cura

## Glosario:
## Problemas:
warping: Se despega la pieza de la cama. Se soluciona con Build Plate Adhesion o aumentando Initial Layer Height, bajando initial layer speed o incrementando Slower Layers
pillowing: agujeros en la top/bottom layer. Se soluciona incrementando el Top/Bottom Thickness. Recomendado: 6 veces el layer height. Layer Height 0.2 => Top/Bottom Thickness 1.2 o +
Stringing: Habilitar retraction, incrementar la velocidad de movimiento (200 mm/s deberia estar bien) o reducir la temperatura de impresion. Reducir la temperatura de impresion implica quizas también reducir la velocidad para evitar under-extruding.


## Slicer's options (Cura 4.3.0) 
Wall thickness: Grosor de las paredes
Infill:
Para uso mecanico usar patron 3D como Cubic o Tetrahedral, caso contrario, usar patron 2D como lines, grid y Triangles:
	- Concentric: cuadrados en el medio ideal para soportar peso desde arriba.
	- Lines: Poca fuerza rapido y poco material
	- Grid: Medio entre Lines y Triangles
	- Triangles: mucha fuerza
Regular Fan Speed At Height: Cantidad de capas (al inicio) que le toma llegar a la velocidad especificada del cooler de capa.
Slower Layers: Idem 'Regular Fan Speed At Height' pero en lugar del fan va incrementando la velocidad de impresion.
Print thin walls: Para que imprima partes mas finas que el nozzle (0.4mm en mi caso)

## Links:
- https://all3dp.com/1/cura-tutorial-software-slicer-cura-3d/