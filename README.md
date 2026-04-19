<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Portafolio Académico - Jennifer Rivera Pecho</title>
  <link href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg-dark: #3b1f6b;
      --bg-card: #52309a;
      --bg-card2: #5e38b0;
      --accent: #d8b4fe;
      --accent2: #c084fc;
      --text: #faf5ff;
      --text-muted: #e9d5ff;
      --border: rgba(216,180,254,0.25);
      --nav-h: 64px;
    }
    * { margin:0; padding:0; box-sizing:border-box; }
    html { scroll-behavior: smooth; }
    body {
      font-family: 'DM Sans', sans-serif;
      background: linear-gradient(135deg, #4c2889 0%, #7c3aed 50%, #4c2889 100%);
      background-attachment: fixed;
      color: var(--text);
      min-height: 100vh;
    }

    /* ─── NAV ─── */
    nav {
      position: fixed; top: 0; left: 0; right: 0;
      height: var(--nav-h);
      background: rgba(76,40,137,0.88);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
      display: flex; align-items: center;
      justify-content: space-between;
      padding: 0 2rem;
      z-index: 100;
    }
    .nav-brand { display:flex; align-items:center; gap:.75rem; }
    .nav-avatar {
      width:38px; height:38px; border-radius:50%;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      display:flex; align-items:center; justify-content:center;
      font-family:'Sora',sans-serif; font-weight:700; font-size:.95rem; color:#3b1f6b;
    }
    .nav-name { font-family:'Sora',sans-serif; font-weight:600; font-size:1rem; }
    .nav-links { display:flex; gap:2rem; }
    .nav-links a {
      color: var(--text-muted); text-decoration:none;
      font-size:.9rem; font-weight:500;
      transition: color .2s;
    }
    .nav-links a:hover { color: var(--accent); }

    /* ─── HERO ─── */
    .hero-card {
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 3rem;
      display: flex;
      align-items: center;
      gap: 3rem;
      position: relative;
      overflow: hidden;
    }
    .hero-card::before {
      content:'';
      position:absolute; top:-60px; right:-60px;
      width:300px; height:300px;
      background: radial-gradient(circle, rgba(216,180,254,.2) 0%, transparent 70%);
      pointer-events:none;
    }
    .hero-logo {
      flex-shrink: 0;
      width: 160px; height: 160px;
      background: #fff;
      border-radius: 22px;
      display:flex; align-items:center; justify-content:center;
      box-shadow: 0 8px 32px rgba(0,0,0,.4);
    }
    .hero-logo svg { width:110px; }
    .hero-content { flex:1; }
    .badge {
      display:inline-block;
      background: rgba(216,180,254,.2);
      color: var(--accent);
      border: 1px solid rgba(216,180,254,.4);
      border-radius:999px;
      padding:.3rem .9rem;
      font-size:.78rem;
      font-weight:600;
      letter-spacing:.04em;
      margin-bottom:1rem;
    }
    .hero-title {
      font-family:'Sora',sans-serif;
      font-size:2.6rem;
      font-weight:800;
      line-height:1.15;
      margin-bottom:.9rem;
    }
    .hero-sub {
      color:var(--text-muted);
      font-size:1rem;
      line-height:1.6;
      max-width:520px;
      margin-bottom:1.8rem;
    }
    .hero-btns { display:flex; gap:1rem; flex-wrap:wrap; }
    .btn-primary {
      background: var(--accent);
      color: #3b1f6b;
      border:none; border-radius:10px;
      padding:.72rem 1.6rem;
      font-family:'Sora',sans-serif;
      font-weight:700; font-size:.9rem;
      cursor:pointer; text-decoration:none;
      transition: transform .15s, box-shadow .15s;
    }
    .btn-primary:hover { transform:translateY(-2px); box-shadow:0 6px 20px rgba(216,180,254,.4); }
    .btn-outline {
      background:transparent;
      color:var(--text);
      border:1px solid rgba(255,255,255,.3);
      border-radius:10px;
      padding:.72rem 1.6rem;
      font-family:'Sora',sans-serif;
      font-weight:600; font-size:.9rem;
      cursor:pointer; text-decoration:none;
      transition: border-color .2s, color .2s;
    }
    .btn-outline:hover { border-color:var(--accent); color:var(--accent); }

    /* ─── QUICK CARDS ─── */
    .quick-grid {
      max-width:1100px; margin:0 auto;
      padding: 0 2rem 4rem;
      display:grid;
      grid-template-columns: repeat(4,1fr);
      gap:1.2rem;
    }
    .qcard {
      background:var(--bg-card);
      border:1px solid var(--border);
      border-radius:16px;
      padding:1.5rem;
      cursor:pointer;
      transition: transform .2s, border-color .2s, box-shadow .2s;
      text-decoration:none; color:inherit;
    }
    .qcard:hover { transform:translateY(-4px); border-color:rgba(216,180,254,.6); box-shadow:0 8px 24px rgba(0,0,0,.3); }
    .qcard-icon {
      width:46px; height:46px; border-radius:12px;
      display:flex; align-items:center; justify-content:center;
      font-size:1.4rem; margin-bottom:1rem;
    }
    .ic-tasks { background:rgba(251,191,36,.15); }
    .ic-login { background:rgba(216,180,254,.15); }
    .ic-profile { background:rgba(236,72,153,.15); }
    .ic-git { background:rgba(192,132,252,.15); }
    .qcard h3 { font-family:'Sora',sans-serif; font-weight:700; font-size:1rem; margin-bottom:.4rem; }
    .qcard p { color:var(--text-muted); font-size:.85rem; line-height:1.5; }

    /* ─── SECTION ─── */
    section { max-width:1100px; margin:0 auto; padding:0 2rem 4rem; }
    .section-title {
      font-family:'Sora',sans-serif;
      font-size:1.6rem; font-weight:700;
      margin-bottom:1.5rem;
      display:flex; align-items:center; gap:.75rem;
    }
    .section-title span {
      display:inline-block; width:6px; height:28px;
      background:var(--accent); border-radius:3px;
    }

    /* ─── WEEKS GRID ─── */
    .weeks-grid {
      display:grid;
      grid-template-columns: repeat(auto-fill,minmax(240px,1fr));
      gap:1.2rem;
    }
    .week-card {
      background:var(--bg-card);
      border:1px solid var(--border);
      border-radius:16px;
      padding:1.4rem;
      transition: transform .2s, border-color .2s;
      position:relative; overflow:hidden;
    }
    .week-card:hover { transform:translateY(-3px); border-color:rgba(216,180,254,.5); }
    .week-card::after {
      content:'';
      position:absolute; bottom:0; left:0; right:0; height:3px;
      background:linear-gradient(90deg,var(--accent2),var(--accent));
      transform:scaleX(0); transform-origin:left;
      transition: transform .3s;
    }
    .week-card:hover::after { transform:scaleX(1); }
    .week-num {
      font-family:'Sora',sans-serif;
      font-size:.75rem; font-weight:700; letter-spacing:.1em;
      color:var(--accent); margin-bottom:.5rem; text-transform:uppercase;
    }
    .week-title {
      font-family:'Sora',sans-serif;
      font-size:1rem; font-weight:700; margin-bottom:.5rem;
    }
    .week-desc { color:var(--text-muted); font-size:.84rem; line-height:1.55; margin-bottom:1rem; }
    .week-status {
      display:inline-flex; align-items:center; gap:.4rem;
      font-size:.78rem; font-weight:600; border-radius:999px;
      padding:.25rem .75rem;
    }
    .s-done { background:rgba(134,239,172,.15); color:#86efac; }
    .s-progress { background:rgba(251,191,36,.12); color:#fbbf24; }
    .s-pending { background:rgba(233,213,255,.1); color:var(--text-muted); }

    /* ─── PERFIL ─── */
    .perfil-card {
      background:var(--bg-card);
      border:1px solid var(--border);
      border-radius:20px; padding:2.5rem;
      display:flex; gap:2.5rem; align-items:flex-start;
    }
    .perfil-avatar {
      flex-shrink:0;
      width:100px; height:100px; border-radius:50%;
      background:linear-gradient(135deg,var(--accent),var(--accent2));
      display:flex; align-items:center; justify-content:center;
      font-family:'Sora',sans-serif; font-weight:800; font-size:2.2rem; color:#3b1f6b;
    }
    .perfil-info h2 { font-family:'Sora',sans-serif; font-size:1.5rem; font-weight:800; margin-bottom:.3rem; }
    .perfil-info .career { color:var(--accent); font-weight:600; margin-bottom:.8rem; font-size:.9rem; }
    .perfil-info p { color:var(--text-muted); line-height:1.65; max-width:520px; }
    .perfil-tags { display:flex; flex-wrap:wrap; gap:.6rem; margin-top:1.2rem; }
    .tag {
      background:rgba(255,255,255,.1);
      border:1px solid var(--border);
      border-radius:8px; padding:.3rem .8rem;
      font-size:.8rem; color:var(--text-muted);
    }

    /* ─── GIT SECTION ─── */
    .git-grid { display:grid; grid-template-columns:1fr 1fr; gap:1.5rem; }
    .git-box {
      background:var(--bg-card); border:1px solid var(--border);
      border-radius:16px; padding:1.8rem;
    }
    .git-box h3 { font-family:'Sora',sans-serif; font-size:1.1rem; font-weight:700; margin-bottom:.8rem; }
    .git-box p { color:var(--text-muted); font-size:.88rem; line-height:1.6; }
    .git-box ul { padding-left:1.2rem; color:var(--text-muted); font-size:.88rem; line-height:2; }

    /* ─── LOGIN ─── */
    .login-box {
      background:var(--bg-card); border:1px solid var(--border);
      border-radius:20px; padding:2.5rem;
      max-width:420px;
    }
    .login-box h2 { font-family:'Sora',sans-serif; font-weight:700; font-size:1.3rem; margin-bottom:1.5rem; }
    .form-group { margin-bottom:1.2rem; }
    .form-group label { display:block; font-size:.83rem; color:var(--text-muted); margin-bottom:.4rem; }
    .form-group input {
      width:100%; background:rgba(255,255,255,.1);
      border:1px solid var(--border); border-radius:10px;
      padding:.7rem 1rem; color:var(--text); font-family:inherit; font-size:.9rem;
      transition:border-color .2s; outline:none;
    }
    .form-group input:focus { border-color:var(--accent); }
    .form-submit {
      width:100%; background:var(--accent); color:#3b1f6b;
      border:none; border-radius:10px; padding:.8rem;
      font-family:'Sora',sans-serif; font-weight:700; font-size:.95rem;
      cursor:pointer; transition:opacity .2s;
    }
    .form-submit:hover { opacity:.85; }

    /* ─── FOOTER ─── */
    footer {
      border-top:1px solid var(--border);
      text-align:center; padding:2rem;
      color:var(--text-muted); font-size:.83rem;
      background: rgba(76,40,137,0.6);
    }

    @media(max-width:768px){
      .hero-card { flex-direction:column; gap:2rem; padding:2rem; }
      .hero-title { font-size:1.8rem; }
      .quick-grid { grid-template-columns:1fr 1fr; }
      .git-grid { grid-template-columns:1fr; }
      .perfil-card { flex-direction:column; }
      .nav-name { display:none; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-brand">
    <div class="nav-avatar">J</div>
    <span class="nav-name">Jennifer Rivera Pecho</span>
  </div>
  <div class="nav-links">
    <a href="#inicio">Inicio</a>
    <a href="#tareas">Tareas</a>
    <a href="#perfil">Perfil</a>
    <a href="#git">Git & GitHub</a>
    <a href="#login">Login</a>
  </div>
</nav>

<!-- HERO -->
<div id="inicio" style="margin-top:var(--nav-h); padding-top:2rem;">
  <div style="max-width:1100px;margin:0 auto;padding:2rem 2rem 0;">
    <div class="hero-card">
      <div class="hero-logo">
        <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
          <polygon points="100,10 185,57.5 185,142.5 100,190 15,142.5 15,57.5" fill="#1a56db"/>
          <path d="M80 80 Q80 130 100 130 Q120 130 120 80" stroke="white" stroke-width="10" fill="none" stroke-linecap="round"/>
          <path d="M95 65 Q100 55 105 65 Q115 80 100 90 Q85 80 95 65Z" fill="white"/>
          <text x="100" y="165" text-anchor="middle" fill="white" font-family="Arial Black" font-size="18" font-weight="900">UPLA</text>
        </svg>
      </div>
      <div class="hero-content">
        <div class="badge">Portafolio académico</div>
        <h1 class="hero-title">Mi Portafolio de Trabajos</h1>
        <p class="hero-sub">Bienvenido a mi espacio académico. Aquí encontrarás mis tareas, proyectos y avances realizados durante el curso.</p>
        <div class="hero-btns">
          <a href="#tareas" class="btn-primary">Ver tareas</a>
          <a href="#perfil" class="btn-outline">Mi perfil</a>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- QUICK CARDS -->
<div class="quick-grid" style="margin-top:2rem;">
  <a href="#tareas" class="qcard">
    <div class="qcard-icon ic-tasks">📁</div>
    <h3>Tareas</h3>
    <p>Revisa los trabajos por semana.</p>
  </a>
  <a href="#login" class="qcard">
    <div class="qcard-icon ic-login">🔐</div>
    <h3>Login</h3>
    <p>Acceso para subir o editar archivos.</p>
  </a>
  <a href="#perfil" class="qcard">
    <div class="qcard-icon ic-profile">👤</div>
    <h3>Perfil</h3>
    <p>Información del estudiante.</p>
  </a>
  <a href="#git" class="qcard">
    <div class="qcard-icon ic-git">💻</div>
    <h3>¿Qué es Git y GitHub?</h3>
    <p>Conoce la diferencia entre estas herramientas.</p>
  </a>
</div>

<!-- TAREAS / 8 SEMANAS -->
<section id="tareas">
  <h2 class="section-title"><span></span>Tareas por Semana</h2>
  <div class="weeks-grid">
    <div class="week-card">
      <div class="week-num">Semana 1</div>
      <div class="week-title">Introducción al curso</div>
      <div class="week-desc">Presentación del sílabo, objetivos del curso y configuración del entorno de trabajo.</div>
      <span class="week-status s-done">✓ Completado</span>
    </div>
    <div class="week-card">
      <div class="week-num">Semana 2</div>
      <div class="week-title">Fundamentos de Git</div>
      <div class="week-desc">Comandos básicos: init, add, commit, log. Creación del primer repositorio local.</div>
      <span class="week-status s-done">✓ Completado</span>
    </div>
    <div class="week-card">
      <div class="week-num">Semana 3</div>
      <div class="week-title">GitHub y repositorios remotos</div>
      <div class="week-desc">Creación de cuenta en GitHub, push, pull, clone y gestión de repositorios en la nube.</div>
      <span class="week-status s-done">✓ Completado</span>
    </div>
    <div class="week-card">
      <div class="week-num">Semana 4</div>
      <div class="week-title">Ramas y Merge</div>
      <div class="week-desc">Trabajo con ramas (branch), fusión de cambios (merge) y resolución de conflictos básicos.</div>
      <span class="week-status s-done">✓ Completado</span>
    </div>
    <div class="week-card">
      <div class="week-num">Semana 5</div>
      <div class="week-title">HTML y CSS básico</div>
      <div class="week-desc">Creación de páginas web con HTML5 y estilos con CSS3. Estructura de un portafolio.</div>
      <span class="week-status s-progress">⏳ En progreso</span>
    </div>
    <div class="week-card">
      <div class="week-num">Semana 6</div>
      <div class="week-title">GitHub Pages</div>
      <div class="week-desc">Publicación del portafolio en línea usando GitHub Pages de forma gratuita.</div>
      <span class="week-status s-progress">⏳ En progreso</span>
    </div>
    <div class="week-card">
      <div class="week-num">Semana 7</div>
      <div class="week-title">Colaboración en equipo</div>
      <div class="week-desc">Pull Requests, revisión de código y buenas prácticas de trabajo colaborativo en GitHub.</div>
      <span class="week-status s-pending">○ Pendiente</span>
    </div>
    <div class="week-card">
      <div class="week-num">Semana 8</div>
      <div class="week-title">Proyecto final integrador</div>
      <div class="week-desc">Entrega del portafolio académico completo con todas las semanas documentadas y publicado.</div>
      <span class="week-status s-pending">○ Pendiente</span>
    </div>
  </div>
</section>

<!-- PERFIL -->
<section id="perfil">
  <h2 class="section-title"><span></span>Perfil del Estudiante</h2>
  <div class="perfil-card">
    <div class="perfil-avatar">J</div>
    <div class="perfil-info">
      <h2>Jennifer Rivera Pecho</h2>
      <div class="career">Ingeniería de Sistemas — UPLA</div>
      <p>Estudiante de la Universidad Peruana Los Andes (UPLA), interesada en el desarrollo de software y el uso de herramientas modernas de control de versiones. Este portafolio documenta mi progreso académico a lo largo del curso.</p>
      <div class="perfil-tags">
        <span class="tag">Git</span>
        <span class="tag">GitHub</span>
        <span class="tag">HTML & CSS</span>
        <span class="tag">GitHub Pages</span>
        <span class="tag">Control de versiones</span>
        <span class="tag">UPLA</span>
      </div>
    </div>
  </div>
</section>

<!-- GIT & GITHUB -->
<section id="git">
  <h2 class="section-title"><span></span>¿Qué es Git y GitHub?</h2>
  <div class="git-grid">
    <div class="git-box">
      <h3>🔧 Git</h3>
      <p>Git es un <strong>sistema de control de versiones</strong> distribuido creado por Linus Torvalds en 2005. Permite rastrear cambios en archivos a lo largo del tiempo y colaborar con otros sin perder historial.</p>
      <ul>
        <li>Se usa desde la <strong>terminal (línea de comandos)</strong></li>
        <li>Funciona de forma <strong>local</strong> en tu computadora</li>
        <li>Guarda "snapshots" del proyecto llamados <strong>commits</strong></li>
        <li>Permite crear <strong>ramas (branches)</strong> independientes</li>
      </ul>
    </div>
    <div class="git-box">
      <h3>🐙 GitHub</h3>
      <p>GitHub es una <strong>plataforma en la nube</strong> que aloja repositorios de Git. Permite compartir código, trabajar en equipo y publicar proyectos en internet de forma gratuita.</p>
      <ul>
        <li>Es una <strong>interfaz web</strong> para repositorios Git</li>
        <li>Permite <strong>colaborar</strong> con otras personas globalmente</li>
        <li>Ofrece <strong>GitHub Pages</strong> para publicar sitios web</li>
        <li>Incluye <strong>Issues y Pull Requests</strong> para gestionar proyectos</li>
      </ul>
    </div>
    <div class="git-box" style="grid-column:1/-1;">
      <h3>📌 Diferencia clave</h3>
      <p><strong>Git</strong> es la herramienta (software) que gestiona versiones en tu máquina. <strong>GitHub</strong> es el servicio en línea donde puedes almacenar y compartir esos repositorios. Git puede usarse sin GitHub, pero GitHub necesita Git para funcionar.</p>
    </div>
  </div>
</section>

<!-- LOGIN -->
<section id="login">
  <h2 class="section-title"><span></span>Acceso al Portafolio</h2>
  <div class="login-box">
    <h2>Iniciar sesión</h2>
    <div class="form-group">
      <label>Usuario</label>
      <input type="text" placeholder="jennifer.rivera" />
    </div>
    <div class="form-group">
      <label>Contraseña</label>
      <input type="password" placeholder="••••••••" />
    </div>
    <button class="form-submit">Ingresar</button>
  </div>
</section>

<!-- FOOTER -->
<footer>
  © 2025 Jennifer Rivera Pecho · UPLA · Portafolio Académico
</footer>

</body>
</html>
