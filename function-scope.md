# Identificacion de functions y scope

* **Track:** _Common Core_
* **Desarrolladora:** _Margarita Sutta._

***

A continuación se identificaran las funciones globales, locales, funciones de callback, function expressions, contextos de ejecución, function statements, scope closure, qué funciones forman parte de la pila de ejecución y qué funciones forman parte de la cola de eventos.

***

## Funciones globales

Son las funciones globales dentro del contexto de ejecuciondel navegador, por lo tanto se identifico una única y es **global execution context**.

```js
$(document).ready(function() {});
```

## Funciones locales

Dentro de la funcion `$(document).ready()` se encuentran las siguientes funciones locales:

* **activeButton()**
* **desactiveButton()**
* **longitud()**
* **soloNumeros()**
* **isValidCreditCard()**

## Funciones expresions

Son aquellas que son declaradas por una variable.

```js
var creditCardNumber = soloNumeros(longitud(numberCard));
```

## Funciones statement

Son aquellas que no han sido declaradas en variables, se identificaron las siguientes con un scope de alcance global:

* **activeButton()**
* **desactiveButton()**
* **longitud()**
* **soloNumeros()**
* **isValidCreditCard()**

## Funciones de callback

Son las se pasan dentro de otra función como argumento.

> (**soloNumeros**) como argumento y es la función **longitud**

```js
soloNumeros(longitud(numberCard));
```

## Funciones closures

Se le llama funciones closures a las que "recuerdan" el entorno en el que se han creado y vendrian a ser las siguientes:

* **activeButton**
* **desactiveButton**

```js
  function activeButton() {
    $buttonNext.attr('disabled', false);
  }

  function desactiveButton() {
    $buttonNext.attr('disabled', true);
  }
```

## Execution stack

* `console.log()`

## Funciones que forman parte de la pila de ejecucion (stack execution)

La pila de ejecución o stack execution, es el orden en el que se ejecutan las funciones, y seria en el siguiente orden (se deberá leer de abajo hacia arriba).

* **isValidCreditCard()**
* **soloNumeros()**
* **longitud()**
* **desactiveButton()**
* **activeButton()**

## Funciones que forman parte de la cola de eventos (event queue)

Son las aquellas funciones que se cargan solo cuando se produce el evento, en este caso hay una función **anonima** que escucha el evento input.

## Variables globales

```js
var $buttonNext = $('#next');
```

## Variables Locales

```js
var regex = /^[0-9]+$/;
var creditCardNumber = soloNumeros(longitud(numberCard));
var arr = [];
var sumaTotal = 0;
```
