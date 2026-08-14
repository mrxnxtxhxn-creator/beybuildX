<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beyblade X — Master Collection & Builder</title>
    <style>
        :root {
            --bg-dark: #0f1117;
            --bg-card: #181b24;
            --bg-card-hover: #222634;
            --accent-primary: #ff5500;
            --accent-blue: #00d2ff;
            --accent-green: #00e676;
            --text-main: #f0f2f5;
            --text-muted: #9aa0a6;
            --border-color: #2a2f3d;
            --radius: 12px;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', system-ui, sans-serif; }
        body { background-color: var(--bg-dark); color: var(--text-main); padding: 20px; }
        .container { max-width: 1350px; margin: 0 auto; }

        header {
            text-align: center; margin-bottom: 25px; padding: 20px;
            background: linear-gradient(135deg, rgba(255,85,0,0.15) 0%, rgba(0,210,255,0.15) 100%);
            border: 1px solid var(--border-color); border-radius: var(--radius);
        }
        header h1 {
            font-size: 2.2rem;
            background: linear-gradient(90deg, var(--accent-primary), var(--accent-blue));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
            margin-bottom: 8px; text-transform: uppercase;
        }

        .builder-grid { display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 25px; }
        @media (max-width: 980px) { .builder-grid { grid-template-columns: 1fr; } }

        .panel { background: var(--bg-card); border: 1px solid var(--border-color); border-radius: var(--radius); padding: 25px; }
        .panel-title { font-size: 1.3rem; color: var(--accent-blue); margin-bottom: 20px; border-bottom: 1px solid var(--border-color); padding-bottom: 10px; }

        .form-group { margin-bottom: 16px; }
        .form-group label { display: block; font-weight: 600; margin-bottom: 6px; font-size: 0.9rem; }
        select { width: 100%; padding: 10px; background: var(--bg-dark); border: 1px solid var(--border-color); border-radius: 8px; color: var(--text-main); outline: none; }
        select:focus { border-color: var(--accent-blue); }

        .badge-row { display: flex; gap: 10px; margin-bottom: 20px; flex-wrap: wrap; }
        .badge { padding: 6px 14px; border-radius: 20px; font-weight: bold; font-size: 0.85rem; }
        .badge-owned { background: #00e676; color: #000; }
        .badge-type { background: #37474f; color: #eceff1; border: 1px solid #546e7a; }

        .stats-summary { display: grid; grid-template-columns: repeat(2, 1fr); gap: 12px; margin-bottom: 20px; }
        .stat-box { background: var(--bg-dark); padding: 12px; border-radius: 8px; border: 1px solid var(--border-color); }
        .stat-box .label { font-size: 0.75rem; color: var(--text-muted); text-transform: uppercase; }
        .stat-box .value { font-size: 1.2rem; font-weight: bold; color: var(--accent-blue); margin-top: 2px; }

        .stat-bar-group { margin-bottom: 12px; }
        .stat-bar-label { display: flex; justify-content: space-between; font-size: 0.85rem; margin-bottom: 4px; }
        .stat-bar-bg { background: var(--bg-dark); height: 8px; border-radius: 4px; border: 1px solid var(--border-color); }
        .stat-bar-fill { height: 100%; background: linear-gradient(90deg, var(--accent-blue), var(--accent-primary)); border-radius: 4px; width: 0%; transition: width 0.3s ease; }

        .eval-card { background: var(--bg-dark); border-left: 4px solid var(--accent-primary); padding: 12px; border-radius: 0 8px 8px 0; margin-bottom: 12px; }
        .eval-card h4 { color: var(--accent-primary); margin-bottom: 4px; font-size: 0.9rem; }
        .eval-card p { font-size: 0.85rem; line-height: 1.4; }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>🌀 Beyblade X — Master Collection & Builder</h1>
        <p>Integrado com sua coleção pessoal e lista completa de componentes</p>
    </header>

    <div class="builder-grid">
        <!-- SELEÇÃO DE COMBOS E PEÇAS -->
        <div class="panel">
            <div class="panel-title">⚙️ Seleção de Combos & Peças</div>

            <div class="form-group">
                <label>Selecione um Combo de Fábrica / Coleção:</label>
                <select id="select-stock" onchange="loadStockCombo()"></select>
            </div>

            <hr style="border-color: var(--border-color); margin: 20px 0;">

            <div class="form-group">
                <label>Blade / Combo Base:</label>
                <select id="select-blade" onchange="updateCustomCombo()"></select>
            </div>

            <div class="form-group">
                <label>Ratchet (Catraca):</label>
                <select id="select-ratchet" onchange="updateCustomCombo()"></select>
            </div>

            <div class="form-group">
                <label>Bit (Ponta):</label>
                <select id="select-bit" onchange="updateCustomCombo()"></select>
            </div>
        </div>

        <!-- DIAGNÓSTICO -->
        <div class="panel">
            <div class="panel-title">📊 Análise do Combo</div>

            <div class="badge-row">
                <span id="badge-status" class="badge badge-owned">NA COLEÇÃO</span>
                <span id="badge-type" class="badge badge-type">ATAQUE / BX</span>
            </div>

            <div class="stats-summary">
                <div class="stat-box">
                    <div class="label">Peso Estimado</div>
                    <div class="value" id="val-weight">44.5g</div>
                </div>
                <div class="stat-box">
                    <div class="label">Linha de Sistema</div>
                    <div class="value" id="val-line">UX</div>
                </div>
            </div>

            <!-- BARRAS DE ATRIBUTO -->
            <div class="stat-bar-group">
                <div class="stat-bar-label"><span>Ataque</span><span id="txt-atk">85%</span></div>
                <div class="stat-bar-bg"><div id="bar-atk" class="stat-bar-fill"></div></div>
            </div>
            <div class="stat-bar-group">
                <div class="stat-bar-label"><span>Defesa</span><span id="txt-def">50%</span></div>
                <div class="stat-bar-bg"><div id="bar-def" class="stat-bar-fill"></div></div>
            </div>
            <div class="stat-bar-group">
                <div class="stat-bar-label"><span>Stamina</span><span id="txt-sta">40%</span></div>
                <div class="stat-bar-bg"><div id="bar-sta" class="stat-bar-fill"></div></div>
            </div>
            <div class="stat-bar-group">
                <div class="stat-bar-label"><span>Mobilidade (X-Dash)</span><span id="txt-mob">90%</span></div>
                <div class="stat-bar-bg"><div id="bar-mob" class="stat-bar-fill"></div></div>
            </div>

            <div class="eval-card">
                <h4>💡 Diagnóstico Técnico</h4>
                <p id="eval-text">Analisando o combo selecionado...</p>
            </div>
        </div>
    </div>
</div>

<script>
// COMBOS EXTRAÍDOS DO DUMP
const STOCK_COMBOS = [
    { name: "BahamutBlitz BK1-50I", type: "Ataque", line: "C-E", owned: true },
    { name: "DranBrave S6-60V", type: "Ataque", line: "CX", owned: true },
    { name: "DranSword 3-60F", type: "Ataque", line: "BX", owned: true },
    { name: "EmperorMight HOp", type: "Equilíbrio", line: "CX", owned: true },
    { name: "GloryValkyrie LF", type: "Ataque", line: "U-E", owned: true },
    { name: "GolemRock M-85HN", type: "Defesa", line: "UX", owned: true },
    { name: "HellsScythe 4-60T", type: "Equilíbrio", line: "BX", owned: true },
    { name: "MeteorDragoon 3-70J", type: "Ataque", line: "UX", owned: true },
    { name: "Rock Leone 6-80GN", type: "Defesa", line: "BX X-Over", owned: true },
    { name: "SharkGill 5-60FB", type: "Resistência", line: "BX", owned: true },
    { name: "UnicornSting 5-60GP", type: "Equilíbrio", line: "BX", owned: true },
    { name: "AeroPegasus 3-70A", type: "Ataque", line: "UX", owned: false },
    { name: "SilverWolf 9-70R", type: "Ataque", line: "UX", owned: false },
    { name: "WizardRod 1-60R", type: "Ataque", line: "UX", owned: false },
    { name: "WyvernHover 8-80B", type: "Resistência", line: "UX", owned: false }
];

const RATCHETS = ["0-70", "0-80", "1-50", "1-60", "1-70", "1-80", "2-60", "2-70", "2-80", "3-60", "3-70", "3-80", "3-85", "4-50", "4-55", "4-60", "4-70", "4-80", "5-55", "5-60", "5-70", "5-80", "6-60", "6-70", "6-80", "7-55", "7-60", "7-70", "7-80", "8-70", "8-80", "9-60", "9-65", "9-70", "9-80", "M-85"];
const BITS = ["Accel (A)", "Ball (B)", "Bound Spike (BS)", "Cyclone (C)", "Dot (D)", "Disk Ball (DB)", "Elevate (E)", "Flat (F)", "Free Ball (FB)", "Gear Ball (GB)", "Gear Flat (GF)", "Gear Needle (GN)", "Gear Point (GP)", "Gear Rush (GR)", "Hexa (H)", "High Needle (HN)", "High Taper (HT)", "Impact (I)", "Jolt (J)", "Kick (K)", "Level (L)", "Low Flat (LF)", "Low Orb (LO)", "Low Rush (LR)", "Metal Needle (MN)", "Needle (N)", "Orb (O)", "Point (P)", "Quake (Q)", "Rush (R)", "Rubber Accel (RA)", "Spike (S)", "Taper (T)", "Trans Kick (TK)", "Trans Point (TP)", "Unite (U)", "Under Needle (UN)", "Vortex (V)", "Wedge (W)", "Wide Ball (WB)", "Yielding (Y)", "Zap (Z)"];

function init() {
    const selStock = document.getElementById('select-stock');
    STOCK_COMBOS.forEach((item, index) => {
        selStock.innerHTML += `<option value="${index}">${item.owned ? '✅ [Coleção] ' : '⭕ '} ${item.name} (${item.type})</option>`;
    });

    const selBlade = document.getElementById('select-blade');
    STOCK_COMBOS.forEach(item => {
        const bladeName = item.name.split(' ')[0];
        selBlade.innerHTML += `<option value="${bladeName}">${bladeName}</option>`;
    });

    const selRatchet = document.getElementById('select-ratchet');
    RATCHETS.forEach(r => selRatchet.innerHTML += `<option value="${r}">${r}</option>`);

    const selBit = document.getElementById('select-bit');
    BITS.forEach(b => selBit.innerHTML += `<option value="${b}">${b}</option>`);

    loadStockCombo();
}

function loadStockCombo() {
    const idx = document.getElementById('select-stock').value;
    const combo = STOCK_COMBOS[idx];

    document.getElementById('badge-status').innerText = combo.owned ? "NA COLEÇÃO" : "FORA DA COLEÇÃO";
    document.getElementById('badge-status').style.background = combo.owned ? "#00e676" : "#ff1744";
    document.getElementById('badge-status').style.color = combo.owned ? "#000" : "#fff";

    document.getElementById('badge-type').innerText = `${combo.type.toUpperCase()} / ${combo.line}`;
    document.getElementById('val-line').innerText = combo.line;

    let atk = 50, def = 50, sta = 50, mob = 50;
    if (combo.type === 'Ataque') { atk = 88; mob = 85; sta = 35; def = 45; }
    else if (combo.type === 'Resistência') { sta = 92; def = 60; atk = 40; mob = 40; }
    else if (combo.type === 'Defesa') { def = 88; sta = 65; atk = 42; mob = 35; }
    else { atk = 65; def = 65; sta = 65; mob = 60; }

    updateBars(atk, def, sta, mob);
    document.getElementById('eval-text').innerText = `Combo ${combo.type} da linha ${combo.line}. ${combo.owned ? 'Item confirmado em seu estoque pessoal.' : 'Item mapeado no banco global.'}`;
}

function updateCustomCombo() {
    const blade = document.getElementById('select-blade').value;
    const ratchet = document.getElementById('select-ratchet').value;
    const bit = document.getElementById('select-bit').value;

    document.getElementById('badge-status').innerText = "COMBO CUSTOMIZADO";
    document.getElementById('badge-status').style.background = "#00d2ff";
    document.getElementById('badge-status').style.color = "#000";

    document.getElementById('eval-text').innerText = `Combinação personalizada utilizando Blade ${blade}, Ratchet ${ratchet} e Bit ${bit}. Excelente para testes de bancada.`;
}

function updateBars(atk, def, sta, mob) {
    document.getElementById('txt-atk').innerText = `${atk}%`;
    document.getElementById('bar-atk').style.width = `${atk}%`;
    document.getElementById('txt-def').innerText = `${def}%`;
    document.getElementById('bar-def').style.width = `${def}%`;
    document.getElementById('txt-sta').innerText = `${sta}%`;
    document.getElementById('bar-sta').style.width = `${sta}%`;
    document.getElementById('txt-mob').innerText = `${mob}%`;
    document.getElementById('bar-mob').style.width = `${mob}%`;
}

window.onload = init;
</script>

</body>
</html>
