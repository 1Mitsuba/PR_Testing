<script setup>
import { ref } from 'vue'

const servicios = [
  { numero: '01', titulo: 'Desarrollo web', descripcion: 'Páginas y aplicaciones web modernas, rápidas y accesibles.' },
  { numero: '02', titulo: 'Aplicaciones móviles', descripcion: 'Experiencias móviles claras para Android e iOS.' },
  { numero: '03', titulo: 'Videojuegos', descripcion: 'Prototipos y juegos 2D con identidad propia.' },
  { numero: '04', titulo: 'Soporte técnico', descripcion: 'Mantenimiento, mejoras y acompañamiento continuo.' },
]

const testimonios = [
  { cita: 'El equipo convirtió una idea compleja en una experiencia sencilla de usar.', nombre: 'Valeria Rojas', rol: 'Emprendedora' },
  { cita: 'La comunicación fue clara durante todo el proyecto y entregaron a tiempo.', nombre: 'Diego Flores', rol: 'Director de producto' },
]

const precios = [
  { nombre: 'Esencial', precio: '$350', detalle: 'Para comenzar', caracteristicas: ['Landing page', 'Diseño responsive', 'Entrega en 7 días'] },
  { nombre: 'Profesional', precio: '$750', detalle: 'Para crecer', caracteristicas: ['Sitio multipágina', 'Integración de formularios', 'Soporte por 30 días'], destacado: true },
  { nombre: 'A medida', precio: 'Consultar', detalle: 'Para proyectos únicos', caracteristicas: ['Aplicación personalizada', 'Plan de trabajo propio', 'Acompañamiento continuo'] },
]

const equipo = [
  { iniciales: 'WR', nombre: 'Wendy Rojas', rol: 'Desarrollo frontend' },
  { iniciales: 'CF', nombre: 'Carolina Flores', rol: 'Diseño de producto' },
  { iniciales: 'TM', nombre: 'Tyler Mendoza', rol: 'Desarrollo backend' },
]

const mensajeEnviado = ref(false)

function enviarMensaje() {
  mensajeEnviado.value = true
}
</script>

<template>
  <header class="encabezado">
    <h1>PR_Testing</h1>
    <p class="subtitulo">Repositorio oficial de BolivianWorks</p>
  </header>

  <main class="contenido">
    <section id="servicios" class="seccion servicios">
      <div class="seccion-encabezado">
        <p class="etiqueta">Lo que hacemos</p>
        <h2>Ideas que toman forma.</h2>
      </div>
      <div class="servicios-lista">
        <article v-for="servicio in servicios" :key="servicio.titulo" class="servicio-tarjeta">
          <span class="servicio-numero">{{ servicio.numero }}</span>
          <h3>{{ servicio.titulo }}</h3>
          <p>{{ servicio.descripcion }}</p>
        </article>
      </div>
    </section>

    <section id="contacto" class="seccion contacto">
      <div class="seccion-encabezado">
        <p class="etiqueta">Hablemos</p>
        <h2>Cuéntanos tu idea.</h2>
      </div>
      <form class="contacto-formulario" @submit.prevent="enviarMensaje">
        <label>
          Nombre
          <input type="text" placeholder="Tu nombre" required />
        </label>
        <label>
          Correo
          <input type="email" placeholder="tu@correo.com" required />
        </label>
        <label class="campo-completo">
          Mensaje
          <textarea placeholder="¿En qué podemos ayudarte?" rows="4" required></textarea>
        </label>
        <button type="submit">Enviar mensaje</button>
        <p v-if="mensajeEnviado" class="formulario-exito">Gracias. Nos pondremos en contacto contigo.</p>
      </form>
    </section>

    <section id="testimonios" class="seccion testimonios">
      <div class="seccion-encabezado">
        <p class="etiqueta">Personas felices</p>
        <h2>Lo dicen quienes ya trabajaron con nosotros.</h2>
      </div>
      <div class="testimonios-lista">
        <blockquote v-for="testimonio in testimonios" :key="testimonio.nombre" class="testimonio">
          <p>“{{ testimonio.cita }}”</p>
          <footer><strong>{{ testimonio.nombre }}</strong><span>{{ testimonio.rol }}</span></footer>
        </blockquote>
      </div>
    </section>

    <section id="precios" class="seccion precios">
      <div class="seccion-encabezado">
        <p class="etiqueta">Planes claros</p>
        <h2>Elige el punto de partida.</h2>
      </div>
      <div class="precios-lista">
        <article v-for="plan in precios" :key="plan.nombre" class="precio-tarjeta" :class="{ destacado: plan.destacado }">
          <span v-if="plan.destacado" class="precio-etiqueta">Más elegido</span>
          <h3>{{ plan.nombre }}</h3>
          <p class="precio">{{ plan.precio }}</p>
          <p>{{ plan.detalle }}</p>
          <ul><li v-for="caracteristica in plan.caracteristicas" :key="caracteristica">{{ caracteristica }}</li></ul>
        </article>
      </div>
    </section>

    <section id="equipo" class="seccion equipo">
      <div class="seccion-encabezado">
        <p class="etiqueta">Las personas detrás</p>
        <h2>Un equipo pequeño, muy involucrado.</h2>
      </div>
      <div class="equipo-lista">
        <article v-for="persona in equipo" :key="persona.nombre" class="persona">
          <span class="persona-iniciales">{{ persona.iniciales }}</span>
          <h3>{{ persona.nombre }}</h3>
          <p>{{ persona.rol }}</p>
        </article>
      </div>
    </section>
  </main>
</template>
