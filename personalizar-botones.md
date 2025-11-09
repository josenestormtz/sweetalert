# 🧩 1. Incluir la librería
Agrega el CDN de SweetAlert2 en tu página (si no usas npm):
```html
<script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
```

# 🧩 2. Crear una alerta con texto personalizado en el botón
La clave está en la propiedad
```👉 confirmButtonText```
Ejemplo:
```html
<script>
Swal.fire({
  title: '¿Listo para continuar?',
  text: 'Puedes personalizar el texto del botón fácilmente',
  icon: 'question',
  confirmButtonText: '¡Vamos allá!' // 👈 Aquí cambias el texto del botón OK
});
</script>
```

# 🧩 3. Ejemplo con dos botones
También puedes cambiar el texto de **ambos botones** si agregas un botón de cancelar:
```js
Swal.fire({
  title: '¿Deseas guardar los cambios?',
  icon: 'warning',
  showCancelButton: true,
  confirmButtonText: 'Sí, guardar',
  cancelButtonText: 'No, cancelar'
});
```

# 🧩 4. Personaliza aún más el estilo (opcional)
Si quieres cambiar el color del botón:
```js
Swal.fire({
  title: 'Personalización avanzada',
  icon: 'success',
  confirmButtonText: 'Perfecto',
  confirmButtonColor: '#3085d6', // Color del botón OK
  cancelButtonColor: '#d33',     // Color del botón Cancelar
  showCancelButton: true
});
```
