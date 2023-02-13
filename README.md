# bookmark-app
Pequeña aplicación que permite guardar nuestras páginas favoritas. Para guardarlas utilizaremos LocalStorage, luego el guardado queda restringido al equipo y navegador utilizados.
De las páginas que guardemos tomaremos los favicons.
Para guardar se abre una ventana modal.

# Recursos
Para poner un fondo svg:
[Hero Pattern Backgrounds](https://www.heropatterns.com/)
Para situar la x de cierre:
[Alineación vertical de objetos](https://www.w3schools.com/cssref/pr_pos_vertical-align.asp)
[FontAwesome](https://fontawesome.com/icons?d=gallery&q=close&m=free)

# Destacable (en el Javascript)
Para cerrar una ventana modal:
**Haciendo clic en la x de la ventana**
*modalClose.addEventListener('click', () => modal.classList.remove('show-modal'));*
**Haciendo clic fuera de la ventana**
*window.addEventListener('click', (e) => (e.target === modal ? modal.classList.remove('show-modal') : false));*
Captura el evento clic al más alto nivel (window), y en las propiedades del evento comprueba donde hemos hecho clic. Si es en el overlay (modal) cierra la ventana. Si es dentro de la ventana, no.

[W3Schools - Prevent Default](https://www.w3schools.com/jsref/event_preventdefault.asp)
e.preventDefault() ---> El comportamiento por defecto de una form, es enviar los datos al servidor con el botón submit. Después, automáticamente se recarga la página. Para evitarlo, utilizamos este método.

Validar que la URL es correcta
**Links interesantes**
[Mozilla - Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
[RegEx Playground Tool](https://regexr.com/) para probar nuestras expresiones regulares

[Splice method for arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
Es el método que utilizaremos para eliminar una posición determinada del array de bookmarks (un determinado bookmark).

**Uso habitual de LOCALSTORAGE**
localStorage.setItem('myCat', 'Tom');
const cat = localStorage.getItem('myCat');
localStorage.removeItem('myCat');
localStorage.clear();
**Además**, cuando enviamos información a LOCALSTORAGE, igual que cuando enviamos información a un servidor, debe ser un string. Por tanto, tendremos que usar JSON.stringify.
Para el proceso inverso (de LOCALSTORAGE al script js) usaremos JSON.parse

**Posibles mejoras**
Añado al repositorio *script2.js*. Es igual al original pero cambiando el array *bookmarks* por un objeto.El objetivo es mejorar el rendimiento.
En este caso es inapreciable, pero si el array fuera muy grande (10.000 o más elementos), la búsqueda y sobre todo la reescritura consumirían un tiempo considerable. Esto no sucedería si utilizáramos objetos. De ahí, la mejora.