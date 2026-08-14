<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BeyDeck X - Gerador de Combos & Estatísticas</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
  <style>
    body { background-color: #0f172a; color: #f8fafc; font-family: system-ui, -apple-system, sans-serif; }
    .card { background-color: #1e293b; border: 1px solid #334155; }
  </style>
</head>
<body class="p-4 md:p-8">

  <div class="max-w-6xl mx-auto space-y-6">
    
    <!-- Header -->
    <header class="flex flex-col md:flex-row justify-between items-center bg-slate-800 p-6 rounded-2xl border border-slate-700 shadow-xl">
      <div>
        <h1 class="text-3xl font-bold bg-gradient-to-r from-cyan-400 to-blue-500 bg-clip-text text-transparent">
          <i class="fa-solid fa-compact-disc rotate-12 mr-2"></i>BeyDeck X Manager
        </h1>
        <p class="text-slate-400 text-sm mt-1">Gerenciador de Peças, Combos e Estatísticas de Beyblade X</p>
      </div>
      <div class="mt-4 md:mt-0 bg-slate-900 px-4 py-2 rounded-xl border border-slate-700 text-right">
        <span class="text-xs text-slate-400 uppercase font-semibold tracking-wider block">Status da Coleção</span>
        <span id="total-acquired" class="text-xl font-bold text-emerald-400">0</span>
        <span class="text-slate-500 text-sm">/ <span id="total-db">0</span> Beyblades</span>
      </div>
    </header>

    <!-- Métricas Rápidas das Peças -->
    <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
      <div class="card p-4 rounded-xl text-center">
        <i class="fa-solid fa-shield-halved text-cyan-400 text-2xl mb-1"></i>
        <div class="text-2xl font-bold" id="count-blades">0</div>
        <div class="text-xs text-slate-400 font-medium uppercase">Lâminas (Blades)</div>
      </div>
      <div class="card p-4 rounded-xl text-center">
        <i class="fa-solid fa-gear text-amber-400 text-2xl mb-1"></i>
        <div class="text-2xl font-bold" id="count-ratchets">0</div>
        <div class="text-xs text-slate-400 font-medium uppercase">Catracas (Ratchets)</div>
      </div>
      <div class="card p-4 rounded-xl text-center">
        <i class="fa-solid fa-vortex text-purple-400 text-2xl mb-1"></i>
        <div class="text-2xl font-bold" id="count-bits">0</div>
        <div class="text-xs text-slate-400 font-medium uppercase">Pontas (Bits)</div>
      </div>
      <div class="card p-4 rounded-xl text-center">
        <i class="fa-solid fa-bolt text-emerald-400 text-2xl mb-1"></i>
        <div class="text-2xl font-bold" id="possible-combos">0</div>
        <div class="text-xs text-slate-400 font-medium uppercase">Combos Possíveis</div>
      </div>
    </div>

    <!-- Seção Principal: Gerador de Combos & Estatísticas -->
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
      
      <!-- Oficina de Combos (2 Colunas) -->
      <div class="card p-6 rounded-2xl lg:col-span-2 space-y-6">
        <div class="flex justify-between items-center border-b border-slate-700 pb-4">
          <h2 class="text-xl font-bold text-slate-200 flex items-center gap-2">
            <i class="fa-solid fa-sliders text-cyan-400"></i> Oficina de Combos
          </h2>
          <button onclick="generateRandomCombo()" class="bg-cyan-600 hover:bg-cyan-500 text-white text-sm px-4 py-2 rounded-lg font-semibold transition flex items-center gap-2 shadow-lg shadow-cyan-900/40 cursor-pointer">
            <i class="fa-solid fa-dice"></i> Combo Aleatório
          </button>
        </div>

        <!-- Seletores de Peças -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <div>
            <label class="block text-xs font-semibold text-slate-400 uppercase mb-2">Lâmina (Blade)</label>
            <select id="select-blade" class="w-full bg-slate-900 border border-slate-700 rounded-xl p-3 text-sm focus:border-cyan-500 outline-none text-slate-200" onchange="updateComboDisplay()">
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-400 uppercase mb-2">Catraca (Ratchet)</label>
            <select id="select-ratchet" class="w-full bg-slate-900 border border-slate-700 rounded-xl p-3 text-sm focus:border-cyan-500 outline-none text-slate-200" onchange="updateComboDisplay()">
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-400 uppercase mb-2">Ponta (Bit)</label>
            <select id="select-bit" class="w-full bg-slate-900 border border-slate-700 rounded-xl p-3 text-sm focus:border-cyan-500 outline-none text-slate-200" onchange="updateComboDisplay()">
            </select>
          </div>
        </div>

        <!-- Card do Combo Resultante -->
        <div class="bg-slate-900/80 border border-cyan-500/30 rounded-2xl p-6 text-center space-y-3 relative overflow-hidden">
          <div class="text-xs uppercase tracking-widest text-cyan-400 font-bold">Configuração Atual do Combo</div>
          <div id="combo-title" class="text-2xl md:text-3xl font-extrabold text-white tracking-wide">---</div>
          <div id="combo-type-badge" class="inline-block px-3 py-1 rounded-full text-xs font-bold uppercase bg-slate-800 text-slate-400">
            Tipo: Selecione as peças
          </div>
        </div>
      </div>

      <!-- Estatísticas da Coleção (1 Coluna) -->
      <div class="card p-6 rounded-2xl space-y-4">
        <h2 class="text-xl font-bold text-slate-200 border-b border-slate-700 pb-4 flex items-center gap-2">
          <i class="fa-solid fa-chart-pie text-purple-400"></i> Distribuição por Tipo
        </h2>
        <div id="type-stats" class="space-y-4">
          <!-- Renderizado via JS -->
        </div>
      </div>

    </div>

    <!-- Lista de Beyblades Adquiridos (Inventário Ativo) -->
    <div class="card p-6 rounded-2xl space-y-4">
      <h2 class="text-xl font-bold text-slate-200 border-b border-slate-700 pb-4 flex items-center gap-2">
        <i class="fa-solid fa-boxes-stacked text-emerald-400"></i> Beyblades na Coleção (Inventário)
      </h2>
      <div id="acquired-list" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-3">
        <!-- Renderizado via JS -->
      </div>
    </div>

  </div>

  <script>
    // Banco de Dados Completo
    const database = [
      { "nome": "Seize Jaguar HN", "tipo": "", "sistema": "UX Expand", "na_colecao": false },
      { "nome": "KnightShield 3-80N", "tipo": "Defesa", "sistema": "BX", "na_colecao": false },
      { "nome": "SilverWolf 9-70R", "tipo": "Ataque", "sistema": "UX", "na_colecao": false },
      { "nome": "WizardArrow 4-80B", "tipo": "Resistência", "sistema": "BX", "na_colecao": false },
      { "nome": "HellsNether Z", "tipo": "Equilíbrio", "sistema": "U·EB / UX Expand", "na_colecao": false },
      { "nome": "WyvernHover 8-80B", "tipo": "Resistência", "sistema": "UX", "na_colecao": false },
      { "nome": "AeroPegasus 3-70A", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Antler Stag B 2-60HN", "tipo": "Defesa", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "Arrow Wizard 4-80O", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "BahamutBlitz BK1-50I", "tipo": "Ataque", "sistema": "C-E / Custom Line Expand Blade", "na_colecao": true },
      { "nome": "BearScratch 5-60F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Bite Croc 3-60LF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "BlackShell 4-60D", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "BlackShell 7-70WB", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "BlackShell 9-80B", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "BrachioWhip OW5-70Nr", "tipo": "Resistência", "sistema": "C-E / Custom Line Expand Blade", "na_colecao": false },
      { "nome": "BucksAntlers B2-60D", "tipo": "Defesa", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "BulletGriffon H", "tipo": "Equilíbrio", "sistema": "U-E / Unique Line Expand Blade", "na_colecao": false },
      { "nome": "Bumblebee 3-60GP", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Buster Dran 5-70DB", "tipo": "Resistência", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Captain America 4-70GB", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "CerberusDark W1-60F", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "CerberusFlame W5-80WB", "tipo": "Resistência", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "CerberusReaper B0-80WB", "tipo": "Resistência", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "Chewbacca 4-80LF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Circle Ghost 4-60LR", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Clamp Crab 9-65S", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "ClockMirage 9-65B", "tipo": "Resistência", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "CobaltDragoon 2-60C", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "CobaltDragoon 4-55WB", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "CobaltDragoon 9-60F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "CobaltDragoon 9-80F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "CobaltDrake 4-60F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "CobaltDrake 9-60R", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Crest Leon 4-55A", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "CrimsonGaruda 4-70TP", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "CrimsonGaruda 7-80GU", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "CrocCrunch 2-60Q", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Cutter Shinobi LF", "tipo": "Ataque", "sistema": "U-E / Unique Line Expand Blade", "na_colecao": false },
      { "nome": "Dagger Dran 4-70Q", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Darth Vader 4-60P", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DracielShield 7-60D", "tipo": "Defesa", "sistema": "BX / Basic Line X-Over Project", "na_colecao": false },
      { "nome": "DragoonStorm 4-60RA", "tipo": "Ataque", "sistema": "BX / Basic Line X-Over Project", "na_colecao": false },
      { "nome": "DrakeBrave G4-70I", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "DranArc S2-70K", "tipo": "Equilíbrio", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "DranBrave H6-60V", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "DranBrave S6-60V", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": true },
      { "nome": "DranBuster 1-60A", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "DranBuster 2-80Q", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DranBuster 3-70N", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "DranBuster 5-80MN", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "DranDagger 2-80GP", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DranDagger 4-60R", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DranDagger 4-70P", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DranDagger 7-55G", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DranDagger 9-60LF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DranStrike 4-50FF", "tipo": "Ataque", "sistema": "B-E / Basic Line Expand Blade", "na_colecao": false },
      { "nome": "DranSword 1-60V", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DranSword 3-60F", "tipo": "Ataque", "sistema": "B· / Basic Line", "na_colecao": true },
      { "nome": "DranSword 3-80B", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DranSword 4-80DB", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "DranzerSpiral 3-80T", "tipo": "Equilíbrio", "sistema": "BX / Basic Line X-Over Project", "na_colecao": false },
      { "nome": "DrigerSlash 4-80P", "tipo": "Equilíbrio", "sistema": "BX / Basic Line X-Over Project", "na_colecao": false },
      { "nome": "EmperorMight HOp", "tipo": "Equilíbrio", "sistema": "CX / Custom Line", "na_colecao": true },
      { "nome": "EvaArc B0-70E", "tipo": "Equilíbrio", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "EvaBrave A1-70V", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "EvaBrush T2-70A", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "Fang Leon T 4-60U", "tipo": "Equilíbrio", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "Fort Hornet R 7-60T", "tipo": "Equilíbrio", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "FoxBrush J0-80DB", "tipo": "Resistência", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "FoxBrush J2-60U", "tipo": "Equilíbrio", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "FoxBrush J9-70GR", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "General Grievous 3-80HN", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "GhostCircle 0-80GB", "tipo": "Resistência", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "GhostCircle 4-60H", "tipo": "Equilíbrio", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "GhostCircle M-85DS", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Gill Shark 4-70O", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "GloryValkyrie LF", "tipo": "Ataque", "sistema": "BX / Unique Line Expand Blade", "na_colecao": true },
      { "nome": "GoatTackle 7-70T", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "GolemRock 1-60UN", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "GolemRock M-85HN", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": true },
      { "nome": "Green Goblin 9-80HT", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Grogu 3-85E", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Gust Bat 3-85GP", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Hack Viking 4-55O", "tipo": "Resistência", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "HeavensRing 0-80DS", "tipo": "Defesa", "sistema": "B-E / Basic Line Expand Blade", "na_colecao": false },
      { "nome": "HeavensRing 6-60TP", "tipo": "Equilíbrio", "sistema": "B-E / Basic Line Expand Blade", "na_colecao": false },
      { "nome": "HellsArc T3-85O", "tipo": "Resistência", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "HellsBrave J3-60GF", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "HellsChain 5-60HT", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "HellsChain 9-80O", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "HellsHammer 3-70H", "tipo": "Equilíbrio", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "HellsHammer 3-85GU", "tipo": "Equilíbrio", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "HellsReaper T4-70K", "tipo": "Equilíbrio", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "HellsScythe 3-80B", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "HellsScythe 3-80F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "HellsScythe 3-85GB", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "HellsScythe 4-60T", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": true },
      { "nome": "HellsScythe 4-80LF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Hover Wyvern 3-85N", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Hurricane Enlil IS 7-55T", "tipo": "Equilíbrio", "sistema": "CX / Custom Line Expand Blade", "na_colecao": false },
      { "nome": "ImpactDrake 7-55FB", "tipo": "Resistência", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "ImpactDrake 9-60LR", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Iron Man 4-80B", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Suppress Superion 0-70LP", "tipo": "Equilíbrio", "sistema": "BX Expand", "na_colecao": false },
      { "nome": "Knife Shinobi 4-80HN", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "KnightFortress GV8-70UN", "tipo": "Defesa", "sistema": "C-E / Custom Line Expand Blade", "na_colecao": false },
      { "nome": "KnightLance 3-60LF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "KnightLance 4-60GB", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "KnightLance 4-80HN", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "KnightMail 3-85BS", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "KnightShield 4-60LF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "KnightShield 4-80T", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "KnightShield 5-80T", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "KrakenWriggle S3-70O", "tipo": "Resistência", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "LeonClaw 0-80E", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "LeonClaw 3-80HN", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "LeonClaw 5-60P", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "LeonCrest 7-60GN", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "LeonCrest 9-80K", "tipo": "Equilíbrio", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "LeonFang T4-60A", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "Lightning L-Drago 1-60F", "tipo": "Ataque", "sistema": "BX / Basic Line X-Over Project", "na_colecao": false },
      { "nome": "Luke Skywalker 4-80B", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "MammothTusk 2-80E", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "MammothTusk 7-60S", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Megatron 4-80B", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "MeteorDragoon 3-70J", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": true },
      { "nome": "Miles Morales 1-60GN", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Moff Gideon 3-80N", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Mosasaurus 9-60U", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "MummyCurse 4-60C", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "MummyCurse 7-55W", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Obi-Wan Kenobi 4-60P", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Obsidian Shell 3-85S", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Optimus Primal 3-60F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Optimus Prime 4-60P", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "OrochiCluster 6-60LF", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "PegasusBlast ATr", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "PegasusBrush M3-85W", "tipo": "Defesa", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "PerseusDark B6-80W", "tipo": "Defesa", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "PhoenixFeather 2-60N", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "PhoenixFeather 3-60F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "PhoenixFlare Z9-80WW", "tipo": "Defesa", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "PhoenixRudder 4-70LF", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "PhoenixRudder 9-70G", "tipo": "Resistência", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "PhoenixWing 5-80H", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "PhoenixWing 9-60GF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "PhoenixWing 9-80DB", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "PteraSwing 7-70B", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Quetzalcoatlus 4-55D", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "RagnaRage FE4-55Y", "tipo": "Resistência", "sistema": "CX / Custom Line Expand Blade", "na_colecao": false },
      { "nome": "Rampart Aegis GB", "tipo": "Resistência", "sistema": "U-E / Unique Line Expand Blade", "na_colecao": false },
      { "nome": "Red Hulk 1-80R", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "RhinoHorn 3-80S", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "RhinoHorn 5-80Q", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "RhinoReaper C4-55D", "tipo": "Defesa", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "Ridge Triceratops 9-80GN", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Roar Tyranno 9-60GF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Rock Leone 6-80GN", "tipo": "Defesa", "sistema": "BX / Basic Line X-Over Project", "na_colecao": true },
      { "nome": "SamuraiCalibur 6-70M", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SamuraiSaber 2-70L", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "SamuraiSaber 5-60K", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SamuraiSaber 9-65LO", "tipo": "Resistência", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "SamuraiSteel 5-70GF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Savage Bear 3-60S", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "ScorpioSpear 0-70Z", "tipo": "Equilíbrio", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "SharkEdge 1-60Q", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SharkEdge 2-60GP", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SharkEdge 3-60LF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SharkEdge 3-80F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SharkEdge 4-70E", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SharkEdge 4-80N", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SharkEdge 5-60GF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SharkGill 5-60FB", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": true },
      { "nome": "SharkScale 4-50UF", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Shatter Horus 9-65GB", "tipo": "Resistência", "sistema": "B-E / Basic Line Expand Blade", "na_colecao": false },
      { "nome": "ShelterDrake 3-60D", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "ShelterDrake 5-70O", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "ShelterDrake 7-80GP", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "ShinobiKnife 4-60LF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "ShinobiShadow 1-80MN", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "ShinobiShadow 3-70GP", "tipo": "Defesa", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "ShinobiShadow 3-80F", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "ShinobiShadow 9-60LF", "tipo": "Ataque", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Shockwave 5-80O", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SilverWolf 3-80FB", "tipo": "Resistência", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "Snowtrooper 7-60O", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SolBrave C9-70TP", "tipo": "Equilíbrio", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "SolEclipse D5-70TK", "tipo": "Equilíbrio", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "SphinxCowl 1-80GF", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SphinxCowl 4-80HT", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SphinxCowl 5-60O", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "SphinxCowl 9-80GN", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Spider-Man 3-60F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Spinosaurus 3-85A", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Starscream 3-80N", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Steel Samurai 4-80T", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Sting Unicorn 4-60P", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "StormPegasis 3-70RA", "tipo": "Ataque", "sistema": "BX / Basic Line X-Over Project", "na_colecao": false },
      { "nome": "StormSpriggan 2-70M", "tipo": "Equilíbrio", "sistema": "BX / Basic Line X-Over Project", "na_colecao": false },
      { "nome": "Stormtrooper 5-70B", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Stun Medusa 9-60GB", "tipo": "Resistência", "sistema": "UX / Unique Line", "na_colecao": false },
      { "nome": "T. Rex 1-80GB", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Tackle Goat 2-70N", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Tail Viper 3-85LO", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Talon Ptera 3-80B", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Thanos 4-60P", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "The Mandalorian 3-60F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "TriceraPress M-85BS", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "Tusk Mammoth 3-60T", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "TyrannoBeat 1-60RA", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "TyrannoBeat 3-60N", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "TyrannoBeat 3-60S", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "TyrannoBeat 4-70Q", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "TyrannoRoar 1-70L", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "UnicornDelta PO1-80GR", "tipo": "Ataque", "sistema": "C-E / Custom Line Expand Blade", "na_colecao": false },
      { "nome": "UnicornDelta PO3-60GU", "tipo": "Equilíbrio", "sistema": "C-E / Custom Line Expand Blade", "na_colecao": false },
      { "nome": "UnicornSting 3-70D", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "UnicornSting 5-60GP", "tipo": "Equilíbrio", "sistema": "BX / Basic Line", "na_colecao": true },
      { "nome": "ValkyrieVolt S4-70V", "tipo": "Ataque", "sistema": "CX / Custom Line", "na_colecao": false },
      { "nome": "Valor Bison FB", "tipo": "Resistência", "sistema": "U-E / Unique Line Expand Blade", "na_colecao": false },
      { "nome": "Venom 3-80N", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "VictoryValkyrie 2-60RA", "tipo": "Ataque", "sistema": "BX / Basic Line X-Over Project", "na_colecao": false },
      { "nome": "ViperTail 3-80HN", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "ViperTail 4-60F", "tipo": "Ataque", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "ViperTail 5-60F", "tipo": "Resistência", "sistema": "BX / Basic Line", "na_colecao": false },
      { "nome": "ViperTail 5-70D", "tipo": "Defesa", "sistema": "BX / Basic Line", "na_colecao": false }
    ];

    // Parser inteligente para extrair Blade, Ratchet e Bit do nome completo
    function parsePartName(fullName) {
      const parts = fullName.trim().split(/\s+/);
      if (parts.length === 1) {
        return { blade: parts[0], ratchet: "N/A", bit: "N/A" };
      }
      const last = parts[parts.length - 1];
      const secondLast = parts[parts.length - 2];
      
      // Verifica se o penúltimo termo tem formato de ratchet (ex: 3-60, 4-80, M-85, S6-60)
      const ratchetRegex = /^[A-Za-z0-9]+-\d+$/;
      if (ratchetRegex.test(secondLast)) {
        const blade = parts.slice(0, parts.length - 2).join(" ");
        return { blade: blade, ratchet: secondLast, bit: last };
      } else {
        // Caso não haja ratchet explícito separado por espaço padrão
        const blade = parts.slice(0, parts.length - 1).join(" ");
        return { blade: blade, ratchet: "Padrão", bit: last };
      }
    }

    let acquiredBlades = [];
    let acquiredRatchets = [];
    let acquiredBits = [];

    function initManager() {
      // Atualizar contadores gerais
      const totalDb = database.length;
      const acquiredItems = database.filter(item => item.na_colecao);
      document.getElementById("total-db").innerText = totalDb;
      document.getElementById("total-acquired").innerText = acquiredItems.length;

      // Extrair peças únicas da coleção adquirida
      const bladesSet = new Set();
      const ratchetsSet = new Set();
      const bitsSet = new Set();

      acquiredItems.forEach(item => {
        const parsed = parsePartName(item.nome);
        if (parsed.blade) bladesSet.add(parsed.blade);
        if (parsed.ratchet) ratchetsSet.add(parsed.ratchet);
        if (parsed.bit) bitsSet.add(parsed.bit);
      });

      acquiredBlades = Array.from(bladesSet);
      acquiredRatchets = Array.from(ratchetsSet);
      acquiredBits = Array.from(bitsSet);

      // Atualizar métricas visuais das peças
      document.getElementById("count-blades").innerText = acquiredBlades.length;
      document.getElementById("count-ratchets").innerText = acquiredRatchets.length;
      document.getElementById("count-bits").innerText = acquiredBits.length;

      // Calcular combos possíveis (Combinação de Lâmina x Catraca x Ponta)
      const possibleCombos = acquiredBlades.length * acquiredRatchets.length * acquiredBits.length;
      document.getElementById("possible-combos").innerText = possibleCombos;

      // Popular selects de montagem de combos
      populateSelect("select-blade", acquiredBlades);
      populateSelect("select-ratchet", acquiredRatchets);
      populateSelect("select-bit", acquiredBits);

      // Renderizar Estatísticas por Tipo
      renderTypeStats(acquiredItems);

      // Renderizar Lista do Inventário
      renderAcquiredList(acquiredItems);

      // Atualizar display inicial do combo
      updateComboDisplay();
    }

    function populateSelect(elementId, items) {
      const select = document.getElementById(elementId);
      select.innerHTML = "";
      if (items.length === 0) {
        const opt = document.createElement("option");
        opt.value = "";
        opt.innerText = "Nenhuma peça disponível";
        select.appendChild(opt);
        return;
      }
      items.forEach(item => {
        const opt = document.createElement("option");
        opt.value = item;
        opt.innerText = item;
        select.appendChild(opt);
      });
    }

    function updateComboDisplay() {
      const blade = document.getElementById("select-blade").value || "---";
      const ratchet = document.getElementById("select-ratchet").value || "---";
      const bit = document.getElementById("select-bit").value || "---";

      document.getElementById("combo-title").innerText = `${blade} ${ratchet} ${bit}`;
      
      // Encontrar o tipo correspondente se houver na base de dados
      const match = database.find(item => item.nome.toLowerCase().includes(blade.toLowerCase()));
      const tipo = match && match.tipo ? match.tipo : "Personalizado";
      
      const badge = document.getElementById("combo-type-badge");
      badge.innerText = `Tipo: ${tipo}`;
      
      // Cores dinâmicas para o badge conforme o tipo
      badge.className = "inline-block px-3 py-1 rounded-full text-xs font-bold uppercase ";
      if (tipo === "Ataque") badge.className += "bg-red-500/20 text-red-400 border border-red-500/30";
      else if (tipo === "Defesa") badge.className += "bg-blue-500/20 text-blue-400 border border-blue-500/30";
      else if (tipo === "Resistência") badge.className += "bg-emerald-500/20 text-emerald-400 border border-emerald-500/30";
      else if (tipo === "Equilíbrio") badge.className += "bg-amber-500/20 text-amber-400 border border-amber-500/30";
      else badge.className += "bg-slate-800 text-slate-400";
    }

    function generateRandomCombo() {
      if (acquiredBlades.length === 0 || acquiredRatchets.length === 0 || acquiredBits.length === 0) return;
      
      const randomBlade = acquiredBlades[Math.floor(Math.random() * acquiredBlades.length)];
      const randomRatchet = acquiredRatchets[Math.floor(Math.random() * acquiredRatchets.length)];
      const randomBit = acquiredBits[Math.floor(Math.random() * acquiredBits.length)];

      document.getElementById("select-blade").value = randomBlade;
      document.getElementById("select-ratchet").value = randomRatchet;
      document.getElementById("select-bit").value = randomBit;

      updateComboDisplay();
    }

    function renderTypeStats(acquiredItems) {
      const statsContainer = document.getElementById("type-stats");
      statsContainer.innerHTML = "";

      const counts = { "Ataque": 0, "Defesa": 0, "Resistência": 0, "Equilíbrio": 0, "Outros": 0 };
      acquiredItems.forEach(item => {
        if (counts[item.tipo] !== undefined) {
          counts[item.tipo]++;
        } else {
          counts["Outros"]++;
        }
      });

      const total = acquiredItems.length || 1;

      for (const [type, count] of Object.entries(counts)) {
        if (type === "Outros" && count === 0) continue;
        const percentage = Math.round((count / total) * 100);
        
        let colorClass = "bg-cyan-500";
        if (type === "Ataque") colorClass = "bg-red-500";
        if (type === "Defesa") colorClass = "bg-blue-500";
        if (type === "Resistência") colorClass = "bg-emerald-500";
        if (type === "Equilíbrio") colorClass = "bg-amber-500";

        statsContainer.innerHTML += `
          <div>
            <div class="flex justify-between text-sm mb-1">
              <span class="text-slate-300 font-medium">${type}</span>
              <span class="text-slate-400">${count} (${percentage}%)</span>
            </div>
            <div class="w-full bg-slate-900 rounded-full h-2.5 border border-slate-700">
              <div class="${colorClass} h-2.5 rounded-full" style="width: ${percentage}%"></div>
            </div>
          </div>
        `;
      }
    }

    function renderAcquiredList(acquiredItems) {
      const listContainer = document.getElementById("acquired-list");
      listContainer.innerHTML = "";

      acquiredItems.forEach(item => {
        listContainer.innerHTML += `
          <div class="bg-slate-900 border border-slate-700/60 p-3 rounded-xl flex flex-col justify-between hover:border-cyan-500/50 transition">
            <span class="font-bold text-slate-200 text-sm">${item.nome}</span>
            <div class="flex justify-between items-center mt-2">
              <span class="text-xs px-2 py-0.5 rounded-full bg-slate-800 text-slate-400 font-semibold">${item.tipo || "Misto"}</span>
              <span class="text-xs text-cyan-400 font-mono">${item.sistema}</span>
            </div>
          </div>
        `;
      });
    }

    // Inicializar ao carregar a página
    window.onload = initManager;
  </script>
</body>
</html>
