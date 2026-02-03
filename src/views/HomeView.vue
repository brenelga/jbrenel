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

const education = ref([
  {
    id: 1,
    period: 'Enero 2025 - Agosto 2026',
    degree: 'Ingeniería en Desarrollo y Gestión de Software',
    school: 'Universidad Tecnológica de la Zona Metropolitana de Guadalajara',
    details: 'Especialización en Desarrollo de Software.'
  },
  {
    id: 2,
    period: 'Enero 2023 - Diciembre 2024',
    degree: 'TSU en Tecnologías de la Información',
    school: 'Universidad Tecnológica de la Zona Metropolitana de Guadalajara',
    details: 'Área de Desarrollo de Software Multiplataforma.',
    cedula: 'Cédula Profesional: 15104776' // Placeholder
  }
]);

const certifications = ref([
  { id: 1, name: 'Data Analyst Associate', issuer: 'DataCamp', icon: '/icons/DA.png' },
  { id: 2, name: 'Google Data Analytics Professional Certificate', issuer: 'Google', icon: '/icons/google.png' },
  { id: 3, name: 'Data Science Fundamentals Level 1', issuer: 'IBM Skills Build', icon: '/icons/DSF.png' },
  { id: 4, name: 'Machine Learning with Python', issuer: 'IBM Skills Build', icon: '/icons/ML.png' },
  { id: 5, name: 'Databases and SQL for Data Science', issuer: 'IBM Skills Build', icon: '/icons/SQL.png' },
  { id: 6, name: 'Data Visualization with Python', issuer: 'IBM Skills Build', icon: '/icons/DV.png' },
  { id: 7, name: 'Hadoop Fundations Level 1', issuer: 'IBM Skills Build', icon: '/icons/Hadoop.png' },
  { id: 8, name: 'DL-00-A01 Digital Awareness', issuer: 'OpenEDG', icon: '/icons/A01.png' }
]);

const socials = ref([
  { id: 1, name: 'LinkedIn', url: 'https://linkedin.com/in/brenelga', icon: 'linkedin' },
  { id: 2, name: 'GitHub', url: 'https://github.com/brenelga', icon: 'github' },
  { id: 3, name: 'Credly', url: 'https://www.credly.com/users/brenelga', icon: 'credly' },
  { id: 4, name: 'Email', url: 'mailto:brenel.galicia@gmail.com', icon: 'email' }
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
          <div v-for="edu in education" :key="edu.id" class="timeline-item">
            <div class="timeline-content">
              <span class="date">{{ edu.period }}</span>
              <h4>{{ edu.degree }}</h4>
              <h5>{{ edu.school }}</h5>
              <p>{{ edu.details }}</p>
              <p v-if="edu.cedula" class="cedula-text">{{ edu.cedula }}</p>
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

    <section id="contact" class="contact section">
      <div class="container">
        <h3 class="section-title"><span>05.</span> Perfiles Profesionales</h3>
        <div class="socials-container">
          <a v-for="social in socials" :key="social.id" :href="social.url" target="_blank" class="social-card">
            <div class="social-icon">
              <!-- Inline SVGs based on social.icon -->
              <svg v-if="social.icon === 'linkedin'" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
              <svg v-if="social.icon === 'github'" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
              <svg v-if="social.icon === 'credly'" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"></path></svg>
              <svg v-if="social.icon === 'email'" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
            </div>
            <span>{{ social.name }}</span>
          </a>
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

/* Cédula */
.cedula-text {
  color: var(--text-accent);
  font-family: monospace;
  font-size: 0.9rem;
  font-weight: 500;
  margin-top: 0.5rem;
  display: inline-block;
  padding: 0.2rem 0.5rem;
  border: 1px dashed var(--text-accent);
  border-radius: 4px;
}

/* Socials */
.socials-container {
  display: flex;
  gap: 2rem;
  flex-wrap: wrap;
  justify-content: start; /* Align left to match flow, or center? Let's go with start or grid */
}

/* Let's actually use grid for consistency */
.socials-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 200px));
  gap: 1.5rem;
}

.social-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  color: var(--text-secondary);
  transition: var(--transition-normal);
  padding: 2rem;
  background-color: var(--bg-secondary);
  border-radius: var(--border-radius);
  text-align: center;
}

.social-card:hover {
  transform: translateY(-5px);
  color: var(--text-accent);
  background-color: var(--bg-tertiary);
}

.social-icon {
  color: var(--text-accent);
}

/* Responsive */
@media (max-width: 768px) {
  .name-text { font-size: 3rem; }
  .role-text { font-size: 2rem; }
  .nav-links { display: none; } /* Hide nav on mobile for simplicity, or add burger later */
  .section-title::after { width: 100%; }
}
</style>
