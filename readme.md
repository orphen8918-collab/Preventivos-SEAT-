# Preventivos T10

Actualización de posicionamiento de datos en órdenes originales.

- Lee los encabezados Nombre y Apellido de cada página y coloca cada nombre centrado en su celda de asignaciones.
- Localiza los encabezados OK y NO para centrar las marcas en la columna correspondiente.
- Centra verticalmente las marcas en la fila del punto preventivo detectado.
- Mantiene el OCR en todas las páginas y la agrupación de órdenes/páginas.

Publicar el contenido de este ZIP en Netlify mediante un nuevo despliegue manual. La lectura OCR requiere conexión a Internet.

## Cambios de esta versión
- Las fotos se enderezan automáticamente (se corrige la inclinación) antes de leerlas.
- Segunda pasada de OCR solo con dígitos sobre la columna Op., para no perder puntos.
- Las columnas OK/NO se calculan con las líneas reales de la tabla y, si no se ven, con los encabezados OK/NO (antes se usaban siempre coordenadas fijas).
- Una página sin número de orden legible ya no se funde con la anterior si repite sus operaciones.
- Los puntos añadidos a mano también reciben tic (posición estimada por su número de operación).
- Asignaciones: cada nombre y apellido se centra en su celda real (bordes detectados en la imagen) y en la fila de datos del recuadro; los encabezados Nombre/Apellido se reconocen aunque el OCR los lea con pequeños errores. Si no se localiza el recuadro en una página, la app lo indica al generar el PDF.
- Asignaciones: detección difusa de «Nombre»/«Apellido»/«ASIGNACIONES» (tolera bordes pegados y errores del OCR), segunda lectura OCR si no aparecen y aviso al exportar si faltan nombres o el recuadro no se localiza.
- Observaciones: detección tolerante del recuadro OBS (bordes y borde inferior reales), texto ajustado dentro del recuadro, caracteres no admitidos por el PDF sustituidos para que no fallen, y aviso si no se localiza el recuadro. En el control cumplimentado se respetan los saltos de línea y las observaciones largas ya no se cortan.
- Observaciones en el recuadro OBS con letra más grande (9,2 pt; se reduce hasta 6,4 pt solo si no cabe).
- Observaciones: si el OCR no lee «OBS:» en la hoja 2, el recuadro se localiza por sus líneas; la hoja de continuación se une a su orden aunque el número no se lea bien. Ya no se confunde «Observar» (texto de las operaciones) con el rótulo OBS.
