<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>BeyDeck X Simulator - Pro</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body { background-color: #050505; color: #e2e8f0; }
    .scroll-container { max-height: 400px; overflow-y: auto; }
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
          <select id="sel-blade" class="bg-black p-2 rounded border border-slate-600"></select>
          <select id="sel-ratchet" class="bg-black p-2 rounded border border-slate-600"></select>
          <select id="sel-bit" class="bg-black p-2 rounded border border-slate-600"></select>
        </div>
      </div>
    </div>
  </div>
</div>

<script>
  const fullDatabase = [
    { id: 1, name: "MeteorDragoon 3-70J", type: "Ataque", blade: "MeteorDragoon", ratchet: "3-70", bit: "J" },
    { id: 2, name: "SharkGill 5-60FB", type: "Resistência", blade: "SharkGill", ratchet: "5-60", bit: "FB" },
    { id: 3, name: "HellsScythe 4-60T", type: "Equilíbrio", blade: "HellsScythe", ratchet: "4-60", bit: "T" },
    { id: 4, name: "Rock Leone 6-80GN", type: "Defesa", blade: "Rock Leone", ratchet: "6-80", bit: "GN" },
    // Adicione mais do seu banco aqui seguindo o padrão
  ];

  let state = {
    owned: [],
    wishlist: []
  };

  function updateStats() {
    const activeParts = [...state.owned, ...state.wishlist];
    
    // Extração única
    const blades = [...new Set(activeParts.map(p => p.blade))];
    const ratchets = [...new Set(activeParts.map(p => p.ratchet))];
    const bits = [...new Set(activeParts.map(p => p.bit))];

    document.getElementById('stat-blades').innerText = blades.length;
    document.getElementById('stat-ratchets').innerText = ratchets.length;
    document.getElementById('stat-bits').innerText = bits.length;
    document.getElementById('stat-combos').innerText = blades.length * ratchets.length * bits.length;

    // Atualiza Selects
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
    fullDatabase.forEach(item => {
      container.innerHTML += `
        <div class="flex items-center gap-2 mb-2 p-2 bg-slate-800 rounded">
          <input type="checkbox" onchange="toggleOwnership(${item.id})" id="check-${item.id}">
          <label class="text-sm">${item.name}</label>
        </div>
      `;
    });
  }

  function toggleOwnership(id) {
    const item = fullDatabase.find(i => i.id === id);
    if(state.owned.find(i => i.id === id)) {
      state.owned = state.owned.filter(i => i.id !== id);
    } else {
      state.owned.push(item);
    }
    updateStats();
  }

  init();
</script>
</body>
</html>
