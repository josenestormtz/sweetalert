# 💡 Detectar cuándo el usuario cierra una alerta en SweetAlert2

Descripción:
En este tutorial aprenderás cómo detectar cuándo el usuario cierra una alerta de SweetAlert2, ya sea presionando el botón de confirmación, la tecla ```Esc```, o haciendo clic fuera del modal. Esto es útil para ejecutar acciones posteriores como limpiar formularios, redirigir o mostrar nuevos mensajes.
```js
🧩 Ejemplo básico
Swal.fire({
  title: '⚠️ Validación requerida',
  text: 'Hay campos que necesitan revisión.',
  icon: 'warning',
  confirmButtonText: 'Corregir'
}).then(() => {
  console.log('El usuario cerró la alerta');
  // Aquí puedes ejecutar otra acción
});
```

👉 Se ejecutará el código dentro de ```.then()``` en cuanto el usuario cierre la alerta, sin importar cómo.

## 🧩 Ejemplo con detección del motivo del cierre
```js
Swal.fire({
  title: '¿Deseas guardar los cambios?',
  showCancelButton: true,
  confirmButtonText: 'Sí, guardar',
  cancelButtonText: 'Cancelar',
  icon: 'question'
}).then((result) => {
  if (result.isConfirmed) {
    console.log('Usuario confirmó');
  } else if (result.isDismissed) {
    console.log('Usuario cerró o canceló la alerta');
  }
});
```

👉 Aquí puedes distinguir si el usuario **confirmó** o **cerró** sin aceptar.

## 🧩 Ejemplo detectando la forma exacta del cierre
```js
Swal.fire({
  title: 'Procesando...',
  showConfirmButton: false,
  allowOutsideClick: true,
  didOpen: () => Swal.showLoading()
}).then((result) => {
  if (result.dismiss === Swal.DismissReason.backdrop) {
    console.log('Cerró haciendo clic fuera del alert');
  } else if (result.dismiss === Swal.DismissReason.esc) {
    console.log('Cerró con la tecla Esc');
  } else if (result.dismiss === Swal.DismissReason.close) {
    console.log('Cerró manualmente con el ícono de cerrar');
  }
});
```

👉 Ideal para **controlar cierres no intencionados** o para mostrar una alerta adicional si el usuario interrumpe un proceso.
