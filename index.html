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
                <label>Blade (Lâmina):</label>
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
// BANCO DE ATRIBUTOS DAS PEÇAS (BASE DE CÁLCULO)
const BLADES_DB = {
    "DranSword": { weight: 35.0, line: "BX", atk: 55, def: 20, sta: 15, mob: 30 },
    "DranBuster": { weight: 38.0, line: "UX", atk: 65, def: 15, sta: 10, mob: 35 },
    "DranDagger": { weight: 34.5, line: "BX", atk: 50, def: 20, sta: 20, mob: 30 },
    "DranBrave": { weight: 36.0, line: "CX", atk: 58, def: 18, sta: 15, mob: 32 },
    "HellsScythe": { weight: 33.0, line: "BX", atk: 30, def: 30, sta: 40, mob: 20 },
    "HellsChain": { weight: 33.5, line: "BX", atk: 32, def: 35, sta: 35, mob: 20 },
    "WizardRod": { weight: 35.5, line: "UX", atk: 15, def: 40, sta: 65, mob: 15 },
    "WizardArrow": { weight: 32.0, line: "BX", atk: 15, def: 35, sta: 55, mob: 15 },
    "KnightShield": { weight: 32.5, line: "BX", atk: 20, def: 55, sta: 25, mob: 15 },
    "KnightMail": { weight: 36.5, line: "UX", atk: 25, def: 60, sta: 20, mob: 15 },
    "PhoenixWing": { weight: 38.0, line: "BX", atk: 60, def: 30, sta: 20, mob: 25 },
    "PhoenixRudder": { weight: 34.0, line: "UX", atk: 20, def: 30, sta: 58, mob: 18 },
    "SharkEdge": { weight: 34.0, line: "BX", atk: 60, def: 15, sta: 10, mob: 35 },
    "SharkGill": { weight: 33.0, line: "BX", atk: 30, def: 25, sta: 50, mob: 20 },
    "CobaltDragoon": { weight: 37.5, line: "BX", atk: 58, def: 20, sta: 15, mob: 30 },
    "AeroPegasus": { weight: 37.0, line: "UX", atk: 55, def: 25, sta: 25, mob: 30 },
    "UnicornSting": { weight: 33.5, line: "BX", atk: 35, def: 35, sta: 35, mob: 25 },
    "SilverWolf": { weight: 36.0, line: "UX", atk: 20, def: 35, sta: 60, mob: 15 },
    "ImpactDrake": { weight: 38.5, line: "UX", atk: 62, def: 20, sta: 10, mob: 30 },
    "GolemRock": { weight: 36.0, line: "UX", atk: 20, def: 58, sta: 25, mob: 15 },
    "MeteorDragoon": { weight: 35.0, line: "UX", atk: 52, def: 20, sta: 20, mob: 30 },
    "WyvernGale": { weight: 32.0, line: "BX", atk: 20, def: 30, sta: 50, mob: 20 },
    "WyvernHover": { weight: 35.5, line: "UX", atk: 18, def: 30, sta: 62, mob: 15 },
    "Rock Leone": { weight: 34.0, line: "X-Over", atk: 25, def: 50, sta: 30, mob: 15 },
    "SamuraiSaber": { weight: 36.0, line: "UX", atk: 50, def: 25, sta: 20, mob: 28 },
    "BahamutBlitz": { weight: 37.0, line: "C-E", atk: 56, def: 22, sta: 18, mob: 30 },
    "EmperorMight": { weight: 35.0, line: "CX", atk: 35, def: 35, sta: 35, mob: 25 },
    "GloryValkyrie": { weight: 36.5, line: "U-E", atk: 58, def: 20, sta: 15, mob: 32 }
};

const RATCHETS_DB = {
    "0-70": 6.2, "0-80": 6.8, "1-50": 5.5, "1-60": 6.0, "1-70": 6.5, "1-80": 7.0,
    "2-60": 6.0, "2-70": 6.4, "2-80": 6.8, "3-60": 6.2, "3-70": 6.6, "3-80": 7.1, "3-85": 7.4,
    "4-50": 5.8, "4-55": 6.0, "4-60": 6.4, "4-70": 6.8, "4-80": 7.2, "5-55": 6.2,
    "5-60": 6.5, "5-70": 6.9, "5-80": 7.3, "6-60": 6.6, "6-70": 7.0, "6-80": 7.4,
    "7-55": 6.4, "7-60": 6.7, "7-70": 7.1, "7-80": 7.5, "8-70": 7.2, "8-80": 7.6,
    "9-60": 6.3, "9-65": 6.6, "9-70": 6.9, "9-80": 7.3, "M-85": 7.8
};

const BITS_DB = {
    "Flat (F)": { weight: 2.4, atk: 30, def: 5, sta: 5, mob: 45 },
    "Low Flat (LF)": { weight: 2.4, atk: 35, def: 5, sta: 5, mob: 50 },
    "Gear Flat (GF)": { weight: 2.6, atk: 35, def: 5, sta: 5, mob: 52 },
    "Accel (A)": { weight: 2.5, atk: 32, def: 5, sta: 5, mob: 48 },
    "Rubber Accel (RA)": { weight: 2.6, atk: 38, def: 5, sta: 0, mob: 55 },
    "Rush (R)": { weight: 2.4, atk: 25, def: 10, sta: 15, mob: 40 },
    "Low Rush (LR)": { weight: 2.4, atk: 28, def: 10, sta: 12, mob: 42 },
    "Gear Rush (GR)": { weight: 2.5, atk: 28, def: 10, sta: 12, mob: 44 },
    "Ball (B)": { weight: 2.2, atk: 5, def: 20, sta: 45, mob: 10 },
    "Disk Ball (DB)": { weight: 2.8, atk: 5, def: 25, sta: 40, mob: 10 },
    "Free Ball (FB)": { weight: 2.3, atk: 5, def: 18, sta: 48, mob: 12 },
    "Gear Ball (GB)": { weight: 2.4, atk: 10, def: 15, sta: 40, mob: 20 },
    "Wide Ball (WB)": { weight: 2.3, atk: 5, def: 28, sta: 38, mob: 10 },
    "Orb (O)": { weight: 2.2, atk: 5, def: 15, sta: 48, mob: 10 },
    "Low Orb (LO)": { weight: 2.2, atk: 5, def: 18, sta: 46, mob: 10 },
    "Needle (N)": { weight: 2.1, atk: 5, def: 40, sta: 20, mob: 10 },
    "High Needle (HN)": { weight: 2.3, atk: 5, def: 38, sta: 22, mob: 12 },
    "Gear Needle (GN)": { weight: 2.3, atk: 10, def: 35, sta: 18, mob: 20 },
    "Metal Needle (MN)": { weight: 2.9, atk: 5, def: 45, sta: 25, mob: 8 },
    "Under Needle (UN)": { weight: 2.2, atk: 5, def: 38, sta: 22, mob: 10 },
    "Hexa (H)": { weight: 2.7, atk: 15, def: 35, sta: 20, mob: 20 },
    "Point (P)": { weight: 2.3, atk: 20, def: 20, sta: 25, mob: 25 },
    "Gear Point (GP)": { weight: 2.4, atk: 22, def: 18, sta: 22, mob: 28 },
    "Taper (T)": { weight: 2.3, atk: 22, def: 18, sta: 20, mob: 30 },
    "High Taper (HT)": { weight: 2.4, atk: 20, def: 18, sta: 22, mob: 32 },
    "Unite (U)": { weight: 2.4, atk: 20, def: 22, sta: 25, mob: 25 },
    "Yielding (Y)": { weight: 2.2, atk: 0, def: 10, sta: 52, mob: 8 },
    "Wedge (W)": { weight: 2.2, atk: 5, def: 30, sta: 25, mob: 10 },
    "Wide Wedge (WW)": { weight: 2.3, atk: 5, def: 35, sta: 22, mob: 10 },
    "Quake (Q)": { weight: 2.3, atk: 35, def: 5, sta: 5, mob: 45 },
    "Spike (S)": { weight: 2.1, atk: 5, def: 25, sta: 25, mob: 10 },
    "Bound Spike (BS)": { weight: 2.5, atk: 5, def: 32, sta: 22, mob: 10 },
    "Cyclone (C)": { weight: 2.4, atk: 28, def: 10, sta: 15, mob: 40 },
    "Dot (D)": { weight: 2.2, atk: 5, def: 30, sta: 25, mob: 10 },
    "Elevate (E)": { weight: 2.5, atk: 15, def: 25, sta: 25, mob: 20 },
    "Impact (I)": { weight: 2.5, atk: 32, def: 10, sta: 10, mob: 40 },
    "Jolt (J)": { weight: 2.4, atk: 30, def: 8, sta: 8, mob: 42 },
    "Kick (K)": { weight: 2.3, atk: 18, def: 18, sta: 20, mob: 28 },
    "Level (L)": { weight: 2.5, atk: 20, def: 20, sta: 25, mob: 25 },
    "Trans Kick (TK)": { weight: 2.4, atk: 20, def: 18, sta: 22, mob: 28 },
    "Trans Point (TP)": { weight: 2.4, atk: 22, def: 20, sta: 22, mob: 26 },
    "Vortex (V)": { weight: 2.5, atk: 28, def: 10, sta: 12, mob: 42 },
    "Zap (Z)": { weight: 2.6, atk: 25, def: 15, sta: 15, mob: 35 }
};

// COMBOS DE FÁBRICA / COLEÇÃO
const STOCK_COMBOS = [
    { name: "BahamutBlitz BK1-50I", blade: "BahamutBlitz", ratchet: "1-50", bit: "Impact (I)", type: "Ataque", line: "C-E", owned: true },
    { name: "DranBrave S6-60V", blade: "DranBrave", ratchet: "6-60", bit: "Vortex (V)", type: "Ataque", line: "CX", owned: true },
    { name: "DranSword 3-60F", blade: "DranSword", ratchet: "3-60", bit: "Flat (F)", type: "Ataque", line: "BX", owned: true },
    { name: "EmperorMight HOp", blade: "EmperorMight", ratchet: "4-60", bit: "Orb (O)", type: "Equilíbrio", line: "CX", owned: true },
    { name: "GloryValkyrie LF", blade: "GloryValkyrie", ratchet: "3-60", bit: "Low Flat (LF)", type: "Ataque", line: "U-E", owned: true },
    { name: "GolemRock M-85HN", blade: "GolemRock", ratchet: "M-85", bit: "High Needle (HN)", type: "Defesa", line: "UX", owned: true },
    { name: "HellsScythe 4-60T", blade: "HellsScythe", ratchet: "4-60", bit: "Taper (T)", type: "Equilíbrio", line: "BX", owned: true },
    { name: "MeteorDragoon 3-70J", blade: "MeteorDragoon", ratchet: "3-70", bit: "Jolt (J)", type: "Ataque", line: "UX", owned: true },
    { name: "Rock Leone 6-80GN", blade: "Rock Leone", ratchet: "6-80", bit: "Gear Needle (GN)", type: "Defesa", line: "BX X-Over", owned: true },
    { name: "SharkGill 5-60FB", blade: "SharkGill", ratchet: "5-60", bit: "Free Ball (FB)", type: "Resistência", line: "BX", owned: true },
    { name: "UnicornSting 5-60GP", blade: "UnicornSting", ratchet: "5-60", bit: "Gear Point (GP)", type: "Equilíbrio", line: "BX", owned: true },
    { name: "AeroPegasus 3-70A", blade: "AeroPegasus", ratchet: "3-70", bit: "Accel (A)", type: "Ataque", line: "UX", owned: false },
    { name: "SilverWolf 9-70R", blade: "SilverWolf", ratchet: "9-70", bit: "Rush (R)", type: "Ataque", line: "UX", owned: false },
    { name: "WizardRod 1-60R", blade: "WizardRod", ratchet: "1-60", bit: "Rush (R)", type: "Ataque", line: "UX", owned: false },
    { name: "WyvernHover 8-80B", blade: "WyvernHover", ratchet: "8-80", bit: "Ball (B)", type: "Resistência", line: "UX", owned: false }
];

function init() {
    const selStock = document.getElementById('select-stock');
    STOCK_COMBOS.forEach((item, index) => {
        selStock.innerHTML += `<option value="${index}">${item.owned ? '✅ [Coleção] ' : '⭕ '} ${item.name} (${item.type})</option>`;
    });

    const selBlade = document.getElementById('select-blade');
    Object.keys(BLADES_DB).sort().forEach(b => selBlade.innerHTML += `<option value="${b}">${b}</option>`);

    const selRatchet = document.getElementById('select-ratchet');
    Object.keys(RATCHETS_DB).forEach(r => selRatchet.innerHTML += `<option value="${r}">${r}</option>`);

    const selBit = document.getElementById('select-bit');
    Object.keys(BITS_DB).sort().forEach(b => selBit.innerHTML += `<option value="${b}">${b}</option>`);

    loadStockCombo();
}

function loadStockCombo() {
    const idx = document.getElementById('select-stock').value;
    const combo = STOCK_COMBOS[idx];

    // Atualiza os dropdowns para sincronizar com o combo de fábrica
    if (combo.blade) document.getElementById('select-blade').value = combo.blade;
    if (combo.ratchet) document.getElementById('select-ratchet').value = combo.ratchet;
    if (combo.bit) document.getElementById('select-bit').value = combo.bit;

    document.getElementById('badge-status').innerText = combo.owned ? "NA COLEÇÃO" : "FORA DA COLEÇÃO";
    document.getElementById('badge-status').style.background = combo.owned ? "#00e676" : "#ff1744";
    document.getElementById('badge-status').style.color = combo.owned ? "#000" : "#fff";

    document.getElementById('badge-type').innerText = `${combo.type.toUpperCase()} / ${combo.line}`;

    updateCustomCombo(false); // Recalcula atributos exatos do combo de fábrica
}

function updateCustomCombo(isCustom = true) {
    const bladeKey = document.getElementById('select-blade').value;
    const ratchetKey = document.getElementById('select-ratchet').value;
    const bitKey = document.getElementById('select-bit').value;

    const bladeData = BLADES_DB[bladeKey] || { weight: 35, line: "BX", atk: 40, def: 30, sta: 30, mob: 20 };
    const ratchetWeight = RATCHETS_DB[ratchetKey] || 6.5;
    const bitData = BITS_DB[bitKey] || { weight: 2.3, atk: 15, def: 15, sta: 15, mob: 20 };

    // CÁLCULO DE PESO REAL
    const totalWeight = (bladeData.weight + ratchetWeight + bitData.weight).toFixed(1);

    // CÁLCULO DOS ATRIBUTOS
    const totalAtk = Math.min(100, bladeData.atk + bitData.atk);
    const totalDef = Math.min(100, bladeData.def + bitData.def);
    const totalSta = Math.min(100, bladeData.sta + bitData.sta);
    const totalMob = Math.min(100, bladeData.mob + bitData.mob);

    // ATUALIZAÇÃO DA INTERFACE
    document.getElementById('val-weight').innerText = `${totalWeight}g`;
    document.getElementById('val-line').innerText = bladeData.line;

    if (isCustom) {
        document.getElementById('badge-status').innerText = "COMBO CUSTOMIZADO";
        document.getElementById('badge-status').style.background = "#00d2ff";
        document.getElementById('badge-status').style.color = "#000";
        document.getElementById('badge-type').innerText = `CUSTOM / ${bladeData.line}`;
        document.getElementById('eval-text').innerText = `Combinação de ${bladeKey} em Ratchet ${ratchetKey} com Bit ${bitKey}. Peso total calculado: ${totalWeight}g.`;
    }

    updateBars(totalAtk, totalDef, totalSta, totalMob);
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
