# Search Source

## Descripcion Reto
The developer of this website mistakenly left an important artifact in the website source, can you find it? The website is [here](http://saturn.picoctf.net:52523/)

## Pistas
1. How could you mirror the website on your local machine so you could use more powerful tools for searching?

## Solución
Inspeccionar la página web
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- basic -->
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <!-- mobile metas -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="viewport" content="initial-scale=1, maximum-scale=1">
    <!-- site metas -->
    <title>flexed</title>
    <meta name="keywords" content="">
    <meta name="description" content="">
    <meta name="author" content="">
    <!-- bootstrap css -->
    <link rel="stylesheet" href="[css/bootstrap.min.css](view-source:http://saturn.picoctf.net:52523/css/bootstrap.min.css)">
    <!-- owl css -->
    <link rel="stylesheet" href="[css/owl.carousel.min.css](view-source:http://saturn.picoctf.net:52523/css/owl.carousel.min.css)">
    <!-- style css -->
    <link rel="stylesheet" href="[css/style.css](view-source:http://saturn.picoctf.net:52523/css/style.css)">
    <!-- responsive-->
    <link rel="stylesheet" href="[css/responsive.css](view-source:http://saturn.picoctf.net:52523/css/responsive.css)">
    <!-- awesome fontfamily -->
    <link rel="stylesheet" href="[https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css](view-source:https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css)">
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script><![endif]-->
</head>
<!-- body -->
```
Ir al archivo style.css mostrado en los link del html
```css
/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_ec95fa49} **/
 .carousel-indicators li {
     width: 20px;
     height: 20px;
     border-radius: 11px;
     background-color: #070000;
}
```
En este archivo se encuentra la bandera comentada.

## Bandera
* picoCTF{1nsp3ti0n_0f_w3bpag3s_ec95fa49}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()