<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<title>Tablero de Priorización de Hipótesis</title>
<meta name="viewport" content="width=device-width,initial-scale=1"/>
<script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.1/dist/chart.umd.min.js"></script>
<style>
:root {
  --font: system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,sans-serif;
  --bg: #f5f7fa; --panel:#fff; --line:#dbe2ea;
  --accent:#0d6efd; --accent2:#8246d0;
  --ok:#198754; --warn:#cc8800; --danger:#c0382b;
}
* { box-sizing:border-box; }
body { margin:0; font-family:var(--font); background:var(--bg); color:#222; -webkit-font-smoothing:antialiased; }
header { padding:20px clamp(16px,3vw,48px) 12px; background:linear-gradient(90deg,var(--accent2),var(--accent)); color:#fff; }
header h1 { margin:0 0 4px; font-size:clamp(1.3rem,3vw,1.9rem); font-weight:600; }
header p { margin:0; font-size:.9rem; opacity:.92; max-width:900px; }
nav.tabs { display:flex; gap:6px; padding:10px clamp(16px,3vw,48px) 0; background:linear-gradient(90deg,var(--accent2),var(--accent)); flex-wrap:wrap; }
nav.tabs button {
  background:rgba(255,255,255,.15); border:none; color:#fff; padding:9px 16px;
  border-radius:10px 10px 0 0; font-size:.78rem; font-weight:600; cursor:pointer; letter-spacing:.3px;
}
nav.tabs button.active { background:#fff; color:var(--accent2); }
main { padding:20px clamp(16px,3vw,48px) 48px; display:grid; gap:28px; }
.view { display:none; } .view.active { display:block; }

.panel { background:var(--panel); border:1px solid var(--line); border-radius:14px; padding:18px 20px 22px; box-shadow:0 2px 4px rgba(0,0,0,.05); margin-bottom:22px; }
.panel h2 { margin:0 0 12px; font-size:1.1rem; font-weight:600; display:flex; align-items:center; gap:10px; color:#2c2f36; }
.panel h2 .pill { background:#eef2f7; padding:4px 10px; font-size:.65rem; border-radius:999px; color:#4a5665; font-weight:600; }
.sub { font-size:.78rem; color:#5d6774; margin:-6px 0 14px; line-height:1.35; }

/* Controles */
.controls { display:flex; flex-wrap:wrap; gap:10px; margin-bottom:14px; align-items:flex-end; }
.controls label { font-size:.62rem; font-weight:600; text-transform:uppercase; letter-spacing:.5px; margin:0 0 4px; color:#49525c; display:block; }
select, input[type=search], input[type=text], textarea {
  padding:7px 9px; border:1px solid var(--line); border-radius:8px; background:#fff; font-size:.76rem; min-width:140px; font-family:var(--font);
}
textarea { resize:vertical; min-width:100%; }
button.btn { border:none; padding:8px 15px; font-size:.72rem; font-weight:600; border-radius:8px; background:var(--accent2); color:#fff; cursor:pointer; }
button.btn.secondary { background:#eef1f6; color:#314152; }
button.btn.danger { background:var(--danger); color:#fff; }
button.btn.ok { background:var(--ok); color:#fff; }
button.btn:hover { filter:brightness(.95); }

/* Tabla */
.table-wrap { overflow-x:auto; border:1px solid var(--line); border-radius:12px; background:#fff; }
table { width:100%; border-collapse:separate; border-spacing:0; font-size:.7rem; min-width:1300px; }
thead th { position:sticky; top:0; background:#fafbfd; text-align:left; padding:9px 9px; font-weight:600; color:#334150; border-bottom:1px solid var(--line); white-space:nowrap; }
thead th.sortable { cursor:pointer; }
tbody td { padding:9px 9px; border-bottom:1px solid #eef2f6; line-height:1.25; vertical-align:top; }
tbody tr:hover td { background:#fbfcfe; }
.status { font-weight:600; font-size:.58rem; padding:4px 8px 3px; border-radius:999px; letter-spacing:.4px; text-transform:uppercase; background:#eceef2; color:#434d57; }
.status.v { background:#e5f7ed; color:var(--ok); }
.status.a { background:#fff5dc; color:var(--warn); }
.status.r { background:#fde6e3; color:var(--danger); }
.impacto,.esfuerzo { font-size:.62rem; font-weight:600; padding:3px 8px; border-radius:7px; display:inline-block; background:#edf0f4; color:#39424a; }
.impacto.alto{background:#ffe9e3;color:#c13826;} .impacto.medio{background:#fff4d8;color:#b67600;} .impacto.bajo{background:#e6f6eb;color:#1a7a45;}
.categoria { font-size:.58rem; font-weight:600; padding:3px 6px; border-radius:6px; background:#f2f5fa; letter-spacing:.3px; }
.rowbtns { display:flex; gap:5px; margin-top:4px; }
.rowbtns button { border:none; font-size:.58rem; padding:3px 7px; border-radius:6px; cursor:pointer; }
.empty { padding:26px; text-align:center; font-size:.75rem; color:#65717d; }

/* Guide Section */
.guide-section { background:#fafbfd; border:1px solid var(--line); border-radius:12px; padding:14px 16px; margin-top:18px; }
.guide-section h3 { margin:0 0 10px; font-size:.9rem; font-weight:700; color:#2c2f36; display:flex; align-items:center; gap:8px; }
.guide-section h3 .tag { background:#e5f7ed; color:var(--ok); padding:2px 8px; border-radius:4px; font-size:.6rem; font-weight:600; text-transform:uppercase; }
.guide-list { display:grid; gap:10px; font-size:.72rem; line-height:1.5; }
.guide-item { padding:10px 12px; background:#fff; border-left:3px solid var(--accent2); border-radius:4px; }
.guide-item strong { color:#2c2f36; font-weight:700; }
.guide-item em { color:#5d6774; font-style:italic; }
.guide-item code { background:#eef1f6; padding:1px 4px; border-radius:3px; font-family:monospace; font-size:.65rem; }

/* KANBAN */
.kanban { display:grid; grid-template-columns:repeat(3,1fr); gap:16px; }
@media (max-width:900px){ .kanban{grid-template-columns:1fr;} }
.kcol { background:#f6f8fb; border:1px solid var(--line); border-radius:12px; padding:12px; min-height:200px; }
.kcol h3 { margin:0 0 10px; font-size:.85rem; display:flex; justify-content:space-between; align-items:center; }
.kcol.v h3 { color:var(--ok); } .kcol.a h3 { color:var(--warn); } .kcol.r h3 { color:var(--danger); }
.kcount { background:#fff; border-radius:999px; padding:2px 8px; font-size:.65rem; font-weight:700; }
.kcard { background:#fff; border:1px solid var(--line); border-radius:10px; padding:10px 12px; margin-bottom:10px; cursor:grab; box-shadow:0 1px 3px rgba(0,0,0,.05); }
.kcard.dragging { opacity:.4; }
.kcard h4 { margin:0 0 4px; font-size:.75rem; font-weight:700; color:#28313a; }
.kcard p { margin:0 0 6px; font-size:.65rem; color:#556270; line-height:1.3; }
.kcard .metaline { display:flex; gap:5px; flex-wrap:wrap; }
.kcol.dragover { background:#eef3fb; border-color:var(--accent); }

/* DASHBOARD */
.kpis { display:grid; grid-template-columns:repeat(6,1fr); gap:14px; margin-bottom:18px; }
@media (max-width:900px){ .kpis{grid-template-columns:repeat(2,1fr);} }
.kpi { background:#fff; border:1px solid var(--line); border-radius:12px; padding:14px 16px; text-align:center; }
.kpi .num { font-size:1.6rem; font-weight:700; color:var(--accent2); }
.kpi .lbl { font-size:.65rem; color:#5d6774; text-transform:uppercase; letter-spacing:.4px; margin-top:2px; }
.charts { display:grid; grid-template-columns:1fr 1fr; gap:18px; }
@media (max-width:900px){ .charts{grid-template-columns:1fr;} }
.chart-box { background:#fff; border:1px solid var(--line); border-radius:12px; padding:14px; }
.chart-box h4 { margin:0 0 8px; font-size:.8rem; color:#334150; }

/* Modal CRUD */
.modal-backdrop { position:fixed; inset:0; background:rgba(20,25,35,.55); display:none; align-items:center; justify-content:center; z-index:50; padding:20px; }
.modal-backdrop.open { display:flex; }
.modal { background:#fff; border-radius:14px; width:min(720px,100%); max-height:88vh; overflow-y:auto; padding:22px 24px 20px; }
.modal h3 { margin:0 0 14px; font-size:1.05rem; }
.form-grid { display:grid; grid-template-columns:1fr 1fr; gap:10px 14px; }
.form-grid .full { grid-column:1/-1; }
.form-grid label { font-size:.62rem; font-weight:700; text-transform:uppercase; color:#49525c; display:block; margin:0 0 3px; }
.modal-actions { display:flex; justify-content:flex-end; gap:8px; margin-top:16px; }

.badge-inline { background:#eef1f6; padding:2px 6px; border-radius:6px; font-size:.55rem; font-weight:600; }
</style>
</head>
<body>
<header>
  <h1>Tablero de Priorización</h1>
  <p>Visualiza y prioriza hipótesis según Impacto, Esfuerzo y Estado.  Gestiona, visualiza y prioriza tus hipótesis en 3 vistas: Tabla, Kanban y Dashboard.</p>
</header>

<nav class="tabs">
  <button class="tabbtn active" data-view="tabla">📋 Tabla</button>
  <button class="tabbtn" data-view="kanban">🗂️ Kanban</button>
  <button class="tabbtn" data-view="dashboard">📊 Dashboard</button>
</nav>

<main>
  <!-- ============ VISTA TABLA ============ -->
  <section class="view active" id="view-tabla">
    <div class="panel">
      <h2>Hipótesis Registradas <span class="pill">CRUD</span></h2>
      <div class="sub">Edita, elimina o agrega nuevas hipótesis (ej. tu "Supuesto 2" y "Supuesto 3" pendientes). Todo se guarda automáticamente en tu navegador.</div>
      <div class="controls">
        <div><label>Estado</label>
          <select id="fEstado"><option value="">Todos</option><option value="v">Verde</option><option value="a">Amarillo</option><option value="r">Rojo</option><option value=nN">Nuevo</option></select>
        </div>
        <div><label>Impacto</label>
          <select id="fImpacto"><option value="">Todos</option><option value="alto">Alto</option><option value="medio">Medio</option><option value="bajo">Bajo</option></select>
        </div>
        <div><label>Fase DT</label>
          <select id="fFase"><option value="">Todas</option><option value="Empatizar">Empatizar</option><option value="Definir">Definir</option><option value="Idear">Idear</option><option value="Definir/Idear/Prototipar">Definir/Idear/Prototipar</option><option value="Prototipar">Prototipar</option><option value="Testear">Testear</option></select>
        </div>
        <div style="flex:1;min-width:180px;"><label>Buscar</label>
          <input type="search" id="fBusca" placeholder="Causa, métrica, variable...">
        </div>
        <div><label>&nbsp;</label><button class="btn secondary" id="btnClear">Limpiar</button></div>
        <div><label>&nbsp;</label><button class="btn" id="btnNew">+ Nueva Hipótesis</button></div>
        <div><label>&nbsp;</label><button class="btn secondary" id="btnExport">Exportar JSON</button></div>
      </div>
      <div class="table-wrap">
        <table id="tabla">
          <thead><tr>
  <th class="sortable" data-key="id">ID</th>
  <th>Fase DT</th>
  <th>Causa / Supuesto</th>
  <th>Métrica clave</th>
  <th class="sortable" data-key="impacto">Impacto</th>
  <th class="sortable" data-key="esfuerzo">Esfuerzo</th>
  <th class="sortable" data-key="score">Score</th>
  <th>Minimum Analytical Experiment</th>
  <th>Estado</th>
  <th>Patrón esperado / Refutación</th>
  <th>Acción confirma</th>
  <th>Acción refuta</th>
  <th>Valor para usuario</th>
  <th>Acciones</th>
</tr></thead>
          <tbody></tbody>
        </table>
                <div class="empty" id="noRes" hidden>
          No hay hipótesis que coincidan con los filtros.
        </div>
      </div>

      <div class="guide-section">
        <h3>📖 Cómo calcular la priorización <span class="tag">Guía</span></h3>

        <div class="guide-list">
          <div class="guide-item">
            <strong>1. Prioridad:</strong>
            Sirve para decidir qué hipótesis revisar primero.
            En general, conviene empezar por las que pueden tener mayor impacto
            y requieren menos esfuerzo para comprobarse.
          </div>

          <div class="guide-item">
            <strong>2. Impacto:</strong>
            Pregunta: <em>“Si esta hipótesis es cierta, ¿cuánto podría cambiar
            la métrica que me importa?”</em>
            Usa <strong>3 = alto</strong>, <strong>2 = medio</strong> y
            <strong>1 = bajo</strong>.
          </div>

          <div class="guide-item">
            <strong>3. Esfuerzo:</strong>
            Estima cuánto tiempo necesitas para obtener datos fiables:
            <strong>1 = ≤30 min</strong>, <strong>2 = ≤2 h</strong> y
            <strong>3 = &gt;2 h</strong>.
          </div>

          <div class="guide-item">
            <strong>4. Estado:</strong>
            Indica qué tan preparados están los datos:
            <strong>Verde = listos</strong>,
            <strong>Amarillo = falta validar</strong>,
            <strong>Rojo = bloqueo</strong> y
            <strong>Nuevo = sin revisión</strong>.
          </div>

          <div class="guide-item">
            <strong>5. Score:</strong>
            Se calcula como <code>ImpactoNum / EsfuerzoNum</code>.
            Por ejemplo, <code>3/1 = 3.0</code>.
            Un score más alto significa que vale más la pena investigar primero.
            Se resta <strong>0.5</strong> si está Amarillo y
            <strong>1</strong> si está Rojo.
          </div>

          <div class="guide-item">
            <strong>6. ¿Qué hacer?</strong>
            Ordena las hipótesis por Score, empieza por las
            <strong>3 primeras</strong>, ejecuta las queries mínimas necesarias
            y clasifica el resultado como
            <strong>Confirmada</strong>, <strong>Refutada</strong> o
            <strong>Indeterminada</strong>.
          </div>

          <div class="guide-item">
            <strong>💡 Tip:</strong>
            Si dos hipótesis necesitan casi los mismos datos, compruébalas juntas
            en un <strong>micro-batch</strong>. Así evitas repetir trabajo de limpieza.
          </div>
        </div>
      </div>

    </div>
  </section>

  <!-- ============ VISTA KANBAN ============ -->
  <section class="view" id="view-kanban">
    <div class="panel">
      <h2>Kanban por Semáforo <span class="pill">ARRASTRABLE</span></h2>
     <div class="sub">Arrastra una tarjeta entre columnas para actualizar su Estado (V/A/R) al avanzar en la validación. <strong>V</strong>=lista para correr hoy · <strong>A</strong>=falta 1 dato · <strong>R</strong>=falta variable clave/patrón.</div>
      <div class="kanban">
        <div class="kcol v" data-estado="v"><h3>🟢 Verde <span class="kcount" id="cnt-v">0</span></h3><div class="kbody" id="kcol-v"></div></div>
        <div class="kcol a" data-estado="a"><h3>🟡 Amarillo <span class="kcount" id="cnt-a">0</span></h3><div class="kbody" id="kcol-a"></div></div>
        <div class="kcol r" data-estado="r"><h3>🔴 Rojo <span class="kcount" id="cnt-r">0</span></h3><div class="kbody" id="kcol-r"></div></div>
      </div>
    </div>
  </section>

  <!-- ============ VISTA DASHBOARD ============ -->
  <section class="view" id="view-dashboard">
    <div class="panel">
      <h2>Dashboard de Avance <span class="pill">RESUMEN</span></h2>
      <div class="sub">Vista ejecutiva para reportar el estado del sprint de validación de hipótesis.</div>
      <div class="kpis">
        <div class="kpi"><div class="num" id="kpi-total">0</div><div class="lbl">Hipótesis totales</div></div>
        <div class="kpi"><div class="num" id="kpi-verde">0</div><div class="lbl">Listas (Verde)</div></div>
        <div class="kpi"><div class="num" id="kpi-score">0</div><div class="lbl">Score promedio</div></div>
        <div class="kpi"><div class="num" id="kpi-altas">0</div><div class="lbl">Impacto Alto</div></div>
        <div class="kpi"><div class="num" id="kpi-confirmed">0</div><div class="lbl">Confirmadas (MAD)</div></div>
        <div class="kpi"><div class="num" id="kpi-refuted">0</div><div class="lbl">Refutadas (MAD)</div></div>
      </div>
      <div class="charts">
        <div class="chart-box"><h4>Distribución por Estado</h4><canvas id="chartEstado" height="220"></canvas></div>
        <div class="chart-box"><h4>Distribución por Fase Design Thinking</h4><canvas id="chartFase" height="220"></canvas></div>
        <div class="chart-box" style="grid-column:1/-1;"><h4>Score por Hipótesis (mayor a menor)</h4><canvas id="chartScore" height="140"></canvas></div>
      </div>
    </div>
  </section>
</main>

<!-- ============ MODAL CRUD ============ -->
<div class="modal-backdrop" id="modalBackdrop">
  <div class="modal">
    <h3 id="modalTitle">Nueva Hipótesis</h3>
    <div class="form-grid">
      <div><label>ID</label><input type="text" id="f_id"></div>
      <div><label>Fase DT origen</label>
        <select id="f_fase"><option value="empatizar">Empatizar</option><option value="definir">Definir</option><option value="idear">Idear</option><option value="Definir/Idear/Prototipar">Definir/Idear/Prototipar</option><option value="Prototipar">Prototipar</option><option value="Testear">Testear</option></select>
      </div>
      <div class="full"><label>Causa / Supuesto central</label><textarea id="f_causa" rows="2"></textarea></div>
      <div class="full"><label>Insight de empatía</label><textarea id="f_insight" rows="2"></textarea></div>
      <div class="full"><label>Métrica clave (nombre + fórmula)</label><input type="text" id="f_metrica"></div>
      <div><label>Impacto</label>
        <select id="f_impacto"><option value="alto">Alto</option><option value="medio">Medio</option><option value="bajo">Bajo</option></select>
      </div>
      <div><label>Esfuerzo</label>
        <select id="f_esfuerzo"><option value="bajo">Bajo</option><option value="medio">Medio</option><option value="alto">Alto</option></select>
      </div>
      <div class="full"><label>Patrón esperado (confirma)</label><input type="text" id="f_patron"></div>
      <div class="full"><label>Condición de refutación</label><input type="text" id="f_refutacion"></div>
      <div class="full"><label>Acción si confirma</label><input type="text" id="f_accionC"></div>
      <div class="full"><label>Acción si refuta</label><input type="text" id="f_accionR"></div>
      <div class="full"><label>Valor esperado para el residente</label><input type="text" id="f_valor"></div>
      <div><label>Estado</label>
        <select id="f_estado"><option value="v">Verde</option><option value="a">Amarillo</option><option value="r">Rojo</option><option value=nN">Nuevo</option></select>
      </div>
      <div class="full"><label>Minimum Analytical Experiment (MAD) — valor numérico</label><input type="number" id="f_mad" step="0.01" placeholder="ej. 13.9"></div>
    </div>
    <div class="modal-actions">
      <button class="btn secondary" id="btnCancel">Cancelar</button>
      <button class="btn ok" id="btnSave">Guardar</button>
    </div>
  </div>
</div>

<script>
/* ============== DATOS BASE (de tu Excel) ============== */
const STORAGE_KEY = "afontibon_hipotesis_v1";

const seedData = [
  {
    id:"H-01",
    fase:"Empatizar",
    causa:"Uso de parqueaderos alternativos por déficit físico real de cupos dentro del conjunto. Si se integra la comunidad completa al sistema de asignación de espacios de parqueaderos, entonces los residentes de Altos de Fontibón tendrán sus vehículos asegurados.",
    insight:"El usuario carece de un lugar seguro para su vehículo.",
    metrica:"IRSV = (Vehículos Afectados por Robos/Daños / Total Vehículos en Vía Pública) × 100",
    impacto:"alto",
    esfuerzo:"medio",
    estado:"a",
    patron:"IRSV ≤ 13,9%",
    refutacion:"IRSV ≥ 16%",
    accionConfirma:"Registro de la población beneficiada para el desarrollo de la integración semana tras semana.",
    accionRefuta:"Outsourcing de seguridad en zonas donde los vehículos queden expuestos.",
    valorUsuario:"Reducción en el gasto promedio semanal de los residentes en sus vehículos.",
    riesgo:"Altos de Fontibón perdería los recursos utilizados en la gestión del software de asignación."
  },
  {
    id:"H-02",
    fase:"Definir",
    causa:"Si se reasignan los cupos subutilizados de visitantes hacia un modelo rotativo para residentes con carros en vía pública, entonces el IRSV se reducirá en un 20% en el próximo trimestre, porque la falta de disponibilidad de espacio físico es el factor que obliga al parqueo alternativo.",
    insight:"Monitoreo de riesgos derivados de la gestión de parqueaderos (comparendos, robos, daños, gastos adicionales).",
    metrica:"IRSV = (N° robos/daños/rayones reportados / Total vehículos residentes expuestos en vía pública) × 100",
    impacto:"alto",
    esfuerzo:"medio",
    estado:"a",
    patron:"IRSV ≤ 13,9% (meta: reducción del 20% trimestral)",
    refutacion:"IRSV ≥ 16%",
    accionConfirma:"Implementar modelo rotativo de cupos de visitantes para residentes.",
    accionRefuta:"Explorar estrategias externas (outsourcing de seguridad / ampliación física).",
    valorUsuario:"Mayor seguridad vehicular y menor exposición a comparendos, robos y daños.",
    riesgo:"Falsos negativos si los residentes no denuncian daños menores; posible inflación en periodos con eventos aislados de inseguridad."
  },
  {
    id:"H-03",
    fase:"Idear",
    causa:"[Escribe tu supuesto 3] — Espacio reservado para tu próxima hipótesis del sprint.",
    insight:"",
    metrica:"",
    impacto:"medio",
    esfuerzo:"medio",
    estado:"r",
    patron:"",
    refutacion:"",
    accionConfirma:"",
    accionRefuta:"",
    valorUsuario:"",
    riesgo:""
  }
];

const impactoWeight = {alto:3, medio:2, bajo:1};
const esfuerzoWeight = {bajo:1, medio:2, alto:3};
const estadoPenalty = {v:0, a:0.5, r:1};

function computeScore(h){
  const base = impactoWeight[h.impacto] / esfuerzoWeight[h.esfuerzo];
  const score = base - (estadoPenalty[h.estado]||0);
  return Number(score.toFixed(2));
}

function loadData(){
  const raw = localStorage.getItem(STORAGE_KEY);
  if(raw){
    try { return JSON.parse(raw); } catch(e){ return [...seedData]; }
  }
  return [...seedData];
}
function saveData(){
  localStorage.setItem(STORAGE_KEY, JSON.stringify(hipotesisData));
}

let hipotesisData = loadData();
let currentSort = {key:"", asc:true};
let editingId = null;

function esc(s){ return (s||"").toString().replace(/[&<>\"']/g,m=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[m])); }
function cap(s){ return s? s.charAt(0).toUpperCase()+s.slice(1) : s; }
function estadoLabel(e){ return {v:"Verde",a:"Amarillo",r:"Rojo"}[e]||e; }

/* ============== EVALUAR MAD ============== */
function safeId(s){ return (s||"").toString().replace(/[^a-zA-Z0-9_-]/g,'_'); }
function parseCondition(text){
  if(!text) return null;
  // Busca operador y número (acepta coma como decimal y %)
  const m = text.match(/([<>≤≥]=?|=)\s*([0-9]+(?:[.,][0-9]+)?)/);
  if(!m){
    // si no hay operador, busca primer número
    const m2 = text.match(/([0-9]+(?:[.,][0-9]+)?)/);
    if(!m2) return null;
    return {op:'=', val:parseFloat(m2[1].replace(',', '.'))};
  }
  const op = m[1].replace('≤','<=').replace('≥','>=');
  const val = parseFloat(m[2].replace(',', '.'));
  return {op, val};
}
function applyOp(op, a, b){
  if(op==='<=') return a <= b;
  if(op==='>=') return a >= b;
  if(op==='<' ) return a < b;
  if(op==='>' ) return a > b;
  if(op==='=') return a === b;
  return false;
}
function evaluateMad(h){
  const v = (h.madValue===undefined || h.madValue===null || h.madValue==='') ? null : Number(h.madValue);
  if(v===null) return null;
  const condP = parseCondition(h.patron);
  const condR = parseCondition(h.refutacion);
  if(condP && applyOp(condP.op, v, condP.val)) return 'Confirmada';
  if(condR && applyOp(condR.op, v, condR.val)) return 'Refutada';
  return 'Indeterminada';
}

/* ============== TABLA ============== */
function getFiltered(){
  const estado = document.getElementById("fEstado").value;
  const impacto = document.getElementById("fImpacto").value;
  const fase = document.getElementById("fFase").value;
  const busca = document.getElementById("fBusca").value.trim().toLowerCase();
  let list = hipotesisData.filter(h=>{
    let ok = true;
    if(estado && h.estado!==estado) ok=false;
    if(impacto && h.impacto!==impacto) ok=false;
    if(fase && h.fase!==fase) ok=false;
    if(busca){
      const blob = (h.id+" "+h.causa+" "+h.metrica+" "+h.accionConfirma+" "+h.accionRefuta).toLowerCase();
      if(!blob.includes(busca)) ok=false;
    }
    return ok;
  });
  list.forEach(h=> h.score = computeScore(h));
  if(currentSort.key){
    list.sort((a,b)=>{
      const av=a[currentSort.key], bv=b[currentSort.key];
      if(typeof av==="number" && typeof bv==="number") return currentSort.asc? av-bv : bv-av;
      return currentSort.asc ? (""+av).localeCompare(""+bv) : (""+bv).localeCompare(""+av);
    });
  }
  return list;
}

function renderTable(){
  const list = getFiltered();
  const tbody = document.querySelector("#tabla tbody");
  tbody.innerHTML = "";
  document.getElementById("noRes").hidden = list.length > 0;

  list.forEach(h=>{
    const tr = document.createElement("tr");

    const safe = safeId(h.id);
    const madVal = (h.madValue===undefined || h.madValue===null || h.madValue==='') ? '' : h.madValue;
    const madResult = evaluateMad(h) || '—';

    tr.innerHTML = `
      <td>
        <strong>${esc(h.id)}</strong><br>
        <span style="font-size:.6rem;color:#66727f;">Score ${h.score}</span>
      </td>

      <td>
        <span class="categoria">${esc(h.fase)}</span>
      </td>

      <td>${esc(h.causa)}</td>

      <td>
        ${esc(h.metrica) || '<span style="color:#aab3bd">— sin definir —</span>'}
      </td>

      <td>
        <span class="impacto ${h.impacto}">
          ${cap(h.impacto)}
        </span>
      </td>

      <td>
        <span class="esfuerzo ${h.esfuerzo}">
          ${cap(h.esfuerzo)}
        </span>
      </td>

      <td style="font-weight:700;color:#2d3a46;">
        ${h.score}
      </td>

      <td>
        <div style="display:flex;gap:6px;align-items:center;">
          <input type="number" id="mad_${safe}" value="${madVal}" step="0.01" style="width:90px;padding:6px;border:1px solid var(--line);border-radius:6px;">
          <button class="btn secondary" style="padding:6px 8px;font-size:.7rem;" onclick="saveMad('${h.id}')">Comprobar</button>
        </div>
        <div style="margin-top:6px;font-size:.65rem;color:#56606a;">Resultado: <strong>${madResult}</strong></div>
      </td>

      <td>
        <span class="status ${h.estado}">
          ${estadoLabel(h.estado)}
        </span>
      </td>

      <td>
        <div><strong>P:</strong> ${esc(h.patron) || '—'}</div>
        <div><strong>R:</strong> ${esc(h.refutacion) || '—'}</div>
      </td>

      <td>
        ${esc(h.accionConfirma) || '—'}
      </td>

      <td>
        ${esc(h.accionRefuta) || '—'}
      </td>

      <td>
        ${esc(h.valorUsuario) || '—'}
      </td>

      <td>
        <div class="rowbtns">
          <button class="btn secondary" style="padding:4px 8px;" onclick="openEdit('${h.id}')">✏️</button>
          <button class="btn danger" style="padding:4px 8px;" onclick="deleteHip('${h.id}')">🗑️</button>
        </div>
      </td>
    `;

    tbody.appendChild(tr);
  });
}

function saveMad(id){
  const h = hipotesisData.find(x=>x.id===id);
  if(!h) return;
  const safe = safeId(id);
  const el = document.getElementById('mad_'+safe);
  if(!el) return;
  const v = el.value.trim();
  if(v===''){
    h.madValue = null; h.madResult = null; saveData(); renderAll(); alert('MAD limpiado.'); return;
  }
  const num = Number(v);
  if(Number.isNaN(num)) { alert('Ingrese un número válido para MAD'); return; }
  h.madValue = num;
  h.madResult = evaluateMad(h);
  saveData(); renderAll();
  if(h.madResult==='Confirmada') alert(`Resultado: Confirmada — MAD=${num}`);
  else if(h.madResult==='Refutada') alert(`Resultado: Refutada — MAD=${num}`);
  else alert(`Resultado: Indeterminada — MAD=${num}`);
}

function bindSort(){
  document.querySelectorAll("th.sortable").forEach(th=>{
    th.addEventListener("click", ()=>{
      const key = th.dataset.key;
      if(currentSort.key===key) currentSort.asc = !currentSort.asc;
      else { currentSort.key=key; currentSort.asc=true; }
      renderTable();
    });
  });
}

function exportJSON(){
  const data = getFiltered();
  const blob = new Blob([JSON.stringify(data,null,2)], {type:"application/json"});
  const url = URL.createObjectURL(blob);
  const a = document.createElement("a");
  a.href=url; a.download="hipotesis_altos_fontibon.json"; document.body.appendChild(a); a.click(); a.remove();
  URL.revokeObjectURL(url);
}

/* ============== CRUD MODAL ============== */
function openNew(){
  editingId = null;
  document.getElementById("modalTitle").textContent = "Nueva Hipótesis";
  ["f_id","f_causa","f_insight","f_metrica","f_patron","f_refutacion","f_accionC","f_accionR","f_valor","f_mad"].forEach(id=>document.getElementById(id).value="");
  document.getElementById("f_fase").value="Empatizar";
  document.getElementById("f_impacto").value="medio";
  document.getElementById("f_esfuerzo").value="medio";
  document.getElementById("f_estado").value="r";
  document.getElementById("f_id").value = "H-" + String(hipotesisData.length+1).padStart(2,"0");
  document.getElementById("modalBackdrop").classList.add("open");
}
function openEdit(id){
  const h = hipotesisData.find(x=>x.id===id);
  if(!h) return;
  editingId = id;
  document.getElementById("modalTitle").textContent = "Editar Hipótesis";
  document.getElementById("f_id").value = h.id;
  document.getElementById("f_fase").value = h.fase;
  document.getElementById("f_causa").value = h.causa;
  document.getElementById("f_insight").value = h.insight;
  document.getElementById("f_metrica").value = h.metrica;
  document.getElementById("f_impacto").value = h.impacto;
  document.getElementById("f_esfuerzo").value = h.esfuerzo;
  document.getElementById("f_patron").value = h.patron;
  document.getElementById("f_refutacion").value = h.refutacion;
  document.getElementById("f_accionC").value = h.accionConfirma;
  document.getElementById("f_accionR").value = h.accionRefuta;
  document.getElementById("f_valor").value = h.valorUsuario;
  document.getElementById("f_estado").value = h.estado;
  document.getElementById("f_mad").value = (h.madValue===undefined || h.madValue===null) ? '' : h.madValue;
  document.getElementById("modalBackdrop").classList.add("open");
}
function closeModal(){ document.getElementById("modalBackdrop").classList.remove("open"); }
function deleteHip(id){
  if(!confirm("¿Eliminar esta hipótesis?")) return;
  hipotesisData = hipotesisData.filter(h=>h.id!==id);
  saveData(); renderAll();
}
function saveForm(){
  const newObj = {
    id: document.getElementById("f_id").value.trim() || ("H-"+Date.now()),
    fase: document.getElementById("f_fase").value,
    causa: document.getElementById("f_causa").value.trim(),
    insight: document.getElementById("f_insight").value.trim(),
    metrica: document.getElementById("f_metrica").value.trim(),
    impacto: document.getElementById("f_impacto").value,
    esfuerzo: document.getElementById("f_esfuerzo").value,
    patron: document.getElementById("f_patron").value.trim(),
    refutacion: document.getElementById("f_refutacion").value.trim(),
    accionConfirma: document.getElementById("f_accionC").value.trim(),
    accionRefuta: document.getElementById("f_accionR").value.trim(),
    valorUsuario: document.getElementById("f_valor").value.trim(),
    estado: document.getElementById("f_estado").value,
    riesgo: "",
    madValue: (document.getElementById("f_mad").value.trim()==='') ? null : Number(document.getElementById("f_mad").value.trim())
  };
  newObj.madResult = evaluateMad(newObj);
  if(editingId){
    const idx = hipotesisData.findIndex(h=>h.id===editingId);
    if(idx>-1) hipotesisData[idx] = {...hipotesisData[idx], ...newObj};
  } else {
    hipotesisData.push(newObj);
  }
  saveData();
  closeModal();
  renderAll();
  if(newObj.madValue!==null){
    if(newObj.madResult==='Confirmada') alert(`Resultado: Confirmada — MAD=${newObj.madValue}`);
    else if(newObj.madResult==='Refutada') alert(`Resultado: Refutada — MAD=${newObj.madValue}`);
    else alert(`Resultado: Indeterminada — MAD=${newObj.madValue}`);
  }
}

/* ============== KANBAN ============== */
function renderKanban(){
  ["v","a","r"].forEach(est=>{
    const col = document.getElementById("kcol-"+est);
    col.innerHTML = "";
    const items = hipotesisData.filter(h=>h.estado===est);
    document.getElementById("cnt-"+est).textContent = items.length;
    items.forEach(h=>{
      const card = document.createElement("div");
      card.className = "kcard";
      card.draggable = true;
      card.dataset.id = h.id;
      card.innerHTML = `
        <h4>${esc(h.id)} — ${esc(h.fase)}</h4>
        <p>${esc(h.causa).slice(0,140)}${h.causa.length>140?"…":""}</p>
        <div class="metaline">
          <span class="impacto ${h.impacto}">${cap(h.impacto)}</span>
          <span class="badge-inline">Score ${computeScore(h)}</span>
        </div>
      `;
      card.addEventListener("dragstart", ()=>{ card.classList.add("dragging"); });
      card.addEventListener("dragend", ()=>{ card.classList.remove("dragging"); });
      col.appendChild(card);
    });
  });
}
function bindKanbanDrop(){
  document.querySelectorAll(".kcol").forEach(col=>{
    col.addEventListener("dragover", e=>{ e.preventDefault(); col.classList.add("dragover"); });
    col.addEventListener("dragleave", ()=> col.classList.remove("dragover"));
    col.addEventListener("drop", e=>{
      e.preventDefault();
      col.classList.remove("dragover");
      const dragging = document.querySelector(".kcard.dragging");
      if(!dragging) return;
      const id = dragging.dataset.id;
      const nuevoEstado = col.dataset.estado;
      const h = hipotesisData.find(x=>x.id===id);
      if(h){ h.estado = nuevoEstado; saveData(); renderAll(); }
    });
  });
}

/* ============== DASHBOARD ============== */
let chartEstadoRef=null, chartFaseRef=null, chartScoreRef=null;
function renderDashboard(){
  hipotesisData.forEach(h=> h.score = computeScore(h));
  document.getElementById("kpi-total").textContent = hipotesisData.length;
  document.getElementById("kpi-verde").textContent = hipotesisData.filter(h=>h.estado==="v").length;
  const avg = hipotesisData.length ? (hipotesisData.reduce((s,h)=>s+h.score,0)/hipotesisData.length).toFixed(2) : 0;
  document.getElementById("kpi-score").textContent = avg;
  document.getElementById("kpi-altas").textContent = hipotesisData.filter(h=>h.impacto==="alto").length;

  // contar resultados MAD
  let confirmed=0, refuted=0;
  hipotesisData.forEach(h=>{
    const res = evaluateMad(h);
    if(res==='Confirmada') confirmed++;
    if(res==='Refutada') refuted++;
  });
  document.getElementById("kpi-confirmed").textContent = confirmed;
  document.getElementById("kpi-refuted").textContent = refuted;

  const estadoCounts = {v:0,a:0,r:0};
  hipotesisData.forEach(h=> estadoCounts[h.estado] = (estadoCounts[h.estado]||0)+1);
  const faseCounts = {};
  hipotesisData.forEach(h=> faseCounts[h.fase] = (faseCounts[h.fase]||0)+1);

  if(chartEstadoRef) chartEstadoRef.destroy();
  chartEstadoRef = new Chart(document.getElementById("chartEstado"), {
    type:"doughnut",
    data:{ labels:["Verde","Amarillo","Rojo"], datasets:[{ data:[estadoCounts.v,estadoCounts.a,estadoCounts.r], backgroundColor:["#198754","#cc8800","#c0382b"] }] },
    options:{ plugins:{legend:{position:"bottom", labels:{font:{size:10}}}} }
  });

  if(chartFaseRef) chartFaseRef.destroy();
  chartFaseRef = new Chart(document.getElementById("chartFase"), {
    type:"pie",
    data:{ labels:Object.keys(faseCounts), datasets:[{ data:Object.values(faseCounts), backgroundColor:["#0d6efd","#8246d0","#2e6fa7","#e67e22"] }] },
    options:{ plugins:{legend:{position:"bottom", labels:{font:{size:10}}}} }
  });

  const sorted = [...hipotesisData].sort((a,b)=>b.score-a.score);
  if(chartScoreRef) chartScoreRef.destroy();
  chartScoreRef = new Chart(document.getElementById("chartScore"), {
    type:"bar",
    data:{ labels:sorted.map(h=>h.id), datasets:[{ label:"Score", data:sorted.map(h=>h.score), backgroundColor:"#8246d0" }] },
    options:{ indexAxis:"y", plugins:{legend:{display:false}}, scales:{x:{beginAtZero:true}} }
  });
}

/* ============== TABS ============== */
function bindTabs(){
  document.querySelectorAll(".tabbtn").forEach(btn=>{
    btn.addEventListener("click", ()=>{
      document.querySelectorAll(".tabbtn").forEach(b=>b.classList.remove("active"));
      document.querySelectorAll(".view").forEach(v=>v.classList.remove("active"));
      btn.classList.add("active");
      document.getElementById("view-"+btn.dataset.view).classList.add("active");
      if(btn.dataset.view==="dashboard") renderDashboard();
      if(btn.dataset.view==="kanban") renderKanban();
    });
  });
}

function renderAll(){
  renderTable();
  renderKanban();
  renderDashboard();
}

document.addEventListener("DOMContentLoaded", ()=>{
  renderAll();
  bindSort();
  bindKanbanDrop();
  bindTabs();
  ["fEstado","fImpacto","fFase"].forEach(id=> document.getElementById(id).addEventListener("change", renderTable));
  document.getElementById("fBusca").addEventListener("input", renderTable);
  document.getElementById("btnClear").addEventListener("click", ()=>{
    ["fEstado","fImpacto","fFase"].forEach(id=>document.getElementById(id).value="");
    document.getElementById("fBusca").value="";
    currentSort.key=""; renderTable();
  });
  document.getElementById("btnNew").addEventListener("click", openNew);
  document.getElementById("btnExport").addEventListener("click", exportJSON);
  document.getElementById("btnCancel").addEventListener("click", closeModal);
  document.getElementById("btnSave").addEventListener("click", saveForm);
  document.getElementById("modalBackdrop").addEventListener("click", (e)=>{ if(e.target.id==="modalBackdrop") closeModal(); });
});
</script>
</body>
</html>
