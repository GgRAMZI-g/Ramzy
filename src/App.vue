<template>
  <div id="app">
    <nav class="navbar">
      <div class="nav-container">
        <div class="logo">RAMZY</div>
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
        <p class="eyebrow">Full-Stack Developer</p>
        <h1>Ramzy Hassan</h1>
        <p class="subtitle">I build fast, elegant, and performance-driven digital experiences.</p>
        <p class="description">
          I design and develop modern web products, interactive dashboards, and scalable frontend experiences for startups and businesses.
        </p>
        <div class="hero-actions">
          <button class="cta-button" @click="scrollTo('projects')">View Projects</button>
          <a class="secondary-button" href="#contact">Hire Me</a>
        </div>
      </div>
      <div class="hero-visual">
        <div class="profile-card">
          <div class="avatar">RH</div>
          <div class="profile-meta">
            <span class="profile-label">Available for work</span>
            <strong>Frontend • Backend • UI/UX</strong>
          </div>
        </div>
      </div>
    </section>

    <section id="about" class="about">
      <div class="container">
        <h2>About Me</h2>
        <div class="about-content">
          <div class="about-text">
            <p>
              I’m a developer focused on creating polished interfaces and high-performing applications. My work combines clean architecture,
              thoughtful user experience, and product-focused thinking.
            </p>
            <p>
              From trading dashboards and SaaS tools to portfolio sites and internal business apps, I enjoy turning complex ideas into simple,
              useful products that people actually enjoy using.
            </p>
          </div>
          <div class="info-panel">
            <div class="info-box">
              <span class="info-label">Experience</span>
              <strong>5+ Years</strong>
            </div>
            <div class="info-box">
              <span class="info-label">Specialization</span>
              <strong>Web Development</strong>
            </div>
            <div class="info-box">
              <span class="info-label">Location</span>
              <strong>Remote / Global</strong>
            </div>
          </div>
        </div>

        <div class="skills">
          <h3>Core Skills</h3>
          <div class="skill-tags">
            <span class="tag">Vue</span>
            <span class="tag">React</span>
            <span class="tag">Node.js</span>
            <span class="tag">JavaScript</span>
            <span class="tag">TypeScript</span>
            <span class="tag">REST APIs</span>
            <span class="tag">Git</span>
            <span class="tag">UI Design</span>
            <span class="tag">Performance</span>
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
            <a href="#" class="project-link">Case Study →</a>
          </div>
        </div>
      </div>
    </section>

    <section id="contact" class="contact">
      <div class="container">
        <h2>Let’s Build Something Great</h2>
        <p class="contact-subtitle">I’m available for freelance work, product building, and long-term collaborations.</p>
        <div class="contact-links">
          <a href="mailto:ramzy@example.com" class="contact-button">Email Me</a>
          <a href="https://github.com/GgRAMZI-g" target="_blank" class="contact-button secondary">GitHub</a>
          <a href="https://www.linkedin.com" target="_blank" class="contact-button secondary">LinkedIn</a>
        </div>
      </div>
    </section>

    <footer class="footer">
      <p>© 2026 Ramzy Hassan. Built with Vue.js.</p>
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
          title: 'TradePulse Dashboard',
          description: 'A real-time analytics dashboard for tracking market performance, alerts, and portfolio movement in a clean UI.',
          icon: '📈',
          tech: ['Vue', 'Chart.js', 'REST API']
        },
        {
          id: 2,
          title: 'Crypto Portfolio Tracker',
          description: 'A web app for monitoring balances, gains, and historical trends across multiple wallet positions.',
          icon: '₿',
          tech: ['Vue', 'Node.js', 'MongoDB']
        },
        {
          id: 3,
          title: 'SaaS Admin Panel',
          description: 'A scalable internal dashboard for managing users, metrics, subscriptions, and operational workflows.',
          icon: '🧩',
          tech: ['React', 'TypeScript', 'Tailwind']
        },
        {
          id: 4,
          title: 'Launch Landing Page',
          description: 'An optimized startup landing page designed to turn traffic into conversions with strong storytelling and CTAs.',
          icon: '🚀',
          tech: ['Vue', 'CSS', 'Performance']
        },
        {
          id: 5,
          title: 'Market Scanner',
          description: 'A signal dashboard using live data feeds to highlight patterns, opportunities, and market conditions.',
          icon: '🔎',
          tech: ['JavaScript', 'APIs', 'UI Design']
        },
        {
          id: 6,
          title: 'Business Intelligence App',
          description: 'An interactive reporting dashboard that combines multiple data sources into one actionable overview.',
          icon: '📊',
          tech: ['Vue', 'Analytics', 'Automation']
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

html {
  scroll-behavior: smooth;
}

#app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #0f172a;
  background: #f8fafc;
}

.navbar {
  position: sticky;
  top: 0;
  z-index: 50;
  border-bottom: 1px solid rgba(148, 163, 184, 0.2);
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(12px);
}

.nav-container,
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 1rem;
  padding-bottom: 1rem;
}

.logo {
  font-size: 1.4rem;
  font-weight: 800;
  letter-spacing: 0.2rem;
  color: #0f172a;
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
}

.nav-links a {
  text-decoration: none;
  color: #334155;
  font-weight: 600;
}

.hero {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  align-items: center;
  gap: 3rem;
  max-width: 1200px;
  margin: 0 auto;
  padding: 5rem 2rem 4rem;
}

.eyebrow {
  color: #2563eb;
  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 0.18rem;
  text-transform: uppercase;
  margin-bottom: 1rem;
}

.hero-content h1 {
  font-size: clamp(2.8rem, 5vw, 5rem);
  line-height: 1;
  margin-bottom: 1rem;
  color: #0f172a;
}

.subtitle {
  font-size: clamp(1.2rem, 2vw, 2rem);
  color: #334155;
  margin-bottom: 1rem;
}

.description {
  font-size: 1.1rem;
  color: #475569;
  line-height: 1.8;
  max-width: 650px;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  align-items: center;
  margin-top: 2rem;
  flex-wrap: wrap;
}

.cta-button,
.secondary-button,
.contact-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  padding: 0 1.7rem;
  border-radius: 999px;
  font-weight: 700;
  text-decoration: none;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.cta-button {
  border: none;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  color: #fff;
  cursor: pointer;
  box-shadow: 0 14px 30px rgba(79, 70, 229, 0.28);
}

.secondary-button {
  background: #e2e8f0;
  color: #0f172a;
}

.cta-button:hover,
.secondary-button:hover,
.contact-button:hover {
  transform: translateY(-2px);
}

.hero-visual {
  display: flex;
  justify-content: center;
}

.profile-card {
  width: min(100%, 340px);
  background: linear-gradient(135deg, #0f172a, #1e293b);
  border-radius: 24px;
  padding: 2rem;
  color: #fff;
  box-shadow: 0 20px 50px rgba(15, 23, 42, 0.22);
}

.avatar {
  width: 110px;
  height: 110px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  font-weight: 800;
  font-size: 2.2rem;
  background: linear-gradient(135deg, #60a5fa, #a78bfa);
  margin-bottom: 1.5rem;
}

.profile-label {
  display: block;
  color: #cbd5e1;
  margin-bottom: 0.5rem;
  font-size: 0.85rem;
}

.about,
.projects,
.contact {
  padding: 6rem 0;
}

.about {
  background: #fff;
}

.about h2,
.projects h2,
.contact h2 {
  font-size: clamp(2rem, 3vw, 3rem);
  text-align: center;
  margin-bottom: 2.5rem;
}

.about-content {
  display: grid;
  grid-template-columns: 1.4fr 0.9fr;
  gap: 2rem;
  align-items: start;
}

.about-text p {
  font-size: 1.08rem;
  line-height: 1.8;
  color: #475569;
  margin-bottom: 1rem;
}

.info-panel {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.info-box {
  background: linear-gradient(135deg, #eff6ff, #f5f3ff);
  border: 1px solid #dbeafe;
  border-radius: 16px;
  padding: 1.3rem 1rem;
}

.info-label {
  display: block;
  font-size: 0.78rem;
  color: #475569;
  text-transform: uppercase;
  letter-spacing: 0.09rem;
  margin-bottom: 0.35rem;
}

.skills {
  margin-top: 2.5rem;
}

.skills h3 {
  margin-bottom: 1rem;
  font-size: 1.4rem;
}

.skill-tags,
.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.tag,
.tech-tag {
  padding: 0.55rem 0.9rem;
  border-radius: 999px;
  background: #e2e8f0;
  color: #334155;
  font-size: 0.82rem;
  font-weight: 600;
}

.projects {
  background: linear-gradient(180deg, #f8fafc 0%, #eef2ff 100%);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 2rem;
}

.project-card {
  background: #fff;
  border: 1px solid rgba(148, 163, 184, 0.2);
  border-radius: 20px;
  padding: 1.8rem;
  box-shadow: 0 12px 30px rgba(15, 23, 42, 0.06);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 40px rgba(15, 23, 42, 0.09);
}

.project-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.project-card h3 {
  font-size: 1.3rem;
  margin-bottom: 0.7rem;
}

.project-card p {
  color: #475569;
  line-height: 1.7;
  min-height: 110px;
}

.project-link {
  display: inline-block;
  margin-top: 1rem;
  color: #2563eb;
  text-decoration: none;
  font-weight: 700;
}

.contact {
  background: linear-gradient(135deg, #0f172a, #1e293b);
  color: #fff;
}

.contact-subtitle {
  max-width: 700px;
  margin: 0 auto 2rem;
  text-align: center;
  color: #cbd5e1;
  font-size: 1.08rem;
}

.contact-links {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
}

.contact-button {
  background: #fff;
  color: #0f172a;
}

.contact-button.secondary {
  background: transparent;
  border: 1px solid rgba(255, 255, 255, 0.5);
  color: #fff;
}

.footer {
  padding: 1.5rem 0;
  background: #020817;
  color: #cbd5e1;
  text-align: center;
}

@media (max-width: 768px) {
  .nav-container {
    flex-direction: column;
    gap: 1rem;
    padding-top: 1rem;
  }

  .nav-links {
    gap: 1rem;
    flex-wrap: wrap;
    justify-content: center;
  }

  .hero {
    grid-template-columns: 1fr;
    padding-top: 3rem;
  }

  .about-content {
    grid-template-columns: 1fr;
  }

  .contact-links {
    flex-direction: column;
    align-items: center;
  }

  .contact-button {
    width: min(100%, 220px);
  }
}
</style>
