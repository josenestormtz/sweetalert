# 🧭 Tutorial: Mostrar mensaje de carga y éxito con SweetAlert2
## 🧩 1. Agregar la librería
Incluye SweetAlert2 en tu proyecto (por CDN o npm):
```html
<script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
```

## ⚙️ 2. Mostrar el mensaje de “procesando”
Cuando inicie tu proceso (por ejemplo, al enviar un formulario), muestra una alerta con **ícono de carga** y evita que el usuario la cierre antes de tiempo:
```js
Swal.fire({
  title: 'Procesando...',
  html: 'Guardando tus datos, por favor espera...',
  allowOutsideClick: false, // evita que se cierre con clic afuera
  didOpen: () => {
    Swal.showLoading(); // muestra el spinner
  }
});
```

## 🚀 3. Ejecutar tu proceso
Ejemplo: una petición con ```fetch``` o un ```setTimeout``` para simular una operación que tarda un poco.
```js
// Simulando un proceso que tarda 3 segundos
setTimeout(() => {
  // Aquí termina tu proceso
  Swal.fire({
    title: '✨ ¡Datos enviados con éxito!',
    text: 'Nos pondremos en contacto contigo muy pronto.',
    icon: 'success',
    confirmButtonText: 'Aceptar',
    confirmButtonColor: '#3085d6'
  });
}, 3000);
```

## 💻 4. Ejemplo completo listo para usar
``` html
<button onclick="enviarDatos()">Enviar datos</button>

<script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
<script>
function enviarDatos() {
  // 1️⃣ Mostrar alerta de carga
  Swal.fire({
    title: 'Procesando...',
    html: 'Guardando tus datos, por favor espera...',
    allowOutsideClick: false,
    didOpen: () => {
      Swal.showLoading();
    }
  });

  // 2️⃣ Simular envío (puedes reemplazar esto con fetch o axios)
  setTimeout(() => {
    // 3️⃣ Mostrar mensaje de éxito al finalizar
    Swal.fire({
      title: '✨ ¡Datos enviados con éxito!',
      text: 'Nos pondremos en contacto contigo muy pronto.',
      icon: 'success',
      confirmButtonText: 'Aceptar',
      confirmButtonColor: '#3085d6'
    });
  }, 3000);
}
</script>
```

## 💡 Consejo adicional
Si usas ```fetch```, reemplaza el ```setTimeout()``` por tu llamada real:
```js
fetch('/api/registrar', {...})
  .then(() => Swal.fire({ title: '¡Éxito!', icon: 'success' }))
  .catch(() => Swal.fire({ title: 'Error', icon: 'error' }));
```
