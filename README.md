<h1 align="center">CRUD App</h1>

<p align="center">Una aplicación web sencilla para crear, leer, actualizar y eliminar datos, diseñada con un enfoque moderno y fácil de usar.</p>

<p align="center">
  <img src="https://img.shields.io/badge/licencia-MAC-green" alt="Licencia MIT">
  <img src="https://img.shields.io/badge/versi%C3%B3n-1.0.0-blue" alt="Versión">
  <img src="https://img.shields.io/badge/contribuidores-2-brightgreen" alt="Contribuidores">
</p>


# Índice

1. [Introducción](#introducción)
2. [Estructura de la CRUD](#estructura-de-la-crud)
3. [Visualización](#visualización)
4. [Tecnologías](#tecnologías)
5. [Codificación](#codificación)
6. [Despliegue](#despliegue)

## Introducción
Las aplicaciones CRUD (Create, Read, Update, Delete) han cobrado una relevancia significativa en el desarrollo de software moderno, especialmente en la gestión de datos y usuarios. Una CRUD APP para el registro de usuarios es esencial en múltiples contextos, desde plataformas de comercio electrónico hasta sistemas internos de empresas. Este tipo de aplicación permite a las organizaciones llevar un control detallado de sus usuarios, mejorando la eficiencia en la gestión de la información y proporcionando una base sólida para el análisis y la toma de decisiones. Además, una CRUD APP facilita la administración de permisos y roles, asegurando que solo el personal autorizado tenga acceso a información sensible. En resumen, la implementación de una CRUD APP para el registro de usuarios no solo optimiza los procesos operativos, sino que también contribuye a la seguridad y precisión de los datos en una organización.

## Estructura de la CRUD
**Header**:Donde aparece el logo y la descripción en título de Registro de Usuarios.
**Formulario de registro de Datos**:Tiene dos campos Nombre y email.
**Tabla de Registros**: Aparece el resgito de los datos, junto a dos acciones editar y eliminar

## Visualización
Se detallan las consideraciones de diseño y usabilidad de la landing page, incluyendo aspectos como:
- **Diseño Responsivo**: La CRUD APP se adaptada a diferentes dispositivos móviles facilitando su visualización.
- **Paleta de Colores**: Se utilizaron conceptos de psicología del color y diseño gráfico para internet a fin de generar una experiencia de usuario inigualable.
- **Tipografía**: Se incorporaron estilos vanguardista de diseño editorial para generar una mejor experiencia del lectura a los visitantes.

A continuación se presenta en imágen la representación de la CRUD APP:

![](https://github.com/monicarias/CRUD-APP/blob/main/img1.jpg?raw=true)

## Tecnologías 
Lista de las tecnologías y herramientas utilizadas para el desarrollo de la landing page, tales como:
- **HTML5**: Estructuración del contenido buscando el estándar que incorpora las últimas tendencias de maquetación.
- **CSS3**: Estilos y diseño visual aconmpañados de técnicas como flat design y UX/UI
- **JavaScript**: Interactividad y funcionalidades dinámicas que facilitan la interacción del ususario.
- **Herramientas de Desarrollo**: Visual Studio Code y Git.

## Codificación

### HTML

```html
<body>
   <main class="container">
    <section class="crud">
        <h1 class="crud_title">Registro de Usuarios</h1>

        <!-- Creamos un formulario para ingresar datos. Etiquetas con id para modificar en Js y Class en CSS -->
        <form id="formRegister" class="crud_form">
            <input type="text" placeholder="Nombre" id="nameinput" class="form_input">
            <input type="email" placeholder="Email" id="emailinput" class="form_input">

        <!-- Este botón tiene una clase general "button" y agregamos modificadores como button--primary -->    
            <button type="submit" id="submitbutton" class="button button--primary" >Agregar</button>
        </form>

        <!-- Creamos una tabla para que se visualicen los datos -->
        <table class="crudtable">
        <thead>
            <tr>
                <th class="table_header">Nombre</th>
                <th class="table_header">E-mail</th>
                <th class="table_header">Acciones</th>
            </tr>
        </thead>

        <!-- Creamos el cuerpo de la tabla que se agrega o elimina automaticamente -->
        <tbody id="tablebody" class="table_body">
        </tbody>
        </table>
    </section>
   </main>
    
    <script src="app.js"></script>    
</body>
```

### CSS

```
/* fuente importada de Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700&display=swap');

/* Se reinician los espacios que se agregan por defecto, quedan en 0 */
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* todo texto tendrá la fuente Montserrat, botones, entradas de texto, body, etc. */
body, button, input {
    font-family: 'Montserrat', sans-serif;
}

/* La clase container estará centrada, que es el contenedor "padre" de todo el formulario */
.container {
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
    padding: 20px;
}

.crud_title {
    text-align: center;
    color: rgb(100, 100, 114);
}

.crud_form{
    display: flex;
    margin: 10px 0;   
}

/* Tamaño de fuente de las entradas a 1rem unidad relativa, equivale al tamaño por defecto del navegador, 2rem = 18px * 2  */
.form_input {
    flex: 1;
    padding: 5px;
    margin-right: 10px;
    font-size: 1rem;
}

/* Estilos al botón "padre" o en general  */
.button {
    padding: 5px 10px;
    border: none;
    border-radius: 5px;
    font-weight: 700;
}

/* efecto al pasar el mouse sobre el botón, crece 1.2  */
.button:hover{
    transform: scale(1.2);
}

/* Estilos especificos a "botón "primary" pero conserva propiedades del botón general "padre" */
.button--primary {
    background-color: aquamarine;
}

/* Estilos especificos a "botón "secundary" que se crean automaticamente en la celda "acciones"*/
.button--secundary {
    background-color: #ffc107;
}

/* Estilos especificos a "botón "terciary" que se crean automaticamente en la celda "acciones"*/
.button--terciary {
    background-color: #dc3545;
    color: #f0f0f0;
}

/* Estilos a la tabla del Crud */
.crudtable{
    width: 100%;
    border-collapse: collapse;
}

.table_header, .table_body td {
    border: 1px solid #cccccc;
    padding: 5px;
}

.table_header {
    background-color: #d0f9fa;
}

/* Estilos para el tercer elemento de la tablebody lo que serán los botones de la celda "acciones" */
.table_body td:nth-child(3){
    display: flex;
    justify-content: space-around;
}
```

## Despliegue
[CRUD APP](https://ejemplocrudapp.netlify.app)

