1. CSS: El botón no tenía estilos porque el nombre de la clase no coincidía. 
Lo corregí de .btn-primery a .btn-primary.

2. API: Los nombres y correos no cargaban. Resulta que las llaves en el JSON que devolvía la API eran diferentes a lo que estaba escrito en el JavaScript, así que lo ajusté a user.name y user.email.

3. Refactorización: Aproveché para separar la lógica de renderizado (renderUser) de la lógica de (loadUsers). Siento que así el código queda mucho más limpio, ordenado y mas facil de añadirle la funcion (filterUsers).

4. Funcionalidad (El buscador): Para hacer la experiencia más fluida, implementé un buscador en tiempo real. Para lograrlo, realicé los siguientes pasos:
Creación del componente: Añadí un elemento <input> en el HTML con el evento oninput.
Lógica de filtrado: Creé la función filterUsers() que toma el valor ingresado y filtra los datos.
Optimización: En lugar de realizar una nueva petición a la API cada vez que el usuario escribe, guardo los usuarios en una variable global (allUsers) tras la primera carga. Esto permite que el filtrado sea instantáneo y no genere tráfico innecesario hacia el servidor.

"Para este ejercicio, implementé el filtrado sobre una variable local por la naturaleza del dataset (limitado). Sin embargo, soy consciente de que para grandes volúmenes de datos (ej. > 5,000 registros), lo ideal sería implementar paginación o realizar el filtrado directamente en el lado del servidor para no impactar el rendimiento del navegador del usuario."

5. SQL: La consulta que venía en el comentario tenía problemas de seguridad. 
Consulta Parametrizada (Recomendada): Utilicé el formato @nombre para demostrar cómo se vinculan variables de forma segura, una práctica muy común en entornos como SQL Server o C#.

Consulta Preparada: Implementé el estándar de signos de interrogación (?), que es la forma más universal y recomendada en entornos como Node.js, PHP o Java para separar el comando SQL de los datos enviados por el usuario.

SQL con valores literales: Incluí un ejemplo básico como referencia para entender la estructura de la consulta, aunque aclarando que este método no se debe usar en producción si los datos provienen de una entrada de usuario.