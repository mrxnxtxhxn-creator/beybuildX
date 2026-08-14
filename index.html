<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>BeyDeck X Simulator - Pro</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body { background-color: #050505; color: #e2e8f0; }
    .scroll-container { max-height: 500px; overflow-y: auto; }
    /* Estilização para garantir que os selects apareçam */
    select { color: white; background-color: #1e293b; border: 1px solid #475569; }
    select option { background-color: #0f172a; }
  </style>
</head>
<body class="p-6">

<div class="max-w-7xl mx-auto">
  <h1 class="text-3xl font-bold mb-6 text-cyan-400">BeyDeck X Simulator</h1>

  <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
    
    <!-- Painel de Seleção -->
    <div class="lg:col-span-1 bg-slate-900 p-6 rounded-xl border border-slate-700">
      <h2 class="text-xl font-bold mb-4 text-white">Sua Coleção & Wishlist</h2>
      <div class="scroll-container" id="bey-list">
        <!-- JS Injeta os Beys aqui -->
      </div>
    </div>

    <!-- Painel de Estatísticas -->
    <div class="lg:col-span-2 space-y-6">
      
      <!-- Cards de Métricas -->
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
        <div class="bg-slate-900 p-4 rounded-xl border border-slate-700">
          <div class="text-xs text-slate-400 uppercase">Lâminas</div>
          <div class="text-2xl font-bold text-cyan-400" id="stat-blades">0</div>
        </div>
        <div class="bg-slate-900 p-4 rounded-xl border border-slate-700">
          <div class="text-xs text-slate-400 uppercase">Catracas</div>
          <div class="text-2xl font-bold text-amber-400" id="stat-ratchets">0</div>
        </div>
        <div class="bg-slate-900 p-4 rounded-xl border border-slate-700">
          <div class="text-xs text-slate-400 uppercase">Pontas</div>
          <div class="text-2xl font-bold text-purple-400" id="stat-bits">0</div>
        </div>
        <div class="bg-slate-900 p-4 rounded-xl border border-slate-700">
          <div class="text-xs text-slate-400 uppercase">Combos</div>
          <div class="text-2xl font-bold text-emerald-400" id="stat-combos">0</div>
        </div>
      </div>

      <!-- Simulador de Combo -->
      <div class="bg-slate-800 p-6 rounded-xl border border-slate-600">
        <h3 class="text-lg font-bold mb-4">Testar Combos (Peças Disponíveis)</h3>
        <div class="grid grid-cols-3 gap-4">
          <select id="sel-blade" class="p-2 rounded w-full"></select>
          <select id="sel-ratchet" class="p-2 rounded w-full"></select>
          <select id="sel-bit" class="p-2 rounded w-full"></select>
        </div>
      </div>
    </div>
  </div>
</div>

<script>
  const fullDatabase = [
    { id: 1, name: "MeteorDragoon 3-70J", blade: "MeteorDragoon", ratchet: "3-70", bit: "J" },
    { id: 2, name: "SharkGill 5-60FB", blade: "SharkGill", ratchet: "5-60", bit: "FB" },
    { id: 3, name: "HellsScythe 4-60T", blade: "HellsScythe", ratchet: "4-60", bit: "T" },
    { id: 4, name: "Rock Leone 6-80GN", blade: "Rock Leone", ratchet: "6-80", bit: "GN" }
  ];

  let state = { owned: [...fullDatabase] }; // Começa com todos selecionados

  function updateStats() {
    const blades = [...new Set(state.owned.map(p => p.blade))];
    const ratchets = [...new Set(state.owned.map(p => p.ratchet))];
    const bits = [...new Set(state.owned.map(p => p.bit))];

    document.getElementById('stat-blades').innerText = blades.length;
    document.getElementById('stat-ratchets').innerText = ratchets.length;
    document.getElementById('stat-bits').innerText = bits.length;
    document.getElementById('stat-combos').innerText = (blades.length * ratchets.length * bits.length) || 0;

    fillSelect('sel-blade', blades);
    fillSelect('sel-ratchet', ratchets);
    fillSelect('sel-bit', bits);
  }

  function fillSelect(id, arr) {
    const el = document.getElementById(id);
    el.innerHTML = arr.map(i => `<option value="${i}">${i}</option>`).join('');
  }

  function init() {
    const container = document.getElementById('bey-list');
    container.innerHTML = fullDatabase.map(item => `
      <div class="flex items-center gap-2 mb-2 p-2 bg-slate-800 rounded hover:bg-slate-700 transition">
        <input type="checkbox" checked onchange="toggleOwnership(${item.id})" id="check-${item.id}" class="w-4 h-4">
        <label class="text-sm cursor-pointer select-none">${item.name}</label>
      </div>
    `).join('');
    
    updateStats(); // Atualiza na inicialização
  }

  function toggleOwnership(id) {
    const item = fullDatabase.find(i => i.id === id);
    const index = state.owned.findIndex(i => i.id === id);
    
    if(index > -1) {
      state.owned.splice(index, 1);
    } else {
      state.owned.push(item);
    }
    updateStats();
  }

  init();
</script>
</body>
</html>
