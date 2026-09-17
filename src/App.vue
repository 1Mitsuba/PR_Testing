<script setup>
const servicios = [
  { icono: '💻', titulo: 'Desarrollo web', descripcion: 'Páginas y aplicaciones web modernas.' },
  { icono: '📱', titulo: 'Aplicaciones móviles', descripcion: 'Apps para Android e iOS.' },
  { icono: '🎮', titulo: 'Videojuegos', descripcion: 'Juegos 2D, 3D y realidad virtual.' },
  { icono: '🔧', titulo: 'Soporte técnico', descripcion: 'Mantenimiento y mejora de sistemas.' },
]
</script>

<template>
  <header class="encabezado">
    <h1>PR_Testing - Wendy</h1>
    <p class="subtitulo">Repositorio oficial de BolivianWorks</p>
  </header>

  <main class="contenido">
    <section class="servicios">
      <h2>Servicios</h2>
      <div class="servicios-lista">
        <article v-for="servicio in servicios" :key="servicio.titulo" class="servicios-tarjeta">
          <span class="servicios-icono">{{ servicio.icono }}</span>
          <h3>{{ servicio.titulo }}</h3>
          <p>{{ servicio.descripcion }}</p>
        </article>
      </div>
    </section>
  </main>
</template>
