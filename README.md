🗂️ CONFIGURACIÓN DEL ARCHIVO JSON PARA IMAGEN MAPEADA 🗂️

Para definir las áreas interactivas de una imagen mediante la librería react-img-mapper, es necesario estructurar los datos según la siguiente interfaz:

export interface IMappedImageArea {
  title: string;
  description?: string;
  shape: 'rect' | 'circle' | 'poly';
  coords: number[];
  fillColor: string;
  openModal: boolean;
  href?: string;
}


📌 DESCRIPCIÓN DE LOS CAMPOS 📌

--> title (string) ✅
    Obligatorio.
    Nombre identificador del área seleccionada que se mostrará dentro del modal.

--> description (string) 📝
    Obligatorio si openModal es true.
    Texto explicativo del área seleccionada que se mostrará dentro del modal.

--> shape ('rect' | 'circle' | 'poly') 🔺
    Obligatorio.
    Tipo de forma geométrica que define el área interactiva:
      'rect': Rectángulo → Requiere 4 coordenadas: [x1, y1, x2, y2]
      'circle': Círculo → Requiere 3 coordenadas: [x, y, radius]
      'poly': Polígono → Requiere múltiples pares de coordenadas: [x1, y1, x2, y2, ..., xn, yn]

--> coords (number[]) 📐
    Obligatorio.
    Lista de coordenadas numéricas que indican la posición y forma del área. La cantidad y el formato dependen del valor de shape.

--> fillColor (string) 🎨
    Obligatorio.
    Color que se aplicará como fondo al área seleccionada. El valor debe estar en formato rgb (por ejemplo: "rgb(255, 0, 0)").
    Se recomienda utilizar rgba (por ejemplo: "rgba(255, 0, 0, 0.5)") para permitir transparencia y mejorar la visualización sobre la imagen.

--> openModal (boolean) 📦
    Obligatorio.
    Define el comportamiento al hacer clic en el área:
      'true': Se abre un modal mostrando el title y la description, y un botón "Ver más" si href está definido.
      'false': Se redirige a una URL externa si href está definido.

--> href (string) 🔗
    Opcional.
    URL a la que redirige el área seleccionada. El enlace se abrirá en una neva pestaña del navegador.


📁 ARCHIVO JSON YA CONFIGURADO DE EJEMPLO 📁

En este repositorio se incluye un archivo .json ya configurado que contiene varias áreas definidas a modo de ejemplo.


📚 DOCUMENTACIÓN ADICIONAL 📚

Para más detalles técnicos y opciones avanzadas, se puede consultar la documentación oficial de la librería utilizada para realizar el mapeo de áreas de la imagen:
--> https://www.npmjs.com/package/react-img-mapper 🔗
