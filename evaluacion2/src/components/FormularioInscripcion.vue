<template>
  <div class="form-root">
    <h2 style="font-size:20px; margin-bottom:12px;">Formulario de Inscripción</h2>

    <form @submit.prevent="enviarFormulario">
      <div class="field">
        <label>Nombre completo</label>
        <input v-model="form.nombre" type="text" placeholder="Ej: Josué Erazo" class="input" />
      </div>

      <div class="field">
        <label>Lugar de procedencia</label>
        <input v-model="form.lugar" type="text" placeholder="Ej: San Salvador" class="input" />
      </div>

      <div class="field">
        <label>Artista a representar</label>
        <input v-model="form.artista" type="text" placeholder="Ej: Luis Miguel" class="input" />
      </div>

      <div class="field">
        <label>Número de teléfono</label>
        <input v-model="form.telefono" type="tel" placeholder="Ej: 7890-1234" class="input" />
      </div>

      <div class="field">
        <label>DUI</label>
        <input v-model="form.dui" type="text" placeholder="Ej: 01234567-8" class="input" />
      </div>

      <div class="field">
        <label>Correo electrónico</label>
        <input v-model="form.correo" type="email" placeholder="ejemplo@correo.com" class="input" />
      </div>

      <div style="display:flex; gap:12px; margin-top:10px;">
        <button type="submit" class="btn-primary">Enviar</button>
        <button type="button" @click="limpiarFormulario" class="btn-ghost">Limpiar</button>
      </div>
    </form>

    <div v-if="enviado" style="margin-top:14px;">
      <div class="success-box">
        <h3 style="margin:0 0 6px 0; font-weight:700;">¡Inscripción enviada con éxito!</h3>
        <pre style="background:transparent; border:none; margin:0; color:rgba(255,255,255,0.85);">{{ JSON.stringify(form, null, 2) }}</pre>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'

const form = reactive({
  nombre: '',
  lugar: '',
  artista: '',
  telefono: '',
  dui: '',
  correo: ''
})

const enviado = ref(false)

function enviarFormulario() {
  if (form.nombre && form.lugar && form.artista && form.telefono && form.dui && form.correo) {
    enviado.value = true
  } else {
    alert('Por favor complete todos los campos antes de enviar.')
  }
}

function limpiarFormulario() {
  Object.keys(form).forEach(key => (form[key] = ''))
  enviado.value = false
}
</script>

<style scoped>
input {
  outline: none;
}
button {
  cursor: pointer;
}
</style>
