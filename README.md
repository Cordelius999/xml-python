# XML, DOM y Python

## Introducción

XML (Extensible Markup Language) es un lenguaje de marcado que se utiliza para almacenar y transportar datos de manera legible tanto para humanos como para máquinas. DOM (Document Object Model) es una interfaz de programación para documentos XML y HTML que proporciona una representación estructurada del documento, permitiendo acceder y manipular su contenido. Python es un lenguaje de programación versátil y potente, con bibliotecas que facilitan el procesamiento de XML.

## XML

![XML](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTb0oeGPazBl_nt_iLP65IvOrOZY_1NMmu52oq9dcy4Tg&s)

- **Extensible Markup Language (XML)**: Lenguaje de marcado utilizado para almacenar y estructurar datos de forma legible y portable.
- **Características de XML**:
  - Define reglas para crear documentos estructurados.
  - Utiliza etiquetas para representar datos.
  - Permite la definición de esquemas para validar documentos.


## Ejemplo de xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<diaris>
    <diari id="1">
        <nom>El País</nom>
        <url>https://elpais.com</url>
    </diari>
    <diari id="2">
        <nom>The New York Times</nom>
        <url>https://www.nytimes.com</url>
    </diari>
    <diari id="3">
        <nom>Le Monde</nom>
        <url>https://www.lemonde.fr</url>
    </diari>
</diaris>
```


## PYTHON

![python](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQmmngeGJFNocA_JXfnBGI-yKvz1WNGQ2P7hYqKDrpO2w&s)

Python es un *lenguaje de programación* de alto nivel ampliamente utilizado en diversos campos, incluyendo desarrollo web, análisis de datos, inteligencia artificial y más. Es conocido por su sintaxis clara y legible, lo que lo hace ideal para principiantes y expertos por igual.

## Características

- **Fácil de aprender:** La sintaxis simple y legible hace que Python sea fácil de aprender incluso para principiantes.
- **Multipropósito:** Python es utilizado en una amplia gama de aplicaciones, desde desarrollo web hasta análisis de datos y aprendizaje automático.
- **Código abierto:** Python es un proyecto de código abierto con una comunidad activa de desarrolladores que contribuyen a su desarrollo y mejora continua.
- **Portabilidad:** Python se ejecuta en múltiples plataformas, incluyendo Windows, macOS y Linux.
- **Librerías extensas:** Python cuenta con una amplia variedad de librerías y frameworks que facilitan el desarrollo de aplicaciones.


## DOM (Document Object Model)

- **Document Object Model (DOM)**: *Interfaz de programación* que representa documentos XML o HTML como una estructura de árbol.

- **Características de DOM**:
  - Permite acceder y manipular la estructura de un documento XML.
  - Proporciona métodos para agregar, modificar y eliminar elementos.
  - Facilita la navegación por el contenido del documento.

- **xml.dom**: xml.dom.minidom es una implementación mínima de la interfaz Document Object Model (Modelo de objetos del documento), con una API similar a la de otros lenguajes. Está destinada a ser más simple que una implementación completa del DOM y también significativamente más pequeña. Aquellos usuarios que aún no dominen el DOM deberían considerar usar el módulo xml.etree.ElementTree en su lugar para su procesamiento XML.

[Enllaç al Moodle de M04](https://moodle.insjoaquimmir.cat/course/view.php?id=223)

## Ejemplo de minidom

```python
from xml.dom import minidom 

doc = minidom.parse("diaris.xml")

tag_principal = doc.documentElement

print("<html><head><title>Diaris DOM</title></head><body>")

llista_tag_diari = tag_principal.getElementsByTagName("diari")
for tag_diari in llista_tag_diari:
    id = tag_diari.getAttribute("id")
    nom = tag_diari.getElementsByTagName("nom")[0].firstChild.data
    url = tag_diari.getElementsByTagName("url")[0].firstChild.data
    
    print("<p>")
    print(f"<a id='{id}' href='{url}'>#{id} {nom}</a>")
    print("</p>")

print("</body></html>")
```
[Enllaç apunts minidom](https://docs.python.org/es/3/library/xml.dom.minidom.html)
