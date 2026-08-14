# beybuildX
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beyblade X — Master Combo Builder & Meta Evaluator</title>
    <style>
        :root {
            --bg-dark: #0f1117;
            --bg-card: #181b24;
            --bg-card-hover: #222634;
            --accent-primary: #ff5500;
            --accent-blue: #00d2ff;
            --accent-green: #00e676;
            --accent-yellow: #ffb700;
            --accent-red: #ff1744;
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
            max-width: 1280px;
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

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        .builder-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
        }

        @media (max-width: 900px) {
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

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: flex;
            justify-content: space-between;
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--text-main);
        }

        .form-group label span.part-type {
            font-size: 0.85rem;
            color: var(--accent-primary);
            text-transform: uppercase;
        }

        select {
            width: 100%;
            padding: 12px 15px;
            background: var(--bg-dark);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            color: var(--text-main);
            font-size: 0.95rem;
            outline: none;
            transition: border-color 0.2s;
        }

        select:focus {
            border-color: var(--accent-blue);
        }

        .part-preview-card {
            background: var(--bg-dark);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 12px 15px;
            margin-top: 8px;
            font-size: 0.88rem;
            color: var(--text-muted);
            line-height: 1.4;
        }

        .part-preview-card strong {
            color: var(--text-main);
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
            margin-bottom: 25px;
        }

        .stat-box {
            background: var(--bg-dark);
            padding: 12px 15px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }

        .stat-box .label {
            font-size: 0.78rem;
            color: var(--text-muted);
            text-transform: uppercase;
        }

        .stat-box .value {
            font-size: 1.25rem;
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
            transition: width 0.4s ease;
        }

        .eval-section {
            background: var(--bg-dark);
            border-left: 4px solid var(--accent-primary);
            padding: 14px;
            border-radius: 0 8px 8px 0;
            margin-bottom: 15px;
        }

        .eval-section h4 {
            color: var(--accent-primary);
            margin-bottom: 4px;
            font-size: 0.95rem;
        }

        .eval-section p {
            font-size: 0.88rem;
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
            font-size: 0.85rem;
            line-height: 1.5;
            max-height: 550px;
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

        .copy-btn:hover {
            opacity: 0.9;
        }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>🌀 Beyblade X — Master Builder & Meta Evaluator</h1>
        <p>Catálogo expandido com todas as peças oficiais, cálculo avançado de estatísticas e diagnóstico para torneios.</p>
    </header>

    <div class="tabs">
        <button class="tab-btn active" onclick="switchTab('builder')">🛠️ Combo Builder</button>
        <button class="tab-btn" onclick="switchTab('sql')">🗄️ Catálogo Completo (SQL)</button>
    </div>

    <!-- TAB 1: BUILDER -->
    <div id="tab-builder" class="tab-content active">
        <div class="builder-grid">
            
            <!-- SELEÇÃO DE PEÇAS -->
            <div class="selection-panel">
                <div class="panel-title">
                    <span>⚡ Seleção de Peças</span>
                    <span class="count-tag" id="total-parts-tag">0 Peças Cadastradas</span>
                </div>
                
                <!-- BLADE -->
                <div class="form-group">
                    <label>
                        Lâmina (Blade)
                        <span class="part-type">Parte Superior</span>
                    </label>
                    <select id="select-blade" onchange="updateCombo()"></select>
                    <div id="preview-blade" class="part-preview-card"></div>
                </div>

                <!-- RATCHET -->
                <div class="form-group">
                    <label>
                        Catraca (Ratchet)
                        <span class="part-type">Parte Central</span>
                    </label>
                    <select id="select-ratchet" onchange="updateCombo()"></select>
                    <div id="preview-ratchet" class="part-preview-card"></div>
                </div>

                <!-- BIT -->
                <div class="form-group">
                    <label>
                        Ponta (Bit)
                        <span class="part-type">Parte Inferior</span>
                    </label>
                    <select id="select-bit" onchange="updateCombo()"></select>
                    <div id="preview-bit" class="part-preview-card"></div>
                </div>
            </div>

            <!-- RESULTADOS -->
            <div class="result-panel">
                <div class="panel-title">📊 Análise de Performance</div>

                <div class="badge-row">
                    <span id="badge-tier" class="badge badge-tier-s">TIER S</span>
                    <span id="badge-type" class="badge badge-type">STAMINA / DEFENSE</span>
                </div>

                <div class="stats-summary">
                    <div class="stat-box">
                        <div class="label">Peso Total Estimado</div>
                        <div class="value" id="val-weight">0.0g</div>
                    </div>
                    <div class="stat-box">
                        <div class="label">Sinergia Física</div>
                        <div class="value" id="val-synergy">0 / 10</div>
                    </div>
                    <div class="stat-box">
                        <div class="label">Risco de Burst</div>
                        <div class="value" id="val-burst">Baixo</div>
                    </div>
                    <div class="stat-box">
                        <div class="label">Estilo de Movimentação</div>
                        <div class="value" id="val-playstyle">Passivo</div>
                    </div>
                </div>

                <!-- BARRAS -->
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
                <div class="eval-section" style="margin-top:18px;">
                    <h4>💡 Diagnóstico Mecânico & Encaixe</h4>
                    <p id="eval-synergy-text">Carregando...</p>
                </div>

                <div class="eval-section" style="border-left-color: var(--accent-blue);">
                    <h4 style="color: var(--accent-blue);">⚔️ Desempenho no Meta Competitivo</h4>
                    <p id="eval-meta-text">Carregando...</p>
                </div>

                <div class="eval-section" style="border-left-color: var(--accent-green);">
                    <h4 style="color: var(--accent-green);">🎯 Recomendação de Lançamento</h4>
                    <p id="eval-launch-text">Carregando...</p>
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
// BANCO DE DADOS EXPANDIDO COMPLETO (BEYBLADE X)
const DB = {
    blades: [
        // STAMINA
        { id: 'wizard_rod', name: 'Wizard Rod', type: 'Stamina', weight: 35.2, atk: 2.0, def: 8.5, sta: 10.0, mob: 3.0, desc: 'Diâmetro circular amplo com massa externa periférica. Líder absoluta em Stamina.' },
        { id: 'silver_wolf', name: 'Silver Wolf', type: 'Stamina', weight: 34.8, atk: 3.0, def: 7.5, sta: 9.2, mob: 4.0, desc: 'Formato livre de baixo atrito aerodinâmico focado em defesa passiva.' },
        { id: 'phoenix_rudder', name: 'Phoenix Rudder', type: 'Stamina', weight: 35.0, atk: 4.0, def: 7.0, sta: 9.0, mob: 4.5, desc: 'Lâmina aerodinâmica de retenção de energia contínua.' },
        { id: 'wyvern_gale', name: 'Wyvern Gale', type: 'Stamina', weight: 32.5, atk: 3.5, def: 6.5, sta: 8.0, mob: 5.0, desc: 'Formatos em hélice que redirecionam o fluxo de ar para manter o giro.' },
        { id: 'wizard_arrow', name: 'Wizard Arrow', type: 'Stamina', weight: 32.0, atk: 3.0, def: 6.0, sta: 7.5, mob: 4.0, desc: 'Lâmina circular clássica para distribuição constante de energia.' },
        { id: 'viper_tail', name: 'Viper Tail', type: 'Stamina', weight: 33.2, atk: 5.0, def: 5.5, sta: 7.5, mob: 4.5, desc: 'Arestas voltadas para baixo para desestabilizar a base do oponente.' },

        // ATTACK
        { id: 'phoenix_wing', name: 'Phoenix Wing', type: 'Attack', weight: 38.0, atk: 9.5, def: 6.0, sta: 4.0, mob: 8.5, desc: 'Pesada e aerodinâmica. Entrega o maior poder de Knockout direto do jogo.' },
        { id: 'cobalt_dragoon', name: 'Cobalt Dragoon', type: 'Attack', weight: 37.8, atk: 9.5, def: 5.0, sta: 4.0, mob: 9.0, desc: 'Lâmina de Rotação Esquerda. Excelente para impactos frontais de repulsão.' },
        { id: 'tyranno_beat', name: 'Tyranno Beat', type: 'Attack', weight: 37.2, atk: 9.0, def: 5.5, sta: 4.2, mob: 7.5, desc: 'Pontos de impacto duplos pesados e rígidos.' },
        { id: 'dran_buster', name: 'Dran Buster', type: 'Attack', weight: 36.5, atk: 10.0, def: 3.0, sta: 2.0, mob: 9.5, desc: 'Lâmina massiva única projetada para One-Hit KO imediato.' },
        { id: 'aero_pegasus', name: 'Aero Pegasus', type: 'Attack', weight: 37.5, atk: 9.2, def: 5.0, sta: 4.5, mob: 9.0, desc: 'Lâmina metálica de alto impacto com asas de sustentação veloz.' },
        { id: 'whale_wave', name: 'Whale Wave', type: 'Attack', weight: 36.0, atk: 8.8, def: 5.0, sta: 4.5, mob: 8.0, desc: 'Ataques verticais pesados (Upper Attack) que levantam o oponente.' },
        { id: 'shark_edge', name: 'Shark Edge', type: 'Attack', weight: 34.5, atk: 9.0, def: 3.5, sta: 2.5, mob: 8.5, desc: 'Lâmina em forma de barbatanas focada em golpear de baixo para cima.' },
        { id: 'dran_sword', name: 'Dran Sword', type: 'Attack', weight: 35.0, atk: 8.2, def: 4.0, sta: 3.0, mob: 8.0, desc: '3 lâminas afiadas para aceleração e colisão contínua.' },
        { id: 'dran_dagger', name: 'Dran Dagger', type: 'Attack', weight: 34.2, atk: 8.0, def: 4.0, sta: 3.5, mob: 8.5, desc: '6 pontos de impacto rápido para combos de golpes múltiplos.' },
        { id: 'cobalt_drake', name: 'Cobalt Drake', type: 'Attack', weight: 38.1, atk: 9.6, def: 5.0, sta: 3.5, mob: 8.0, desc: 'Lâmina rara e ultra pesada com foco em destruição central.' },

        // BALANCE
        { id: 'scythe_incendio', name: 'Scythe Incendio', type: 'Balance', weight: 33.0, atk: 6.0, def: 6.0, sta: 7.0, mob: 6.0, desc: 'Lâmina versátil ideal para contra-ataques e transição de ritmo.' },
        { id: 'hells_chain', name: 'Hells Chain', type: 'Balance', weight: 34.2, atk: 6.5, def: 6.5, sta: 6.8, mob: 5.5, desc: 'Formatos intercalados que amortecem ataques pesados.' },
        { id: 'hells_hammer', name: 'Hells Hammer', type: 'Balance', weight: 33.5, atk: 7.5, def: 5.0, sta: 5.0, mob: 7.0, desc: 'Focada em Smash Attack descendente.' },
        { id: 'unicorn_sting', name: 'Unicorn Sting', type: 'Balance', weight: 33.8, atk: 6.0, def: 6.5, sta: 6.5, mob: 6.0, desc: 'Design assimétrico: um lado ataca e o outro defende.' },

        // DEFENSE
        { id: 'knight_mail', name: 'Knight Mail', type: 'Defense', weight: 36.0, atk: 4.0, def: 9.0, sta: 5.5, mob: 3.5, desc: 'Lâmina blindada pesada com anel defensivo reforçado.' },
        { id: 'knight_shield', name: 'Knight Shield', type: 'Defense', weight: 33.5, atk: 3.5, def: 8.5, sta: 6.0, mob: 3.0, desc: 'Formatos curvos para dissipar o impacto de oponentes agressivos.' },
        { id: 'knight_lance', name: 'Knight Lance', type: 'Defense', weight: 33.2, atk: 4.5, def: 8.0, sta: 5.5, mob: 4.0, desc: 'Contra-ataques defensivos com pontas afiadas nas bordas.' },
        { id: 'sphinx_cowl', name: 'Sphinx Cowl', type: 'Defense', weight: 33.8, atk: 4.0, def: 8.2, sta: 5.0, mob: 3.5, desc: 'Paredes espessas focadas em manter o Bey imóvel no centro.' },
        { id: 'rhino_horn', name: 'Rhino Horn', type: 'Defense', weight: 32.8, atk: 3.0, def: 8.0, sta: 4.0, mob: 2.0, desc: 'Compacto e denso, focado em evitar expulsão por Knockout.' }
    ],

    ratchets: [
        { id: '1-60', name: '1-60', height: 60, protrusions: 1, weight: 6.0, burstRisk: 'Alto', desc: 'Saliência única concentrada. Induz vibração e impacto assimétrico.' },
        { id: '2-60', name: '2-60', height: 60, protrusions: 2, weight: 6.1, burstRisk: 'Médio', desc: '2 pontos de contato alinhados para corte aerodinâmico.' },
        { id: '3-60', name: '3-60', height: 60, protrusions: 3, weight: 6.3, burstRisk: 'Médio', desc: '3 saliências equilibradas. O padrão tradicional para atacantes.' },
        { id: '4-60', name: '4-60', height: 60, protrusions: 4, weight: 6.3, burstRisk: 'Médio', desc: '4 pontos de contato compactos.' },
        { id: '5-60', name: '5-60', height: 60, protrusions: 5, weight: 6.4, burstRisk: 'Baixo', desc: '5 saliências circulares. Um dos Ratchets mais seguros e usados do jogo.' },
        { id: '7-60', name: '7-60', height: 60, protrusions: 7, weight: 6.5, burstRisk: 'Baixo', desc: '7 dentes que suavizam colisões e oferecem excelente massa.' },
        { id: '9-60', name: '9-60', height: 60, protrusions: 9, weight: 6.2, burstRisk: 'Muito Baixo', desc: '9 dentes pequenos que reduzem drasticamente o risco de eclosão.' },
        { id: '1-70', name: '1-70', height: 70, protrusions: 1, weight: 6.3, burstRisk: 'Alto', desc: 'Altura média de 70mm com peso concentrado.' },
        { id: '3-70', name: '3-70', height: 70, protrusions: 3, weight: 6.5, burstRisk: 'Médio', desc: 'Altura intermediária para encaixe de alinhamento com a Blade.' },
        { id: '5-70', name: '5-70', height: 70, protrusions: 5, weight: 6.6, burstRisk: 'Baixo', desc: 'Excelente estabilidade em altura moderada.' },
        { id: '3-80', name: '3-80', height: 80, protrusions: 3, weight: 7.1, burstRisk: 'Alto', desc: 'Altura elevada de 80mm ideal para Smash Attacks de cima para baixo.' },
        { id: '4-80', name: '4-80', height: 80, protrusions: 4, weight: 7.0, burstRisk: 'Alto', desc: 'Estrutura alta para combos defensivos de alcance de topo.' },
        { id: '5-80', name: '5-80', height: 80, protrusions: 5, weight: 7.2, burstRisk: 'Médio', desc: 'Fornece peso extra em 80mm mantendo bom equilíbrio.' },
        { id: '0-80', name: '0-80', height: 80, protrusions: 0, weight: 7.4, burstRisk: 'Baixo', desc: 'Design totalmente liso sem saliências expostas.' },
        { id: '4-55', name: '4-55', height: 55, protrusions: 4, weight: 6.1, burstRisk: 'Muito Baixo', desc: 'Perfil rebaixado ultra baixo (55mm) para proteger o ponto de Burst.' }
    ],

    bits: [
        // STAMINA
        { id: 'ball', name: 'Ball (B)', type: 'Stamina', weight: 2.1, atk: 1.0, def: 7.0, sta: 10.0, mob: 2.0, burstRes: 'Média', desc: 'Ponta esférica padrão de baixo atrito. Fica firme no centro.' },
        { id: 'disc_ball', name: 'Disc Ball (DB)', type: 'Stamina', weight: 2.4, atk: 1.0, def: 8.0, sta: 9.5, mob: 2.0, burstRes: 'Média', desc: 'Possui anel circular que evita raspagem no chão quando perde o equilíbrio.' },
        { id: 'free_ball', name: 'Free Ball (FB)', type: 'Stamina', weight: 2.3, atk: 1.0, def: 7.5, sta: 9.8, mob: 2.5, burstRes: 'Média', desc: 'Esfera com rotação livre que diminui drasticamente o atrito de contato.' },
        { id: 'gear_ball', name: 'Gear Ball (GB)', type: 'Stamina', weight: 2.2, atk: 3.0, def: 6.5, sta: 8.5, mob: 4.0, burstRes: 'Média', desc: 'Ponta Ball com engrenagens estendidas para X-Dash ocasional.' },
        { id: 'orb', name: 'Orb (O)', type: 'Stamina', weight: 2.0, atk: 1.0, def: 6.5, sta: 9.0, mob: 2.0, burstRes: 'Baixa', desc: 'Esfera menor focada em atrito ultra reduzido.' },

        // ATTACK
        { id: 'flat', name: 'Flat (F)', type: 'Attack', weight: 2.0, atk: 9.5, def: 2.0, sta: 2.0, mob: 10.0, burstRes: 'Alta', desc: 'Ponta plana clássica para velocidade máxima no X-Celerator Rail.' },
        { id: 'gear_flat', name: 'Gear Flat (GF)', type: 'Attack', weight: 2.3, atk: 10.0, def: 1.0, sta: 1.0, mob: 10.0, burstRes: 'Alta', desc: 'Dentes estendidos até a base. Aceleração extrema e agressiva.' },
        { id: 'low_flat', name: 'Low Flat (LF)', type: 'Attack', weight: 2.1, atk: 9.8, def: 2.0, sta: 1.5, mob: 10.0, burstRes: 'Alta', desc: 'Rebaixa a altura do Beyblade para desferir Upper Attacks.' },
        { id: 'rush', name: 'Rush (R)', type: 'Attack', weight: 2.1, atk: 8.5, def: 3.0, sta: 4.0, mob: 9.0, burstRes: 'Alta', desc: 'Dentes finos que mantêm ritmo de ataque rápido sem gastar energia tão rápido.' },
        { id: 'low_rush', name: 'Low Rush (LR)', type: 'Attack', weight: 2.2, atk: 8.8, def: 3.0, sta: 3.5, mob: 9.0, burstRes: 'Alta', desc: 'Versão rebaixada da ponta Rush para contato direto sob a Blade oponente.' },
        { id: 'accel', name: 'Accel (A)', type: 'Attack', weight: 2.1, atk: 9.0, def: 2.5, sta: 2.5, mob: 9.5, burstRes: 'Alta', desc: 'Engrenagens anguladas para arrancadas de alta velocidade.' },
        { id: 'quake', name: 'Quake (Q)', type: 'Attack', weight: 2.2, atk: 8.5, def: 1.0, sta: 1.0, mob: 8.0, burstRes: 'Alta', desc: 'Corte diagonal assimétrico que faz o Bey saltar na arena para Smash Attacks.' },

        // BALANCE
        { id: 'point', name: 'Point (P)', type: 'Balance', weight: 2.2, atk: 6.0, def: 6.0, sta: 7.5, mob: 6.5, burstRes: 'Alta', desc: 'Centro esférico com bordas planas. Alterna entre postura de centro e ataques.' },
        { id: 'gear_point', name: 'Gear Point (GP)', type: 'Balance', weight: 2.4, atk: 7.0, def: 5.5, sta: 6.5, mob: 7.5, burstRes: 'Alta', desc: 'Engrenagens extras para reações mais agressivas nas bordas.' },
        { id: 'taper', name: 'Taper (T)', type: 'Balance', weight: 2.2, atk: 6.5, def: 5.0, sta: 6.0, mob: 7.0, burstRes: 'Alta', desc: 'Ponta cônica que mescla movimentação perimetral com controle.' },
        { id: 'high_taper', name: 'High Taper (HT)', type: 'Balance', weight: 2.4, atk: 6.5, def: 5.0, sta: 6.0, mob: 7.0, burstRes: 'Alta', desc: 'Eixo elevado para ataques de cima para baixo.' },
        { id: 'elevate', name: 'Elevate (E)', type: 'Balance', weight: 2.5, atk: 5.0, def: 7.0, sta: 6.0, mob: 6.0, burstRes: 'Alta', desc: 'Aumenta a altura e absorve colisões sem tombar fácil.' },

        // DEFENSE
        { id: 'needle', name: 'Needle (N)', type: 'Defense', weight: 2.0, atk: 2.0, def: 8.5, sta: 6.0, mob: 2.0, burstRes: 'Muito Alta', desc: 'Ponta afiada que fixa o Beyblade exatamente onde ele pousa.' },
        { id: 'high_needle', name: 'High Needle (HN)', type: 'Defense', weight: 2.2, atk: 2.0, def: 8.0, sta: 6.0, mob: 2.5, burstRes: 'Muito Alta', desc: 'Versão elevada da Needle para resistir a ataques descendentes.' },
        { id: 'hexa', name: 'Hexa (H)', type: 'Defense', weight: 2.3, atk: 3.0, def: 9.5, sta: 5.0, mob: 3.0, burstRes: 'Muito Alta', desc: 'Ponta hexagonal pesada de alta aderência contra reveses de KO.' },
        { id: 'bound_spike', name: 'Bound Spike (BS)', type: 'Defense', weight: 2.4, atk: 2.0, def: 9.0, sta: 5.5, mob: 2.0, burstRes: 'Muito Alta', desc: 'Mecanismo interno com mola para amortecimento mecânico de impactos.' }
    ]
};

function initApp() {
    const bSel = document.getElementById('select-blade');
    const rSel = document.getElementById('select-ratchet');
    const btSel = document.getElementById('select-bit');

    bSel.innerHTML = '';
    rSel.innerHTML = '';
    btSel.innerHTML = '';

    // Sort Alphabetically
    DB.blades.sort((a,b) => a.name.localeCompare(b.name)).forEach(b => bSel.innerHTML += `<option value="${b.id}">${b.name} (${b.type})</option>`);
    DB.ratchets.sort((a,b) => a.name.localeCompare(b.name)).forEach(r => rSel.innerHTML += `<option value="${r.id}">${r.name} (${r.height}mm)</option>`);
    DB.bits.sort((a,b) => a.name.localeCompare(b.name)).forEach(bt => btSel.innerHTML += `<option value="${bt.id}">${bt.name} (${bt.type})</option>`);

    const totalCount = DB.blades.length + DB.ratchets.length + DB.bits.length;
    document.getElementById('total-parts-tag').innerText = `${totalCount} Peças no Catálogo`;

    // Defaults (Top Meta)
    bSel.value = 'wizard_rod';
    rSel.value = '5-60';
    btSel.value = 'ball';

    generateSqlBlock();
    updateCombo();
}

function updateCombo() {
    const blade = DB.blades.find(b => b.id === document.getElementById('select-blade').value);
    const ratchet = DB.ratchets.find(r => r.id === document.getElementById('select-ratchet').value);
    const bit = DB.bits.find(bt => bt.id === document.getElementById('select-bit').value);

    document.getElementById('preview-blade').innerHTML = `<strong>${blade.name} [${blade.type}]:</strong> ${blade.desc} (Massa: ~${blade.weight}g)`;
    document.getElementById('preview-ratchet').innerHTML = `<strong>${ratchet.name}:</strong> ${ratchet.desc} (Massa: ~${ratchet.weight}g)`;
    document.getElementById('preview-bit').innerHTML = `<strong>${bit.name} [${bit.type}]:</strong> ${bit.desc} (Massa: ~${bit.weight}g)`;

    const totalWeight = (blade.weight + ratchet.weight + bit.weight).toFixed(1);
    
    let calcAtk = Math.min(100, Math.round(((blade.atk * 0.6) + (bit.atk * 0.4)) * 10));
    let calcDef = Math.min(100, Math.round(((blade.def * 0.5) + (bit.def * 0.5)) * 10));
    let calcSta = Math.min(100, Math.round(((blade.sta * 0.6) + (bit.sta * 0.4)) * 10));
    let calcMob = Math.min(100, Math.round(((blade.mob * 0.3) + (bit.mob * 0.7)) * 10));

    let synergyScore = 7.0;
    let metaTier = 'TIER A (COMPETITIVO)';
    let badgeClass = 'badge-tier-a';
    let comboType = `${blade.type.toUpperCase()} / ${bit.type.toUpperCase()}`;
    
    let synergyText = "Combinação estável. As peças conversam bem entre si para jogos padrão.";
    let metaText = "Possui bom desempenho geral. Capaz de enfrentar a maioria dos combos casuais e avançados.";
    let launchText = "Ajuste a inclinação de acordo com o adversário (Lançamento plano contra atacantes, angulado contra stamina).";

    // Regras de Sinergia do Meta
    if (blade.id === 'wizard_rod' && (bit.type === 'Stamina') && (ratchet.height === 60 || ratchet.height === 55)) {
        synergyScore = 10.0;
        metaTier = 'TIER S+ (DOMINANTE)';
        badgeClass = 'badge-tier-s';
        synergyText = 'Sinergia perfeita de Stamina/Defesa. A largura massiva da Wizard Rod cobre completamente a catraca rebaixada, impedindo oponentes de acertarem as travas de eclosão.';
        metaText = 'Inimigo número 1 dos torneios. Vence com facilidade por Spin Finish (sobrevivência) contra praticamente qualquer setup passivo.';
        launchText = 'Lançamento Plano (Flat Launch) suave e centralizado com força máxima. Não precisa arriscar ir para as bordas.';
    } else if ((blade.id === 'phoenix_wing' || blade.id === 'cobalt_dragoon' || blade.id === 'aero_pegasus') && bit.type === 'Attack') {
        synergyScore = 9.8;
        metaTier = 'TIER S (AGGRO META)';
        badgeClass = 'badge-tier-s';
        synergyText = 'Combo de altíssimo impacto e transferência de energia cinética. A Blade pesada empurra o oponente diretamente para a Extreme Zone.';
        metaText = 'A resposta primária para destruir combos pesados de Stamina (como Wizard Rod) antes que o combate se estenda.';
        launchText = 'Lançamento Inclinado (Banked Launch) para pegar a X-Line com velocidade máxima no segundo 1 de combate.';
    } else if (blade.type === 'Attack' && bit.type === 'Stamina') {
        synergyScore = 5.5;
        metaTier = 'TIER B (INCONSISTENTE)';
        badgeClass = 'badge-tier-b';
        synergyText = 'Conflito de conceitos: A Blade quer causar impacto pesado, mas o Bit passivo reduz a velocidade de aceleração na X-Line.';
        metaText = 'Funciona como surpresa em rodadas específicas, mas perde poder de nocaute e gasta stamina rápido devido ao peso desalinhado.';
        launchText = 'Lançar com leve inclinação lateral tentando acertar um golpe crítico rápido antes de perder rotação.';
    }

    document.getElementById('val-weight').innerText = `${totalWeight}g`;
    document.getElementById('val-synergy').innerText = `${synergyScore} / 10`;
    document.getElementById('val-burst').innerText = ratchet.burstRisk;
    document.getElementById('val-playstyle').innerText = bit.type === 'Attack' ? 'Agressivo (X-Dash)' : (bit.type === 'Stamina' ? 'Passivo (Centro)' : 'Híbrido');

    const badgeTierEl = document.getElementById('badge-tier');
    badgeTierEl.innerText = metaTier;
    badgeTierEl.className = `badge ${badgeClass}`;
    document.getElementById('badge-type').innerText = comboType;

    document.getElementById('txt-atk').innerText = `${calcAtk}%`;
    document.getElementById('bar-atk').style.width = `${calcAtk}%`;

    document.getElementById('txt-def').innerText = `${calcDef}%`;
    document.getElementById('bar-def').style.width = `${calcDef}%`;

    document.getElementById('txt-sta').innerText = `${calcSta}%`;
    document.getElementById('bar-sta').style.width = `${calcSta}%`;

    document.getElementById('txt-mob').innerText = `${calcMob}%`;
    document.getElementById('bar-mob').style.width = `${calcMob}%`;

    document.getElementById('eval-synergy-text').innerText = synergyText;
    document.getElementById('eval-meta-text').innerText = metaText;
    document.getElementById('eval-launch-text').innerText = launchText;
}

function generateSqlBlock() {
    let sql = `-- SCRIPT DE CRIAÇÃO E CARGA COMPLETA - BEYBLADE X DATABASE\n\n`;
    sql += `CREATE TABLE blades (id VARCHAR(50) PRIMARY KEY, name VARCHAR(100), type VARCHAR(30), weight_g DECIMAL(4,1), description TEXT);\n`;
    sql += `CREATE TABLE ratchets (id VARCHAR(50) PRIMARY KEY, name VARCHAR(100), height_mm INT, protrusions INT, weight_g DECIMAL(4,1), burst_risk VARCHAR(30));\n`;
    sql += `CREATE TABLE bits (id VARCHAR(50) PRIMARY KEY, name VARCHAR(100), type VARCHAR(30), weight_g DECIMAL(4,1), burst_resistance VARCHAR(30));\n\n`;

    sql += `-- INSERINDO ALL BLADES (${DB.blades.length})\n`;
    DB.blades.forEach(b => {
        sql += `INSERT INTO blades VALUES ('${b.id}', '${b.name.replace("'", "''")}', '${b.type}', ${b.weight}, '${b.desc.replace("'", "''")}');\n`;
    });

    sql += `\n-- INSERINDO ALL RATCHETS (${DB.ratchets.length})\n`;
    DB.ratchets.forEach(r => {
        sql += `INSERT INTO ratchets VALUES ('${r.id}', '${r.name}', ${r.height}, ${r.protrusions}, ${r.weight}, '${r.burstRisk}');\n`;
    });

    sql += `\n-- INSERINDO ALL BITS (${DB.bits.length})\n`;
    DB.bits.forEach(bt => {
        sql += `INSERT INTO bits VALUES ('${bt.id}', '${bt.name.replace("'", "''")}', '${bt.type}', ${bt.weight}, '${bt.burstRes}');\n`;
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
        alert('Script SQL de todo o catálogo copiado com sucesso!');
    });
}

window.onload = initApp;
</script>

</body>
</html>
