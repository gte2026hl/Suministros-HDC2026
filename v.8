<!DOCTYPE html>
<html lang="es" class="h-full bg-slate-950 text-slate-200">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
    <script src="https://unpkg.com/jspdf@latest/dist/jspdf.umd.min.js"></script>
    <script src="https://unpkg.com/jspdf-autotable@latest/dist/jspdf.plugin.autotable.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&family=JetBrains+Mono:wght@500&display=swap" rel="stylesheet">
    <title>Sistema de Cobro / HDC Design & Tech  / </title>
    <style>
        body { font-family: 'Inter', sans-serif; -webkit-tap-highlight-color: transparent; background-color: #020617; overscroll-behavior-y: contain; }
        .mono { font-family: 'JetBrains Mono', monospace; }
        .glass { background: rgba(15, 23, 42, 0.7); backdrop-filter: blur(12px); border: 1px solid rgba(255,255,255,0.05); }
        .tab-active { border-bottom: 3px solid #10b981 !important; color: #10b981 !important; font-weight: 900 !important; }
        input, select, textarea { font-size: 16px !important; } 
        .sello-bg { background: linear-gradient(135deg, #fbbf24 0%, #b45309 100%); box-shadow: 0 4px 15px rgba(180, 83, 9, 0.4); border: 2px solid rgba(255, 255, 255, 0.2); }
        .sello-text { background: linear-gradient(to right, #f8fafc 0%, #94a3b8 40%, #2563eb 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; font-weight: 900; line-height: 1; text-shadow: 0 2px 4px rgba(0,0,0,0.1); }
        input::-webkit-outer-spin-button, input::-webkit-inner-spin-button { -webkit-appearance: none; margin: 0; }
        .loading-bar { height: 3px; background: linear-gradient(to right, #fbbf24, #10b981); width: 0%; transition: width 0.4s ease; position: fixed; top: 0; left: 0; z-index: 200; }
        .fade-in { animation: fadeIn 0.3s ease-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(5px); } to { opacity: 1; transform: translateY(0); } }
        @media print { .no-print { display: none !important; } }
    </style>
</head>
<body class="min-h-screen flex flex-col overflow-x-hidden">

    <div id="loader" class="loading-bar"></div>

    <div id="login-view" class="fixed inset-0 z-[100] bg-slate-950 flex items-center justify-center p-6">
        <div class="max-w-md w-full glass p-10 rounded-[3rem] text-center space-y-8 border border-white/10 shadow-2xl">
            <div class="sello-bg w-28 h-28 rounded-2xl flex items-center justify-center mx-auto transform rotate-3 scale-110"><span class="sello-text text-2xl">HDC<br>2026</span></div>
            <div><h1 class="text-2xl font-black uppercase tracking-tighter text-white italic">Acceso al Sistema</h1><p class="text-[9px] text-slate-500 font-bold uppercase tracking-[0.3em] mt-2 italic">HDC Design & Tech</p></div>
            <div class="space-y-4">
                <input type="text" id="user-input" placeholder="Usuario" class="w-full bg-slate-900 border border-slate-800 p-4 rounded-2xl outline-none focus:border-amber-500 text-xs font-bold uppercase text-white">
                
                <div class="relative">
                    <input type="password" id="pass-input" placeholder="Contraseña" class="w-full bg-slate-900 border border-slate-800 p-4 rounded-2xl outline-none focus:border-amber-500 text-xs font-bold text-white">
                    <button onclick="togglePass()" class="absolute right-4 top-1/2 -translate-y-1/2 text-slate-500 hover:text-white transition-colors" id="eye-icon">👁️</button>
                </div>

                <button onclick="intentarLogin()" class="w-full bg-amber-600 hover:bg-amber-500 text-white py-4 rounded-2xl font-black uppercase text-[10px] tracking-[0.3em] shadow-xl active:scale-95 transition-all">Entrar al Portal</button>
            </div>
        </div>
    </div>

    <div id="main-app" class="hidden min-h-screen flex flex-col">
        <nav class="w-full h-auto glass sticky top-0 z-50 flex flex-col px-4 border-b border-slate-800 no-print">
    <div class="flex items-center justify-between w-full pt-3 pb-1">
        <div class="flex items-center gap-2">
            <div id="sello-nav" class="sello-bg w-8 h-8 rounded flex items-center justify-center transform -rotate-2">
                <span class="sello-text text-[6px]">HDC<br>2026</span>
            </div>
            <h2 id="nav-comunidad" class="text-[10px] font-black uppercase text-slate-200 truncate max-w-[140px]">---</h2>
        </div>
        <p id="nav-sector" class="text-[8px] text-emerald-500 font-bold uppercase tracking-widest">---</p>
    </div>
    
    <div id="nav-container" class="flex justify-between items-center w-full h-10 border-t border-slate-900/50 mt-1">
        </div>
</nav>

    <script>
        const SB_URL = "https://wokszafewnnsmmhsvsqf.supabase.co";
        const SB_KEY = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Indva3N6YWZld25uc21taHN2c3FmIiwicm9sZSI6ImFub24iLCJpYXQiOjE3Nzg2ODkyMjEsImV4cCI6MjA5NDI2NTIyMX0.gYZ6rVgc74nE1Kxlykvr_beItgA6ndfv2bMs3godQK0";
        const _sb = supabase.createClient(SB_URL, SB_KEY);

        let uSession = null, censo = [], pagos = [], config = {}, selectedComId = null;

        window.onload = async () => {
            const saved = localStorage.getItem('hdc_session');
            if(saved) {
                uSession = JSON.parse(saved);
                document.getElementById('login-view').classList.add('hidden');
                document.getElementById('main-app').classList.remove('hidden');
                await syncData(); renderNav();
                uSession.role === 'MASTER' ? showMaster() : showSection('gestion');
            }
        }

        // FUNCIÓN QUIRÚRGICA: TOGGLE CONTRASEÑA
        function togglePass() {
            const p = document.getElementById('pass-input');
            const e = document.getElementById('eye-icon');
            if (p.type === 'password') {
                p.type = 'text'; e.innerText = '👁️‍🗨️';
            } else {
                p.type = 'password'; e.innerText = '👁️';
            }
        }

        async function syncData() {
            const id = uSession.id;
            const { data: c } = await _sb.from('configuracion').select('*').eq('comunidad_id', id).maybeSingle();
            const { data: h } = await _sb.from('habitantes').select('*').eq('comunidad_id', id);
            const { data: pg } = await _sb.from('pagos').select('*').eq('comunidad_id', id).order('created_at', { ascending: false });
            config = c || { p10:1500, p18:2500, p43:5500 }; censo = h || []; pagos = pg || [];
            document.getElementById('nav-comunidad').innerText = uSession.comunidad_name;
            document.getElementById('nav-sector').innerText = uSession.municipio_name || "SISTEMA CENTRAL";
        }

        function updateLoader(p) { document.getElementById('loader').style.width = p+"%"; if(p===100)setTimeout(()=>document.getElementById('loader').style.width="0%",400); }
        function logout() { localStorage.removeItem('hdc_session'); location.reload(); }

        async function intentarLogin() {
            updateLoader(30);
            const u = document.getElementById('user-input').value.toLowerCase().trim();
            const p = document.getElementById('pass-input').value.trim();
            const { data } = await _sb.from('perfiles').select('*').eq('usuario', u).eq('password', p).maybeSingle();
            if(data) {
                uSession = data; localStorage.setItem('hdc_session', JSON.stringify(data));
                document.getElementById('login-view').classList.add('hidden');
                document.getElementById('main-app').classList.remove('hidden');
                await syncData(); renderNav();
                uSession.role === 'MASTER' ? showMaster() : showSection('gestion');
                updateLoader(100);
            } else { updateLoader(0); alert("Acceso Denegado."); }
        }

        function renderNav() {
            // INTEGRACIÓN NIEVES: OCULTAR LOGO SI ES JEFE
            const esJefe = uSession.role === 'JEFE';
            document.getElementById('sello-nav').style.display = esJefe ? 'none' : 'flex';
            document.getElementById('info-comunidad').className = esJefe ? "leading-none" : "leading-none border-l border-slate-800 pl-4 ml-2";

            const c = document.getElementById('nav-container');
            if(uSession.role === 'MASTER') {
                c.innerHTML = `<button onclick="showMaster()" class="h-full px-4 text-[9px] font-black uppercase tab-active">Admin Central</button>`;
            } else {
                c.innerHTML = `
                    <button onclick="showSection('gestion')" id="nav-gestion" class="h-full px-4 text-[9px] font-black uppercase tab-active">Cobros</button>
                    <button onclick="showSection('stats')" id="nav-stats" class="h-full px-4 text-[9px] font-black uppercase text-slate-500">Estadísticas</button>
                    <button onclick="showSection('despacho')" id="nav-despacho" class="h-full px-4 text-[9px] font-black uppercase text-slate-500">Despacho</button>`;
            }
            c.innerHTML += `<button onclick="logout()" class="px-4 text-rose-500">✕</button>`;
        }

        // --- MASTER ---
        async function showMaster() {
            updateLoader(50);
            const { data: coms } = await _sb.from('perfiles').select('*').eq('role', 'JEFE');
            updateLoader(100);
            document.getElementById('app-view').innerHTML = `
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 fade-in">
                    <div class="glass p-8 rounded-[2.5rem] space-y-6">
                        <h3 class="text-xs font-black text-amber-500 uppercase italic">Activar Comunidad</h3>
                        <div class="space-y-4">
                            <input type="text" id="nu-u" placeholder="USUARIO" class="w-full bg-slate-900 border-slate-800 p-4 rounded-xl text-xs text-white outline-none">
                            <input type="text" id="nu-p" placeholder="PASSWORD" class="w-full bg-slate-900 border-slate-800 p-4 rounded-xl text-xs text-white outline-none">
                            <input type="text" id="nu-c" placeholder="COMUNIDAD" class="w-full bg-slate-900 border-slate-800 p-4 rounded-xl text-xs text-white outline-none uppercase">
                            <input type="text" id="nu-m" placeholder="MUNICIPIO" class="w-full bg-slate-900 border-slate-800 p-4 rounded-xl text-xs text-white outline-none uppercase">
                            <button onclick="crearComunidad()" class="w-full bg-white text-slate-950 py-4 rounded-xl font-black text-[10px] uppercase">Registrar Jefe</button>
                        </div>
                    </div>
                    <div class="lg:col-span-2 glass p-8 rounded-[2.5rem] space-y-4">
                        <h3 class="text-xs font-black text-slate-500 uppercase italic">Ecosistemas Activos</h3>
                        <div class="grid grid-cols-1 gap-3">${coms.map(c => `
                            <div class="glass p-5 rounded-[1.8rem] border-l-4 border-amber-500 flex justify-between items-center">
                                <div><h4 class="text-xs font-black text-white uppercase">${c.comunidad_name}</h4><p class="text-[8px] text-emerald-500 font-bold uppercase">${c.municipio_name}</p></div>
                                <div class="flex gap-2">
                                    <button onclick="prepararCarga('${c.id}')" class="bg-slate-800 text-white px-4 py-2 rounded-xl text-[9px] font-black uppercase">Excel</button>
                                    <button onclick="borrarComunidad('${c.id}')" class="text-rose-500 px-3">✕</button>
                                </div>
                            </div>`).join('')}</div>
                    </div>
                </div>`;
        }

        async function crearComunidad() {
            const u = document.getElementById('nu-u').value.toLowerCase().trim();
            const p = document.getElementById('nu-p').value;
            const c = document.getElementById('nu-c').value.toUpperCase();
            const m = document.getElementById('nu-m').value.toUpperCase();
            const { data: newUser } = await _sb.from('perfiles').insert([{ usuario:u, password:p, comunidad_name:c, municipio_name:m }]).select().single();
            if(newUser) { await _sb.from('configuracion').insert([{ comunidad_id: newUser.id }]); showMaster(); }
        }

        async function borrarComunidad(id) { if(confirm("¿Eliminar?")) { await _sb.from('perfiles').delete().eq('id', id); showMaster(); } }
        function prepararCarga(id) { selectedComId = id; const i = document.createElement('input'); i.type='file'; i.accept='.xlsx'; i.onchange=(e)=>ejecutarExcel(e.target.files[0]); i.click(); }
        async function ejecutarExcel(file) {
            updateLoader(30); const reader = new FileReader();
            reader.onload = async (e) => {
                const b = XLSX.read(new Uint8Array(e.target.result), {type:'array'});
                const j = XLSX.utils.sheet_to_json(b.Sheets[b.SheetNames[0]], {header:1});
                const rows = j.slice(1).map(r => ({ nombre:String(r[0]||"").toUpperCase().trim(), calle:String(r[1]||"").toUpperCase().trim(), ci:String(r[2]||"").trim(), comunidad_id:selectedComId })).filter(h => h.ci.length > 4);
                const unique = Array.from(new Map(rows.map(h => [h.ci, h])).values());
                await _sb.from('habitantes').delete().eq('comunidad_id', selectedComId);
                await _sb.from('habitantes').insert(unique); updateLoader(100); alert("Censo Sincronizado.");
            }; reader.readAsArrayBuffer(file);
        }

        // --- JEFE ---
        function showSection(id) {
            ['gestion', 'stats', 'despacho'].forEach(s => { const el = document.getElementById(`nav-${s}`); if(el){el.classList.remove('tab-active'); el.classList.add('text-slate-500');} });
            document.getElementById(`nav-${id}`).classList.add('tab-active'); document.getElementById(`nav-${id}`).classList.remove('text-slate-500');
            
            const v = document.getElementById('app-view');
            if(id === 'gestion') {
                v.innerHTML = `
                <div class="space-y-6 fade-in">
                    <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                        <div class="lg:col-span-4 glass p-6 rounded-3xl border-l-4 border-amber-500">
                            <div class="flex justify-between items-center mb-4"><p class="text-[10px] font-black text-amber-500 uppercase italic">Precios Ciclo</p><button onclick="guardarPrecios()" class="bg-emerald-600 px-3 py-1 rounded-full text-[8px] font-black uppercase text-white">Fijar</button></div>
                            <div class="grid grid-cols-3 gap-2">
                                <div class="bg-slate-950 p-2 rounded-xl text-center"><label class="text-[7px] text-slate-500 block">10kg</label><input type="number" id="p10" value="${config.p10}" oninput="validarCobro()" class="bg-transparent w-full font-black text-xs text-center outline-none"></div>
                                <div class="bg-slate-950 p-2 rounded-xl text-center"><label class="text-[7px] text-slate-500 block">18kg</label><input type="number" id="p18" value="${config.p18}" oninput="validarCobro()" class="bg-transparent w-full font-black text-xs text-center outline-none"></div>
                                <div class="bg-slate-950 p-2 rounded-xl text-center"><label class="text-[7px] text-slate-500 block">43kg</label><input type="number" id="p43" value="${config.p43}" oninput="validarCobro()" class="bg-transparent w-full font-black text-xs text-center outline-none"></div>
                            </div>
                        </div>
                        <div id="tot-cont" class="lg:col-span-8 grid grid-cols-2 sm:grid-cols-4 gap-2"></div>
                    </div>
                    <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                        <div class="lg:col-span-8 glass p-6 sm:p-10 rounded-[2.5rem] space-y-8">
                            <div class="flex justify-between items-start"><h3 class="text-xl font-black italic uppercase tracking-tighter">Validador Tactical .01</h3><div id="status-val" class="px-5 py-2 rounded-full text-[9px] font-black bg-slate-800 text-slate-500 uppercase tracking-widest">Esperando Cédula</div></div>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
                                <div class="space-y-6">
                                    <input type="number" id="ci" oninput="lookCI(this.value)" class="w-full bg-slate-950 border border-slate-800 p-5 rounded-2xl text-2xl mono text-white outline-none focus:border-amber-500" placeholder="00000000">
                                    <div id="v-name" class="text-emerald-400 font-black uppercase text-[11px] italic min-h-[1.5rem]"></div>
                                    <div class="grid grid-cols-2 gap-4">
                                        <input type="text" id="ref" class="bg-slate-950 p-4 rounded-xl border border-slate-800 text-white uppercase outline-none text-xs" placeholder="REFERENCIA">
                                        <input type="number" id="m-ref" oninput="validarCobro()" class="bg-slate-900 p-4 rounded-xl border border-slate-700 font-black text-white outline-none text-xs" placeholder="MONTO BS">
                                    </div>
                                </div>
                                <div class="bg-slate-950/40 p-8 rounded-3xl border border-white/5 space-y-6">
                                    <div class="grid grid-cols-3 gap-3">
                                        <div class="text-center"><span class="text-[8px] font-bold opacity-30 block mb-1 uppercase">10kg</span><input type="number" id="q10" value="0" oninput="validarCobro()" class="w-full bg-slate-900 p-3 rounded-xl text-center font-black text-emerald-500"></div>
                                        <div class="text-center"><span class="text-[8px] font-bold opacity-30 block mb-1 uppercase">18kg</span><input type="number" id="q18" value="0" oninput="validarCobro()" class="w-full bg-slate-900 p-3 rounded-xl text-center font-black text-emerald-500"></div>
                                        <div class="text-center"><span class="text-[8px] font-bold opacity-30 block mb-1 uppercase">43kg</span><input type="number" id="q43" value="0" oninput="validarCobro()" class="w-full bg-slate-900 p-3 rounded-xl text-center font-black text-emerald-500"></div>
                                    </div>
                                    <div class="pt-6 border-t border-slate-800 flex justify-between items-center"><span class="text-[10px] font-black text-slate-500 uppercase tracking-widest">Requerido:</span><span id="v-calc" class="text-3xl font-black mono text-white">0.00</span></div>
                                    <button onclick="cobrar()" id="v-btn" disabled class="w-full bg-slate-800 text-slate-500 py-5 rounded-2xl font-black uppercase text-[10px] tracking-widest transition-all">Registrar Transacción</button>
                                </div>
                            </div>
                        </div>
                        <div class="lg:col-span-4 glass p-8 rounded-[2.5rem] flex flex-col"><h4 class="text-[10px] font-black uppercase mb-6 flex justify-between"><span>Historial Activo</span><span id="p-count" class="text-emerald-500">0</span></h4><div id="h-list" class="space-y-4 overflow-y-auto max-h-[500px]"></div></div>
                    </div>
                </div>`;
                updateJefeUI();
            } else if(id === 'stats') {
                const paid = pagos.map(p => p.ci); const pend = censo.filter(h => !paid.includes(h.ci));
                const ejes = pagos.reduce((a,p)=>{
                    const c = censo.find(h=>h.ci===p.ci)?.calle || 'S/C';
                    if(!a[c]) a[c] = {q10:0, q18:0, q43:0, bs:0};
                    a[c].q10 += p.q10; a[c].q18 += p.q18; a[c].q43 += p.q43; a[c].bs += p.monto;
                    return a;
                },{});
                const totalG = Object.values(ejes).reduce((a,b)=>({q10:a.q10+b.q10, q18:a.q18+b.q18, q43:a.q43+b.q43, bs:a.bs+b.bs}),{q10:0,q18:0,q43:0,bs:0});

                v.innerHTML = `
                <div class="space-y-6 fade-in">
                    <div class="flex justify-end gap-2"><button onclick="printStats()" class="bg-rose-600 text-white px-4 py-2 rounded-xl font-black text-[10px] uppercase">Imprimir Reporte A4</button></div>
                    <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                        <div class="glass p-8 rounded-[2.5rem]">
                            <h3 class="text-xl font-black italic mb-6 uppercase">Recaudación por Calle</h3>
                            <div class="overflow-x-auto"><table class="w-full text-left text-[11px]">
                                <thead class="text-slate-500 uppercase font-black tracking-widest border-b border-slate-800"><tr><th class="p-4">Calle</th><th class="p-4 text-center">10kg</th><th class="p-4 text-center">18kg</th><th class="p-4 text-center">43kg</th><th class="p-4 text-right">Bs</th></tr></thead>
                                <tbody class="divide-y divide-slate-900">${Object.entries(ejes).map(([c,d])=>`<tr><td class="p-4 font-bold text-white uppercase">${c}</td><td class="p-4 text-center mono">${d.q10}</td><td class="p-4 text-center mono">${d.q18}</td><td class="p-4 text-center mono">${d.q43}</td><td class="p-4 text-right font-black text-emerald-500 font-mono">${d.bs.toFixed(2)}</td></tr>`).join('')}</tbody>
                                <tfoot class="border-t-2 border-slate-700 bg-slate-900/50 font-black"><tr><td class="p-4 uppercase text-amber-500">TOTAL GENERAL</td><td class="p-4 text-center text-white">${totalG.q10}</td><td class="p-4 text-center text-white">${totalG.q18}</td><td class="p-4 text-center text-white">${totalG.q43}</td><td class="p-4 text-right text-emerald-400 font-mono">${totalG.bs.toFixed(2)}</td></tr></tfoot>
                            </table></div>
                        </div>
                        <div class="glass p-8 rounded-[2.5rem] border-l-4 border-rose-500"><h3 class="text-xl font-black italic mb-6 text-rose-500 uppercase">Pendientes (${pend.length})</h3><div class="overflow-y-auto max-h-[400px]">${pend.map(h=>`<div class="p-3 bg-slate-900/40 rounded-xl flex justify-between items-center mb-2"><div><p class="text-[10px] font-black text-white uppercase">${h.nombre}</p><p class="text-[8px] text-slate-500 font-bold uppercase">${h.calle}</p></div><span class="text-[9px] mono text-rose-400 opacity-40">${h.ci}</span></div>`).join('') || '<p class="p-8 text-center text-emerald-500 font-black italic uppercase">Recaudación 100% Completa</p>'}</div></div>
                    </div>
                </div>`;
            } else if(id === 'despacho') {
                v.innerHTML = `
                <div class="glass p-6 sm:p-10 rounded-[2.5rem] fade-in space-y-6">
                    <div class="flex flex-col sm:flex-row justify-between gap-4 sm:items-center"><h3 class="text-xl font-black italic text-rose-500 uppercase">Conciliación de Despacho</h3><button onclick="printDespacho()" class="bg-amber-600 text-white px-4 py-2 rounded-xl font-black text-[10px] uppercase">Exportar Día D</button></div>
                    <div class="overflow-x-auto"><table class="w-full text-left text-[11px]"><thead class="text-slate-500 uppercase font-black tracking-widest"><tr><th class="p-4">Beneficiario</th><th class="p-4 text-center">Pagados</th><th class="p-4 text-center">Recibidos</th><th class="p-4 text-center">Diff</th><th class="p-4 text-right">Estatus</th></tr></thead>
                    <tbody class="divide-y divide-slate-900">${pagos.map(p => { 
                        const h=censo.find(x=>x.ci===p.ci); const t=p.q10+p.q18+p.q43; const diff=p.recibidos-t;
                        return `<tr><td class="p-4"><b class="uppercase font-black text-white">${h?.nombre||p.ci}</b><br><small class="text-slate-500 font-bold uppercase">${h?.calle}</small></td><td class="p-4 text-center font-mono text-slate-500">${p.q10}/${p.q18}/${p.q43}</td><td class="p-4 text-center"><input type="number" value="${p.recibidos}" onchange="updR('${p.id}',this.value)" class="w-12 bg-slate-900 border border-slate-800 rounded p-1 text-center font-black text-white focus:border-rose-500 outline-none"></td><td class="p-4 text-center font-black ${diff===0?'text-emerald-500':'text-rose-500'}">${diff===0?'✓':diff}</td><td class="p-4 text-right"><span class="px-3 py-1 rounded-full text-[8px] font-black ${diff===0 && p.recibidos > 0 ? 'bg-emerald-500/20 text-emerald-500' : 'bg-slate-800 text-slate-500'} uppercase">${diff===0 && p.recibidos > 0 ? 'CONCILIADO' : 'PENDIENTE'}</span></td></tr>` }).join('')}</tbody></table></div>
                </div>`;
            }
        }

        async function guardarPrecios() { await _sb.from('configuracion').update({p10:document.getElementById('p10').value,p18:document.getElementById('p18').value,p43:document.getElementById('p43').value}).eq('comunidad_id',uSession.id); await syncData(); alert("Precios Fijos."); }
        function lookCI(v) { const h=censo.find(x=>x.ci===v); document.getElementById('v-name').innerText=h?`${h.nombre} • ${h.calle}`:"Cédula no en Censo"; validarCobro(); }
        function validarCobro() {
            const r=(document.getElementById('q10').value*document.getElementById('p10').value)+(document.getElementById('q18').value*document.getElementById('p18').value)+(document.getElementById('q43').value*document.getElementById('p43').value);
            const m=parseFloat(document.getElementById('m-ref').value)||0, b=document.getElementById('v-btn'), s=document.getElementById('status-val');
            document.getElementById('v-calc').innerText=r.toFixed(2);
            if(r>0 && Math.abs(m-r)<0.1) { b.disabled=false; b.className="w-full bg-emerald-600 text-white py-5 rounded-2xl font-black uppercase text-[10px] tracking-widest shadow-lg shadow-emerald-900/20"; s.innerText="✓ MONTO COINCIDE"; s.className="px-5 py-2 rounded-full text-[9px] font-black bg-emerald-500 text-slate-950 shadow-lg shadow-emerald-500/20"; }
            else { b.disabled=true; b.className="w-full bg-slate-800 text-slate-500 py-5 rounded-2xl font-black uppercase text-[10px] tracking-widest"; s.innerText=r>0?"✗ ERROR EN MONTO":"ESPERANDO CARGA"; s.className=r>0?"px-5 py-2 rounded-full text-[9px] font-black bg-rose-500 text-white shadow-lg shadow-rose-950/20":"px-5 py-2 rounded-full text-[9px] font-black bg-slate-800 text-slate-500 uppercase tracking-widest"; }
        }
        async function cobrar() { updateLoader(40); const d={ci:document.getElementById('ci').value, referencia:document.getElementById('ref').value, monto:parseFloat(document.getElementById('m-ref').value), q10:parseInt(document.getElementById('q10').value), q18:parseInt(document.getElementById('q18').value), q43:parseInt(document.getElementById('q43').value), comunidad_id:uSession.id, registrado_por:uSession.usuario }; await _sb.from('pagos').insert([d]); await syncData(); showSection('gestion'); updateLoader(100); }
        async function updR(id,v) { await _sb.from('pagos').update({recibidos:parseInt(v)||0}).eq('id',id); await syncData(); showSection('despacho'); }

        function updateJefeUI() {
            const t=pagos.reduce((a,p)=>({c10:a.c10+p.q10,c18:a.c18+p.q18,c43:a.c43+p.q43,bs:a.bs+p.monto}),{c10:0,c18:0,c43:0,bs:0});
            document.getElementById('tot-cont').innerHTML=`
                <div class="glass p-3 rounded-2xl border-l-4 border-emerald-500"><p class="text-[7px] font-black text-slate-500 uppercase tracking-widest">10kg</p><p class="text-lg font-black text-white">${t.c10}</p></div>
                <div class="glass p-3 rounded-2xl border-l-4 border-emerald-500"><p class="text-[7px] font-black text-slate-500 uppercase tracking-widest">18kg</p><p class="text-lg font-black text-white">${t.c18}</p></div>
                <div class="glass p-3 rounded-2xl border-l-4 border-emerald-500"><p class="text-[7px] font-black text-slate-500 uppercase tracking-widest">43kg</p><p class="text-lg font-black text-white">${t.c43}</p></div>
                <div class="glass p-3 rounded-2xl border-l-4 border-blue-500"><p class="text-[7px] font-black text-slate-500 uppercase tracking-widest">Total Bs</p><p class="text-lg font-black text-white">${t.bs.toFixed(2)}</p></div>`;
            document.getElementById('p-count').innerText=pagos.length + " Registros";
            document.getElementById('h-list').innerHTML=pagos.map(p=>`<div class="bg-slate-900/50 p-4 rounded-2xl border border-slate-800 flex justify-between items-center animate-fade-in"><div><p class="text-[10px] font-black text-white uppercase">${censo.find(h=>h.ci===p.ci)?.nombre||p.ci}</p><p class="text-[8px] text-slate-500">REF: ${p.referencia} | ${new Date(p.created_at).toLocaleTimeString([],{hour:'2-digit',minute:'2-digit'})}</p></div><p class="text-emerald-500 font-black text-[11px]">${p.monto.toFixed(2)} BS</p></div>`).join('');
        }

        // MOTORES DE IMPRESIÓN (SIN CAMBIOS ESTRUCTURALES)
        function printStats() {
            try {
                const { jsPDF } = window.jspdf;
                if (!jsPDF) throw new Error("jsPDF no cargada");
                const doc = new jsPDF('p', 'mm', 'a4');
                doc.setFontSize(18); doc.setFont("helvetica", "bold"); doc.text("HDC Design & Tech- REPORTE DE RECAUDACIÓN", 14, 20);
                doc.setFontSize(10); doc.text(`COMUNIDAD: ${uSession.comunidad_name.toUpperCase()}`, 14, 28);
                const ejes = pagos.reduce((a, p) => {
                    const h = censo.find(x => x.ci === p.ci); const calle = h ? h.calle.toUpperCase() : 'DESCONOCIDA';
                    if (!a[calle]) a[calle] = { q10: 0, q18: 0, q43: 0, bs: 0 };
                    a[calle].q10 += (p.q10 || 0); a[calle].q18 += (p.q18 || 0); a[calle].q43 += (p.q43 || 0); a[calle].bs += (p.monto || 0);
                    return a;
                }, {});
                const tableData = Object.entries(ejes).map(([calle, d]) => [calle, d.q10, d.q18, d.q43, d.bs.toFixed(2)]);
                const totales = tableData.reduce((acc, row) => { acc[0] += row[1]; acc[1] += row[2]; acc[2] += row[3]; acc[3] += parseFloat(row[4]); return acc; }, [0, 0, 0, 0]);
                doc.autoTable({ startY: 45, head: [['CALLE / EJE', '10KG', '18KG', '43KG', 'MONTO BS']], body: tableData, foot: [['TOTAL GENERAL', totales[0], totales[1], totales[2], totales[3].toFixed(2) + " BS"]], theme: 'grid', headStyles: { fillColor: [16, 185, 129] }, footStyles: { fillColor: [15, 23, 42], textColor: [251, 191, 36] } });
                doc.save(`HDC_RECAUDACION_${uSession.comunidad_name.replace(/\s+/g, '_')}.pdf`);
            } catch (error) { alert("Error PDF: " + error.message); }
        }

        function printDespacho() {
            try {
                const { jsPDF } = window.jspdf; const doc = new jsPDF('p', 'mm', 'a4');
                doc.setFontSize(16); doc.text("HDC Design & Tech- LISTADO DE DESPACHO", 14, 20);
                const data = pagos.map(p => { const h = censo.find(x => x.ci === p.ci); const totalP = (p.q10||0) + (p.q18||0) + (p.q43||0);
                    return [h ? h.nombre.toUpperCase() : p.ci, h ? h.calle.toUpperCase() : '-', `${p.q10}/${p.q18}/${p.q43}`, p.recibidos || 0, (p.recibidos == totalP ? 'ENTREGADO' : 'PENDIENTE')];
                });
                doc.autoTable({ startY: 35, head: [['BENEFICIARIO', 'CALLE', 'PEDIDO', 'RECIBIDO', 'ESTADO']], body: data, headStyles: { fillColor: [180, 83, 9] } });
                doc.save(`HDC_DESPACHO_${uSession.comunidad_name.replace(/\s+/g, '_')}.pdf`);
            } catch (error) { alert("Error PDF: " + error.message); }
        }
    </script>
</body>
</html>
