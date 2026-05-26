<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Kyoto 2026">
<title>Kyoto 2026 — Directorio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+JP:wght@300;400;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --red: #C0392B;
    --red-light: #E74C3C;
    --ink: #1A0A0A;
    --paper: #FDF8F3;
    --mist: #F2EBE2;
    --gold: #B8860B;
    --gold-light: #DAA520;
    --slate: #5A4A4A;
    --slate-light: #8B7070;
    --white: #FFFFFF;
    --shadow: rgba(26,10,10,0.12);
    --safe-top: env(safe-area-inset-top, 0px);
    --safe-bottom: env(safe-area-inset-bottom, 0px);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; -webkit-tap-highlight-color: transparent; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--paper);
    color: var(--ink);
    min-height: 100dvh;
    overflow-x: hidden;
  }

  /* HEADER */
  .header {
    background: var(--ink);
    padding: calc(var(--safe-top) + 16px) 20px 16px;
    position: sticky;
    top: 0;
    z-index: 100;
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .header-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo-area {
    display: flex;
    align-items: baseline;
    gap: 10px;
  }

  .logo-kanji {
    font-family: 'Noto Serif JP', serif;
    font-size: 22px;
    color: var(--red-light);
    line-height: 1;
  }

  .logo-text {
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 600;
    color: var(--white);
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  .logo-year {
    font-size: 11px;
    color: var(--slate-light);
    font-weight: 300;
    letter-spacing: 0.15em;
  }

  .count-badge {
    background: var(--red);
    color: white;
    font-size: 11px;
    font-weight: 600;
    padding: 3px 8px;
    border-radius: 20px;
    letter-spacing: 0.05em;
  }

  /* SEARCH */
  .search-wrap {
    position: relative;
  }

  .search-input {
    width: 100%;
    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 10px;
    padding: 10px 14px 10px 38px;
    font-size: 15px;
    color: white;
    font-family: 'DM Sans', sans-serif;
    outline: none;
    transition: border-color 0.2s;
  }

  .search-input::placeholder { color: rgba(255,255,255,0.35); }
  .search-input:focus { border-color: rgba(192,57,43,0.6); }

  .search-icon {
    position: absolute;
    left: 12px;
    top: 50%;
    transform: translateY(-50%);
    color: rgba(255,255,255,0.35);
    font-size: 15px;
    pointer-events: none;
  }

  /* TABS */
  .tabs {
    display: flex;
    background: var(--mist);
    border-bottom: 1px solid rgba(26,10,10,0.08);
    overflow-x: auto;
    scrollbar-width: none;
  }
  .tabs::-webkit-scrollbar { display: none; }

  .tab {
    flex: 0 0 auto;
    padding: 12px 20px;
    font-size: 13px;
    font-weight: 500;
    color: var(--slate-light);
    cursor: pointer;
    border-bottom: 2.5px solid transparent;
    transition: all 0.2s;
    white-space: nowrap;
    letter-spacing: 0.02em;
  }

  .tab.active {
    color: var(--red);
    border-bottom-color: var(--red);
    font-weight: 600;
  }

  /* CONTENT */
  .content {
    padding: 0 0 calc(var(--safe-bottom) + 20px);
  }

  /* GRUPO ADRI — GRID CARDS */
  .section-label {
    padding: 16px 20px 8px;
    font-size: 11px;
    font-weight: 600;
    color: var(--slate-light);
    letter-spacing: 0.12em;
    text-transform: uppercase;
  }

  .grid-cards {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    padding: 0 16px 16px;
  }

  .student-card {
    background: var(--white);
    border-radius: 14px;
    padding: 14px;
    box-shadow: 0 2px 12px var(--shadow);
    cursor: pointer;
    transition: transform 0.15s, box-shadow 0.15s;
    position: relative;
    overflow: hidden;
    border: 1px solid rgba(26,10,10,0.06);
  }

  .student-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: var(--red);
  }

  .student-card.edgar::before { background: var(--gold); }

  .student-card:active { transform: scale(0.97); box-shadow: 0 1px 6px var(--shadow); }

  .card-avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Noto Serif JP', serif;
    font-size: 16px;
    font-weight: 700;
    color: white;
    margin-bottom: 10px;
    background: var(--red);
  }

  .student-card.edgar .card-avatar { background: var(--gold); }

  .card-name {
    font-size: 13px;
    font-weight: 600;
    color: var(--ink);
    line-height: 1.3;
    margin-bottom: 4px;
  }

  .card-prepa {
    font-size: 10px;
    color: var(--slate-light);
    line-height: 1.3;
  }

  .card-phone {
    margin-top: 8px;
    font-size: 12px;
    font-weight: 500;
    color: var(--red);
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .student-card.edgar .card-phone { color: var(--gold); }

  /* LIST VIEW (otros) */
  .list-view { padding: 0 16px; }

  .list-item {
    background: var(--white);
    border-radius: 12px;
    padding: 14px 16px;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 14px;
    cursor: pointer;
    box-shadow: 0 1px 6px var(--shadow);
    border: 1px solid rgba(26,10,10,0.05);
    transition: transform 0.15s;
  }

  .list-item:active { transform: scale(0.98); }

  .list-avatar {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    background: var(--mist);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
    font-weight: 700;
    color: var(--slate);
    flex-shrink: 0;
    font-family: 'Noto Serif JP', serif;
  }

  .list-info { flex: 1; min-width: 0; }

  .list-name {
    font-size: 15px;
    font-weight: 600;
    color: var(--ink);
    margin-bottom: 2px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .list-sub {
    font-size: 12px;
    color: var(--slate-light);
  }

  .list-chevron { color: var(--slate-light); font-size: 12px; }

  /* MODAL */
  .modal-overlay {
    position: fixed;
    inset: 0;
    background: rgba(26,10,10,0.6);
    z-index: 200;
    display: none;
    align-items: flex-end;
    backdrop-filter: blur(4px);
  }

  .modal-overlay.open { display: flex; }

  .modal {
    background: var(--paper);
    border-radius: 24px 24px 0 0;
    width: 100%;
    max-height: 90dvh;
    overflow-y: auto;
    padding-bottom: calc(var(--safe-bottom) + 24px);
    animation: slideUp 0.3s cubic-bezier(0.34,1.56,0.64,1);
  }

  @keyframes slideUp {
    from { transform: translateY(100%); }
    to { transform: translateY(0); }
  }

  .modal-handle {
    width: 40px;
    height: 4px;
    background: rgba(26,10,10,0.15);
    border-radius: 2px;
    margin: 12px auto 0;
  }

  .modal-header {
    padding: 20px 24px 16px;
    display: flex;
    align-items: flex-start;
    gap: 16px;
    border-bottom: 1px solid rgba(26,10,10,0.08);
  }

  .modal-avatar {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: var(--red);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Noto Serif JP', serif;
    font-size: 22px;
    font-weight: 700;
    color: white;
    flex-shrink: 0;
  }

  .modal-avatar.edgar { background: var(--gold); }

  .modal-name {
    font-size: 20px;
    font-weight: 700;
    color: var(--ink);
    line-height: 1.2;
    margin-bottom: 4px;
  }

  .modal-matricula {
    font-size: 12px;
    color: var(--slate-light);
    font-weight: 500;
    letter-spacing: 0.05em;
  }

  .modal-grupo-badge {
    display: inline-block;
    margin-top: 6px;
    padding: 2px 8px;
    border-radius: 20px;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .badge-adri { background: rgba(192,57,43,0.1); color: var(--red); }
  .badge-edgar { background: rgba(184,134,11,0.1); color: var(--gold); }

  .modal-close {
    margin-left: auto;
    background: var(--mist);
    border: none;
    border-radius: 50%;
    width: 32px;
    height: 32px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    font-size: 14px;
    color: var(--slate);
    flex-shrink: 0;
  }

  .modal-body { padding: 0 24px; }

  .section-group {
    margin-top: 20px;
  }

  .section-title {
    font-size: 10px;
    font-weight: 700;
    color: var(--slate-light);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: rgba(26,10,10,0.08);
  }

  .info-row {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 8px 0;
    border-bottom: 1px solid rgba(26,10,10,0.05);
  }

  .info-row:last-child { border-bottom: none; }

  .info-icon { font-size: 15px; width: 20px; text-align: center; flex-shrink: 0; margin-top: 1px; }

  .info-content { flex: 1; min-width: 0; }

  .info-label {
    font-size: 10px;
    color: var(--slate-light);
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 1px;
  }

  .info-value {
    font-size: 14px;
    color: var(--ink);
    font-weight: 400;
    word-break: break-word;
  }

  .info-value a {
    color: var(--red);
    text-decoration: none;
  }

  .action-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    width: 100%;
    padding: 14px;
    border-radius: 12px;
    border: none;
    font-family: 'DM Sans', sans-serif;
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    margin-top: 8px;
    transition: opacity 0.15s;
  }

  .action-btn:active { opacity: 0.75; }

  .btn-call { background: var(--red); color: white; }
  .btn-whatsapp { background: #25D366; color: white; }
  .btn-email { background: var(--mist); color: var(--ink); }

  .alert-tag {
    display: inline-block;
    background: rgba(192,57,43,0.1);
    color: var(--red);
    border-radius: 6px;
    font-size: 12px;
    padding: 2px 8px;
    font-weight: 500;
    margin-top: 3px;
  }

  .alert-tag.ok {
    background: rgba(39,174,96,0.1);
    color: #27AE60;
  }

  /* SALUD TAB */
  .health-list { padding: 0 16px; }

  .health-item {
    background: var(--white);
    border-radius: 12px;
    padding: 14px 16px;
    margin-bottom: 10px;
    box-shadow: 0 1px 6px var(--shadow);
    cursor: pointer;
    border: 1px solid rgba(26,10,10,0.05);
    transition: transform 0.15s;
  }

  .health-item:active { transform: scale(0.98); }

  .health-name { font-size: 15px; font-weight: 600; color: var(--ink); margin-bottom: 6px; }

  .health-tags { display: flex; flex-wrap: wrap; gap: 6px; }

  .htag {
    font-size: 11px;
    padding: 3px 8px;
    border-radius: 20px;
    font-weight: 500;
  }

  .htag-blood { background: rgba(192,57,43,0.1); color: var(--red); }
  .htag-allergy { background: rgba(230,126,34,0.1); color: #E67E22; }
  .htag-condition { background: rgba(155,89,182,0.1); color: #8E44AD; }
  .htag-ok { background: rgba(39,174,96,0.08); color: #27AE60; }

  /* EMPTY STATE */
  .empty {
    text-align: center;
    padding: 60px 20px;
    color: var(--slate-light);
  }

  .empty-icon { font-size: 40px; margin-bottom: 12px; }
  .empty-text { font-size: 15px; }

  /* HIDDEN */
  .hidden { display: none !important; }

  /* SCROLLBAR */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: rgba(26,10,10,0.15); border-radius: 2px; }
</style>
</head>
<body>

<div class="header">
  <div class="header-top">
    <div class="logo-area">
      <span class="logo-kanji">京都</span>
      <div>
        <div class="logo-text">Kyoto 2026</div>
        <div class="logo-year">Genki Japanese & Culture School</div>
      </div>
    </div>
    <span class="count-badge" id="count-badge">20 est.</span>
  </div>
  <div class="search-wrap">
    <span class="search-icon">🔍</span>
    <input class="search-input" type="search" placeholder="Buscar nombre, matrícula, prepa..." id="search" autocomplete="off" autocorrect="off" autocapitalize="off">
  </div>
</div>

<div class="tabs">
  <div class="tab active" data-tab="adri">⛩ Grupo Adri</div>
  <div class="tab" data-tab="edgar">🌸 Grupo Edgar</div>
  <div class="tab" data-tab="todos">📋 Todos</div>
  <div class="tab" data-tab="salud">🏥 Salud</div>
</div>

<div class="content">
  <div id="tab-adri"></div>
  <div id="tab-edgar" class="hidden"></div>
  <div id="tab-todos" class="hidden"></div>
  <div id="tab-salud" class="hidden"></div>
</div>

<!-- MODAL -->
<div class="modal-overlay" id="modal-overlay" onclick="closeModal(event)">
  <div class="modal" id="modal">
    <div class="modal-handle"></div>
    <div id="modal-content"></div>
  </div>
</div>

<script>
// ===================== DATA =====================
const healthData = {
  "Bruno Esparza Aguilar":           { altura:"1.63m", peso:"60kg", sangre:"A-", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"" },
  "Candy Loán Monreal Mora":         { altura:"1.53m", peso:"53kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"" },
  "Carmina Nicole Ramírez Mata":     { altura:"1.57m", peso:"52kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"" },
  "César Patricio Hernández Martínez": { altura:"1.71m", peso:"56kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:["Paperas", "Varicela"], notas:"" },
  "Diana Laura Álvarez López De Lara": { altura:"1.60m", peso:"61.1kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:["Tiroides"], notas:"" },
  "Erika Lorena Medina Osornio":     { altura:"1.57m", peso:"53kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"" },
  "Iker Rene Tort Navarrete":        { altura:"—", peso:"—", sangre:"—", alergia_comida:"—", fuma:"—", alergia_animal:"—", alergia_med:"—", otras_alergias:"—", condiciones:[], notas:"Sin datos" },
  "Iñigo Vacas Rogel":               { altura:"2.02m", peso:"78kg", sangre:"AB+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"" },
  "Jesús Pablo Padilla Matus":       { altura:"1.81m", peso:"85kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:["Varicela"], notas:"" },
  "José Manuel Saavedra Carrillo":   { altura:"1.72m", peso:"70kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"Sí - Caballos", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"Alergia caballos: rinitis y ojos rojos, tratamiento: Claritine" },
  "Juliette Landey Aguilera":        { altura:"1.56m", peso:"49kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"Sí - Perros", alergia_med:"No", otras_alergias:"Sí - Pasto", condiciones:[], notas:"Alergia perros: estornudos, Pastillas para alergia. Alergia pasto: estornudos e irritación" },
  "Kamila Miranda Sánchez":          { altura:"1.60m", peso:"53kg", sangre:"A+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:["Epilepsia"], notas:"" },
  "María José Pérez Alcazar":        { altura:"1.56m", peso:"50kg", sangre:"A+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"" },
  "Mauricio González Franco":        { altura:"1.72m", peso:"72kg", sangre:"O-", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"" },
  "Maya Guajardo Recio":             { altura:"1.65m", peso:"56kg", sangre:"B+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:["Varicela","Epilepsia"], notas:"" },
  "Oliver Gutiérrez Herrera":        { altura:"1.75m", peso:"60kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"" },
  "Regina Sandoval Arredondo":       { altura:"—", peso:"—", sangre:"—", alergia_comida:"—", fuma:"—", alergia_animal:"—", alergia_med:"—", otras_alergias:"—", condiciones:[], notas:"Sin datos médicos registrados" },
  "Santiago Magaña Canalizo":        { altura:"1.70m", peso:"60kg", sangre:"A+", alergia_comida:"No", fuma:"No", alergia_animal:"Sí - Rasguños gato", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"Alergia rasguños de gato: inflamación, tratamiento: lavar herida" },
  "Santiago Rafael Ericon Sarabia":  { altura:"1.80m", peso:"61kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:[], notas:"" },
  "Yariana Morfin Hernández":        { altura:"1.54m", peso:"55kg", sangre:"O+", alergia_comida:"No", fuma:"No", alergia_animal:"No", alergia_med:"No", otras_alergias:"No", condiciones:["Varicela"], notas:"" },
};

const students = [
  // ---- GRUPO ADRI ----
  {
    grupo: "adri",
    nombre: "Carmina Nicole Ramírez Mata",
    matricula: "A01233965",
    correo_inst: "A01233965@tec.mx",
    correo_personal: "carmina.nicole@icloud.com",
    celular: "8711140465",
    genero: "Femenino",
    nacimiento: "2009-10-16",
    prepa: "LAG sede Laguna",
    estatus: "Admitido",
    pasaporte: "En trámite",
    visa_americana: "No",
    tel_casa: "8712682256",
    direccion: "San Juan 437, Villas de San Ángel, CP 27086, Torreón, Coahuila, México",
    padre: "Luis Humberto Ramírez Reyes",
    padre_correo: "luis_est62@hotmail.com",
    padre_cel: "8711153652",
    padre_tel: "8712682256",
    padre_of: "8712704432",
  },
  {
    grupo: "adri",
    nombre: "Juliette Landey Aguilera",
    matricula: "A01743474",
    correo_inst: "A01743474@tec.mx",
    correo_personal: "jttlandey@gmail.com",
    celular: "6673155868",
    genero: "Femenino",
    nacimiento: "2009-05-11",
    prepa: "SIN sede Sinaloa",
    estatus: "Admitido",
    pasaporte: "G41224026 (vence 2027-05-21)",
    visa_americana: "No",
    tel_casa: "6671291528",
    direccion: "Tetepan 6063, Privada Natura Perisur 2, CP 80197, Culiacán, Sinaloa, México",
    padre: "Julio César Landey Zamudio",
    padre_correo: "juliolandey@yahoo.com.mx",
    padre_cel: "6671291528",
    padre_tel: "6671291528",
    padre_of: "6671291528",
  },
  {
    grupo: "adri",
    nombre: "Maya Guajardo Recio",
    matricula: "A01288420",
    correo_inst: "A01288420@tec.mx",
    correo_personal: "mayagure@gmail.com",
    celular: "8134061352",
    genero: "Femenino",
    nacimiento: "2009-01-16",
    prepa: "EGS sede Garza Lagüera",
    estatus: "Admitido",
    pasaporte: "N06051676 (vence 2028-12-12)",
    visa_americana: "Sí",
    tel_casa: "8140575107",
    direccion: "Teresa de Ávila 417, Jardines Roma, CP 64740, Monterrey, Nuevo León, México",
    padre: "Alejandro Guajardo Moreno",
    padre_correo: "alejandro.guajardo@gmail.com",
    padre_cel: "8112557505",
    padre_tel: "8140575107",
    padre_of: "8180886414",
  },
  {
    grupo: "adri",
    nombre: "Diana Laura Álvarez López De Lara",
    matricula: "A01712785",
    correo_inst: "A01712785@tec.mx",
    correo_personal: "a01712785@tec.mx",
    celular: "4461174232",
    genero: "Femenino",
    nacimiento: "2009-08-01",
    prepa: "QRO sede Querétaro",
    estatus: "Admitido",
    pasaporte: "N06688891 (vence 2029-01-21)",
    visa_americana: "No",
    tel_casa: "4422419589",
    direccion: "Condesa de Querétaro 1017, Frac. Condesa Juriquilla, CP 76230, Santiago de Querétaro, Qro., México",
    padre: "Antonio Álvarez Olivares",
    padre_correo: "antonio.alvarez72@hotmail.com",
    padre_cel: "8110399594",
    padre_tel: "4422419589",
    padre_of: "4424714522",
  },
  {
    grupo: "adri",
    nombre: "Mauricio González Franco",
    matricula: "A01786395",
    correo_inst: "A01786395@tec.mx",
    correo_personal: "mauglez628@gmail.com",
    celular: "5529423877",
    genero: "Masculino",
    nacimiento: "2008-02-06",
    prepa: "CSF sede Santa Fe",
    estatus: "Admitido",
    pasaporte: "N10362258 (vence 2029-08-16)",
    visa_americana: "No",
    tel_casa: "5527274662",
    direccion: "Paseo de la Herradura 303 int 33, Jardines de la Herradura, CP 52785, Huixquilucan, Edo. Méx., México",
    padre: "N/A",
    padre_correo: "",
    padre_cel: "",
    padre_tel: "",
    padre_of: "",
  },
  {
    grupo: "adri",
    nombre: "Jesús Pablo Padilla Matus",
    matricula: "A01572978",
    correo_inst: "A01572978@tec.mx",
    correo_personal: "A01572978@tec.mx",
    celular: "8182803069",
    genero: "Masculino",
    nacimiento: "2009-03-20",
    prepa: "EGS sede Cumbres",
    estatus: "Admitido",
    pasaporte: "N10439462 (vence 2029-09-06)",
    visa_americana: "No",
    tel_casa: "8123510149",
    direccion: "Calvados 223, Cumbres Madeira Francés Alpes, CP 64349, Monterrey, Nuevo León, México",
    padre: "Jesús Javier Padilla Higuera",
    padre_correo: "jjpadilla1975@gmail.com",
    padre_cel: "8123510149",
    padre_tel: "8123510149",
    padre_of: "8123510149",
  },
  {
    grupo: "adri",
    nombre: "María José Pérez Alcazar",
    matricula: "A01563802",
    correo_inst: "A01563802@tec.mx",
    correo_personal: "a01563802@tec.mx",
    celular: "6141318400",
    genero: "Femenino",
    nacimiento: "2009-10-07",
    prepa: "CHI sede Chihuahua",
    estatus: "Admitido",
    pasaporte: "N18671979 (vence 2031-03-03)",
    visa_americana: "No",
    tel_casa: "6142208492",
    direccion: "Vicuña 10714, Valdivia 1, CP 31160, Chihuahua, Chih., México",
    padre: "Ramón Francisco Pérez Domíguez",
    padre_correo: "ramonn.perez@hotmail.com",
    padre_cel: "6141839303",
    padre_tel: "6141839303",
    padre_of: "6141839303",
  },
  {
    grupo: "adri",
    nombre: "Yariana Morfin Hernández",
    matricula: "A01739299",
    correo_inst: "A01739299@tec.mx",
    correo_personal: "A01739299@tec.mx",
    celular: "2382008996",
    genero: "Femenino",
    nacimiento: "2009-10-15",
    prepa: "PUE sede Puebla",
    estatus: "Admitido",
    pasaporte: "N18006940 (vence 2031-01-18)",
    visa_americana: "No",
    tel_casa: "2381099600",
    direccion: "Boulevard del Bosque 14, Puebla de Zaragoza, CP 72523, Puebla, Pue., México",
    padre: "Ismael Morfin Carrera",
    padre_correo: "mat.mor@hotmail.com",
    padre_cel: "2491704514",
    padre_tel: "2491704514",
    padre_of: "2494876124",
  },
  {
    grupo: "adri",
    nombre: "Bruno Esparza Aguilar",
    matricula: "A01802187",
    correo_inst: "A01802187@tec.mx",
    correo_personal: "A01802187@tec.mx",
    celular: "5558265435",
    genero: "Masculino",
    nacimiento: "2008-10-31",
    prepa: "CEM Sede Esmeralda",
    estatus: "Admitido",
    pasaporte: "En trámite",
    visa_americana: "No",
    tel_casa: "5530060543",
    direccion: "2da Privada de Blvd Condado de Sayavedra casa 5, Condado de Sayavedra, CP 52938, Atizapán de Zaragoza, Edo. Méx., México",
    padre: "César Omar Esparza Soule",
    padre_correo: "coes76@yahoo.com.mx",
    padre_cel: "5521066164",
    padre_tel: "5521066164",
    padre_of: "5521066164",
  },
  {
    grupo: "adri",
    nombre: "Iker Rene Tort Navarrete",
    matricula: "A01713926",
    correo_inst: "A01713926@tec.mx",
    correo_personal: "ikertort@hotmail.com",
    celular: "5633668531",
    genero: "Masculino",
    nacimiento: "2007-08-01",
    prepa: "QRO sede Querétaro",
    estatus: "Admitido",
    pasaporte: "N13344776 (vence 2030-11-06)",
    visa_americana: "No",
    tel_casa: "4421099966",
    direccion: "Condesa de Juriquilla 1337, Condesa de Juriquilla, CP 76230, Querétaro, Qro., México",
    padre: "Mario René Tort Aguilar",
    padre_correo: "renetort@hotmail.com",
    padre_cel: "5585979774",
    padre_tel: "5585979774",
    padre_of: "5585979774",
  },
  // ---- GRUPO EDGAR ----
  {
    grupo: "edgar",
    nombre: "Oliver Gutiérrez Herrera",
    matricula: "A01801996",
    correo_inst: "A01801996@tec.mx",
    correo_personal: "A01801996@tec.mx",
    celular: "5516877453",
    genero: "Masculino",
    nacimiento: "2008-01-12",
    prepa: "CEM sede Edo de México",
    estatus: "Admitido",
    pasaporte: "N11105792 (vence 2029-09-29)",
    visa_americana: "No",
    tel_casa: "5520464250",
    direccion: "Espiritu Santo 199, Lomas de Valle Escondido, CP 52930, Lopez Mateos, Edo. Méx., México",
    padre: "Alejandro Gutiérrez Valencia",
    padre_correo: "agutierrez@guval.com.mx",
    padre_cel: "5531585235",
    padre_tel: "5531585235",
    padre_of: "5531585235",
  },
  {
    grupo: "edgar",
    nombre: "Santiago Rafael Ericon Sarabia",
    matricula: "A01743809",
    correo_inst: "A01743809@tec.mx",
    correo_personal: "santiagoericon@gmail.com",
    celular: "6671183078",
    genero: "Masculino",
    nacimiento: "2009-01-15",
    prepa: "SIN sede Sinaloa",
    estatus: "Admitido",
    pasaporte: "22220932 (vence 2032-02-03)",
    visa_americana: "No",
    tel_casa: "6673036763",
    direccion: "Av. Nicolas Bravo 1546, Cañadas, CP 80178, Culiacán, Sinaloa, México",
    padre: "Rafael Ericón Plata",
    padre_correo: "rafaplata1215@gmail.com",
    padre_cel: "6673036763",
    padre_tel: "6673036763",
    padre_of: "6673036763",
  },
  {
    grupo: "edgar",
    nombre: "César Patricio Hernández Martínez",
    matricula: "A01668575",
    correo_inst: "A01668575@tec.mx",
    correo_personal: "cesar.p.hdz.mtz@gmail.com",
    celular: "5548469383",
    genero: "Masculino",
    nacimiento: "2009-06-27",
    prepa: "CCM sede Cd de México",
    estatus: "Admitido",
    pasaporte: "N18113866 (vence 2031-02-01)",
    visa_americana: "No",
    tel_casa: "55129584",
    direccion: "Hacienda Coacalco 38, Prado Coapa 3ra Sección, CP 14357, CDMX, México",
    padre: "Jorge César Hernández Maciel",
    padre_correo: "jcesarhm@hotmail.com",
    padre_cel: "55129584",
    padre_tel: "55129584",
    padre_of: "5585034213",
  },
  {
    grupo: "edgar",
    nombre: "Iñigo Vacas Rogel",
    matricula: "A01787244",
    correo_inst: "A01787244@tec.mx",
    correo_personal: "inivacas@gmail.com",
    celular: "5532549992",
    genero: "Masculino",
    nacimiento: "2008-06-27",
    prepa: "CSF sede Santa Fe",
    estatus: "Admitido",
    pasaporte: "N12567482 (vence 2029-12-26) + Otra: XDE276108 (vence 2027-06-27)",
    visa_americana: "No",
    tel_casa: "5552237731",
    direccion: "Gonzalez de Cossio 621 int 501, Del Valle, CP 03100, CDMX, México",
    padre: "Santiago Vacas Castañeda",
    padre_correo: "santiagovacas@gmail.com",
    padre_cel: "5639566061",
    padre_tel: "5552237731",
    padre_of: "5639566061",
  },
  {
    grupo: "edgar",
    nombre: "Candy Loán Monreal Mora",
    matricula: "A01403620",
    correo_inst: "A01403620@tec.mx",
    correo_personal: "artanimals@icloud.com",
    celular: "4494609730",
    genero: "Femenino",
    nacimiento: "2009-03-31",
    prepa: "AGS Sede Aguascalientes",
    estatus: "Admitido",
    pasaporte: "N13554991 (vence 2030-03-22)",
    visa_americana: "No",
    tel_casa: "4494616224",
    direccion: "Sendero de los Balcones 117, Residenciales las Plazas, CP 20126, Aguascalientes, Ags., México",
    padre: "César Francisco Monreal Ruvalcaba",
    padre_correo: "cesarmonrealr@hotmail.com",
    padre_cel: "4491039244",
    padre_tel: "4491039244",
    padre_of: "4491039244",
  },
  {
    grupo: "edgar",
    nombre: "Regina Sandoval Arredondo",
    matricula: "A01787456",
    correo_inst: "A01787456@tec.mx",
    correo_personal: "a01787456@tec.mx",
    celular: "5585720803",
    genero: "Femenino",
    nacimiento: "2009-08-13",
    prepa: "CSF sede Santa Fe",
    estatus: "Admitido",
    pasaporte: "N12621700 (vence 2030-01-25)",
    visa_americana: "No",
    tel_casa: "5585720803",
    direccion: "Dr. Jose Maria Veriz 1261, Letran Valle, CP 03650, CDMX, México | Padre: Adolfo Prieto 1743, Acacias, CP 03240, CDMX",
    padre: "Said Omar Sandoval Rosas",
    padre_correo: "said.sanros@gmail.com",
    padre_cel: "5570099608",
    padre_tel: "5570099608",
    padre_of: "5570099608",
  },
  {
    grupo: "edgar",
    nombre: "Erika Lorena Medina Osornio",
    matricula: "A01425883",
    correo_inst: "A01425883@tec.mx",
    correo_personal: "medinaosornioerika@gmail.com",
    celular: "7774946300",
    genero: "Femenino",
    nacimiento: "2008-08-05",
    prepa: "CVA sede Cuernavaca",
    estatus: "Admitido",
    pasaporte: "N09689620 (vence 2029-07-21)",
    visa_americana: "No",
    tel_casa: "7773800007",
    direccion: "Loma Panoramica 303, Lomas del Sol, CP 62156, Cuernavaca, Morelos, México",
    padre: "Agustín Medina Madrigal",
    padre_correo: "drbeatle@hotmail.com",
    padre_cel: "7775634878",
    padre_tel: "7773800007",
    padre_of: "7777919910",
  },
  {
    grupo: "edgar",
    nombre: "Kamila Miranda Sánchez",
    matricula: "A01425928",
    correo_inst: "A01425883@tec.mx",
    correo_personal: "kamilamirand8975@gmail.com",
    celular: "7775700008",
    genero: "Femenino",
    nacimiento: "2008-10-19",
    prepa: "CVA sede Cuernavaca",
    estatus: "Admitido",
    pasaporte: "N12675321 (vence 2030-02-15)",
    visa_americana: "No",
    tel_casa: "7779942328",
    direccion: "Calzada de los Reyes 472, Rancho Tetela, CP 62160, Cuernavaca, Morelos, México",
    padre: "Carlos Alberto Miranda Castro",
    padre_correo: "mirandaretros2@gmail.com",
    padre_cel: "7771193617",
    padre_tel: "7779942328",
    padre_of: "7779766777",
  },
  {
    grupo: "edgar",
    nombre: "Santiago Magaña Canalizo",
    matricula: "A01234647",
    correo_inst: "A01234647@tec.mx",
    correo_personal: "A01234647@tec.mx",
    celular: "8711338281",
    genero: "Masculino",
    nacimiento: "2009-02-03",
    prepa: "LAG sede Laguna",
    estatus: "Admitido",
    pasaporte: "N00386630 (vence 2027-12-02)",
    visa_americana: "No",
    tel_casa: "8717204484",
    direccion: "Via Capellini 682, Frac. Roma, CP 27258, Torreon, Coahuila, México | Padre: Paseo del Tecnológico 909, Residencial Tecnológico, CP 27272, Torreon",
    padre: "Armando Magaña Cobos",
    padre_correo: "maganaarmando@hotmail.com",
    padre_cel: "8718879327",
    padre_tel: "8718879327",
    padre_of: "8717300695",
  },
  {
    grupo: "edgar",
    nombre: "José Manuel Saavedra Carrillo",
    matricula: "A01712578",
    correo_inst: "A01712578@tec.mx",
    correo_personal: "jmanuel.scarrillo@gmail.com",
    celular: "4423361422",
    genero: "Masculino",
    nacimiento: "2007-12-27",
    prepa: "QRO sede Querétaro",
    estatus: "Admitido",
    pasaporte: "N18607828 (vence 2031-03-07)",
    visa_americana: "Sí",
    tel_casa: "4421284691",
    direccion: "Cerro Lago Palomas 136, Cumbres del Lago, CP 76230, Querétaro, Qro., México",
    padre: "José Manuel Saavedra Horita",
    padre_correo: "jms.horita@gmail.com",
    padre_cel: "4422501587",
    padre_tel: "4422501587",
    padre_of: "4422501587",
  },
];

// ===================== HELPERS =====================
function initials(nombre) {
  const parts = nombre.trim().split(' ');
  return (parts[0][0] + (parts[1] ? parts[1][0] : '')).toUpperCase();
}

function edad(dob) {
  const d = new Date(dob);
  if (isNaN(d)) return '';
  const now = new Date();
  let age = now.getFullYear() - d.getFullYear();
  if (now < new Date(now.getFullYear(), d.getMonth(), d.getDate())) age--;
  return age + ' años';
}

function formatDate(str) {
  if (!str) return '—';
  const d = new Date(str);
  if (isNaN(d)) return str;
  return d.toLocaleDateString('es-MX', { day: '2-digit', month: 'long', year: 'numeric' });
}

// ===================== RENDER =====================
function renderCard(s) {
  const ini = initials(s.nombre);
  return `
    <div class="student-card ${s.grupo}" onclick="openModal('${s.matricula}')">
      <div class="card-avatar">${ini}</div>
      <div class="card-name">${s.nombre}</div>
      <div class="card-prepa">${s.prepa.replace(' sede ', '\n')}</div>
      <div class="card-phone">📱 ${s.celular}</div>
    </div>`;
}

function renderListItem(s) {
  const ini = initials(s.nombre);
  const gr = s.grupo === 'adri' ? '⛩' : '🌸';
  return `
    <div class="list-item" onclick="openModal('${s.matricula}')">
      <div class="list-avatar">${ini}</div>
      <div class="list-info">
        <div class="list-name">${s.nombre}</div>
        <div class="list-sub">${gr} ${s.prepa} · ${s.celular}</div>
      </div>
      <span class="list-chevron">›</span>
    </div>`;
}

function renderHealthItem(s) {
  const h = healthData[s.nombre] || {};
  const alergias = [h.alergia_comida !== 'No' && h.alergia_comida !== '—' ? 'Alimento' : null,
                    h.alergia_animal && h.alergia_animal !== 'No' && h.alergia_animal !== '—' ? 'Animal' : null,
                    h.alergia_med !== 'No' && h.alergia_med !== '—' ? 'Medicamento' : null,
                    h.otras_alergias !== 'No' && h.otras_alergias !== '—' ? 'Otra alergia' : null]
    .filter(Boolean);
  const hasAlerts = alergias.length > 0 || h.condiciones?.length > 0;
  return `
    <div class="health-item" onclick="openModal('${s.matricula}')">
      <div class="health-name">${s.nombre}</div>
      <div class="health-tags">
        <span class="htag htag-blood">🩸 ${h.sangre || '—'}</span>
        ${alergias.map(a => `<span class="htag htag-allergy">⚠️ ${a}</span>`).join('')}
        ${(h.condiciones || []).map(c => `<span class="htag htag-condition">💊 ${c}</span>`).join('')}
        ${!hasAlerts ? '<span class="htag htag-ok">✓ Sin alertas</span>' : ''}
      </div>
    </div>`;
}

// ===================== TABS =====================
let currentTab = 'adri';
let searchQuery = '';

function getFiltered(grupo) {
  const q = searchQuery.toLowerCase();
  return students.filter(s =>
    (grupo === 'todos' ? true : s.grupo === grupo) &&
    (!q || s.nombre.toLowerCase().includes(q) ||
     s.matricula.toLowerCase().includes(q) ||
     s.prepa.toLowerCase().includes(q) ||
     s.celular.includes(q))
  );
}

function renderTab(tab) {
  const filtered = getFiltered(tab === 'salud' ? 'todos' : tab);
  const container = document.getElementById(`tab-${tab}`);

  if (filtered.length === 0) {
    container.innerHTML = `<div class="empty"><div class="empty-icon">🔍</div><div class="empty-text">Sin resultados para "${searchQuery}"</div></div>`;
    return;
  }

  if (tab === 'adri') {
    container.innerHTML = `<div class="section-label">Grupo Adri · ${filtered.length} estudiantes</div>
      <div class="grid-cards">${filtered.map(renderCard).join('')}</div>`;
  } else if (tab === 'edgar') {
    container.innerHTML = `<div class="section-label">Grupo Edgar · ${filtered.length} estudiantes</div>
      <div class="grid-cards">${filtered.map(renderCard).join('')}</div>`;
  } else if (tab === 'todos') {
    const adri = filtered.filter(s => s.grupo === 'adri');
    const edgar = filtered.filter(s => s.grupo === 'edgar');
    let html = '';
    if (adri.length) html += `<div class="section-label">⛩ Grupo Adri</div><div class="list-view">${adri.map(renderListItem).join('')}</div>`;
    if (edgar.length) html += `<div class="section-label">🌸 Grupo Edgar</div><div class="list-view">${edgar.map(renderListItem).join('')}</div>`;
    container.innerHTML = html;
  } else if (tab === 'salud') {
    const hasAlert = filtered.filter(s => {
      const h = healthData[s.nombre] || {};
      return (h.alergia_animal && h.alergia_animal !== 'No' && h.alergia_animal !== '—') ||
             (h.condiciones && h.condiciones.length > 0) ||
             (h.otras_alergias && h.otras_alergias !== 'No' && h.otras_alergias !== '—');
    });
    const clean = filtered.filter(s => !hasAlert.includes(s));
    let html = '';
    if (hasAlert.length) html += `<div class="section-label">⚠️ Con alertas (${hasAlert.length})</div><div class="health-list">${hasAlert.map(renderHealthItem).join('')}</div>`;
    if (clean.length) html += `<div class="section-label">✓ Sin alertas (${clean.length})</div><div class="health-list">${clean.map(renderHealthItem).join('')}</div>`;
    container.innerHTML = html;
  }

  // Count badge shows total visible
  document.getElementById('count-badge').textContent = getFiltered('todos').length + ' est.';
}

function renderAllTabs() {
  ['adri','edgar','todos','salud'].forEach(renderTab);
}

// Init
renderAllTabs();

// Tab switching
document.querySelectorAll('.tab').forEach(tab => {
  tab.addEventListener('click', () => {
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    tab.classList.add('active');
    currentTab = tab.dataset.tab;
    ['adri','edgar','todos','salud'].forEach(t => {
      document.getElementById(`tab-${t}`).classList.toggle('hidden', t !== currentTab);
    });
  });
});

// Search
document.getElementById('search').addEventListener('input', function() {
  searchQuery = this.value;
  renderAllTabs();
});

// ===================== MODAL =====================
function openModal(matricula) {
  const s = students.find(st => st.matricula === matricula);
  if (!s) return;
  const h = healthData[s.nombre] || {};
  const ini = initials(s.nombre);
  const badgeClass = s.grupo === 'adri' ? 'badge-adri' : 'badge-edgar';
  const badgeLabel = s.grupo === 'adri' ? '⛩ Grupo Adri' : '🌸 Grupo Edgar';
  const avatarClass = s.grupo === 'edgar' ? 'edgar' : '';

  const alergias = [];
  if (h.alergia_comida && h.alergia_comida !== 'No' && h.alergia_comida !== '—') alergias.push('🍽 Alimento: ' + h.alergia_comida);
  if (h.alergia_animal && h.alergia_animal !== 'No' && h.alergia_animal !== '—') alergias.push('🐾 Animal: ' + h.alergia_animal);
  if (h.alergia_med && h.alergia_med !== 'No' && h.alergia_med !== '—') alergias.push('💊 Medicamento: ' + h.alergia_med);
  if (h.otras_alergias && h.otras_alergias !== 'No' && h.otras_alergias !== '—') alergias.push('🌿 Otra: ' + h.otras_alergias);

  const condicionesBadges = (h.condiciones || []).map(c => `<span class="alert-tag">💊 ${c}</span>`).join(' ');

  document.getElementById('modal-content').innerHTML = `
    <div class="modal-header">
      <div class="modal-avatar ${avatarClass}">${ini}</div>
      <div style="flex:1">
        <div class="modal-name">${s.nombre}</div>
        <div class="modal-matricula">${s.matricula}</div>
        <span class="modal-grupo-badge ${badgeClass}">${badgeLabel}</span>
      </div>
      <button class="modal-close" onclick="closeModal()">✕</button>
    </div>
    <div class="modal-body">

      <div style="display:flex;gap:8px;margin-top:16px">
        <button class="action-btn btn-call" style="flex:1" onclick="window.location='tel:${s.celular}'">📞 Llamar</button>
        <button class="action-btn btn-whatsapp" style="flex:1" onclick="window.location='https://wa.me/52${s.celular}'">💬 WhatsApp</button>
      </div>
      <button class="action-btn btn-email" onclick="window.location='mailto:${s.correo_personal || s.correo_inst}'">✉️ ${s.correo_personal || s.correo_inst}</button>

      <div class="section-group">
        <div class="section-title">Información Personal</div>
        <div class="info-row">
          <span class="info-icon">🎂</span>
          <div class="info-content">
            <div class="info-label">Fecha de nacimiento</div>
            <div class="info-value">${formatDate(s.nacimiento)} · ${edad(s.nacimiento)}</div>
          </div>
        </div>
        <div class="info-row">
          <span class="info-icon">🏫</span>
          <div class="info-content">
            <div class="info-label">Prepa origen</div>
            <div class="info-value">${s.prepa}</div>
          </div>
        </div>
        <div class="info-row">
          <span class="info-icon">📱</span>
          <div class="info-content">
            <div class="info-label">Celular</div>
            <div class="info-value"><a href="tel:${s.celular}">${s.celular}</a></div>
          </div>
        </div>
        ${s.tel_casa ? `<div class="info-row">
          <span class="info-icon">🏠</span>
          <div class="info-content">
            <div class="info-label">Teléfono casa</div>
            <div class="info-value"><a href="tel:${s.tel_casa}">${s.tel_casa}</a></div>
          </div>
        </div>` : ''}
        <div class="info-row">
          <span class="info-icon">📧</span>
          <div class="info-content">
            <div class="info-label">Correo institucional</div>
            <div class="info-value">${s.correo_inst}</div>
          </div>
        </div>
        ${s.correo_personal && s.correo_personal !== s.correo_inst ? `<div class="info-row">
          <span class="info-icon">📩</span>
          <div class="info-content">
            <div class="info-label">Correo personal</div>
            <div class="info-value">${s.correo_personal}</div>
          </div>
        </div>` : ''}
        <div class="info-row">
          <span class="info-icon">📍</span>
          <div class="info-content">
            <div class="info-label">Dirección</div>
            <div class="info-value">${s.direccion}</div>
          </div>
        </div>
      </div>

      <div class="section-group">
        <div class="section-title">Documentos de Viaje</div>
        <div class="info-row">
          <span class="info-icon">🛂</span>
          <div class="info-content">
            <div class="info-label">Pasaporte</div>
            <div class="info-value">${s.pasaporte}</div>
          </div>
        </div>
        <div class="info-row">
          <span class="info-icon">🇺🇸</span>
          <div class="info-content">
            <div class="info-label">Visa americana</div>
            <div class="info-value">${s.visa_americana}</div>
          </div>
        </div>
      </div>

      <div class="section-group">
        <div class="section-title">Datos Médicos</div>
        <div class="info-row">
          <span class="info-icon">🩸</span>
          <div class="info-content">
            <div class="info-label">Tipo de sangre</div>
            <div class="info-value">${h.sangre || '—'}</div>
          </div>
        </div>
        <div class="info-row">
          <span class="info-icon">📏</span>
          <div class="info-content">
            <div class="info-label">Talla / Peso</div>
            <div class="info-value">${h.altura || '—'} · ${h.peso || '—'}</div>
          </div>
        </div>
        ${alergias.length > 0 ? `<div class="info-row">
          <span class="info-icon">⚠️</span>
          <div class="info-content">
            <div class="info-label">Alergias</div>
            <div class="info-value">${alergias.map(a => `<span class="alert-tag">${a}</span>`).join('<br>')}</div>
          </div>
        </div>` : ''}
        ${h.condiciones && h.condiciones.length > 0 ? `<div class="info-row">
          <span class="info-icon">💉</span>
          <div class="info-content">
            <div class="info-label">Antecedentes</div>
            <div class="info-value">${condicionesBadges}</div>
          </div>
        </div>` : ''}
        ${h.notas ? `<div class="info-row">
          <span class="info-icon">📋</span>
          <div class="info-content">
            <div class="info-label">Notas médicas</div>
            <div class="info-value">${h.notas}</div>
          </div>
        </div>` : ''}
        ${alergias.length === 0 && (!h.condiciones || h.condiciones.length === 0) ? `<div class="info-row">
          <span class="info-icon">✅</span>
          <div class="info-content">
            <div class="info-value"><span class="alert-tag ok">Sin alertas médicas registradas</span></div>
          </div>
        </div>` : ''}
      </div>

      ${s.padre && s.padre !== 'N/A' ? `<div class="section-group">
        <div class="section-title">Padre / Tutor</div>
        <div class="info-row">
          <span class="info-icon">👤</span>
          <div class="info-content">
            <div class="info-label">Nombre</div>
            <div class="info-value">${s.padre}</div>
          </div>
        </div>
        ${s.padre_cel ? `<div class="info-row">
          <span class="info-icon">📱</span>
          <div class="info-content">
            <div class="info-label">Celular</div>
            <div class="info-value"><a href="tel:${s.padre_cel}">${s.padre_cel}</a></div>
          </div>
        </div>` : ''}
        ${s.padre_tel && s.padre_tel !== s.padre_cel ? `<div class="info-row">
          <span class="info-icon">📞</span>
          <div class="info-content">
            <div class="info-label">Tel. casa</div>
            <div class="info-value"><a href="tel:${s.padre_tel}">${s.padre_tel}</a></div>
          </div>
        </div>` : ''}
        ${s.padre_of && s.padre_of !== s.padre_cel ? `<div class="info-row">
          <span class="info-icon">🏢</span>
          <div class="info-content">
            <div class="info-label">Tel. oficina</div>
            <div class="info-value"><a href="tel:${s.padre_of}">${s.padre_of}</a></div>
          </div>
        </div>` : ''}
        ${s.padre_correo ? `<div class="info-row">
          <span class="info-icon">📧</span>
          <div class="info-content">
            <div class="info-label">Correo</div>
            <div class="info-value"><a href="mailto:${s.padre_correo}">${s.padre_correo}</a></div>
          </div>
        </div>
        <button class="action-btn btn-call" onclick="window.location='tel:${s.padre_cel}'" style="margin-top:8px">📞 Llamar al tutor</button>
        ` : ''}
      </div>` : ''}

    </div>`;

  document.getElementById('modal-overlay').classList.add('open');
  document.body.style.overflow = 'hidden';
}

function closeModal(e) {
  if (e && e.target !== document.getElementById('modal-overlay')) return;
  document.getElementById('modal-overlay').classList.remove('open');
  document.body.style.overflow = '';
}

// Swipe down to close
let startY = 0;
document.getElementById('modal').addEventListener('touchstart', e => { startY = e.touches[0].clientY; });
document.getElementById('modal').addEventListener('touchend', e => {
  if (e.changedTouches[0].clientY - startY > 80) {
    document.getElementById('modal-overlay').classList.remove('open');
    document.body.style.overflow = '';
  }
});
</script>
</body>
</html>
