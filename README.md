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
      
      <!-- Gerador de Combos (2 Colunas) -->
      <div class="card p-6 rounded-2xl lg:col-span-2 space-y-6">
        <div class="flex justify-between items-center border-b border-slate-700 pb-4">
          <h2 class="text-xl font-bold text-slate-200 flex items-center gap-2">
            <i class="fa-solid fa-sliders text-cyan-400"></i> Ofina de Combos
          </h2>
          <button onclick="generateRandomCombo()" class="bg-cyan-600 hover:bg-cyan-500 text-white text-sm px-4 py-2 rounded-lg font-semibold transition flex items-center gap-2 shadow-lg shadow-cyan-900/40">
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
          <div class="text-xs uppercase tracking-widest text-cyan-400 font-bold">Configuração Atual</div>
          <div id="combo-title" class="text-2xl md:text-3xl font-extrabold text-white tracking-wide">---</div>
          <div id="combo-type-badge" class="inline-block px-3 py-1 rounded-full text-xs font-bold uppercase bg-slate-800 text-slate-400">
            Tipo: Padrão da Lâmina
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
        <i class="fa-solid fa-boxes-stacked text-emerald-400"></i> Beyblades na Coleção (Peças Dísponiveis)
      </h2>
      <div id="acquired-list" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-3">
        <!-- Renderizado via JS -->
      </div>
    </div>

  </div>

  <script>
    // Banco de Dados Integrado
    const database = [
      { nome: "BahamutBlitz BK1-50I", tipo: "Ataque", sistema: "C-E", na_colecao: true },
      { nome: "DranBrave S6-60V", tipo: "Ataque", sistema: "CX", na_colecao: true },
      { nome: "DranSword 3-60F", tipo: "Ataque", sistema: "BX", na_colecao: true },
      { nome: "EmperorMight HOp", tipo: "Equilíbrio", sistema: "CX", na_colecao: true },
      { nome: "GloryValkyrie LF", tipo: "Ataque", sistema: "BX", na_colecao: true },
      { nome: "GolemRock M-85HN", tipo: "Defesa", sistema: "UX", na_colecao: true },
      { nome: "HellsScythe 4-60T", tipo: "Equilíbrio", sistema: "BX", na_colecao: true },
      { nome: "MeteorDragoon 3-70J", tipo: "Ataque", sistema: "UX", na_colecao: true },
      { nome: "Rock Leone 6-80GN", tipo: "Defesa", sistema: "BX", na_colecao: true },
      { nome: "SharkGill 5-60FB", tipo: "Resistência", sistema: "BX", na_colecao: true },
      { nome: "UnicornSting 5-60GP", tipo: "Equilíbrio", sistema: "BX", na_colecao: true },
      // Itens não adquiridos para controle do banco
      { nome: "KnightShield 3-80N", tipo: "Defesa", sistema: "BX", na_colecao: false },
      { nome: "SilverWolf 9-70R", tipo: "Ataque", sistema: "UX", na_colecao: false },
      { nome: "WizardArrow 4-80B", tipo: "Resistência", sistema: "BX", na_colecao: false }
    ];

    // Arrays de Peças Extraídas
    let inventory = {
      blades: new Map(), // name -> { type, origin }
      ratchets: new Set(),
      bits: new Set()
    };

    // Função para Desmembrar Peças
    function parseBeybladeParts(item) {
      const parts = item.nome.split(" ");
      let blade = "", ratchet = "", bit = "";

      if (parts.length === 2) {
        blade = parts[0];
        const code = parts[1];
        // Verifica se tem ratchet separado por hífen ex: 3-60F ou BK1-50I ou M-85HN
        const match = code.match(/^([A-Z0-9]+-[0-9]+|S[0-9]-[0-9]+|BK[0-9]-[0-9]+|M-[0-9]+)?([A-Z]+)$/i);
        if (match) {
          ratchet = match[1] || "Integrado";
          bit = match[2] || "";
        } else {
          bit = code;
        }
      } else if (parts.length >= 3) {
        bit = parts.pop();
        ratchet = parts.pop();
        blade = parts.join(" ");
      }

      return { blade, ratchet, bit, tipo: item.tipo };
    }

    // Inicialização dos Dados
    function initApp() {
      const acquiredList = database.filter(item => item.na_colecao);
      
      // Atualiza Contadores Totais
      document.getElementById('total-acquired').innerText = acquiredList.length;
      document.getElementById('total-db').innerText = database.length;

      // Processa e Separa Peças dos Beyblades Adquiridos
      acquiredList.forEach(item => {
        const { blade, ratchet, bit, tipo } = parseBeybladeParts(item);
        if (blade) inventory.blades.set(blade, tipo);
        if (ratchet && ratchet !== "Integrado") inventory.ratchets.add(ratchet);
        if (bit) inventory.bits.add(bit);
      });

      // Preenche os Selects de Combos
      populateSelect('select-blade', Array.from(inventory.blades.keys()));
      populateSelect('select-ratchet', Array.from(inventory.ratchets));
      populateSelect('select-bit', Array.from(inventory.bits));

      // Atualiza Métricas
      document.getElementById('count-blades').innerText = inventory.blades.size;
      document.getElementById('count-ratchets').innerText = inventory.ratchets.size;
      document.getElementById('count-bits').innerText = inventory.bits.size;
      
      const totalCombos = inventory.blades.size * (inventory.ratchets.size || 1) * (inventory.bits.size || 1);
      document.getElementById('possible-combos').innerText = totalCombos;

      // Renderiza Estatísticas e Inventário
      renderTypeStats(acquiredList);
      renderAcquiredList(acquiredList);
      updateComboDisplay();
    }

    function populateSelect(id, items) {
      const select = document.getElementById(id);
      select.innerHTML = '';
      items.sort().forEach(item => {
        const opt = document.createElement('option');
        opt.value = item;
        opt.textContent = item;
        select.appendChild(opt);
      });
    }

    function updateComboDisplay() {
      const blade = document.getElementById('select-blade').value;
      const ratchet = document.getElementById('select-ratchet').value;
      const bit = document.getElementById('select-bit').value;

      document.getElementById('combo-title').innerText = `${blade} ${ratchet}${bit}`;
      
      const bladeType = inventory.blades.get(blade) || "Desconhecido";
      const badge = document.getElementById('combo-type-badge');
      badge.innerText = `Tipo Predominante: ${bladeType}`;
      
      // Cores por tipo
      const typeColors = {
        "Ataque": "bg-red-500/20 text-red-400 border-red-500/40",
        "Defesa": "bg-green-500/20 text-green-400 border-green-500/40",
        "Resistência": "bg-yellow-500/20 text-yellow-400 border-yellow-500/40",
        "Equilíbrio": "bg-purple-500/20 text-purple-400 border-purple-500/40"
      };
      
      badge.className = `inline-block px-3 py-1 rounded-full text-xs font-bold uppercase border ${typeColors[bladeType] || 'bg-slate-800 text-slate-400'}`;
    }

    function generateRandomCombo() {
      const getRandom = arr => arr[Math.floor(Math.random() * arr.length)];
      
      document.getElementById('select-blade').value = getRandom(Array.from(inventory.blades.keys()));
      document.getElementById('select-ratchet').value = getRandom(Array.from(inventory.ratchets));
      document.getElementById('select-bit').value = getRandom(Array.from(inventory.bits));
      
      updateComboDisplay();
    }

    function renderTypeStats(items) {
      const counts = { "Ataque": 0, "Defesa": 0, "Resistência": 0, "Equilíbrio": 0 };
      items.forEach(i => { if (counts[i.tipo] !== undefined) counts[i.tipo]++; });

      const total = items.length || 1;
      const container = document.getElementById('type-stats');
      container.innerHTML = '';

      const colorMap = {
        "Ataque": "bg-red-500",
        "Defesa": "bg-emerald-500",
        "Resistência": "bg-amber-500",
        "Equilíbrio": "bg-purple-500"
      };

      Object.keys(counts).forEach(tipo => {
        const pct = Math.round((counts[tipo] / total) * 100);
        container.innerHTML += `
          <div>
            <div class="flex justify-between text-xs font-semibold mb-1">
              <span class="text-slate-300">${tipo}</span>
              <span class="text-slate-400">${counts[tipo]} (${pct}%)</span>
            </div>
            <div class="w-full bg-slate-900 rounded-full h-2 overflow-hidden">
              <div class="${colorMap[tipo]} h-2 rounded-full" style="width: ${pct}%"></div>
            </div>
          </div>
        `;
      });
    }

    function renderAcquiredList(items) {
      const container = document.getElementById('acquired-list');
      container.innerHTML = '';

      items.forEach(item => {
        const { blade, ratchet, bit } = parseBeybladeParts(item);
        container.innerHTML += `
          <div class="bg-slate-900/60 p-3 rounded-xl border border-slate-700/60 flex flex-col justify-between">
            <div class="font-bold text-sm text-slate-200">${item.nome}</div>
            <div class="mt-2 text-xs flex flex-wrap gap-1">
              <span class="bg-slate-800 text-cyan-400 px-2 py-0.5 rounded border border-slate-700">${blade}</span>
              ${ratchet !== "Integrado" ? `<span class="bg-slate-800 text-amber-400 px-2 py-0.5 rounded border border-slate-700">${ratchet}</span>` : ''}
              <span class="bg-slate-800 text-purple-400 px-2 py-0.5 rounded border border-slate-700">${bit}</span>
            </div>
          </div>
        `;
      });
    }

    // Inicializar na Carga da Página
    document.addEventListener('DOMContentLoaded', initApp);
  </script>
</body>
</html>
