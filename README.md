<p align="center">
  <img width="500" height="140" alt="CacheLib" src="website/static/img/CacheLib-Logo-Large-transp.png">
</p>

## Challenge: Amigo secreto 

Esta aplicación permite a los usuarios organizar un sorteo de "amigo secreto" de manera sencilla. Para participar, los usuarios pueden ingresar nombres en un campo de texto y agregarlos a una lista presionando el botón `Adicionar`.

Los nombres ingresados aparecerán en pantalla en forma de lista. Una vez que todos los participantes hayan sido agregados, el usuario podrá hacer clic en el botón `Sortear Amigo`, y el programa seleccionará aleatoriamente un nombre, mostrando el resultado en pantalla.

## :hammer: Desglosando el código

El programa se compone de tres partes principales, cada una con una funcionalidad específica, implementada a través de funciones. Antes de comenzar, se define una variable `listaAmigos`, que almacenará los nombres ingresados en un array.

```sh
let listaAmigos = [];
```

1. Agregar nombres con: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ***function agregarAmigo()*** 

Los usuarios escribirán el nombre de sus amigos en el campo de texto y lo agregarán a la lista presionando el botón `Adicionar`. Para ello: <br><br>


Se obtiene el valor ingresado con `document.getElementById`.

```sh
let nombresAmigos = document.getElementById("amigo").value;
```
<br>

Se almacena en la variable `listaAmigos` utilizando el método `push()`.

```sh
listaAmigos.push(nombresAmigos);
```
<br>

Si el campo de texto está vacío, se muestra una alerta solicitando un nombre válido mediante un condicional `if`.

```sh
if (nombresAmigos===""){
  listaAmigos.pop();
  alert("Casilla vacia, intente nuevamente")
  console.log(listaAmigos);
}
```
<br>

Para visualizar la lista en pantalla, se accede al elemento `<ul id="listaAmigos"></ul>` y se crea una nueva variable `listaFijaAmigos`, que contendrá los nombres con un salto de línea entre cada uno de los elemnetos.

```sh
let printListaAmigos = document.getElementById("listaAmigos");
let listaFijaAmigos = listaAmigos.join("\n");
printListaAmigos.innerText = listaFijaAmigos;
```

> [!NOTE]
> - Se usa `join('\n')` para convertir el array `listaAmigos` en una cadena de texto con saltos de línea, mostrando los nombres uno debajo del otro.
> - Se utiliza `innerText` en lugar de `innerHTML` para evitar interpretar el contenido como HTML y mantener los saltos de línea visibles. <br>
>  ✔ innerText → Si solo se quiere mostrar los nombres como texto simple. <br>
>  ✔ innerHTML → Si necesitas estructurar la lista con `<ul>` y `<li>`.
 <br>

Para mejorar la experiencia del usuario, se implementa la función limpiarCaja(), que borra automáticamente el contenido del campo de texto después de agregar un nombre.

```sh
limpiarCaja();
```
<br>

2. Limpiar caja con: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ***function limpiarCaja()*** 

Cada vez que un usuario agrega un nombre, debe borrar manualmente el campo antes de ingresar otro. Para evitar esto, se crea la función `limpiarCaja()`, que vacía el campo de texto automáticamente después de cada adición. Esta función se llama dentro de `agregarAmigo()`, asegurando que el campo quede listo para un nuevo ingreso.

```sh
document.getElementById("amigo").value = "";
```
<br>

3. Sorteo aleatorio con: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ***function sortearAmigo()***
   
Al hacer clic en el botón `Sortear Amigo`, el programa selecciona aleatoriamente un nombre de la lista y lo muestra en pantalla. <br><br>

Se crea una variable numérica que almacena el tamaño de `listaAmigos`.

```sh
let tamañoListaAmigos = parseInt(listaAmigos.length);
```
<br>

Con `Math.random()` y `Math.floor()`, se genera un número aleatorio dentro del rango de la lista. Este número representa una posición en el array.

```sh
let elementoAleatorio = Math.floor(Math.random()*tamañoListaAmigos);
```
<br>

Se almacena en la variable amigoSecreto, que obtiene el nombre correspondiente.

```sh
let amigoSecreto = listaAmigos[elementoAleatorio];
```
<br>

Finalmente, se actualiza el contenido en la interfaz para mostrar el resultado, accede al elemento `<ul id="resultado"></ul>`

```sh
let printAmigoSecreto = document.getElementById("resultado");
printAmigoSecreto.innerHTML = "El amigo secreto sorteado es " + amigoSecreto + "!";
```
<br>

 

## :construction: Mejoras

1. `Evitar nombres repetidos:` Antes de agregar un nombre a la lista, verificar si ya existe en el array. Si el nombre está repetido, mostrar un mensaje de alerta y evitar que se agregue nuevamente.

2. :collision: `Asignación sin repetición:` En lugar de elegir solo un "amigo secreto", asignar a cada participante un amigo de forma aleatoria sin repeticiones, asegurando que nadie se asigne a sí mismo. Esto se puede lograr con un algoritmo que reorganice aleatoriamente los nombres en la lista y asigne cada persona a otra.

3. `Validación del campo de entrada:` Evitar que se ingresen números o caracteres especiales en lugar de nombres.
Si el usuario ingresa algo inválido, mostrar un popup con un mensaje de error y no permitir la adición.

4. :collision: `Eliminar nombres de la lista:` Agregar una opción para eliminar un nombre de la lista en caso de errores o cambios.
Se puede agregar un botón junto a cada nombre para borrarlo.

5. `Límite de participantes:` Definir un número mínimo de participantes para realizar el sorteo. Mostrar un mensaje si no hay suficientes personas.

<br><br>

> [!NOTE]
> :collision: Para expertos 











