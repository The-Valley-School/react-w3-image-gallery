# WORKSHOP 3: Galería de imágenes

En esta ocasión vamos a realizar un buscador de imágenes como el que se muestra en la siguiente imagen:

![Untitled](/assets/Untitled.png)

Una vez introducido un texto de búsqueda y pulsado ENTER veremos las imágenes que nos devuelva el API, por ejemplo al buscar Formula 1 veremos los resultados del API:

![Untitled](/assets/Untitled%201.png)

Si pulsamos sobre una imagen, esta quedará marcada como favorita. Para guardar como favorita una imagen la guardaremos en el localStorage, y las mostraremos en la parte de abajo de la galería:

![Untitled](/assets/Untitled%202.png)

Por otro lado, en la parte superior de la página además del buscador, tendremos un botón para cambiar el tema entre tema normal (el que hemos visto hasta ahora) y el tema “fantasía” que mostrará la web de una forma más divertida:

![Untitled](/assets/Untitled%203.png)

Durante este WorkShop debemos implementar todo lo que se ha visto esta semana:

- **useMemo**: Usaremos useMemo para ordenar las imágenes devueltas por el API en orden alfabético en función de su texto alternativo (el que estamos mostrando debajo de la foto)
- **useReducer**: Usaremos useReducer para mantener un estado con los favoritos. Tendremos dos acciones (ADD_FAVORITE y REMOVE_FAVORITE) que añadirán y eliminarán las imágenes sobre un array en el local storage
- **Custom Hooks**: Crea un custom hook que te sirva para consumir el API de imágenes, el hook te devolverá directamente la lista de imágenes y recibirá el texto de búsqueda a aplicar en la query de la API
- **UseContext**: Utilizaremos un contexto para gestionar el tema de la aplicación (tema básico o tema fantasía)

Datos de la API:

Vamos a utilizar la API de imágenes PEXELS: [https://www.pexels.com/api](https://www.pexels.com/api/) 

Para poder usar la API te tendrás que registrar y generar un API KEY : [https://www.pexels.com/join-consumer](https://www.pexels.com/join-consumer/) 

![Untitled](/assets/Untitled%204.png)

Y generar API KEY:

![Untitled](/assets/Untitled%205.png)

Una vez tengas tu API Key podrás hacer llamadas GET a la API:

[https://api.pexels.com/v1/search?query=arbol](https://api.pexels.com/v1/search?query=arbol) 

Para que te funcione tendrás que mandar una cabecera “Authorization” con la clave que has generado, te dejamos por aquí un fragmento de código de ejemplo:

```jsx
const options = {
  headers: {
    'Authorization': "XXXXXXXXXXX"
  }
};

const finalUrl = `https://api.pexels.com/v1/search?query=${searchText}`;
fetch(finalUrl, options)
  .then(data => data.json())
  .then(dataParsed => {
    console.log(dataParsed);
  });
```

**CODIGO DE LA APLICACIÓN RESUELTA
NO ENTREGAR A LOS ALUMNOS**

[https://github.com/The-Valley-School/react-w3-image-gallery](https://github.com/The-Valley-School/react-w3-image-gallery)