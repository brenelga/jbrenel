<script setup>
import { ref, onMounted } from 'vue';

const activeSection = ref('hero');

const projects = ref([
  {
    id: 1,
    title: 'Sistema de Clasificación de Riesgo Municipal',
    description: 'Este proyecto implementa un modelo de Machine Learning para clasificar el nivel de riesgo por municipio en base al comportamiento histórico de delitos relacionados con vehículos.',
    tech: ['Python', 'Pandas', 'Scikit-learn', 'Random Forest', 'Clustering'],
    link: 'https://github.com/brenelga/Modelo'
  },
  {
    id: 2,
    title: 'Coffee Card',
    description: 'Sistema que combina Web, App móvil y dispositivos IoT con RFID para control y gestión de accesos',
    tech: ['RFID', 'IoT', 'Web', 'App móvil', 'Laravel'],
    link: 'https://github.com/brenelga/CoffeeCardAppWeb'
  },
  {
    id: 3,
    title: 'Encuesta',
    description: 'Plataforma de encuestas para recolectar respuestas, almacenarlas en MongoDB y generar análisis de datos con Python. Desplegada en Railway.',
    tech: ['Python', 'MongoDB', 'Data Analysis', 'Railway'],
    link: 'https://github.com/brenelga/Encuesta'
  }
]);

const certifications = ref([
  { id: 1, name: 'Data Analyst Associate', issuer: 'DataCamp', icon: '/icons/DA.png' },
  { id: 2, name: 'Google Data Analytics Professional Certificate', issuer: 'Google', icon: '/icons/google.png' },
  { id: 3, name: 'Meta Back-End Developer', issuer: 'Meta', icon: 'M' },
  { id: 4, name: 'Python for Everybody', issuer: 'University of Michigan', icon: 'P' }
]);

const scrollTo = (id) => {
  const element = document.getElementById(id);
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' });
  }
};
</script>

<template>
  <div class="home-view">
    <!-- Navigation -->
    <nav class="navbar">
      <div class="container nav-content">
        <div class="logo">JBGA.</div>
        <ul class="nav-links">
          <li><a @click.prevent="scrollTo('about')" href="#about">Sobre Mí</a></li>
          <li><a @click.prevent="scrollTo('education')" href="#education">Educación</a></li>
          <li><a @click.prevent="scrollTo('projects')" href="#projects">Proyectos</a></li>
          <li><a @click.prevent="scrollTo('certifications')" href="#certifications">Certificaciones</a></li>
        </ul>
      </div>
    </nav>

    <!-- Hero Section -->
    <section id="hero" class="hero section">
      <div class="container">
        <h4 class="intro-text">Hola, mi nombre es</h4>
        <h1 class="name-text">J. Brenel Galicia Aguilar.</h1>
        <h2 class="role-text">Transformando datos en soluciones.</h2>
        <p class="summary-text">
          Estudiante de Ingeniería en Software con formación técnica en análisis de datos y desarrollo de soluciones multiplataforma. 
          Apasionado por la tecnología y la mejora continua.
        </p>
        <div class="hero-cta">
          <a @click.prevent="scrollTo('projects')" href="#projects" class="btn">Ver Mis Proyectos</a>
        </div>
      </div>
    </section>

    <!-- About / Skills (integrated for flow) -->
    <section id="about" class="about section">
      <div class="container">
        <h3 class="section-title"><span>01.</span> Sobre Mí</h3>
        <div class="about-content">
          <div class="about-text">
            <p>
              Soy un apasionado de la tecnología con habilidades para transformar datos en conocimiento útil. 
              Tengo experiencia en proyectos complejos que integran hardware y software, siempre con un enfoque analítico y proactivo.
            </p>
            <p>Aquí hay algunas tecnologías con las que he estado trabajando recientemente:</p>
            <ul class="skills-list">
              <li>Python</li>
              <li>SQL & Bases de Datos</li>
              <li>Análisis de Datos</li>
              <li>Desarrollo Multiplataforma</li>
              <li>Hardware & Software Integration</li>
              <li>Vue.js (Learning)</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="education section">
      <div class="container">
        <h3 class="section-title"><span>02.</span> Educación</h3>
        <div class="timeline">
          <div class="timeline-item">
            <div class="timeline-content">
              <span class="date">Enero 2025 - Agosto 2026</span>
              <h4>Ingeniería en Desarrollo y Gestión de Software</h4>
              <h5>Universidad Tecnológica de la Zona Metropolitana de Guadalajara</h5>
              <p>Especialización en Desarrollo de Software.</p>
            </div>
          </div>
          <div class="timeline-item">
            <div class="timeline-content">
              <span class="date">Enero 2023 - Diciembre 2024</span>
              <h4>TSU en Tecnologías de la Información</h4>
              <h5>Universidad Tecnológica de la Zona Metropolitana de Guadalajara</h5>
              <p>Área de Desarrollo de Software Multiplataforma.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects section">
      <div class="container">
        <h3 class="section-title"><span>03.</span> Proyectos Relevantes</h3>
        <div class="projects-grid">
          <div v-for="project in projects" :key="project.id" class="project-card">
            <div class="card-header">
              <div class="folder-icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 19a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h5l2 3h9a2 2 0 0 1 2 2z"></path></svg>
              </div>
              <div class="external-link">
                <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>
              </div>
            </div>
            <h4 class="project-title">{{ project.title }}</h4>
            <div class="project-description">
              <p>{{ project.description }}</p>
            </div>
            <ul class="project-tech-list">
              <li v-for="tech in project.tech" :key="tech">{{ tech }}</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Certifications Section -->
    <section id="certifications" class="certifications section">
      <div class="container">
        <h3 class="section-title"><span>04.</span> Certificaciones</h3>
        <div class="cert-grid">
          <div v-for="cert in certifications" :key="cert.id" class="cert-card">
            <div class="cert-icon">
              <img :src="cert.icon" :alt="cert.name" class="cert-img" />
            </div>
            <div class="cert-info">
              <h4>{{ cert.name }}</h4>
              <p>{{ cert.issuer }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="container">
        <p>Diseñado y Construido por J. Brenel Galicia Aguilar</p>
      </div>
    </footer>
  </div>
</template>

<style scoped>
/* Page Layout */
.home-view {
  width: 100%;
}

/* Navbar */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 1.5rem 0;
  background: rgba(10, 25, 47, 0.85);
  backdrop-filter: blur(10px);
  z-index: 100;
  transition: all 0.3s ease;
  box-shadow: 0 10px 30px -10px rgba(2, 12, 27, 0.7);
}

.nav-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  color: var(--text-accent);
  font-weight: 700;
  font-size: 1.5rem;
  letter-spacing: 1px;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-links a {
  color: var(--text-primary);
  font-size: 0.9rem;
  font-weight: 500;
}

.nav-links a:hover {
  color: var(--text-accent);
}

/* Section Titles */
.section-title {
  display: flex;
  align-items: center;
  font-size: 1.75rem;
  margin-bottom: 2.5rem;
  color: var(--text-primary);
}

.section-title span {
  color: var(--text-accent);
  font-family: inherit; /* Monospace if desired */
  margin-right: 0.5rem;
  font-size: 1.5rem;
}

.section-title::after {
  content: "";
  display: block;
  width: 300px;
  height: 1px;
  background-color: var(--bg-tertiary);
  margin-left: 20px;
}

/* Hero */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding-top: 0; /* Centering vertically */
}

.intro-text {
  color: var(--text-accent);
  font-size: 1.1rem;
  font-weight: 400;
  margin-bottom: 1.5rem;
}

.name-text {
  font-size: 4.5rem;
  color: var(--text-primary);
  margin-bottom: 0.5rem;
}

.role-text {
  font-size: 3.5rem;
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
}

.summary-text {
  max-width: 600px;
  font-size: 1.1rem;
  color: var(--text-secondary);
  margin-bottom: 3rem;
}

/* About & Skills */
.about-text {
  color: var(--text-secondary);
  font-size: 1.1rem;
  max-width: 700px;
}

.skills-list {
  display: grid;
  grid-template-columns: repeat(2, minmax(140px, 200px));
  gap: 0 10px;
  padding: 0;
  margin: 20px 0 0 0;
  overflow: hidden;
  list-style: none;
}

.skills-list li {
  position: relative;
  margin-bottom: 10px;
  padding-left: 20px;
  font-family: var(--font-main);
  font-size: 13px;
  color: var(--text-secondary);
}

.skills-list li::before {
  content: "▹";
  position: absolute;
  left: 0;
  color: var(--text-accent);
}

/* Education (Timeline) */
.timeline {
  border-left: 2px solid var(--bg-tertiary);
  padding-left: 2rem;
}

.timeline-item {
  position: relative;
  margin-bottom: 3rem;
}

.timeline-item::before {
  content: "";
  position: absolute;
  left: -2.6rem;
  top: 5px;
  width: 1rem;
  height: 1rem;
  border-radius: 50%;
  background-color: var(--bg-primary);
  border: 2px solid var(--text-accent);
}

.timeline-content span.date {
  font-family: monospace;
  color: var(--text-accent);
  font-size: 0.9rem;
}

.timeline-content h4 {
  color: var(--text-primary);
  font-size: 1.3rem;
  margin-top: 0.5rem;
}

.timeline-content h5 {
  color: var(--text-secondary);
  font-weight: 500;
}

.timeline-content p {
  color: var(--text-secondary);
  margin-top: 0.5rem;
  font-size: 1rem;
}

/* Projects */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1.5rem;
}

.project-card {
  background-color: var(--bg-secondary);
  padding: 2rem;
  border-radius: var(--border-radius);
  transition: transform 0.2s ease;
  cursor: pointer;
}

.project-card:hover {
  transform: translateY(-5px);
}

.card-header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 1.5rem;
}

.folder-icon {
  color: var(--text-accent);
}

.external-link {
  color: var(--text-secondary);
}

.external-link:hover {
  color: var(--text-accent);
}

.project-title {
  color: var(--text-primary);
  font-size: 1.4rem;
  margin-bottom: 0.75rem;
}

.project-description {
  color: var(--text-secondary);
  font-size: 1rem;
  margin-bottom: 1.5rem;
}

.project-tech-list {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  font-family: monospace;
  font-size: 0.8rem;
  color: var(--text-secondary);
}

/* Certifications */
.cert-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1.5rem;
}

.cert-card {
  background-color: var(--bg-secondary);
  padding: 1.5rem;
  border-radius: var(--border-radius);
  display: flex;
  align-items: center;
  gap: 1rem;
  transition: var(--transition-normal);
}

.cert-card:hover {
  background-color: var(--bg-tertiary);
}

.cert-icon {
  width: 50px;
  height: 50px;
  background-color: var(--bg-primary);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--text-accent);
  font-weight: 700;
  font-size: 1.5rem;
  border: 1px solid var(--bg-tertiary);
}

.cert-info h4 {
  font-size: 1.1rem;
  margin-bottom: 0.2rem;
}

.cert-info p {
  font-size: 0.9rem;
  color: var(--text-secondary);
}

/* Footer */
.footer {
  text-align: center;
  padding: 2rem 0;
  color: var(--text-secondary);
  font-size: 0.9rem;
}

/* Responsive */
@media (max-width: 768px) {
  .name-text { font-size: 3rem; }
  .role-text { font-size: 2rem; }
  .nav-links { display: none; } /* Hide nav on mobile for simplicity, or add burger later */
  .section-title::after { width: 100%; }
}
</style>
