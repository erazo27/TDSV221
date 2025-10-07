<template>
  <div id="app">
    <div class="app-container">
      <header class="header">
        <h1 class="title">Concurso de Canto 2025</h1>
        <p class="subtitle">Inscríbete y demuestra tu talento 🎤</p>
      </header>

      <main style="margin-top:18px; display:grid; gap:18px;">
        <div class="card">
          <FormularioInscripcion />
        </div>
      </main>
    </div>
  </div>
</template>

<script setup>
import FormularioInscripcion from './components/FormularioInscripcion.vue'
</script>

<style>
body {
  margin: 0;
  font-family: 'Inter', system-ui, sans-serif;
}
</style>
