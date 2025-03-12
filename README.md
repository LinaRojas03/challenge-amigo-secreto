## Challenge: Amigo secreto 

Aplicación que permite a el usuario ingresar nombres de amigos en una lista para luego realizar un sorteo aleatorio y determinar quién es el "amigo secreto". En el programa, el usuario deberá digitar los nombres mediante un campo de texto y agregarlos con el botón "Adicionar". Los nombres ingresados se mostrarán en pantalla en forma de lista, y al finalizar, haciendo click en el botón "Sortear Amigo", se seleccionará uno de los nombres de forma aleatoria, mostrando el resultado en pantalla.

### Desglosando el código

El programa se compone de 3 partes importrantes que se encragaran de una funcioonalidad en particular y para esto se crearon tres funciones. Antes de iniciar es importante crear la variable, que en este caso será la lista de amigos en forma de un array. 

1. Agregar nombres:
Los usuarios escribirán el nombre de sus amigos en el campo de texto disponible, estos seran almacenados en la varibale listaAmigos. Para acceder a el valor que el usuario ingresó en el campo de entrada se emplea la funcionalidad document.getElementById, de esta forma tendremos acceso a cada uno de los nombres ingresados.
Cada nombre que se digite, será agregado al final del array con la funcion push.
Para validar la entrada, en caso de que el campo esté vacío, el programa mostrará una alerta pidiendo un nombre válido. Para esto se crea un condicional if y un pop up saldrá

Para visualizar la lista de los nombres ingresados se accede al campo debajo que es un ul, se agrega un texto y se crea un nueva variable listaFijaamigos que es el mimso array pero impreso con un salto de línea entre cada elemento y esta nueva lista es la que se mostrará en pantalla 

El usuario tine que borrar y escribir el nuevo nom,bre cada vez que quiere agregar un nuevo amigo. Para mejorar esto, se crea un funcion limpoiar caja y se llama a la funcion dentro de la funcion de agregarAmigo para que cada vez que se haga click en agregar amigo, la funcion limpiar caja limpie el campo de netrada como si se estuviera preparando para que el usuario ingrese oro elemnento. 

2. Limpioar caja: se crea la funcion de limpiar caja
El usuario tine que borrar y escribir el nuevo nom,bre cada vez que quiere agregar un nuevo amigo. Para mejorar esto, se crea un funcion limpoiar caja y se llama a la funcion dentro de la funcion de agregarAmigo para que cada vez que se haga click en agregar amigo, la funcion limpiar caja limpie el campo de netrada como si se estuviera preparando para que el usuario ingrese oro elemnento.

3. Sorteo aleatorio: Al hacer clic en el botón "Sortear Amigo", se seleccionará aleatoriamente un nombre de la lista y se mostrará en la página. para esto, se crea una variable de tipo numerico (entero) con el tamaño de lista, luego con la funcion math random y math floor se escoge aleatoriamente un numero entre los limites establecidos y se almacena en una nueva variable, este nuevo numero aleatorio sera la posicion del elemento en la lista, que siempre irá cambiando cada que se haga cllick en el boton, luego se crea otra variable amigoSecreto a la que se le asigantra el nombre de la poscion aleatoria y luego se accede a el valor del campo para imprimir quien fue el amigo secreto  

## Mejoras

Que no se pueda repetir elemento
que asigne el nombre ac cada uno de los integrantes sin repetir 
Si el campo de entrada es no valido cono un numero que saque un pop up


