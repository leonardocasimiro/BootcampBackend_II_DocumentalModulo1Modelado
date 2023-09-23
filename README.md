# Modelado de Base de Datos
## _La muerte a pellizos por lemonCode_

![Limon llorando...](./img/lemon.png)

Para esta practica se nos solicita:

- Diagrama del modelo de datos.
- Markdown con explicación de por qué se ha realizado dicho modelado, patrones aplicados y razón.

## Introducción


> Para estre trabajo se ha requerido una plataforma de videos de formación, en la cual al darte de alta como alumno accedes a  los videos de la plataforma.

## Consideraciones

> Existe una propiedad en el suscriptor que es "credito", el cual viene a ser el dinero que dispone para ir consumiendo videos. Nosotros hemos considerado que la carga de dichos creditos así como el pago de estos se realiza en otra platarma de pagos que no vamos a considerar aqui. Por esto solo consideramos una plataforma de videos donde tu llegas con o sin creditos. Este se actualizará mediante una API, u otro metodo.

## Parte Obligatoria

Generar un modelado que refleje los siguiente requerimientos:

>Queremos mostrar los últimos cursos publicados. Para ello se añade el campo "fecha de publicación" en el documento "videos"

>Queremos mostrar cursos por área (devops / front End ...). Para ello, en el documento "videos" hay un objeto llamado "tematica", a traves del cual se pone a true cada tematica que trata el video, pudiendo tratar no solo una tematica, ya que a veces se enrtelazan las tematicas de los cursos.

>Queremos mostrar un curso con sus videos. Para ello tenemos el documento "curos" un campo con un array sobre los cursos que pertenece

>En un video queremos mostrar su autor. Para ello tenemos el docuento "videos" relacionado con el documento "autores"

## Documentos
- Modelado_documental.dmm, donde tratamos de mostrar una ejemplificación de modelado documental 
    - ✅ Modelado No SQL.
    - ❌ Modelado SQL

- Modelado_relacional.dmm, donde tratamos de mostrar una ejemplificación de modelado documental.
    - ❌ Modelado No SQL.
    - ✅ Modelado SQL
## Patrones de diseño

Para esta practica hemos intentado aplicar dos patrones de diseño.

| Patron | Descripcion | Ejemplo |
| ------ | ------ | ------ |
| Subset Pattern | Nos permite manejar documentos grandes |Tengo un documento de reseñas, pero he creado un reseñas_last_3 en el docuemento videos (tendra las 3 ultimas reseña) para evitar tirar de un documento reseñas grande.  |
| Extended ref | Evita tener que hacer "joins" |En el documento suscriptores he embebido la direccion para tener que tirar de doble consulta a este dato cuando adquiramos del cliente. Se ha hecho un objeto que bien podria ser un array de objetos si quisieramos añadir varias direcciones. |
