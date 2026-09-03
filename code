<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>StudyBloom</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@500;600;700&family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#FFF9F7;
    --card:#FFFFFF;
    --pink:#F4B6C2;
    --pink-deep:#E893A5;
    --lavender:#D6C7F0;
    --lavender-deep:#B79EEB;
    --mint:#B8E3D8;
    --mint-deep:#8FD3C1;
    --peach:#FFD9B3;
    --peach-deep:#FFC285;
    --text:#4A4453;
    --text-soft:#8A8194;
    --alert:#F4978E;
    --success:#7FD1AE;
    --border:#F0E6E9;
    --shadow: 0 8px 24px rgba(180,140,160,0.12);
    --radius: 20px;
    --radius-sm: 12px;
  }
  html.dark{
    --bg:#241F29;
    --card:#332C3A;
    --text:#F3ECF3;
    --text-soft:#B7ACC2;
    --border:#453B4E;
    --shadow: 0 8px 24px rgba(0,0,0,0.45);
  }
  *{box-sizing:border-box;}
  body{margin:0;}
  html,body{
    background:var(--bg);
    color:var(--text);
    font-family:'Nunito',sans-serif;
    -webkit-font-smoothing:antialiased;
    transition: background-color .3s ease, color .3s ease;
  }
  h1,h2,h3,h4,.display{
    font-family:'Quicksand',sans-serif;
    font-weight:700;
    margin:0;
  }
  button{font-family:inherit;}
  ::selection{background:var(--pink); color:#fff;}

  /* Reduced motion */
  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.001ms !important; transition-duration:0.001ms !important;}
  }

  .app{
    max-width:1080px;
    margin:0 auto;
    padding:0 20px 100px;
    min-height:100vh;
  }

  /* Header */
  header.top{
    display:flex;
    align-items:center;
    justify-space:between;
    padding:28px 0 18px;
  }
  .brand{
    display:flex;
    align-items:center;
    gap:10px;
  }
  .brand-mark{
    width:38px;height:38px;
    border-radius:12px;
    background:linear-gradient(135deg,var(--pink),var(--lavender));
    display:flex;align-items:center;justify-content:center;
    font-size:20px;
    box-shadow: var(--shadow);
  }
  .brand h1{font-size:22px; color:var(--text); letter-spacing:-0.02em;}
  .date-pill{
    font-size:13px;
    color:var(--text-soft);
    background:var(--card);
    padding:8px 14px;
    border-radius:999px;
    border:1px solid var(--border);
  }

  /* Nav */
  nav.tabs{
    display:flex;
    gap:6px;
    background:var(--card);
    padding:6px;
    border-radius:999px;
    border:1px solid var(--border);
    width:fit-content;
    margin-bottom:26px;
    overflow-x:auto;
  }
  nav.tabs button{
    border:none;
    background:transparent;
    padding:10px 18px;
    border-radius:999px;
    font-weight:700;
    font-size:13.5px;
    color:var(--text-soft);
    cursor:pointer;
    white-space:nowrap;
    transition:all .25s ease;
  }
  nav.tabs button.active{
    background:linear-gradient(135deg,var(--pink),var(--lavender));
    color:#fff;
    box-shadow: 0 4px 12px rgba(214,199,240,0.5);
  }
  nav.tabs button:not(.active):hover{
    background:var(--bg);
    color:var(--text);
  }

  .view{display:none; animation: fadeIn .35s ease;}
  .view.active{display:block;}
  @keyframes fadeIn{from{opacity:0; transform:translateY(6px);} to{opacity:1; transform:translateY(0);}}

  /* Cards */
  .card{
    background:var(--card);
    border-radius:var(--radius);
    padding:22px;
    border:1px solid var(--border);
    box-shadow:var(--shadow);
  }
  .grid{
    display:grid;
    grid-template-columns: 1.3fr 1fr;
    gap:18px;
  }
  @media (max-width:760px){ .grid{grid-template-columns:1fr;} }

  .card h3{font-size:16px; margin-bottom:14px; display:flex; align-items:center; gap:8px;}

  /* Progress ring */
  .progress-wrap{display:flex; align-items:center; gap:18px;}
  .ring{position:relative; width:88px; height:88px; flex-shrink:0;}
  .ring svg{transform:rotate(-90deg);}
  .ring-label{
    position:absolute; inset:0; display:flex; flex-direction:column;
    align-items:center; justify-content:center;
  }
  .ring-label b{font-size:20px; font-family:'Quicksand';}
  .ring-label span{font-size:10px; color:var(--text-soft);}

  /* quick access cards */
  .quick-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:12px; margin-top:18px;}
  .quick-card{
    background:var(--card);
    border:1px solid var(--border);
    border-radius:var(--radius-sm);
    padding:16px 12px;
    text-align:center;
    cursor:pointer;
    transition: transform .2s ease, box-shadow .2s ease;
  }
  .quick-card:hover{transform:translateY(-3px); box-shadow:var(--shadow);}
  .quick-card .emoji{font-size:26px; display:block; margin-bottom:6px;}
  .quick-card span{font-size:12.5px; font-weight:700; color:var(--text-soft);}

  /* Task rows */
  .task-row{
    display:flex; align-items:center; gap:12px;
    padding:11px 0;
    border-bottom:1px solid var(--border);
  }
  .task-row:last-child{border-bottom:none;}
  .check{
    width:22px;height:22px;
    border-radius:8px;
    border:2px solid var(--lavender-deep);
    flex-shrink:0;
    cursor:pointer;
    display:flex;align-items:center;justify-content:center;
    transition: all .25s cubic-bezier(.68,-0.4,.27,1.4);
    background:var(--card);
  }
  .check.done{
    background:linear-gradient(135deg,var(--mint),var(--mint-deep));
    border-color:var(--mint-deep);
    transform:scale(1.08) rotate(-6deg);
  }
  .check.done::after{content:"✓"; color:#fff; font-size:13px; font-weight:800;}
  .task-info{flex:1; min-width:0;}
  .task-title{font-size:14.5px; font-weight:700; color:var(--text);}
  .task-title.done{text-decoration:line-through; color:var(--text-soft);}
  .task-meta{font-size:12px; color:var(--text-soft); display:flex; gap:8px; align-items:center; margin-top:2px; flex-wrap:wrap;}
  .tag{
    font-size:10.5px; font-weight:800; padding:2px 8px; border-radius:999px; color:#fff;
  }
  .prio{font-size:11px;}
  .reminder-tag{font-size:11px; color:var(--text-soft); background:var(--bg); padding:1px 6px; border-radius:6px; border:1px solid var(--border);}
  .task-date{font-size:12px; color:var(--text-soft); white-space:nowrap;}
  .task-date.overdue{color:var(--alert); font-weight:800;}
  .empty-state{padding:26px 10px; text-align:center; color:var(--text-soft); font-size:13.5px;}

  /* FAB */
  .fab{
    position:fixed;
    bottom:26px; right:26px;
    width:60px; height:60px;
    border-radius:50%;
    background:linear-gradient(135deg,var(--pink),var(--lavender-deep));
    color:#fff; font-size:28px;
    border:none; cursor:pointer;
    box-shadow: 0 10px 24px rgba(180,140,200,0.45);
    display:flex; align-items:center; justify-content:center;
    transition: transform .2s cubic-bezier(.68,-0.4,.27,1.4);
    z-index:50;
  }
  .fab:hover{transform:scale(1.08) rotate(90deg);}

  /* Calendar */
  .cal-header{display:flex; align-items:center; justify-content:space-between; margin-bottom:14px; flex-wrap:wrap; gap:10px;}
  .cal-nav{display:flex; gap:8px;}
  .cal-nav button{
    background:var(--card); border:1px solid var(--border); border-radius:10px;
    width:32px; height:32px; cursor:pointer; font-size:14px; color:var(--text);
  }
  .cal-grid{display:grid; grid-template-columns:repeat(7,1fr); gap:6px;}
  .cal-dow{font-size:11px; font-weight:800; color:var(--text-soft); text-align:center; padding-bottom:6px;}
  .cal-day{
    aspect-ratio:1; border-radius:12px; border:1px solid var(--border);
    background:var(--card); padding:6px; cursor:pointer; position:relative;
    display:flex; flex-direction:column; transition:all .2s ease;
  }
  .cal-day:hover{border-color:var(--lavender-deep);}
  .cal-day.today{border:2px solid var(--pink-deep);}
  .cal-day.selected{background:var(--lavender); border-color:var(--lavender-deep);}
  .cal-day.selected .num{color:#4A4453;}
  .cal-day.empty{visibility:hidden;}
  .cal-day .num{font-size:12px; font-weight:700;}
  .cal-dots{display:flex; gap:2px; flex-wrap:wrap; margin-top:auto;}
  .cal-dots span{width:6px; height:6px; border-radius:50%; display:inline-block;}

  .day-panel{margin-top:16px;}

  /* View toggle (mes/semana) */
  .view-toggle{display:flex; background:var(--bg); border:1px solid var(--border); border-radius:999px; padding:3px;}
  .view-toggle button{border:none; background:transparent; padding:6px 13px; border-radius:999px; font-size:11.5px; font-weight:800; color:var(--text-soft); cursor:pointer;}
  .view-toggle button.active{background:var(--card); color:var(--text); box-shadow:0 2px 6px rgba(0,0,0,0.1);}

  /* Week view */
  .week-day{background:var(--card); border:1px solid var(--border); border-radius:var(--radius-sm); padding:14px; margin-bottom:10px;}
  .week-day.today{border:2px solid var(--pink-deep);}
  .week-day-head{display:flex; justify-content:space-between; align-items:center; margin-bottom:4px;}
  .wd-name{font-weight:800; font-size:13px; color:var(--text); text-transform:capitalize;}
  .wd-num{font-size:11.5px; color:var(--text-soft); font-weight:700;}

  /* Stats */
  .stat-row{margin-bottom:18px;}
  .stat-row:last-child{margin-bottom:0;}
  .stat-head{display:flex; justify-content:space-between; align-items:center; font-size:13px; font-weight:700; margin-bottom:7px;}
  .stat-name{display:flex; align-items:center; gap:8px;}
  .stat-dot{width:10px; height:10px; border-radius:50%; display:inline-block; flex-shrink:0;}
  .stat-count{color:var(--text-soft); font-weight:800; font-size:12px;}
  .stat-bar-bg{height:10px; border-radius:999px; background:var(--bg); overflow:hidden;}
  .stat-bar-fg{height:100%; border-radius:999px; transition:width .5s ease;}

  .theme-toggle{
    background:var(--card); border:1px solid var(--border); border-radius:50%;
    width:38px; height:38px; cursor:pointer; font-size:15px;
    display:flex; align-items:center; justify-content:center;
    transition: transform .2s ease;
  }
  .theme-toggle:hover{transform:rotate(20deg);}

  /* Subjects */
  .subject-grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(190px,1fr)); gap:14px;}
  .subject-card{
    border-radius:var(--radius-sm);
    padding:18px;
    cursor:pointer;
    color:#fff;
    position:relative;
    overflow:hidden;
    min-height:110px;
    display:flex; flex-direction:column; justify-content:space-between;
    transition:transform .2s ease;
  }
  .subject-card:hover{transform:translateY(-4px);}
  .subject-card h4{font-size:16px; color:#fff;}
  .subject-card .count{font-size:12px; opacity:.9; font-weight:700;}
  .add-subject-card{
    border-radius:var(--radius-sm);
    border:2px dashed var(--border);
    min-height:110px;
    display:flex; align-items:center; justify-content:center;
    flex-direction:column; gap:6px;
    cursor:pointer; color:var(--text-soft); font-weight:700; font-size:13px;
    background:transparent;
  }
  .add-subject-card:hover{border-color:var(--lavender-deep); color:var(--lavender-deep);}

  /* Subject detail */
  .back-btn{
    background:none; border:none; color:var(--text-soft); font-weight:700;
    cursor:pointer; font-size:13px; margin-bottom:14px; display:flex; align-items:center; gap:4px;
  }
  .subject-title-bar{display:flex; align-items:center; gap:12px; margin-bottom:18px;}
  .subject-dot{width:16px; height:16px; border-radius:50%;}
  .subtabs{display:flex; gap:6px; margin-bottom:16px;}
  .subtabs button{
    border:1px solid var(--border); background:#fff; padding:8px 16px; border-radius:999px;
    font-weight:700; font-size:12.5px; color:var(--text-soft); cursor:pointer;
  }
  .subtabs button.active{background:var(--text); color:#fff; border-color:var(--text);}

  .note-card{
    background:#fff; border:1px solid var(--border); border-radius:var(--radius-sm);
    padding:16px; margin-bottom:10px;
  }
  .note-date{font-size:11px; color:var(--text-soft); font-weight:700; margin-bottom:6px;}
  .note-body{font-size:13.5px; white-space:pre-wrap; line-height:1.5;}

  textarea, input[type=text], input[type=number], select, input[type=date]{
    width:100%;
    font-family:'Nunito',sans-serif;
    font-size:14px;
    padding:11px 13px;
    border-radius:12px;
    border:1.5px solid var(--border);
    background:var(--card);
    color:var(--text);
    outline:none;
    transition:border-color .2s ease;
  }
  textarea:focus, input:focus, select:focus{border-color:var(--lavender-deep);}
  textarea{resize:vertical; min-height:90px;}
  label{font-size:12px; font-weight:800; color:var(--text-soft); display:block; margin:14px 0 6px;}
  label:first-of-type{margin-top:0;}

  .btn{
    border:none; border-radius:999px; padding:11px 20px; font-weight:800; font-size:13.5px;
    cursor:pointer; transition:transform .15s ease;
  }
  .btn:hover{transform:translateY(-1px);}
  .btn-primary{background:linear-gradient(135deg,var(--pink),var(--lavender-deep)); color:#fff;}
  .btn-ghost{background:var(--bg); color:var(--text-soft);}
  .btn-danger{background:var(--alert); color:#fff;}
  .chip-row{display:flex; gap:8px;}
  .chip{
    flex:1; text-align:center; padding:9px 0; border-radius:10px; border:1.5px solid var(--border);
    font-size:12.5px; font-weight:800; cursor:pointer; color:var(--text-soft);
  }
  .chip.active-alta{background:var(--alert); color:#fff; border-color:var(--alert);}
  .chip.active-media{background:var(--peach); color:#fff; border-color:var(--peach-deep);}
  .chip.active-baja{background:var(--mint); color:#fff; border-color:var(--mint-deep);}

  /* Modal */
  .overlay{
    position:fixed; inset:0; background:rgba(74,68,83,0.35);
    display:none; align-items:flex-end; justify-content:center; z-index:100;
    backdrop-filter: blur(2px);
  }
  .overlay.open{display:flex; animation:fadeIn .2s ease;}
  .modal{
    background:var(--card); width:100%; max-width:480px; border-radius:24px 24px 0 0;
    padding:26px 22px 30px; max-height:88vh; overflow-y:auto;
    animation:slideUp .3s cubic-bezier(.2,.8,.2,1);
  }
  @media (min-width:600px){
    .overlay{align-items:center;}
    .modal{border-radius:24px; margin:20px;}
  }
  @keyframes slideUp{from{transform:translateY(40px); opacity:0;} to{transform:translateY(0); opacity:1;}}
  .modal-head{display:flex; justify-content:space-between; align-items:center; margin-bottom:6px;}
  .modal-head h3{font-size:18px;}
  .modal-close{background:none; border:none; font-size:20px; color:var(--text-soft); cursor:pointer;}
  .modal-actions{display:flex; gap:10px; margin-top:20px;}
  .modal-actions .btn{flex:1;}

  .swatches{display:flex; gap:9px; margin-top:6px; flex-wrap:wrap; max-width:280px;}
  .swatch{width:28px; height:28px; border-radius:50%; cursor:pointer; border:3px solid transparent;}
  .swatch.selected{border-color:var(--text);}

  /* Filters bar */
  .filters{display:flex; gap:8px; margin-bottom:16px; flex-wrap:wrap;}
  .filters select{width:auto; padding:8px 12px; font-size:12.5px; font-weight:700;}

  .toast{
    position:fixed; bottom:100px; left:50%; transform:translateX(-50%);
    background:#4A4453; color:#fff; padding:10px 18px; border-radius:999px;
    font-size:13px; font-weight:700; opacity:0; pointer-events:none;
    transition:opacity .3s ease, transform .3s ease; z-index:200;
  }
  .toast.show{opacity:1; transform:translateX(-50%) translateY(-8px);}

  .settings-row{
    display:flex; align-items:center; justify-content:space-between;
    padding:14px 0; border-bottom:1px solid var(--border);
  }
  .settings-row:last-child{border:none;}
  .switch{
    width:44px; height:26px; border-radius:999px; background:var(--border);
    position:relative; cursor:pointer; transition:background .2s ease; flex-shrink:0;
  }
  .switch.on{background:linear-gradient(135deg,var(--pink),var(--lavender-deep));}
  .switch::after{
    content:""; position:absolute; top:3px; left:3px; width:20px; height:20px; border-radius:50%;
    background:#fff; transition:transform .2s ease; box-shadow:0 1px 3px rgba(0,0,0,0.2);
  }
  .switch.on::after{transform:translateX(18px);}
</style>
</head>
<body>

<div class="app">
  <header class="top">
    <div class="brand">
      <div class="brand-mark">🌸</div>
      <h1>StudyBloom</h1>
    </div>
    <div style="display:flex; align-items:center; gap:10px;">
      <div class="date-pill" id="todayPill"></div>
      <button class="theme-toggle" id="themeToggle" title="Cambiar tema" aria-label="Cambiar entre modo claro y oscuro">🌙</button>
    </div>
  </header>

  <nav class="tabs" id="mainTabs">
    <button data-view="dashboard" class="active">Dashboard</button>
    <button data-view="calendar">Calendario</button>
    <button data-view="subjects">Materias</button>
    <button data-view="tasks">Tareas</button>
    <button data-view="stats">Estadísticas</button>
    <button data-view="settings">Ajustes</button>
  </nav>

  <!-- DASHBOARD -->
  <section class="view active" id="view-dashboard">
    <div class="grid">
      <div class="card">
        <h3>📌 Próximas entregas</h3>
        <div id="upcomingList"></div>
      </div>
      <div class="card">
        <h3>🌱 Progreso semanal</h3>
        <div class="progress-wrap">
          <div class="ring">
            <svg width="88" height="88">
              <circle cx="44" cy="44" r="38" stroke="#F0E6E9" stroke-width="9" fill="none"/>
              <circle id="ringFg" cx="44" cy="44" r="38" stroke="url(#g1)" stroke-width="9" fill="none" stroke-linecap="round"/>
              <defs>
                <linearGradient id="g1" x1="0%" y1="0%" x2="100%" y2="100%">
                  <stop offset="0%" stop-color="#F4B6C2"/>
                  <stop offset="100%" stop-color="#B79EEB"/>
                </linearGradient>
              </defs>
            </svg>
            <div class="ring-label"><b id="ringPct">0%</b><span id="ringSub">0/0</span></div>
          </div>
          <div>
            <div style="font-size:13px; color:var(--text-soft); line-height:1.5;" id="progressText">
              Aún no tienes tareas registradas esta semana.
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="quick-grid">
      <div class="quick-card" data-goto="calendar"><span class="emoji">🗓️</span><span>Calendario</span></div>
      <div class="quick-card" data-goto="subjects"><span class="emoji">📚</span><span>Materias</span></div>
      <div class="quick-card" data-goto="tasks"><span class="emoji">✅</span><span>Tareas</span></div>
    </div>
  </section>

  <!-- CALENDAR -->
  <section class="view" id="view-calendar">
    <div class="card">
      <div class="cal-header">
        <h3 id="calMonthLabel" style="margin:0;"></h3>
        <div style="display:flex; align-items:center; gap:10px; flex-wrap:wrap;">
          <div class="view-toggle" id="calViewToggle">
            <button data-mode="month" class="active">Mes</button>
            <button data-mode="week">Semana</button>
          </div>
          <div class="cal-nav">
            <button id="calPrev">‹</button>
            <button id="calNext">›</button>
          </div>
        </div>
      </div>
      <div class="cal-grid" id="calGrid"></div>
      <div id="calWeekView" style="display:none;"></div>
    </div>
    <div class="card day-panel" id="dayPanel" style="display:none;">
      <h3 id="dayPanelTitle"></h3>
      <div id="dayPanelList"></div>
    </div>
  </section>

  <!-- SUBJECTS LIST -->
  <section class="view" id="view-subjects">
    <div class="subject-grid" id="subjectGrid"></div>
  </section>

  <!-- SUBJECT DETAIL -->
  <section class="view" id="view-subject-detail">
    <button class="back-btn" id="backToSubjects">← Materias</button>
    <div class="subject-title-bar">
      <div class="subject-dot" id="detailDot"></div>
      <h2 id="detailTitle"></h2>
    </div>
    <div class="subtabs">
      <button data-sub="tasks" class="active">Tareas</button>
      <button data-sub="journal">Journal</button>
    </div>
    <div id="detailTasksView">
      <div class="card"><div id="detailTaskList"></div></div>
    </div>
    <div id="detailJournalView" style="display:none;">
      <div class="card">
        <label>Nueva nota</label>
        <textarea id="newNoteText" placeholder="Escribe lo que quieras recordar de esta materia..."></textarea>
        <div style="margin-top:10px; text-align:right;">
          <button class="btn btn-primary" id="saveNoteBtn">Guardar nota</button>
        </div>
      </div>
      <div id="notesList" style="margin-top:14px;"></div>
    </div>
  </section>

  <!-- TASKS GLOBAL -->
  <section class="view" id="view-tasks">
    <div class="filters">
      <select id="filterSubject"><option value="">Todas las materias</option></select>
      <select id="filterStatus">
        <option value="">Todos los estados</option>
        <option value="pending">Pendientes</option>
        <option value="done">Completadas</option>
      </select>
      <select id="filterSort">
        <option value="date">Ordenar por fecha</option>
        <option value="priority">Ordenar por prioridad</option>
      </select>
    </div>
    <div class="card"><div id="globalTaskList"></div></div>
  </section>

  <!-- STATS -->
  <section class="view" id="view-stats">
    <div class="card">
      <div class="cal-header">
        <h3>📊 <span id="statsMonthLabel"></span></h3>
        <div class="cal-nav">
          <button id="statsPrev">‹</button>
          <button id="statsNext">›</button>
        </div>
      </div>
      <div id="statsList" style="margin-top:6px;"></div>
    </div>
  </section>

  <!-- SETTINGS -->
  <section class="view" id="view-settings">
    <div class="card">
      <h3>🎨 Materias</h3>
      <div id="settingsSubjectList"></div>
    </div>
    <div class="card" style="margin-top:16px;">
      <h3>🌙 Apariencia</h3>
      <div class="settings-row">
        <div>
          <div style="font-weight:700; font-size:13.5px;">Modo oscuro</div>
          <div style="font-size:12px; color:var(--text-soft);">Mantiene la paleta pastel sobre fondo oscuro</div>
        </div>
        <div class="switch" id="darkSwitch" data-key="darkMode"></div>
      </div>
    </div>
    <div class="card" style="margin-top:16px;">
      <h3>🔔 Recordatorios Generales</h3>
      <div class="settings-row">
        <div>
          <div style="font-weight:700; font-size:13.5px;">Recordatorio 3 días antes</div>
          <div style="font-size:12px; color:var(--text-soft);">Avisa con anticipación por defecto</div>
        </div>
        <div class="switch" id="notif3" data-key="notif3days"></div>
      </div>
      <div class="settings-row">
        <div>
          <div style="font-weight:700; font-size:13.5px;">Recordatorio 1 día antes</div>
          <div style="font-size:12px; color:var(--text-soft);">Último aviso por defecto</div>
        </div>
        <div class="switch" id="notif1" data-key="notif1day"></div>
      </div>
    </div>
  </section>
</div>

<button class="fab" id="fabAdd">+</button>

<!-- MODAL: Add Task -->
<div class="overlay" id="taskOverlay">
  <div class="modal">
    <div class="modal-head">
      <h3>Nueva tarea</h3>
      <button class="modal-close" data-close="taskOverlay">✕</button>
    </div>
    <label>Título</label>
    <input type="text" id="taskTitle" placeholder="Ej. Ensayo de historia">
    <label>Materia</label>
    <select id="taskSubject"></select>
    <label>Fecha de entrega</label>
    <input type="date" id="taskDate">
    <label>Prioridad</label>
    <div class="chip-row" id="prioChips">
      <div class="chip" data-prio="alta">Alta</div>
      <div class="chip" data-prio="media">Media</div>
      <div class="chip" data-prio="baja">Baja</div>
    </div>
    <label>Recordatorio</label>
    <select id="taskReminder">
      <option value="none">Sin recordatorio</option>
      <option value="1">1 día antes</option>
      <option value="3">3 días antes</option>
      <option value="7">1 semana antes</option>
      <option value="custom">Personalizado…</option>
    </select>
    <div id="customReminderWrap" style="display:none;">
      <label>Fecha de aviso personalizada</label>
      <input type="date" id="taskReminderCustomDate">
    </div>
    <div class="modal-actions">
      <button class="btn btn-ghost" data-close="taskOverlay">Cancelar</button>
      <button class="btn btn-primary" id="saveTaskBtn">Guardar</button>
    </div>
  </div>
</div>

<!-- MODAL: Add Subject -->
<div class="overlay" id="subjectOverlay">
  <div class="modal">
    <div class="modal-head">
      <h3>Nueva materia</h3>
      <button class="modal-close" data-close="subjectOverlay">✕</button>
    </div>
    <label>Nombre</label>
    <input type="text" id="subjectName" placeholder="Ej. Cálculo II">
    <label>Color</label>
    <div class="swatches" id="colorSwatches"></div>
    <div class="modal-actions">
      <button class="btn btn-ghost" data-close="subjectOverlay">Cancelar</button>
      <button class="btn btn-primary" id="saveSubjectBtn">Crear materia</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
(function(){
  const COLORS = [
    "#F4B6C2","#D6C7F0","#B8E3D8","#FFD9B3","#F4978E","#9CC7F0",
    "#C9E4A5","#FFE29A","#E3B8E8","#A8DADC","#F7C6D9","#B8C4F0",
    "#FFB4A2","#C6E2E9","#E8D5B7","#D4A5A5"
  ];
  const DOW = ["D","L","M","M","J","V","S"];
  const DOW_FULL = ["Domingo","Lunes","Martes","Miércoles","Jueves","Viernes","Sábado"];
  const MONTHS = ["Enero","Febrero","Marzo","Abril","Mayo","Junio","Julio","Agosto","Septiembre","Octubre","Noviembre","Diciembre"];

  let state = {
    subjects: [],   
    tasks: [],      
    notes: [],      
    settings: { notif3days:true, notif1day:true, darkMode:false }
  };

  let currentSubjectId = null;
  let calDate = new Date();
  let selectedDay = null;
  let calViewMode = 'month';
  let statsDate = new Date();

  const $ = (sel, root=document) => root.querySelector(sel);
  const $$ = (sel, root=document) => Array.from(root.querySelectorAll(sel));
  const uid = () => Math.random().toString(36).slice(2,10);
  const todayStr = () => new Date().toISOString().slice(0,10);

  function showToast(msg){
    const t = $('#toast');
    t.textContent = msg;
    t.classList.add('show');
    setTimeout(()=>t.classList.remove('show'), 1800);
  }

  function applyTheme(){
    document.documentElement.classList.toggle('dark', !!state.settings.darkMode);
    $('#themeToggle').textContent = state.settings.darkMode ? '☀️' : '🌙';
  }
  $('#themeToggle').addEventListener('click', async ()=>{
    state.settings.darkMode = !state.settings.darkMode;
    applyTheme();
    await saveState();
    if($('#view-settings').classList.contains('active')) renderSettings();
  });

  // ---------- STORAGE ----------
  async function loadState(){
    try{
      if (window.storage && window.storage.get) {
        const r = await window.storage.get('studybloom-data');
        if(r && r.value){
          const parsed = JSON.parse(r.value);
          state = Object.assign(state, parsed);
        }
      } else {
        const localData = localStorage.getItem('studybloom-data');
        if(localData) state = Object.assign(state, JSON.parse(localData));
      }
    }catch(e){ /* no data yet */ }
    if(state.subjects.length === 0){
      state.subjects = [
        {id:uid(), name:"Matemáticas", color:COLORS[0]},
        {id:uid(), name:"Historia", color:COLORS[1]},
      ];
      await saveState();
    }
    if(state.settings.darkMode === undefined) state.settings.darkMode = false;
    applyTheme();
    renderAll();
  }

  let saveTimer=null;
  async function saveState(){
    try{
      if (window.storage && window.storage.set) {
        await window.storage.set('studybloom-data', JSON.stringify(state));
      } else {
        localStorage.setItem('studybloom-data', JSON.stringify(state));
      }
    }catch(e){
      console.error('Error al guardar', e);
      showToast('No se pudo guardar 😢');
    }
  }
  function saveDebounced(){
    clearTimeout(saveTimer);
    saveTimer = setTimeout(saveState, 250);
  }

  // ---------- NAV ----------
  function goto(view){
    $$('.view').forEach(v=>v.classList.remove('active'));
    $('#view-'+view).classList.add('active');
    $$('#mainTabs button').forEach(b=>b.classList.toggle('active', b.dataset.view===view));
    if(view==='dashboard') renderDashboard();
    if(view==='calendar') renderCalendar();
    if(view==='subjects') renderSubjects();
    if(view==='tasks') renderGlobalTasks();
    if(view==='stats') renderStats();
    if(view==='settings') renderSettings();
  }
  $('#mainTabs').addEventListener('click', e=>{
    const btn = e.target.closest('button');
    if(!btn) return;
    goto(btn.dataset.view);
  });
  $$('.quick-card').forEach(c=>c.addEventListener('click', ()=>goto(c.dataset.goto)));

  // ---------- DASHBOARD ----------
  function subjectById(id){ return state.subjects.find(s=>s.id===id); }

  function renderDashboard(){
    $('#todayPill').textContent = new Date().toLocaleDateString('es-ES',{weekday:'long', day:'numeric', month:'long'});

    const upcoming = state.tasks
      .filter(t=>!t.done)
      .sort((a,b)=> a.date.localeCompare(b.date))
      .slice(0,5);

    const list = $('#upcomingList');
    list.innerHTML = '';
    if(upcoming.length===0){
      list.innerHTML = `<div class="empty-state">✨ No tienes entregas pendientes. ¡Buen momento para adelantar algo!</div>`;
    } else {
      upcoming.forEach(t=> list.appendChild(taskRow(t)));
    }

    const weekTasks = state.tasks.filter(t=> isThisWeek(t.date));
    const done = weekTasks.filter(t=>t.done).length;
    const total = weekTasks.length;
    const pct = total? Math.round(done/total*100) : 0;
    const circumference = 2*Math.PI*38;
    $('#ringFg').setAttribute('stroke-dasharray', circumference);
    $('#ringFg').setAttribute('stroke-dashoffset', circumference - (pct/100)*circumference);
    $('#ringPct').textContent = pct+'%';
    $('#ringSub').textContent = done+'/'+total;
    $('#progressText').textContent = total
      ? `Llevas ${done} de ${total} tareas completadas esta semana. ¡Sigue así! 🌷`
      : 'Aún no tienes tareas registradas esta semana.';
  }

  function isThisWeek(dateStr){
    const d = new Date(dateStr+'T00:00:00');
    const now = new Date();
    const start = new Date(now); start.setDate(now.getDate()-now.getDay());
    start.setHours(0,0,0,0);
    const end = new Date(start); end.setDate(start.getDate()+6); end.setHours(23,59,59,999);
    return d>=start && d<=end;
  }

  function getReminderText(t){
    if(!t.reminder || t.reminder==='none') return null;
    if(t.reminder==='1') return '🔔 1 día antes';
    if(t.reminder==='3') return '🔔 3 días antes';
    if(t.reminder==='7') return '🔔 1 semana antes';
    if(t.reminder==='custom' && t.customReminderDate) {
      const rd = new Date(t.customReminderDate+'T00:00:00');
      return `🔔 Avisar el ${rd.toLocaleDateString('es-ES', {day:'numeric', month:'short'})}`;
    }
    return null;
  }

  function taskRow(t){
    const row = document.createElement('div');
    row.className = 'task-row';
    const subj = subjectById(t.subjectId);
    const overdue = !t.done && t.date < todayStr();
    const remStr = getReminderText(t);

    row.innerHTML = `
      <div class="check ${t.done?'done':''}" data-task="${t.id}"></div>
      <div class="task-info">
        <div class="task-title ${t.done?'done':''}">${escapeHtml(t.title)}</div>
        <div class="task-meta">
          ${subj?`<span class="tag" style="background:${subj.color}">${escapeHtml(subj.name)}</span>`:''}
          <span class="prio">${prioEmoji(t.priority)}</span>
          ${remStr ? `<span class="reminder-tag">${remStr}</span>` : ''}
        </div>
      </div>
      <div class="task-date ${overdue?'overdue':''}">${formatDate(t.date)}</div>
    `;
    row.querySelector('.check').addEventListener('click', ()=>toggleTask(t.id));
    return row;
  }

  function prioEmoji(p){
    return p==='alta' ? '🔴 Alta' : p==='media' ? '🟠 Media' : '🟢 Baja';
  }
  function formatDate(dateStr){
    const d = new Date(dateStr+'T00:00:00');
    return d.toLocaleDateString('es-ES',{day:'numeric', month:'short'});
  }
  function escapeHtml(s){
    return s.replace(/[&<>"']/g, c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
  }

  function toggleTask(id){
    const t = state.tasks.find(x=>x.id===id);
    if(!t) return;
    t.done = !t.done;
    saveDebounced();
    const active = $('.view.active').id.replace('view-','');
    if(active==='dashboard') renderDashboard();
    else if(active==='tasks') renderGlobalTasks();
    else if(active==='subject-detail') renderDetailTasks();
    else if(active==='calendar') { renderCalendar(); renderDayPanel(); }
    else if(active==='stats') renderStats();
  }

  // ---------- CALENDAR ----------
  function renderCalendar(){
    if(calViewMode==='week'){
      $('#calGrid').style.display = 'none';
      $('#calWeekView').style.display = 'block';
      renderWeekCalendar();
    } else {
      $('#calGrid').style.display = 'grid';
      $('#calWeekView').style.display = 'none';
      renderMonthCalendar();
    }
  }

  function startOfWeek(d){
    const nd = new Date(d);
    nd.setHours(0,0,0,0);
    nd.setDate(nd.getDate() - nd.getDay());
    return nd;
  }

  function renderWeekCalendar(){
    const start = startOfWeek(calDate);
    const end = new Date(start); end.setDate(start.getDate()+6);
    const sameMonth = start.getMonth()===end.getMonth();
    $('#calMonthLabel').textContent = sameMonth
      ? `${start.getDate()}–${end.getDate()} ${MONTHS[start.getMonth()]} ${end.getFullYear()}`
      : `${start.getDate()} ${MONTHS[start.getMonth()].slice(0,3)} – ${end.getDate()} ${MONTHS[end.getMonth()].slice(0,3)} ${end.getFullYear()}`;
    const wrap = $('#calWeekView');
    wrap.innerHTML = '';
    const today = todayStr();
    for(let i=0;i<7;i++){
      const d = new Date(start); d.setDate(start.getDate()+i);
      const dateStr = `${d.getFullYear()}-${String(d.getMonth()+1).padStart(2,'0')}-${String(d.getDate()).padStart(2,'0')}`;
      const dayTasks = state.tasks.filter(t=>t.date===dateStr);
      const dayCard = document.createElement('div');
      dayCard.className = 'week-day' + (dateStr===today?' today':'');
      dayCard.innerHTML = `<div class="week-day-head"><span class="wd-name">${DOW_FULL[d.getDay()]}</span><span class="wd-num">${d.getDate()} ${MONTHS[d.getMonth()].slice(0,3)}</span></div>`;
      const list = document.createElement('div');
      if(dayTasks.length===0){
        list.innerHTML = `<div class="empty-state" style="padding:8px 0;">Sin entregas 🌤️</div>`;
      } else {
        dayTasks.forEach(t=>list.appendChild(taskRow(t)));
      }
      dayCard.appendChild(list);
      wrap.appendChild(dayCard);
    }
  }

  function renderMonthCalendar(){
    const y = calDate.getFullYear(), m = calDate.getMonth();
    $('#calMonthLabel').textContent = MONTHS[m] + ' ' + y;
    const grid = $('#calGrid');
    grid.innerHTML = '';
    DOW.forEach(d=>{
      const el = document.createElement('div');
      el.className='cal-dow'; el.textContent=d;
      grid.appendChild(el);
    });
    const firstDay = new Date(y,m,1).getDay();
    const daysInMonth = new Date(y,m+1,0).getDate();
    for(let i=0;i<firstDay;i++){
      const e = document.createElement('div'); e.className='cal-day empty'; grid.appendChild(e);
    }
    const today = todayStr();
    for(let day=1; day<=daysInMonth; day++){
      const dateStr = `${y}-${String(m+1).padStart(2,'0')}-${String(day).padStart(2,'0')}`;
      const cell = document.createElement('div');
      cell.className = 'cal-day' + (dateStr===today?' today':'') + (dateStr===selectedDay?' selected':'');
      const dayTasks = state.tasks.filter(t=>t.date===dateStr);
      cell.innerHTML = `<span class="num">${day}</span><div class="cal-dots">${
        dayTasks.slice(0,4).map(t=>{
          const s = subjectById(t.subjectId);
          return `<span style="background:${s?s.color:'#ccc'}"></span>`;
        }).join('')
      }</div>`;
      cell.addEventListener('click', ()=>{ selectedDay = dateStr; renderCalendar(); renderDayPanel(); });
      grid.appendChild(cell);
    }
  }
  $('#calPrev').addEventListener('click', ()=>{
    if(calViewMode==='week') calDate.setDate(calDate.getDate()-7);
    else calDate.setMonth(calDate.getMonth()-1);
    renderCalendar();
  });
  $('#calNext').addEventListener('click', ()=>{
    if(calViewMode==='week') calDate.setDate(calDate.getDate()+7);
    else calDate.setMonth(calDate.getMonth()+1);
    renderCalendar();
  });
  $('#calViewToggle').addEventListener('click', e=>{
    const btn = e.target.closest('button');
    if(!btn) return;
    calViewMode = btn.dataset.mode;
    $$('#calViewToggle button').forEach(b=>b.classList.toggle('active', b===btn));
    renderCalendar();
  });

  function renderDayPanel(){
    if(!selectedDay){ $('#dayPanel').style.display='none'; return; }
    $('#dayPanel').style.display='block';
    const d = new Date(selectedDay+'T00:00:00');
    $('#dayPanelTitle').textContent = d.toLocaleDateString('es-ES',{weekday:'long', day:'numeric', month:'long'});
    const list = $('#dayPanelList');
    list.innerHTML = '';
    const dayTasks = state.tasks.filter(t=>t.date===selectedDay);
    if(dayTasks.length===0){
      list.innerHTML = `<div class="empty-state">Sin entregas este día 🌤️</div>`;
    } else {
      dayTasks.forEach(t=>list.appendChild(taskRow(t)));
    }
  }

  // ---------- STATS ----------
  function renderStats(){
    const y = statsDate.getFullYear(), m = statsDate.getMonth();
    $('#statsMonthLabel').textContent = MONTHS[m] + ' ' + y;
    const list = $('#statsList');
    list.innerHTML = '';

    const monthTasks = state.tasks.filter(t=>{
      const d = new Date(t.date+'T00:00:00');
      return d.getFullYear()===y && d.getMonth()===m;
    });

    if(state.subjects.length===0){
      list.innerHTML = `<div class="empty-state">No hay materias registradas.</div>`;
      return;
    }

    state.subjects.forEach(s=>{
      const sTasks = monthTasks.filter(t=>t.subjectId===s.id);
      const total = sTasks.length;
      const done = sTasks.filter(t=>t.done).length;
      const pct = total ? Math.round((done/total)*100) : 0;

      const row = document.createElement('div');
      row.className = 'stat-row';
      row.innerHTML = `
        <div class="stat-head">
          <div class="stat-name">
            <span class="stat-dot" style="background:${s.color}"></span>
            <span>${escapeHtml(s.name)}</span>
          </div>
          <div class="stat-count">${done}/${total} (${pct}%)</div>
        </div>
        <div class="stat-bar-bg">
          <div class="stat-bar-fg" style="width:${pct}%; background:${s.color}"></div>
        </div>
      `;
      list.appendChild(row);
    });
  }
  $('#statsPrev').addEventListener('click', ()=>{ statsDate.setMonth(statsDate.getMonth()-1); renderStats(); });
  $('#statsNext').addEventListener('click', ()=>{ statsDate.setMonth(statsDate.getMonth()+1); renderStats(); });

  // ---------- SUBJECTS ----------
  function renderSubjects(){
    const grid = $('#subjectGrid');
    grid.innerHTML = '';
    state.subjects.forEach(s=>{
      const pending = state.tasks.filter(t=>t.subjectId===s.id && !t.done).length;
      const card = document.createElement('div');
      card.className='subject-card';
      card.style.background = `linear-gradient(135deg, ${s.color}, ${shade(s.color)})`;
      card.innerHTML = `<h4>${escapeHtml(s.name)}</h4><span class="count">${pending} tarea${pending!==1?'s':''} pendiente${pending!==1?'s':''}</span>`;
      card.addEventListener('click', ()=>openSubjectDetail(s.id));
      grid.appendChild(card);
    });
    const addCard = document.createElement('div');
    addCard.className='add-subject-card';
    addCard.innerHTML = `<span style="font-size:22px;">＋</span><span>Agregar materia</span>`;
    addCard.addEventListener('click', ()=>openModal('subjectOverlay'));
    grid.appendChild(addCard);
  }
  function shade(hex){
    const c = hex.replace('#','');
    const num = parseInt(c,16);
    let r = (num>>16) - 24, g = ((num>>8)&0xff) - 24, b = (num&0xff) - 24;
    r=Math.max(0,r); g=Math.max(0,g); b=Math.max(0,b);
    return `rgb(${r},${g},${b})`;
  }

  function openSubjectDetail(id){
    currentSubjectId = id;
    const s = subjectById(id);
    $('#detailTitle').textContent = s.name;
    $('#detailDot').style.background = s.color;
    $$('.view').forEach(v=>v.classList.remove('active'));
    $('#view-subject-detail').classList.add('active');
    $$('#mainTabs button').forEach(b=>b.classList.remove('active'));
    $$('.subtabs button').forEach((b,i)=>b.classList.toggle('active', i===0));
    $('#detailTasksView').style.display='block';
    $('#detailJournalView').style.display='none';
    renderDetailTasks();
    renderNotes();
  }
  $('#backToSubjects').addEventListener('click', ()=>goto('subjects'));

  $('.subtabs').addEventListener('click', e=>{
    const btn = e.target.closest('button');
    if(!btn) return;
    $$('.subtabs button').forEach(b=>b.classList.remove('active'));
    btn.classList.add('active');
    const sub = btn.dataset.sub;
    $('#detailTasksView').style.display = sub==='tasks' ? 'block':'none';
    $('#detailJournalView').style.display = sub==='journal' ? 'block':'none';
  });

  function renderDetailTasks(){
    const list = $('#detailTaskList');
    list.innerHTML = '';
    const tasks = state.tasks.filter(t=>t.subjectId===currentSubjectId).sort((a,b)=>a.date.localeCompare(b.date));
    if(tasks.length===0){
      list.innerHTML = `<div class="empty-state">Sin tareas aún. Usa el botón + para agregar una.</div>`;
    } else {
      tasks.forEach(t=>list.appendChild(taskRow(t)));
    }
  }

  function renderNotes(){
    const list = $('#notesList');
    list.innerHTML = '';
    const notes = state.notes.filter(n=>n.subjectId===currentSubjectId).sort((a,b)=>b.date.localeCompare(a.date));
    if(notes.length===0){
      list.innerHTML = `<div class="empty-state">Aún no hay notas para esta materia.</div>`;
      return;
    }
    notes.forEach(n=>{
      const el = document.createElement('div');
      el.className='note-card';
      const d = new Date(n.date);
      el.innerHTML = `<div class="note-date">${d.toLocaleDateString('es-ES',{day:'numeric',month:'long',year:'numeric',hour:'2-digit',minute:'2-digit'})}</div><div class="note-body">${escapeHtml(n.text)}</div>`;
      list.appendChild(el);
    });
  }
  $('#saveNoteBtn').addEventListener('click', async ()=>{
    const txt = $('#newNoteText').value.trim();
    if(!txt) return;
    state.notes.push({id:uid(), subjectId:currentSubjectId, text:txt, date:new Date().toISOString()});
    $('#newNoteText').value='';
    await saveState();
    renderNotes();
    showToast('Nota guardada 📝');
  });

  // ---------- GLOBAL TASKS ----------
  function renderGlobalTasks(){
    const subSel = $('#filterSubject');
    subSel.innerHTML = '<option value="">Todas las materias</option>' + state.subjects.map(s=>`<option value="${s.id}">${escapeHtml(s.name)}</option>`).join('');

    let tasks = [...state.tasks];
    const fSub = $('#filterSubject').value;
    const fStatus = $('#filterStatus').value;
    const fSort = $('#filterSort').value;
    if(fSub) tasks = tasks.filter(t=>t.subjectId===fSub);
    if(fStatus==='pending') tasks = tasks.filter(t=>!t.done);
    if(fStatus==='done') tasks = tasks.filter(t=>t.done);
    if(fSort==='date') tasks.sort((a,b)=>a.date.localeCompare(b.date));
    if(fSort==='priority'){
      const order = {alta:0, media:1, baja:2};
      tasks.sort((a,b)=>order[a.priority]-order[b.priority]);
    }

    const list = $('#globalTaskList');
    list.innerHTML = '';
    if(tasks.length===0){
      list.innerHTML = `<div class="empty-state">No hay tareas que coincidan con los filtros.</div>`;
    } else {
      tasks.forEach(t=>list.appendChild(taskRow(t)));
    }
  }
  ['filterSubject','filterStatus','filterSort'].forEach(id=>{
    $('#'+id).addEventListener('change', renderGlobalTasks);
  });

  // ---------- SETTINGS ----------
  function renderSettings(){
    const list = $('#settingsSubjectList');
    list.innerHTML = '';
    state.subjects.forEach(s=>{
      const row = document.createElement('div');
      row.className='settings-row';
      row.innerHTML = `
        <div style="display:flex; align-items:center; gap:10px;">
          <span style="width:14px; height:14px; border-radius:50%; background:${s.color}; display:inline-block;"></span>
          <span style="font-weight:700; font-size:13.5px;">${escapeHtml(s.name)}</span>
        </div>
        <button class="btn btn-danger" style="padding:6px 14px; font-size:11.5px;" data-del="${s.id}">Eliminar</button>
      `;
      row.querySelector('[data-del]').addEventListener('click', ()=>deleteSubject(s.id));
      list.appendChild(row);
    });
    $('#notif3').classList.toggle('on', state.settings.notif3days);
    $('#notif1').classList.toggle('on', state.settings.notif1day);
  }
  $$('.switch').forEach(sw=>{
    sw.addEventListener('click', async ()=>{
      const key = sw.dataset.key;
      state.settings[key] = !state.settings[key];
      sw.classList.toggle('on', state.settings[key]);
      await saveState();
    });
  });

  async function deleteSubject(id){
    if(!confirm('¿Eliminar esta materia y todas sus tareas y notas asociadas?')) return;
    state.subjects = state.subjects.filter(s=>s.id!==id);
    state.tasks = state.tasks.filter(t=>t.subjectId!==id);
    state.notes = state.notes.filter(n=>n.subjectId!==id);
    await saveState();
    renderSettings();
    renderAll();
    showToast('Materia eliminada');
  }

  // ---------- MODALS ----------
  function openModal(id){
    if(id==='taskOverlay'){
      $('#taskTitle').value='';
      $('#taskDate').value = todayStr();
      $$('#prioChips .chip').forEach(c=>c.className='chip');
      $('#taskReminder').value='none';
      $('#customReminderWrap').style.display='none';
      $('#taskReminderCustomDate').value = todayStr();
      const subSel = $('#taskSubject');
      subSel.innerHTML = state.subjects.map(s=>`<option value="${s.id}">${escapeHtml(s.name)}</option>`).join('');
      if(currentSubjectId && $('#view-subject-detail').classList.contains('active')){
        subSel.value = currentSubjectId;
      }
      selectedPrio = null;
    }
    if(id==='subjectOverlay'){
      $('#subjectName').value='';
      renderSwatches();
    }
    $('#'+id).classList.add('open');
  }
  function closeModal(id){ $('#'+id).classList.remove('open'); }
  $$('[data-close]').forEach(b=>b.addEventListener('click', ()=>closeModal(b.dataset.close)));
  $$('.overlay').forEach(o=>o.addEventListener('click', e=>{ if(e.target===o) closeModal(o.id); }));

  $('#fabAdd').addEventListener('click', ()=>openModal('taskOverlay'));

  let selectedPrio = null;
  $('#prioChips').addEventListener('click', e=>{
    const chip = e.target.closest('.chip');
    if(!chip) return;
    $$('#prioChips .chip').forEach(c=>c.className='chip');
    selectedPrio = chip.dataset.prio;
    chip.classList.add('active-'+selectedPrio);
  });

  $('#taskReminder').addEventListener('change', e=>{
    if(e.target.value === 'custom'){
      $('#customReminderWrap').style.display = 'block';
    } else {
      $('#customReminderWrap').style.display = 'none';
    }
  });

  $('#saveTaskBtn').addEventListener('click', async ()=>{
    const title = $('#taskTitle').value.trim();
    const subjectId = $('#taskSubject').value;
    const date = $('#taskDate').value;
    const reminder = $('#taskReminder').value;
    const customReminderDate = $('#taskReminderCustomDate').value;

    if(!title || !subjectId || !date){
      showToast('Completa título, materia y fecha ⚠️');
      return;
    }
    if(reminder === 'custom' && !customReminderDate){
      showToast('Selecciona la fecha del recordatorio ⚠️');
      return;
    }

    state.tasks.push({
      id:uid(), 
      title, 
      subjectId, 
      date,
      priority: selectedPrio || 'media',
      reminder,
      customReminderDate: reminder === 'custom' ? customReminderDate : null,
      done:false
    });
    await saveState();
    closeModal('taskOverlay');
    showToast('Tarea agregada 🌷');
    renderAll();
  });

  let selectedColor = COLORS[0];
  function renderSwatches(){
    const wrap = $('#colorSwatches');
    wrap.innerHTML='';
    selectedColor = COLORS[0];
    COLORS.forEach((c,i)=>{
      const sw = document.createElement('div');
      sw.className = 'swatch'+(i===0?' selected':'');
      sw.style.background = c;
      sw.addEventListener('click', ()=>{
        selectedColor = c;
        $$('.swatch').forEach(s=>s.classList.remove('selected'));
        sw.classList.add('selected');
      });
      wrap.appendChild(sw);
    });
  }
  $('#saveSubjectBtn').addEventListener('click', async ()=>{
    const name = $('#subjectName').value.trim();
    if(!name){ showToast('Escribe un nombre ⚠️'); return; }
    state.subjects.push({id:uid(), name, color:selectedColor});
    await saveState();
    closeModal('subjectOverlay');
    showToast('Materia creada 🌸');
    renderSubjects();
  });

  // ---------- INIT ----------
  function renderAll(){
    renderDashboard();
    renderCalendar();
    renderSubjects();
    renderGlobalTasks();
    renderSettings();
  }

  loadState();
})();
</script>
</body>
</html>
