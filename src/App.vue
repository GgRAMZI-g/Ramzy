<template>
  <div id="app">
    <nav class="navbar">
      <div class="nav-container">
        <div class="logo">Ramzy</div>
        <ul class="nav-links">
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </nav>

    <section id="home" class="hero">
      <div class="hero-content">
        <h1>Hi, I'm Ramzy</h1>
        <p class="subtitle">Full Stack Developer & Creative Problem Solver</p>
        <p class="description">Building modern web applications with cutting-edge technologies</p>
        <button class="cta-button" @click="scrollTo('projects')">View My Work</button>
      </div>
      <div class="hero-visual">
        <div class="floating-card">💻</div>
      </div>
    </section>

    <section id="about" class="about">
      <div class="container">
        <h2>About Me</h2>
        <div class="about-content">
          <div class="about-text">
            <p>I'm a passionate developer with expertise in building scalable web applications. I love combining clean code with beautiful design to create exceptional user experiences.</p>
            <div class="skills">
              <h3>Skills</h3>
              <div class="skill-tags">
                <span class="tag">Vue.js</span>
                <span class="tag">React</span>
                <span class="tag">Node.js</span>
                <span class="tag">JavaScript</span>
                <span class="tag">TypeScript</span>
                <span class="tag">CSS3</span>
                <span class="tag">REST APIs</span>
                <span class="tag">Git</span>
              </div>
            </div>
          </div>
          <div class="stats">
            <div class="stat-box">
              <div class="stat-number">50+</div>
              <div class="stat-label">Projects</div>
            </div>
            <div class="stat-box">
              <div class="stat-number">100+</div>
              <div class="stat-label">Happy Clients</div>
            </div>
            <div class="stat-box">
              <div class="stat-number">5+</div>
              <div class="stat-label">Years Experience</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="projects" class="projects">
      <div class="container">
        <h2>Featured Projects</h2>
        <div class="projects-grid">
          <div class="project-card" v-for="project in projects" :key="project.id">
            <div class="project-icon">{{ project.icon }}</div>
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
            <div class="project-tags">
              <span v-for="tech in project.tech" :key="tech" class="tech-tag">{{ tech }}</span>
            </div>
            <a href="#" class="project-link">Learn More →</a>
          </div>
        </div>
      </div>
    </section>

    <section id="contact" class="contact">
      <div class="container">
        <h2>Let's Work Together</h2>
        <p class="contact-subtitle">Have an interesting project? I'd love to hear from you.</p>
        <div class="contact-links">
          <a href="mailto:your-email@example.com" class="contact-button">Email Me</a>
          <a href="https://github.com" target="_blank" class="contact-button secondary">GitHub</a>
          <a href="https://linkedin.com" target="_blank" class="contact-button secondary">LinkedIn</a>
        </div>
      </div>
    </section>

    <footer class="footer">
      <p>&copy; 2026 Ramzy. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          id: 1,
          title: "E-Commerce Platform",
          description: "A full-featured shopping platform with real-time inventory management and payment integration.",
          icon: "🛒",
          tech: ["Vue.js", "Node.js", "MongoDB"]
        },
        {
          id: 2,
          title: "Task Management App",
          description: "Collaborative task management tool with real-time updates and team collaboration features.",
          icon: "✓",
          tech: ["React", "Firebase", "Tailwind"]
        },
        {
          id: 3,
          title: "Analytics Dashboard",
          description: "Interactive data visualization dashboard for tracking business metrics and KPIs.",
          icon: "📊",
          tech: ["Vue.js", "D3.js", "Express"]
        },
        {
          id: 4,
          title: "Social Media App",
          description: "Modern social platform with real-time messaging, notifications, and user interactions.",
          icon: "👥",
          tech: ["React", "WebSocket", "PostgreSQL"]
        },
        {
          id: 5,
          title: "AI Content Generator",
          description: "Smart content generation tool powered by AI for creating blog posts and marketing copy.",
          icon: "✨",
          tech: ["Vue.js", "OpenAI API", "Python"]
        },
        {
          id: 6,
          title: "Weather Dashboard",
          description: "Beautiful weather application with real-time forecasts and interactive maps.",
          icon: "🌤️",
          tech: ["Vue.js", "Weather API", "Mapbox"]
        }
      ]
    }
  },
  methods: {
    scrollTo(section) {
      const element = document.getElementById(section)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
      }
    }
  }
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #333;
  background: #fff;
}

.navbar {
  position: sticky;
  top: 0;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  z-index: 100;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
  color: #42b983;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 2rem;
}

.nav-links a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  transition: color 0.3s;
}

.nav-links a:hover {
  color: #42b983;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.hero {
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  gap: 4rem;
  padding: 6rem 2rem;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  min-height: 600px;
}

.hero-content h1 {
  font-size: 3.5rem;
  margin-bottom: 1rem;
  font-weight: 700;
}

.hero-content .subtitle {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  opacity: 0.95;
}

.hero-content .description {
  font-size: 1.1rem;
  margin-bottom: 2rem;
  opacity: 0.9;
  line-height: 1.6;
}

.cta-button {
  padding: 1rem 2rem;
  font-size: 1rem;
  background: white;
  color: #667eea;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  font-weight: 600;
  transition: transform 0.3s, box-shadow 0.3s;
}

.cta-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.floating-card {
  font-size: 8rem;
  animation: float 3s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
}

.about {
  padding: 6rem 0;
  background: #f8f9fa;
}

.about h2,
.projects h2,
.contact h2 {
  font-size: 2.5rem;
  margin-bottom: 3rem;
  text-align: center;
  color: #333;
}

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
}

.about-text p {
  font-size: 1.1rem;
  line-height: 1.8;
  margin-bottom: 2rem;
  color: #555;
}

.skills h3 {
  font-size: 1.3rem;
  margin-bottom: 1rem;
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tag {
  background: #42b983;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.9rem;
}

.stats {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.stat-box {
  background: white;
  padding: 2rem;
  border-radius: 10px;
  text-align: center;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
}

.stat-number {
  font-size: 2.5rem;
  font-weight: bold;
  color: #42b983;
}

.stat-label {
  font-size: 0.95rem;
  color: #666;
  margin-top: 0.5rem;
}

.projects {
  padding: 6rem 0;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.project-card {
  background: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
  transition: transform 0.3s, box-shadow 0.3s;
}

.project-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
}

.project-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.project-card h3 {
  font-size: 1.3rem;
  margin-bottom: 0.75rem;
  color: #333;
}

.project-card p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  font-size: 0.95rem;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.tech-tag {
  background: #f0f0f0;
  color: #666;
  padding: 0.4rem 0.8rem;
  border-radius: 15px;
  font-size: 0.85rem;
}

.project-link {
  color: #42b983;
  text-decoration: none;
  font-weight: 600;
  transition: color 0.3s;
}

.project-link:hover {
  color: #359268;
}

.contact {
  padding: 6rem 0;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  text-align: center;
}

.contact-subtitle {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  opacity: 0.95;
}

.contact-links {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
}

.contact-button {
  padding: 0.75rem 2rem;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s;
  display: inline-block;
}

.contact-button {
  background: white;
  color: #667eea;
}

.contact-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
}

.contact-button.secondary {
  background: transparent;
  color: white;
  border: 2px solid white;
}

.contact-button.secondary:hover {
  background: white;
  color: #667eea;
}

.footer {
  background: #333;
  color: white;
  text-align: center;
  padding: 2rem;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .hero {
    grid-template-columns: 1fr;
    padding: 3rem 1rem;
    min-height: auto;
  }

  .hero-content h1 {
    font-size: 2rem;
  }

  .hero-content .subtitle {
    font-size: 1.2rem;
  }

  .hero-visual {
    display: none;
  }

  .about-content {
    grid-template-columns: 1fr;
  }

  .nav-links {
    gap: 1rem;
    font-size: 0.9rem;
  }

  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>
