<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rodman — Software Engineer</title>
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --navy: #0b1120;
      --navy-mid: #131e30;
      --navy-card: #1a2740;
      --navy-border: rgba(100,140,200,0.13);
      --gold: #c9a84c;
      --gold-light: #e8c76d;
      --gold-dim: rgba(201,168,76,0.12);
      --blue-accent: #4e8fc7;
      --blue-soft: rgba(78,143,199,0.15);
      --text-primary: #eef2f8;
      --text-secondary: #8fa8c8;
      --text-muted: #526070;
      --serif: 'DM Serif Display', Georgia, serif;
      --sans: 'Inter', system-ui, sans-serif;
      --mono: 'DM Mono', monospace;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: var(--sans);
      background: var(--navy);
      color: var(--text-primary);
      min-height: 100vh;
      -webkit-font-smoothing: antialiased;
    }

    /* ──────── LAYOUT ──────── */
    .container {
      max-width: 900px;
      margin: 0 auto;
      padding: 0 2rem;
    }

    /* ──────── HEADER / HERO ──────── */
    header {
      padding: 72px 0 56px;
      border-bottom: 1px solid var(--navy-border);
      position: relative;
      overflow: hidden;
    }

    header::before {
      content: '';
      position: absolute;
      top: -120px; right: -160px;
      width: 480px; height: 480px;
      background: radial-gradient(circle, rgba(201,168,76,0.07) 0%, transparent 70%);
      pointer-events: none;
    }

    .header-tag {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-family: var(--mono);
      font-size: 11px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--gold);
      background: var(--gold-dim);
      border: 1px solid rgba(201,168,76,0.25);
      padding: 5px 12px;
      border-radius: 4px;
      margin-bottom: 24px;
    }
    .header-tag::before { content: '◆'; font-size: 8px; }

    h1 {
      font-family: var(--serif);
      font-size: clamp(2.8rem, 6vw, 4.2rem);
      font-weight: 400;
      line-height: 1.05;
      letter-spacing: -0.01em;
      margin-bottom: 8px;
    }

    h1 em {
      font-style: italic;
      color: var(--gold-light);
    }

    .header-subtitle {
      font-size: 1rem;
      color: var(--text-secondary);
      font-weight: 300;
      margin-bottom: 32px;
      letter-spacing: 0.01em;
    }

    .header-tagline {
      font-family: var(--mono);
      font-size: 12px;
      color: var(--text-muted);
      border-left: 2px solid var(--gold);
      padding-left: 14px;
      line-height: 1.6;
      max-width: 520px;
    }

    .header-contacts {
      display: flex;
      gap: 20px;
      margin-top: 32px;
      flex-wrap: wrap;
    }

    .contact-link {
      display: flex;
      align-items: center;
      gap: 6px;
      font-size: 13px;
      color: var(--text-secondary);
      text-decoration: none;
      border: 1px solid var(--navy-border);
      padding: 7px 14px;
      border-radius: 6px;
      background: var(--navy-card);
      transition: border-color 0.2s, color 0.2s;
    }

    .contact-link:hover { border-color: var(--gold); color: var(--gold-light); }
    .contact-link svg { flex-shrink: 0; }

    /* ──────── SECTION HEADERS ──────── */
    .section {
      padding: 64px 0;
      border-bottom: 1px solid var(--navy-border);
    }

    .section:last-child { border-bottom: none; }

    .section-label {
      font-family: var(--mono);
      font-size: 10px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 10px;
    }

    .section-title {
      font-family: var(--serif);
      font-size: 1.9rem;
      font-weight: 400;
      margin-bottom: 36px;
    }

    /* ──────── STACK GRID ──────── */
    .stack-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 12px;
    }

    .stack-card {
      background: var(--navy-card);
      border: 1px solid var(--navy-border);
      border-radius: 8px;
      padding: 18px 20px;
      transition: border-color 0.2s, transform 0.2s;
    }

    .stack-card:hover {
      border-color: rgba(201,168,76,0.3);
      transform: translateY(-2px);
    }

    .stack-card-label {
      font-family: var(--mono);
      font-size: 10px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-bottom: 10px;
    }

    .stack-card-title {
      font-size: 14px;
      font-weight: 500;
      color: var(--text-primary);
      margin-bottom: 8px;
    }

    .stack-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 5px;
    }

    .tag {
      font-family: var(--mono);
      font-size: 10px;
      background: rgba(78,143,199,0.1);
      border: 1px solid rgba(78,143,199,0.2);
      color: var(--blue-accent);
      padding: 3px 8px;
      border-radius: 4px;
    }

    /* ──────── EXPERIENCE ──────── */
    .exp-block {
      display: grid;
      grid-template-columns: 1fr 3fr;
      gap: 32px;
      align-items: start;
      padding: 28px 0;
      border-bottom: 1px solid var(--navy-border);
    }

    .exp-block:last-child { border-bottom: none; padding-bottom: 0; }

    .exp-meta {
      padding-top: 3px;
    }

    .exp-period {
      font-family: var(--mono);
      font-size: 11px;
      color: var(--gold);
      background: var(--gold-dim);
      display: inline-block;
      padding: 4px 10px;
      border-radius: 4px;
      margin-bottom: 6px;
    }

    .exp-company {
      font-size: 12px;
      color: var(--text-muted);
    }

    .exp-role {
      font-size: 16px;
      font-weight: 500;
      margin-bottom: 10px;
    }

    .exp-desc {
      font-size: 14px;
      color: var(--text-secondary);
      line-height: 1.7;
    }

    .exp-bullets {
      list-style: none;
      margin-top: 10px;
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .exp-bullets li {
      font-size: 13.5px;
      color: var(--text-secondary);
      line-height: 1.6;
      padding-left: 16px;
      position: relative;
    }

    .exp-bullets li::before {
      content: '▸';
      position: absolute;
      left: 0;
      color: var(--gold);
      font-size: 10px;
      top: 3px;
    }

    /* ──────── PROJECTS GRID ──────── */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 16px;
    }

    .project-card {
      background: var(--navy-card);
      border: 1px solid var(--navy-border);
      border-radius: 10px;
      padding: 24px 22px;
      display: flex;
      flex-direction: column;
      gap: 10px;
      transition: border-color 0.2s, transform 0.2s;
      position: relative;
      overflow: hidden;
    }

    .project-card::after {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
      background: linear-gradient(90deg, transparent, var(--gold), transparent);
      opacity: 0;
      transition: opacity 0.3s;
    }

    .project-card:hover {
      border-color: rgba(201,168,76,0.3);
      transform: translateY(-3px);
    }

    .project-card:hover::after { opacity: 1; }

    .project-sector {
      font-family: var(--mono);
      font-size: 10px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--text-muted);
    }

    .project-name {
      font-size: 15px;
      font-weight: 500;
      color: var(--text-primary);
      line-height: 1.3;
    }

    .project-desc {
      font-size: 13px;
      color: var(--text-secondary);
      line-height: 1.6;
      flex: 1;
    }

    .project-badge {
      display: inline-block;
      font-family: var(--mono);
      font-size: 10px;
      padding: 3px 8px;
      border-radius: 4px;
      align-self: flex-start;
    }

    .badge-financial {
      background: rgba(201,168,76,0.12);
      border: 1px solid rgba(201,168,76,0.25);
      color: var(--gold);
    }

    .badge-enterprise {
      background: rgba(78,143,199,0.1);
      border: 1px solid rgba(78,143,199,0.2);
      color: var(--blue-accent);
    }

    /* ──────── GITHUB STATS ──────── */
    .github-block {
      background: var(--navy-card);
      border: 1px solid var(--navy-border);
      border-radius: 10px;
      padding: 28px;
      text-align: center;
    }

    .github-block img {
      max-width: 100%;
      border-radius: 8px;
    }

    /* ──────── FOOTER ──────── */
    footer {
      padding: 40px 0;
      text-align: center;
    }

    footer p {
      font-family: var(--mono);
      font-size: 11px;
      color: var(--text-muted);
      letter-spacing: 0.08em;
    }

    /* ──────── RESPONSIVE ──────── */
    @media (max-width: 620px) {
      .exp-block { grid-template-columns: 1fr; gap: 12px; }
      h1 { font-size: 2.4rem; }
    }
  </style>
</head>
<body>

  <!-- ▌HEADER ▌ -->
  <header>
    <div class="container">
      <div class="header-tag">.NET / Full Stack Engineer</div>
      <h1>Rodman<br><em>García</em></h1>
      <p class="header-subtitle">Software Engineer · Sector Financiero · Ecuador</p>
      <p class="header-tagline">
        "Enfocado en dominar el ecosistema .NET para crear<br>
        software que mueva el mundo financiero."
      </p>
      <div class="header-contacts">
        <a href="mailto:jg38903@gmail.com" class="contact-link">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="2" y="4" width="20" height="16" rx="3"/><path d="M2 7l10 7 10-7"/></svg>
          jg38903@gmail.com
        </a>
        <a href="https://www.linkedin.com/in/rodmansito" target="_blank" class="contact-link">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="2" y="2" width="20" height="20" rx="4"/><path d="M7 10v7M7 7v.5M12 17v-4a2 2 0 0 1 4 0v4M12 10v7"/></svg>
          LinkedIn
        </a>
        <a href="https://github.com/rodman751" target="_blank" class="contact-link">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77a5.07 5.07 0 0 0-.09-3.77S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
          GitHub
        </a>
      </div>
    </div>
  </header>

  <!-- ▌STACK TECNOLÓGICO ▌ -->
  <section class="section">
    <div class="container">
      <p class="section-label">01 — Tecnologías</p>
      <h2 class="section-title">Stack Tecnológico</h2>
      <div class="stack-grid">

        <div class="stack-card">
          <p class="stack-card-label">Backend</p>
          <p class="stack-card-title">Ecosistema .NET</p>
          <div class="stack-tags">
            <span class="tag">.NET Core</span>
            <span class="tag">.NET Framework</span>
            <span class="tag">C#</span>
            <span class="tag">Web APIs</span>
            <span class="tag">MVC</span>
          </div>
        </div>

        <div class="stack-card">
          <p class="stack-card-label">Arquitectura</p>
          <p class="stack-card-title">Diseño de Sistemas</p>
          <div class="stack-tags">
            <span class="tag">Clean Architecture</span>
            <span class="tag">N-Capas</span>
            <span class="tag">REST</span>
          </div>
        </div>

        <div class="stack-card">
          <p class="stack-card-label">Base de Datos</p>
          <p class="stack-card-title">SQL Server</p>
          <div class="stack-tags">
            <span class="tag">T-SQL</span>
            <span class="tag">Optimización</span>
            <span class="tag">Diseño relacional</span>
          </div>
        </div>

        <div class="stack-card">
          <p class="stack-card-label">Infraestructura</p>
          <p class="stack-card-title">Deploy & Servidores</p>
          <div class="stack-tags">
            <span class="tag">IIS</span>
            <span class="tag">Publicación</span>
            <span class="tag">Configuración</span>
          </div>
        </div>

        <div class="stack-card">
          <p class="stack-card-label">Herramientas</p>
          <p class="stack-card-title">Entorno de Desarrollo</p>
          <div class="stack-tags">
            <span class="tag">Visual Studio</span>
            <span class="tag">Git</span>
            <span class="tag">GLPI</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ▌EXPERIENCIA ▌ -->
  <section class="section">
    <div class="container">
      <p class="section-label">02 — Trayectoria</p>
      <h2 class="section-title">Experiencia Profesional</h2>

      <div class="exp-block">
        <div class="exp-meta">
          <div class="exp-period">2024 – Actualidad</div>
          <p class="exp-company">Institución Financiera<br>Ecuador</p>
        </div>
        <div>
          <p class="exp-role">Desarrollador de Software</p>
          <p class="exp-desc">Desarrollo y mantenimiento de sistemas core bancarios y herramientas financieras internas, bajo normativas estrictas de seguridad del sector.</p>
          <ul class="exp-bullets">
            <li>Desarrollo y mantenimiento de módulos del core bancario institucional.</li>
            <li>Implementación de flujos de trabajo bajo normativas de seguridad bancaria.</li>
            <li>Colaboración directa en la optimización de procesos financieros internos.</li>
          </ul>
        </div>
      </div>

    </div>
  </section>

  <!-- ▌PROYECTOS ▌ -->
  <section class="section">
    <div class="container">
      <p class="section-label">03 — Proyectos</p>
      <h2 class="section-title">Proyectos Destacados</h2>
      <div class="projects-grid">

        <div class="project-card">
          <span class="project-badge badge-financial">Financiero · Tesis</span>
          <p class="project-name">Plataforma de Banca Electrónica</p>
          <p class="project-desc">Desarrollo integral de una plataforma transaccional con altos estándares de seguridad, validación y flujo de operaciones bancarias en línea.</p>
        </div>

        <div class="project-card">
          <span class="project-badge badge-financial">Financiero</span>
          <p class="project-name">Módulo de Apertura de Cuentas</p>
          <p class="project-desc">Sistema automatizado para el registro, validación y onboarding de nuevos clientes en entorno de banca regulada.</p>
        </div>

        <div class="project-card">
          <span class="project-badge badge-financial">Financiero · IT</span>
          <p class="project-name">Implantación GLPI</p>
          <p class="project-desc">Configuración y despliegue de sistema de gestión de activos y tickets, optimizando el soporte IT en el entorno bancario.</p>
        </div>

        <div class="project-card">
          <span class="project-badge badge-enterprise">Empresarial · CRM/ERP</span>
          <p class="project-name">CRM Exportadora de Frutas</p>
          <p class="project-desc">Sistema de gran escala para gestión logística de camiones, control de inventarios y coordinación de exportación de productos agrícolas.</p>
        </div>

        <div class="project-card">
          <span class="project-badge badge-enterprise">Empresarial · CRM</span>
          <p class="project-name">CRM Gestión de Gimnasios</p>
          <p class="project-desc">Plataforma multisucursal (3 sedes) para control de membresías, pagos, acceso y administración de usuarios en tiempo real.</p>
        </div>

      </div>
    </div>
  </section>

  <!-- ▌GITHUB STATS ▌ -->
  <section class="section">
    <div class="container">
      <p class="section-label">04 — Actividad</p>
      <h2 class="section-title">GitHub</h2>
      <div class="github-block">
        <img
          src="https://github-readme-stats.vercel.app/api?username=rodman751&show_icons=true&theme=dark&bg_color=1a2740&title_color=c9a84c&text_color=8fa8c8&icon_color=4e8fc7&border_color=1e3050&include_all_commits=true&count_private=true"
          alt="GitHub Stats de Rodman"
        />
      </div>
    </div>
  </section>

  <!-- ▌FOOTER ▌ -->
  <footer>
    <div class="container">
      <p>© 2025 · Rodman García · Software Engineer · .NET / C# · Ecuador</p>
    </div>
  </footer>

</body>
</html>
