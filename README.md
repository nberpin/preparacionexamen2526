
## **División estructural del HTML según el diseño**
Este es el diseño que nos ha dado nuestro responsable de UX/UI o diseñador gráfico para móvil:
![mobile-design](https://hackmd.io/_uploads/rkLx8QWZbl.jpg)


Al fijarnos en la estructura dividimos en distintas secciones que suelen ser bastante standards, todo lo vamos haciendo con práctica!
Como ven he usado de base el proyecto de su compañero Jonathan pero como era responsive he quitado algunas cosas que aún no hemos dado, en todo caso dejo su nombre porque se lo merece!
Esta versión del código está en: 

Pero les recomiendo que intenten hacerlo solos para que estén preparados para mañana. 

Mucho ánimo para el examen!
### **1. Un contenedor principal**

- **Elemento:**
    - `<section class="contenido">`
- **Motivo de uso:**
    - Agrupa todo el componente y permite centrarlo, limitar ancho y aplicar estilos generales como el borde redondeado y el overflow.
    - Facilita que todos los bloques “vivan” juntos, tal como se ve en la carta o tarjeta central del diseño.


### **2. Primer bloque: Presentación**

- **Elemento:**
    - `<div class="comunidad">`
- **Motivo de uso:**
    - Separa el encabezado superior del resto.
    - Permite que tenga fondo, colores y padding distintos.
    - Dentro incluye:
        - `<h2>` para el título principal
        - `<div class="subtitulo">` para el texto de garantía destacado
        - `<p>` para la descripción


### **3. Segundo bloque: Suscripción**

- **Elemento:**
    - `<div class="suscripcion">`
- **Motivo de uso:**
    - Un div propio para el área de suscripción, facilitando color de fondo separado y espaciado específico.
    - Dentro incluye:
        - `<h3>` para el subtítulo

```
- `<div class="precio">` para el precio destacado (y el periodo en `<span>`)
```

        - `<p>` explicativo
        - `<a>` como botón de acción (con estilos y hover)


### **4. Tercer bloque: Motivos/Beneficios**

- **Elemento:**
    - `<div class="motivos">`
- **Motivo de uso:**
    - Un div adicional para separar el área de motivos.
    - Su propia clase permite estilos fondos, lista, color y márgenes adaptados.
    - Dentro:
        - `<h3>` para el título de la sección
        - `<ul>` para la lista de beneficios
        - `<li>` para cada elemento (ventaja), sin viñetas gracias al CSS



## **¿Por qué esta división?**

- Cada **división representada en el diseño** tiene su propia agrupación en HTML, usando divs y clases.
- Usar **`section`** para el principal y **`div`** para los bloques internos permite control granular de estilos y jerarquía.
- Cada clase (`comunidad`, `suscripcion`, `motivos`) tiene sentido propio en el CSS y representa una “zona” visualmente distinta.
- El uso de clases en cada elemento interno (`subtitulo`, `precio`, etc.) permite aplicar exactamente el aspecto que ves en el diseño.

***

**En resumen:**
La división en `section` y varios `div` con sus propias `class` responde a la necesidad de separar visualmente y estilísticamente cada bloque del diseño tal y como lo plantea el diseñador; cada clase es un “área” independiente para modificar o adaptar con claridad y rapidez.


## **Explicación del HTML**

El HTML estructura el contenido y otorga nombres de clase para conectar con el estilo CSS:

```html
<section class="contenido">
  <div class="comunidad">
    <h2>Join our community</h2>
    <div class="subtitulo">30-day, hassle-free money back guarantee</div>
    <p>Gain access to our full library of tutorials along with expert code reviews. Perfect for any developers who are serious about honing their skills.</p>
  </div>
  <div class="suscripcion">
    <h3>Monthly Subscription</h3>
    <div class="precio">
      &dollar;29 <span>per month</span>
    </div>
    <p>Full access for less than &dollar;1 a day</p>
    <a href="#">Sign Up</a>
  </div>
  <div class="motivos">
    <h3>Why Us</h3>
    <ul>
      <li>Tutorials by industry experts</li>
      <li>Peer & expert code review</li>
      <li>Coding exercises</li>
      <li>Access to our GitHub repos</li>
      <li>Community forum</li>
      <li>Flashcard decks</li>
      <li>New videos every week</li>
    </ul>
  </div>
</section>
<footer>
  <p class="attribution">
    Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
    Coded by <a href="https://github.com/JonathanBetPer">Jonathan Betancor</a>.
  </p>
</footer>
```


### **Partes clave del HTML**

- **`contenido`**: bloque principal que engloba todo y aplica estilos comunes (tamaño, borde, etc).
- **`comunidad`**: primera sección, color blanco, invita y motiva. Incluye h2 y subtítulo.
- **`suscripcion`**: sección con fondo cian oscuro, precio y botón de suscripción destacado.
- **`motivos`**: lista con fondo cian claro, detalla las ventajas del servicio.
- Clases como `subtitulo`, `precio`, y el footer, organizan y permiten estilos específicos.

***

## **Explicación del CSS**

Tu CSS define los estilos visuales y el comportamiento interactivo. Veamos las claves y cómo afectan el resultado:

### **Paleta de colores y variables CSS**

```css
:root {
  --blanco: hsl(0, 0%, 100%);
  --cyan: hsl(179, 62%, 40%);
  --cyanClaro: hsl(179, 62%, 45%);
  --amarillo: hsl(71, 73%, 54%);
  --amarilloOscuro: hsl(71, 73%, 48%);
  --gris: hsl(204, 43%, 93%);
  --grisOscuro: hsl(218, 22%, 67%);
}
```

- Usas variables para toda la paleta, lo que facilita el mantenimiento y coherencia del diseño.


### **Unidades rem y el font-size**

```css
html {
  box-sizing: border-box;
  font-size: 62.5%; /* 1rem = 10px */
}
```

- Todo el sitio usa rem como unidad base, para tamaño y espaciado flexible y proporcional.


### **Estilos generales**

```css
body {
  font-family: 'Karla', sans-serif;
  line-height: 1.3;
  background-color: var(--gris);
  color: var(--grisOscuro);
  padding: 2rem;
}
```

- Fuente cómoda y moderna, color base de fondo gris claro y texto gris oscuro, buen contraste y legibilidad.


### **La estructura principal**

```css
.contenido {
  border-radius: 1rem;
  overflow: hidden;
  max-width: 40rem;
  margin: auto;
}
```

- El componente principal tiene esquinas redondeadas, límite de anchura para móvil (~400px) y centrado.


### **Sección comunidad**

```css
.comunidad {
  background-color: var(--blanco);
  padding: 2rem;  
}
.comunidad h2 {
  color: var(--cyan);
}
.comunidad .subtitulo {    
  font-size: 1rem;
  color: var(--amarillo);
  font-weight: bold;  
  margin-bottom: 1rem;
}
.comunidad p {
  font-size: 1rem;  
  line-height: 1.75;
  margin-bottom: 0;
}
```

- Fondo blanco, título en cian, subtítulo llamativo en amarillo, buen espaciado y altura de línea óptima para leer.


### **Sección suscripción**

```css
.suscripcion {
  background-color: var(--cyan); 
  padding: 2rem; 
  color: var(--gris);
}
.precio {  
  display: flex;
  align-items: center;
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 0.25rem;
}
.precio span {
  font-size: 1rem;
  margin-left: 1rem;
  font-weight: normal;
  opacity: 0.75;
}
.suscripcion p {
  font-size: 1rem;
  margin-bottom: 2rem;
}
.suscripcion a {
  display: block;
  background-color: var(--amarillo);
  color: var(--blanco);
  padding: 1rem;
  text-align: center;
  border-radius: 0.25rem;
  box-shadow: 0 1rem 1rem rgba(0,0,0,0.15); 
}
.suscripcion a:hover {
  background-color: var(--amarilloOscuro);  
}
```

- Fondo cian, texto claro y botón amarillo muy visible, sombreado, “hover” para que los alumnos vean interacción. El precio es grande, claro, y el periodo (“per month”) queda más discreto.


### **Sección motivos**

```css
.motivos {
  background-color: var(--cyanClaro);
  padding: 2rem;
  color: var(--gris);
}
.motivos ul {
  margin-top: 0;
  padding: 0;
}
.motivos ul li {
  list-style-type: none;
  font-size: 1rem;
  margin-bottom: 0.2rem;
}
```

- Fondo azul cian algo más claro, lista sin viñetas, texto claro y organizado.

***

## **¿Qué aprende el alumno con este proyecto?**

- **Organización profesional:** Usar contenedores semánticos para dividir la información y mantener el código limpio.
- **Variables custom properties:** Cómo definir una paleta mantenible y reutilizable.
- **Maquetación moderna:** Separar cada parte y controlar el diseño usando clases.
- **Flexibilidad:** El uso de rem y variables permite adaptar el diseño fácilmente a otras resoluciones o necesidades.
- **Interactividad y accesibilidad:** Con hover en botones, tamaño y color contrastado.
- **Aspecto visual:** Adaptación a móviles gracias al `max-width`, paddings y tipografía web.
- **Buenas prácticas:** Comentarios claros, fuentes externas, favicon y estructura base bien definida.

***

**En resumen:**
Este proyecto es un ejemplo ideal de cómo aplicar las bases de HTML y CSS modernas: estructura clara, estilos reutilizables con variables, diseño atractivo y responsivo. El resultado es profesional, fácil de mantener y escalable, y los alumnos pueden entender cómo aplicar estas técnicas a cualquier web real.



