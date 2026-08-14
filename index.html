<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beyblade X — Master Builder & Meta Evaluator (Database Completo)</title>
    <style>
        :root {
            --bg-dark: #0f1117;
            --bg-card: #181b24;
            --bg-card-hover: #222634;
            --accent-primary: #ff5500;
            --accent-blue: #00d2ff;
            --accent-green: #00e676;
            --accent-yellow: #ffb700;
            --text-main: #f0f2f5;
            --text-muted: #9aa0a6;
            --border-color: #2a2f3d;
            --radius: 12px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-main);
            padding: 20px;
            min-height: 100vh;
        }

        .container {
            max-width: 1350px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            margin-bottom: 25px;
            padding: 20px;
            background: linear-gradient(135deg, rgba(255,85,0,0.12) 0%, rgba(0,210,255,0.12) 100%);
            border: 1px solid var(--border-color);
            border-radius: var(--radius);
        }

        header h1 {
            font-size: 2.2rem;
            background: linear-gradient(90deg, var(--accent-primary), var(--accent-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 8px;
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        header p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        .tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            border-bottom: 2px solid var(--border-color);
            padding-bottom: 10px;
        }

        .tab-btn {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s ease;
        }

        .tab-btn:hover {
            background: var(--bg-card-hover);
            border-color: var(--accent-blue);
        }

        .tab-btn.active {
            background: var(--accent-primary);
            color: #fff;
            border-color: var(--accent-primary);
        }

        .builder-grid {
            display: grid;
            grid-template-columns: 1.1fr 0.9fr;
            gap: 25px;
        }

        @media (max-width: 980px) {
            .builder-grid {
                grid-template-columns: 1fr;
            }
        }

        .selection-panel, .result-panel {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius);
            padding: 25px;
        }

        .panel-title {
            font-size: 1.3rem;
            color: var(--accent-blue);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 10px;
        }

        .count-tag {
            font-size: 0.8rem;
            background: rgba(0, 210, 255, 0.15);
            color: var(--accent-blue);
            padding: 4px 10px;
            border-radius: 12px;
            border: 1px solid rgba(0, 210, 255, 0.3);
        }

        .mode-toggle {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            background: var(--bg-dark);
            padding: 5px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }

        .mode-btn {
            flex: 1;
            padding: 8px;
            background: transparent;
            border: none;
            color: var(--text-muted);
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            text-align: center;
        }

        .mode-btn.active {
            background: var(--accent-blue);
            color: #000;
        }

        .form-group {
            margin-bottom: 18px;
        }

        .form-group label {
            display: flex;
            justify-content: space-between;
            font-weight: 600;
            margin-bottom: 6px;
            font-size: 0.9rem;
        }

        .form-group label span.part-type {
            font-size: 0.8rem;
            color: var(--accent-primary);
            text-transform: uppercase;
        }

        select {
            width: 100%;
            padding: 10px 12px;
            background: var(--bg-dark);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            color: var(--text-main);
            font-size: 0.9rem;
            outline: none;
        }

        select:focus {
            border-color: var(--accent-blue);
        }

        .badge-row {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-bottom: 20px;
        }

        .badge {
            padding: 6px 14px;
            border-radius: 20px;
            font-weight: bold;
            font-size: 0.85rem;
            text-transform: uppercase;
        }

        .badge-tier-s { background: #ff1744; color: #fff; }
        .badge-tier-a { background: #ff9100; color: #fff; }
        .badge-tier-b { background: #00e676; color: #000; }
        .badge-type { background: #37474f; color: #eceff1; border: 1px solid #546e7a; }

        .stats-summary {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
            margin-bottom: 20px;
        }

        .stat-box {
            background: var(--bg-dark);
            padding: 12px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }

        .stat-box .label {
            font-size: 0.75rem;
            color: var(--text-muted);
            text-transform: uppercase;
        }

        .stat-box .value {
            font-size: 1.2rem;
            font-weight: bold;
            color: var(--accent-blue);
            margin-top: 2px;
        }

        .stat-bar-group {
            margin-bottom: 12px;
        }

        .stat-bar-label {
            display: flex;
            justify-content: space-between;
            font-size: 0.85rem;
            margin-bottom: 4px;
        }

        .stat-bar-bg {
            background: var(--bg-dark);
            height: 8px;
            border-radius: 4px;
            overflow: hidden;
            border: 1px solid var(--border-color);
        }

        .stat-bar-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--accent-blue), var(--accent-primary));
            border-radius: 4px;
            width: 0%;
            transition: width 0.3s ease;
        }

        .eval-section {
            background: var(--bg-dark);
            border-left: 4px solid var(--accent-primary);
            padding: 12px;
            border-radius: 0 8px 8px 0;
            margin-bottom: 12px;
        }

        .eval-section h4 {
            color: var(--accent-primary);
            margin-bottom: 4px;
            font-size: 0.9rem;
        }

        .eval-section p {
            font-size: 0.85rem;
            color: var(--text-main);
            line-height: 1.4;
        }

        .sql-container {
            background: #0d1117;
            padding: 20px;
            border-radius: var(--radius);
            border: 1px solid var(--border-color);
            position: relative;
        }

        .sql-code {
            font-family: 'Consolas', 'Courier New', monospace;
            color: #e6edf3;
            white-space: pre-wrap;
            font-size: 0.82rem;
            line-height: 1.5;
            max-height: 500px;
            overflow-y: auto;
        }

        .copy-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--accent-blue);
            color: #000;
            border: none;
            padding: 8px 16px;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
        }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>🌀 Beyblade X — Master Builder & Meta Evaluator</h1>
        <p>Catálogo 100% completo com suporte ao Sistema Standard e Sistema Custom CX.</p>
    </header>

    <div class="tabs">
        <button class="tab-btn active" onclick="switchTab('builder')">🛠️ Combo Builder</button>
        <button class="tab-btn" onclick="switchTab('sql')">🗄️ Database Completo (SQL)</button>
    </div>

    <!-- TAB 1: BUILDER -->
    <div id="tab-builder" class="tab-content active">
        <div class="builder-grid">
            
            <!-- SELEÇÃO DE PEÇAS -->
            <div class="selection-panel">
                <div class="panel-title">
                    <span>⚡ Seleção de Componentes</span>
                    <span class="count-tag" id="total-parts-tag">137 Peças Cadastradas</span>
                </div>

                <div class="mode-toggle">
                    <button class="mode-btn active" id="btn-mode-std" onclick="setSystemMode('standard')">Sistema Standard (Blade)</button>
                    <button class="mode-btn" id="btn-mode-cx" onclick="setSystemMode('cx')">Sistema CX (Custom Blade)</button>
                </div>

                <!-- CAMPO STANDARD: BLADE -->
                <div class="form-group" id="grp-blade">
                    <label>Lâmina (Blade) <span class="part-type">Standard Blade</span></label>
                    <select id="select-blade" onchange="updateCombo()"></select>
                </div>

                <!-- CAMPOS CX: LOCK CHIP, MAIN BLADE, ASSIST BLADE -->
                <div id="grp-cx-container" style="display: none;">
                    <div class="form-group">
                        <label>Lock Chip <span class="part-type">CX Core</span></label>
                        <select id="select-lockchip" onchange="updateCombo()"></select>
                    </div>
                    <div class="form-group">
                        <label>Main Blade <span class="part-type">CX Main Metal</span></label>
                        <select id="select-mainblade" onchange="updateCombo()"></select>
                    </div>
                    <div class="form-group">
                        <label>Assist Blade <span class="part-type">CX Sub Ring</span></label>
                        <select id="select-assistblade" onchange="updateCombo()"></select>
                    </div>
                </div>

                <!-- RATCHET -->
                <div class="form-group">
                    <label>Catraca (Ratchet) <span class="part-type">Parte Central</span></label>
                    <select id="select-ratchet" onchange="updateCombo()"></select>
                </div>

                <!-- BIT -->
                <div class="form-group">
                    <label>Ponta (Bit) <span class="part-type">Base de Rotação</span></label>
                    <select id="select-bit" onchange="updateCombo()"></select>
                </div>
            </div>

            <!-- RESULTADOS -->
            <div class="result-panel">
                <div class="panel-title">📊 Diagnóstico do Combo</div>

                <div class="badge-row">
                    <span id="badge-tier" class="badge badge-tier-s">TIER S</span>
                    <span id="badge-type" class="badge badge-type">STAMINA / DEFENSE</span>
                </div>

                <div class="stats-summary">
                    <div class="stat-box">
                        <div class="label">Peso Estimado</div>
                        <div class="value" id="val-weight">0.0g</div>
                    </div>
                    <div class="stat-box">
                        <div class="label">Sinergia</div>
                        <div class="value" id="val-synergy">0 / 10</div>
                    </div>
                    <div class="stat-box">
                        <div class="label">Risco de Burst</div>
                        <div class="value" id="val-burst">Baixo</div>
                    </div>
                    <div class="stat-box">
                        <div class="label">Estilo de Jogo</div>
                        <div class="value" id="val-playstyle">Passivo</div>
                    </div>
                </div>

                <!-- BARRAS DE STATUS -->
                <div class="stat-bar-group">
                    <div class="stat-bar-label"><span>Ataque / Impacto</span><span id="txt-atk">0%</span></div>
                    <div class="stat-bar-bg"><div id="bar-atk" class="stat-bar-fill"></div></div>
                </div>
                <div class="stat-bar-group">
                    <div class="stat-bar-label"><span>Defesa / Resistência a KO</span><span id="txt-def">0%</span></div>
                    <div class="stat-bar-bg"><div id="bar-def" class="stat-bar-fill"></div></div>
                </div>
                <div class="stat-bar-group">
                    <div class="stat-bar-label"><span>Stamina / Retenção de Giro</span><span id="txt-sta">0%</span></div>
                    <div class="stat-bar-bg"><div id="bar-sta" class="stat-bar-fill"></div></div>
                </div>
                <div class="stat-bar-group">
                    <div class="stat-bar-label"><span>Mobilidade / X-Dash Speed</span><span id="txt-mob">0%</span></div>
                    <div class="stat-bar-bg"><div id="bar-mob" class="stat-bar-fill"></div></div>
                </div>

                <!-- DIAGNÓSTICOS -->
                <div class="eval-section">
                    <h4>💡 Encaixe Mecânico & Sinergia</h4>
                    <p id="eval-synergy-text">Calculando...</p>
                </div>

                <div class="eval-section" style="border-left-color: var(--accent-blue);">
                    <h4 style="color: var(--accent-blue);">⚔️ Posição no Meta Competitivo</h4>
                    <p id="eval-meta-text">Calculando...</p>
                </div>

                <div class="eval-section" style="border-left-color: var(--accent-green);">
                    <h4 style="color: var(--accent-green);">🎯 Recomendação de Lançamento</h4>
                    <p id="eval-launch-text">Calculando...</p>
                </div>
            </div>

        </div>
    </div>

    <!-- TAB 2: SQL -->
    <div id="tab-sql" class="tab-content">
        <div class="sql-container">
            <button class="copy-btn" onclick="copySql()">📋 Copiar Script SQL</button>
            <div class="sql-code" id="sql-code-block"></div>
        </div>
    </div>
</div>

<script>
// TODAS AS 137 PEÇAS DA LISTA ORGANIZADAS POR CATEGORIA
const RAW_LIST = {
    assistBlades: ["Bumper", "Jaggy", "Round", "Slash", "Turn"],
    bits: [
        "Accel", "Bound Spike", "Cyclone", "Disk Ball", "Dot", "Elevate", "Flat", "Free Ball", 
        "Gear Ball", "Gear Flat", "Gear Needle", "Gear Point", "Gear Rush", "Hexa", "High Needle", 
        "High Taper", "Kick", "Level", "Low Flat", "Low Orb", "Low Rush", "Metal Needle", "Orb", 
        "Point", "Rubber Accel", "Rush", "Spike", "Trans Kick", "Trans Point", "Under Needle", 
        "Unite", "Wedge"
    ],
    blades: [
        "AeroPegasus", "Bite Croc", "BlackShell", "Bumblebee", "CobaltDragoon", "CrimsonGaruda", 
        "Darth Vader", "DranBuster", "DranDagger", "DranSword", "DranzerSpiral", "DrigerSlash", 
        "GhostCircle", "Gill Shark", "GolemRock", "HellsChain", "HellsHammer", "HellsScythe", 
        "Hover Wyvern", "ImpactDrake", "Iron Man", "Knife Shinobi", "KnightMail", "KnightShield", 
        "LeonClaw", "LeonCrest", "Lightning L-Drago (Rapid-Hit Type)", "Lightning L-Drago (Upper Type)", 
        "Luke Skywalker", "Megatron", "Moff Gideon", "Optimus Primal", "Optimus Prime", "PhoenixWing", 
        "RhinoHorn", "Roar Tyranno", "SamuraiSaber", "Savage Bear", "ShelterDrake", "ShinobiShadow", 
        "Shockwave", "SilverWolf", "SphinxCowl", "Spider-Man", "Starscream", "Steel Samurai", 
        "Tackle Goat", "Talon Ptera", "Thanos", "The Mandalorian", "TriceraSpiky", "Trypio", 
        "Tusk Mammoth", "TyrannoBeat", "UnicornSting", "Venom", "ViperTail", "WeissTiger", 
        "WhaleWave", "WizardRod", "WyvernGale", "Yell Kong"
    ],
    lockChips: ["Drake", "Dran", "Fox", "Hells", "Perseus", "Sol", "Valkyrie", "Wizard"],
    mainBlades: ["Arc", "Brave", "Brush", "Dark", "Reaper", "Volt"],
    ratchets: [
        "0-80", "1-60", "1-70", "1-80", "2-60", "2-70", "2-80", "3-60", "3-70", "3-85", 
        "4-55", "4-60", "4-70", "5-60", "5-70", "5-80", "6-60", "6-80", "7-60", "7-70", 
        "7-80", "9-60", "9-65", "9-70", "9-80"
    ]
};

let currentSystemMode = 'standard';

function getBitType(name) {
    if (["Flat", "Gear Flat", "Low Flat", "Rush", "Low Rush", "Accel", "Rubber Accel", "Gear Rush", "Cyclone", "Level"].includes(name)) return "Attack";
    if (["Ball", "Disk Ball", "Free Ball", "Orb", "Low Orb", "Gear Ball"].includes(name)) return "Stamina";
    if (["Needle", "High Needle", "Hexa", "Bound Spike", "Metal Needle", "Spike", "Under Needle", "Wedge", "Dot"].includes(name)) return "Defense";
    return "Balance";
}

function getBladeType(name) {
    if (["WizardRod", "SilverWolf", "WyvernGale", "GhostCircle", "Hover Wyvern", "Trypio"].includes(name)) return "Stamina";
    if (["PhoenixWing", "CobaltDragoon", "DranBuster", "TyrannoBeat", "WhaleWave", "ImpactDrake", "AeroPegasus", "Shark Edge", "Gill Shark"].includes(name)) return "Attack";
    if (["KnightMail", "KnightShield", "SphinxCowl", "BlackShell", "ShinobiShadow"].includes(name)) return "Defense";
    return "Balance";
}

function getRatchetHeight(name) {
    const parts = name.split('-');
    return parts.length > 1 ? parseInt(parts[1]) : 60;
}

function initApp() {
    // Populando os Selects
    const selBlade = document.getElementById('select-blade');
    RAW_LIST.blades.forEach(item => selBlade.innerHTML += `<option value="${item}">${item} [${getBladeType(item)}]</option>`);

    const selLock = document.getElementById('select-lockchip');
    RAW_LIST.lockChips.forEach(item => selLock.innerHTML += `<option value="${item}">${item}</option>`);

    const selMain = document.getElementById('select-mainblade');
    RAW_LIST.mainBlades.forEach(item => selMain.innerHTML += `<option value="${item}">${item}</option>`);

    const selAssist = document.getElementById('select-assistblade');
    RAW_LIST.assistBlades.forEach(item => selAssist.innerHTML += `<option value="${item}">${item}</option>`);

    const selRatchet = document.getElementById('select-ratchet');
    RAW_LIST.ratchets.forEach(item => selRatchet.innerHTML += `<option value="${item}">${item}</option>`);

    const selBit = document.getElementById('select-bit');
    RAW_LIST.bits.forEach(item => selBit.innerHTML += `<option value="${item}">${item} [${getBitType(item)}]</option>`);

    // Defaults
    selBlade.value = "WizardRod";
    selRatchet.value = "5-60";
    selBit.value = "Disk Ball";

    generateSqlBlock();
    updateCombo();
}

function setSystemMode(mode) {
    currentSystemMode = mode;
    document.getElementById('btn-mode-std').classList.toggle('active', mode === 'standard');
    document.getElementById('btn-mode-cx').classList.toggle('active', mode === 'cx');

    document.getElementById('grp-blade').style.display = mode === 'standard' ? 'block' : 'none';
    document.getElementById('grp-cx-container').style.display = mode === 'cx' ? 'block' : 'none';

    updateCombo();
}

function updateCombo() {
    const ratchetName = document.getElementById('select-ratchet').value;
    const bitName = document.getElementById('select-bit').value;
    const bitType = getBitType(bitName);

    let bladeName = "";
    let bladeType = "";
    let weightBlade = 35.0;

    if (currentSystemMode === 'standard') {
        bladeName = document.getElementById('select-blade').value;
        bladeType = getBladeType(bladeName);
        if (["PhoenixWing", "CobaltDragoon", "ImpactDrake"].includes(bladeName)) weightBlade = 38.0;
        if (["WizardRod", "KnightMail"].includes(bladeName)) weightBlade = 35.5;
        if (["DranBuster"].includes(bladeName)) weightBlade = 36.2;
    } else {
        const lock = document.getElementById('select-lockchip').value;
        const main = document.getElementById('select-mainblade').value;
        const assist = document.getElementById('select-assistblade').value;
        bladeName = `${lock} ${main} ${assist} (CX)`;
        bladeType = "Balance";
        weightBlade = 36.5; // Estimativa média da montagem CX
    }

    const height = getRatchetHeight(ratchetName);
    const totalWeight = (weightBlade + 6.3 + 2.3).toFixed(1);

    // Cálculo dinâmico de atributos
    let atk = bitType === 'Attack' ? 85 : (bladeType === 'Attack' ? 75 : 40);
    let def = bitType === 'Defense' ? 85 : (bladeType === 'Defense' ? 80 : 50);
    let sta = bitType === 'Stamina' ? 90 : (bladeType === 'Stamina' ? 85 : 45);
    let mob = bitType === 'Attack' ? 90 : 35;

    if (bladeName.includes("WizardRod") && bitType === 'Stamina' && height === 60) {
        sta = 98;
        def = 88;
    }

    // Tiers e Avaliação
    let tier = "TIER A (COMPETITIVO)";
    let badgeClass = "badge-tier-a";
    let synergyScore = "8.2";
    let synergyText = "Combinação sólida com excelente encaixe entre a altura do Ratchet e a base da ponta.";
    let metaText = "Possui ótimo desempenho em torneios locais, mantendo controle contra investidas.";
    let launchText = "Lançamento paralelo ao stadium para garantir equilíbrio no primeiro segundo de rotação.";

    if ((bladeName.includes("WizardRod") || bladeName.includes("SilverWolf")) && bitType === 'Stamina' && height <= 60) {
        tier = "TIER S+ (META DOMINANTE)";
        badgeClass = "badge-tier-s";
        synergyScore = "9.9";
        synergyText = "Sinergia perfeita de retenção de energia e defesa periférica. O diâmetro cobre totalmente a trava central.";
        metaText = "Um dos combos mais difíceis de derrotar por sobrevivência (Spin Finish).";
        launchText = "Lançamento plano centralizado com força moderada a alta.";
    } else if ((bladeName.includes("PhoenixWing") || bladeName.includes("ImpactDrake") || bladeName.includes("DranBuster")) && bitType === 'Attack') {
        tier = "TIER S (KO Agressivo)";
        badgeClass = "badge-tier-s";
        synergyScore = "9.5";
        synergyText = "Combinação explosiva de massa e velocidade no X-Celerator Rail para expulsão direta.";
        metaText = "O principal contador contra combos passivos de alta stamina.";
        launchText = "Lançamento inclinado (Banked Launch) para rasgar a X-Line com aceleração imediata.";
    }

    document.getElementById('badge-tier').innerText = tier;
    document.getElementById('badge-tier').className = `badge ${badgeClass}`;
    document.getElementById('badge-type').innerText = `${bladeType.toUpperCase()} / ${bitType.toUpperCase()}`;

    document.getElementById('val-weight').innerText = `${totalWeight}g`;
    document.getElementById('val-synergy').innerText = `${synergyScore} / 10`;
    document.getElementById('val-burst').innerText = height >= 80 ? "Médio/Alto" : "Baixo";
    document.getElementById('val-playstyle').innerText = bitType === 'Attack' ? 'Agressivo (X-Dash)' : 'Controle / Centro';

    document.getElementById('txt-atk').innerText = `${atk}%`;
    document.getElementById('bar-atk').style.width = `${atk}%`;
    document.getElementById('txt-def').innerText = `${def}%`;
    document.getElementById('bar-def').style.width = `${def}%`;
    document.getElementById('txt-sta').innerText = `${sta}%`;
    document.getElementById('bar-sta').style.width = `${sta}%`;
    document.getElementById('txt-mob').innerText = `${mob}%`;
    document.getElementById('bar-mob').style.width = `${mob}%`;

    document.getElementById('eval-synergy-text').innerText = synergyText;
    document.getElementById('eval-meta-text').innerText = metaText;
    document.getElementById('eval-launch-text').innerText = launchText;
}

function generateSqlBlock() {
    let sql = `-- SCRIPT COMPLETO DE DADOS DE BEYBLADE X (${Object.values(RAW_LIST).flat().length} PEÇAS)\n\n`;
    
    Object.keys(RAW_LIST).forEach(category => {
        sql += `-- CATEGORIA: ${category.toUpperCase()} (${RAW_LIST[category].length} itens)\n`;
        RAW_LIST[category].forEach(item => {
            sql += `INSERT INTO beyblade_parts (category, name) VALUES ('${category}', '${item.replace("'", "''")}');\n`;
        });
        sql += `\n`;
    });

    document.getElementById('sql-code-block').innerText = sql;
}

function switchTab(tabName) {
    document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
    document.querySelectorAll('.tab-content').forEach(content => content.classList.remove('active'));

    if(tabName === 'builder') {
        document.querySelectorAll('.tab-btn')[0].classList.add('active');
        document.getElementById('tab-builder').classList.add('active');
    } else {
        document.querySelectorAll('.tab-btn')[1].classList.add('active');
        document.getElementById('tab-sql').classList.add('active');
    }
}

function copySql() {
    const sqlText = document.getElementById('sql-code-block').innerText;
    navigator.clipboard.writeText(sqlText).then(() => {
        alert('Script SQL com todas as 137 peças copiado com sucesso!');
    });
}

window.onload = initApp;
</script>

</body>
</html>
