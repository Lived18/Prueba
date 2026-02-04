# Instrucciones para personalizar el Carrusel

## ¿Qué se agregó?

Se añadió un carrusel automático de imágenes debajo del banner en la página de Hamburgueserías. El carrusel:
- Se mueve automáticamente cada 2 segundos
- Tiene botones para mover manualmente (flechas ❮ ❯)
- Se reinicia al llegar al final
- Es responsivo (se adapta a móviles y escritorio)

---

## Cómo personalizar las imágenes

### 1. **Preparar tus imágenes**
   - Guarda tus imágenes en: `imagenes/`
   - Formatos recomendados: `.jpg`, `.png`
   - Tamaño recomendado: 1200x400px (o similar proporción 3:1)

### 2. **Cambiar las imágenes**
   
   Abre: `hamburgueserias/index.html`
   
   Busca esta sección (línea ~31-37):
   ```html
   <!-- CARRUSEL DE IMÁGENES -->
   <div class="carrusel-container">
       <div class="carrusel-wrapper">
           <img class="carrusel-imagen" src="../../imagenes/carrusel-1.jpg" alt="Hamburguesa 1">
           <img class="carrusel-imagen" src="../../imagenes/carrusel-2.jpg" alt="Hamburguesa 2">
           <img class="carrusel-imagen" src="../../imagenes/carrusel-3.jpg" alt="Hamburguesa 3">
           <img class="carrusel-imagen" src="../../imagenes/carrusel-4.jpg" alt="Hamburguesa 4">
       </div>
   ```

### 3. **Reemplazar rutas de imágenes**
   
   Cambia `carrusel-1.jpg`, `carrusel-2.jpg`, etc. por los nombres de tus imágenes:
   
   **Ejemplo:**
   ```html
   <img class="carrusel-imagen" src="../../imagenes/hamburgueseria-apollo.jpg" alt="Apollo Burger">
   <img class="carrusel-imagen" src="../../imagenes/hamburgueseria-bigyola.jpg" alt="Big Yola">
   <img class="carrusel-imagen" src="../../imagenes/hamburgueseria-otro.jpg" alt="Otro local">
   ```

### 4. **Agregar más imágenes**
   
   Si quieres más de 4 imágenes, solo agrega más líneas `<img>`:
   ```html
   <img class="carrusel-imagen" src="../../imagenes/carrusel-5.jpg" alt="Hamburguesa 5">
   <img class="carrusel-imagen" src="../../imagenes/carrusel-6.jpg" alt="Hamburguesa 6">
   ```

---

## Cambiar velocidad del carrusel

Si quieres que se mueva más rápido o más lento:

1. Abre: `hamburgueserias/index.html`
2. Busca (línea ~163):
   ```javascript
   setInterval(() => {
       moverCarrusel(1);
   }, 2000);  // ← Aquí está el tiempo en milisegundos
   ```

3. **Cambia `2000` por:**
   - `1000` = 1 segundo (más rápido)
   - `3000` = 3 segundos (más lento)
   - `5000` = 5 segundos (muy lento)

---

## Personalizar altura/tamaño del carrusel

1. Abre: `css/hamburgueserias.css`
2. Busca (línea ~510):
   ```css
   .carrusel-imagen {
       min-width: 100%;
       height: 400px;  /* ← Cambia este valor */
       object-fit: cover;
       display: block;
   }
   ```

3. Cambia `400px` a la altura que desees (ej: `300px`, `500px`)

---

## Notas

- El carrusel se pausa si haces clic en los botones de flecha
- Para móviles, la altura se reduce automáticamente a 250px
- Las imágenes se ajustan automáticamente (no se distorsionan)

¡Listo! Ahora solo reemplaza las rutas de las imágenes con las tuyas.
