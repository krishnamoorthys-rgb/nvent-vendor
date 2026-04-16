<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>nVent - Master List of Vendors</title>
<style>
  *{box-sizing:border-box;margin:0;padding:0;font-family:'Segoe UI',Arial,sans-serif;}
  body{background:#f0f4f8;min-height:100vh;}

  /* HEADER */
  .header{background:#fff;border-bottom:2px solid #1a73e8;padding:14px 24px;text-align:center;box-shadow:0 2px 6px rgba(0,0,0,0.07);}
  .header h1{font-size:22px;font-weight:700;color:#1a1a2e;display:flex;align-items:center;justify-content:center;gap:10px;}
  .header h1 span.icon{font-size:24px;}

  /* TOOLBAR */
  .toolbar{background:#e8f0fe;padding:12px 20px;display:flex;gap:10px;flex-wrap:wrap;align-items:center;}
  .btn{padding:8px 16px;border:none;border-radius:6px;font-size:13px;font-weight:600;cursor:pointer;display:flex;align-items:center;gap:6px;transition:opacity .15s;}
  .btn:hover{opacity:.87;}
  .btn-green{background:#34a853;color:#fff;}
  .btn-purple{background:#673ab7;color:#fff;}
  .btn-teal{background:#00897b;color:#fff;}
  .btn-blue{background:#1565c0;color:#fff;}
  .btn-red{background:#c62828;color:#fff;}
  .stats{margin-left:auto;display:flex;gap:10px;align-items:center;flex-wrap:wrap;}
  .stat-badge{padding:5px 12px;border-radius:20px;font-size:12px;font-weight:600;border:1px solid #ccc;background:#fff;}
  .stat-badge.approved{border-color:#34a853;color:#2d7d46;}
  .stat-badge.notapproved{border-color:#e53935;color:#b71c1c;}

  /* MAIN LAYOUT */
  .main{display:grid;grid-template-columns:220px 1fr 320px;gap:0;height:calc(100vh - 120px);}

  /* LEFT PANEL - CATEGORIES */
  .panel-cat{background:#fff;border-right:1px solid #dde3ea;display:flex;flex-direction:column;overflow:hidden;}
  .panel-cat h2{padding:14px 16px 8px;font-size:14px;color:#333;font-weight:700;display:flex;align-items:center;gap:6px;}
  .search-box{margin:0 12px 10px;padding:7px 10px;border:1px solid #ccc;border-radius:6px;font-size:13px;outline:none;width:calc(100% - 24px);}
  .search-box:focus{border-color:#1a73e8;}
  .cat-list{overflow-y:auto;flex:1;}
  .cat-item{display:flex;align-items:center;justify-content:space-between;padding:10px 16px;font-size:13px;cursor:pointer;border-left:3px solid transparent;transition:background .12s;}
  .cat-item:hover{background:#f1f5ff;}
  .cat-item.active{background:#1a73e8;color:#fff;border-left-color:#0d47a1;}
  .cat-item .badge{background:rgba(0,0,0,0.15);color:inherit;border-radius:12px;font-size:11px;font-weight:700;padding:1px 7px;}
  .cat-item.active .badge{background:rgba(255,255,255,0.3);}

  /* MIDDLE PANEL - SUPPLIERS */
  .panel-sup{background:#fff;border-right:1px solid #dde3ea;display:flex;flex-direction:column;overflow:hidden;}
  .panel-sup-header{padding:14px 16px 0;border-bottom:1px solid #eee;}
  .panel-sup-header h2{font-size:14px;font-weight:700;color:#333;display:flex;align-items:center;gap:6px;margin-bottom:10px;}
  .cat-title{font-size:12px;font-weight:800;color:#1a73e8;letter-spacing:.5px;margin:0 16px 8px;text-transform:uppercase;}
  .filter-bar{display:flex;gap:8px;flex-wrap:wrap;padding:0 16px 12px;}
  .filter-btn{padding:5px 12px;border-radius:20px;border:1px solid #ccc;background:#fff;font-size:12px;cursor:pointer;font-weight:500;}
  .filter-btn:hover{background:#f1f5ff;border-color:#1a73e8;}
  .filter-btn.active{background:#1a73e8;color:#fff;border-color:#1a73e8;}
  .sup-list{overflow-y:auto;flex:1;padding:8px 0;}
  .sup-item{display:flex;align-items:center;gap:10px;padding:10px 16px;font-size:13px;cursor:pointer;border-left:3px solid transparent;border-bottom:1px solid #f3f4f6;transition:background .12s;}
  .sup-item:hover{background:#f1f5ff;}
  .sup-item.active{background:#e8f0fe;border-left-color:#1a73e8;}
  .dot{width:10px;height:10px;border-radius:50%;flex-shrink:0;}
  .dot.pending{background:#f59e0b;}
  .dot.approved{background:#22c55e;}
  .dot.notapproved{background:#ef4444;}

  /* RIGHT PANEL - DETAILS */
  .panel-det{background:#fafbfc;overflow-y:auto;padding:16px;}
  .det-header{display:flex;align-items:center;justify-content:space-between;margin-bottom:16px;padding-bottom:10px;border-bottom:2px solid #1a73e8;}
  .det-header h2{font-size:15px;font-weight:700;color:#1a1a2e;display:flex;align-items:center;gap:8px;}
  .status-pill{padding:4px 12px;border-radius:20px;font-size:11px;font-weight:700;text-transform:uppercase;}
  .status-pill.pending{background:#fef3c7;color:#92400e;border:1px solid #fcd34d;}
  .status-pill.approved{background:#dcfce7;color:#166534;border:1px solid #86efac;}
  .status-pill.notapproved{background:#fee2e2;color:#991b1b;border:1px solid #fca5a5;}

  .det-section{background:#fff;border:1px solid #e5e7eb;border-radius:8px;padding:14px;margin-bottom:12px;}
  .det-section h3{font-size:13px;font-weight:700;color:#374151;margin-bottom:10px;display:flex;align-items:center;gap:6px;}
  .det-row{display:flex;gap:8px;margin-bottom:7px;font-size:13px;}
  .det-label{color:#6b7280;min-width:90px;font-weight:600;}
  .det-value{color:#1f2937;flex:1;word-break:break-word;}

  /* MODAL */
  .modal-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,0.45);z-index:1000;align-items:center;justify-content:center;}
  .modal-overlay.open{display:flex;}
  .modal{background:#fff;border-radius:10px;padding:24px;width:480px;max-width:95vw;max-height:90vh;overflow-y:auto;box-shadow:0 8px 32px rgba(0,0,0,0.18);}
  .modal h2{font-size:17px;font-weight:700;margin-bottom:18px;color:#1a1a2e;}
  .form-group{margin-bottom:13px;}
  .form-group label{display:block;font-size:12px;font-weight:600;color:#374151;margin-bottom:4px;}
  .form-group input,.form-group select,.form-group textarea{width:100%;padding:8px 10px;border:1px solid #ccc;border-radius:6px;font-size:13px;outline:none;}
  .form-group input:focus,.form-group select:focus,.form-group textarea:focus{border-color:#1a73e8;}
  .modal-actions{display:flex;gap:10px;justify-content:flex-end;margin-top:18px;}

  /* TOAST */
  .toast{position:fixed;bottom:20px;right:20px;background:#1a1a2e;color:#fff;padding:10px 18px;border-radius:8px;font-size:13px;font-weight:500;z-index:2000;opacity:0;transition:opacity .3s;pointer-events:none;}
  .toast.show{opacity:1;}

  /* RESPONSIVE */
  @media(max-width:900px){
    .main{grid-template-columns:180px 1fr;}
    .panel-det{display:none;}
  }
  @media(max-width:600px){
    .main{grid-template-columns:1fr;}
    .panel-cat{display:none;}
  }
</style>
</head>
<body>

<!-- HEADER -->
<div class="header">
  <h1><span class="icon">📊</span> nVent — Master List of Vendors</h1>
</div>

<!-- TOOLBAR -->
<div class="toolbar">
  <button class="btn btn-green" onclick="openAddSupplierModal()">+ Add New Supplier</button>
  <button class="btn btn-purple" onclick="openAddCategoryModal()">🗂 Add New Category</button>
  <button class="btn btn-teal" onclick="exportData()">⬆ Export Data (JSON)</button>
  <button class="btn btn-blue" onclick="importData()">⬇ Import Data</button>
  <button class="btn btn-red" onclick="resetToDefault()">↺ Reset to Default</button>
  <div class="stats">
    <span class="stat-badge" id="stat-cats">Categories: 0</span>
    <span class="stat-badge" id="stat-sups">Suppliers: 0</span>
    <span class="stat-badge approved" id="stat-app">✓ Approved: 0</span>
    <span class="stat-badge notapproved" id="stat-notapp">✗ Not Approved: 0</span>
  </div>
</div>

<!-- MAIN -->
<div class="main">
  <!-- CATEGORIES -->
  <div class="panel-cat">
    <h2>🗂 Categories</h2>
    <input class="search-box" id="catSearch" placeholder="Search categories..." oninput="renderCategories()"/>
    <div class="cat-list" id="catList"></div>
  </div>

  <!-- SUPPLIERS -->
  <div class="panel-sup">
    <div class="panel-sup-header">
      <h2>👥 Suppliers</h2>
      <div class="cat-title" id="activeCatLabel">ALL</div>
      <div class="filter-bar">
        <button class="filter-btn active" onclick="setFilter('all',this)">All</button>
        <button class="filter-btn" onclick="setFilter('approved',this)">✓ Approved</button>
        <button class="filter-btn" onclick="setFilter('notapproved',this)">✗ Not Approved</button>
        <button class="filter-btn" onclick="setFilter('pending',this)">⏳ Pending</button>
      </div>
    </div>
    <div class="sup-list" id="supList"></div>
  </div>

  <!-- DETAILS -->
  <div class="panel-det" id="detPanel">
    <div style="color:#9ca3af;font-size:14px;text-align:center;margin-top:60px;">Select a supplier to view details</div>
  </div>
</div>

<!-- ADD SUPPLIER MODAL -->
<div class="modal-overlay" id="addSupModal">
  <div class="modal">
    <h2>➕ Add New Supplier</h2>
    <div class="form-group">
      <label>Supplier Name *</label>
      <input id="sup-name" placeholder="e.g. General Foundries"/>
    </div>
    <div class="form-group">
      <label>Category *</label>
      <select id="sup-cat"></select>
    </div>
    <div class="form-group">
      <label>Status</label>
      <select id="sup-status">
        <option value="pending">Pending</option>
        <option value="approved">Approved</option>
        <option value="notapproved">Not Approved</option>
      </select>
    </div>
    <div class="form-group">
      <label>Address</label>
      <input id="sup-address" placeholder="Office address"/>
    </div>
    <div class="form-group">
      <label>Phone</label>
      <input id="sup-phone" placeholder="+91 ..."/>
    </div>
    <div class="form-group">
      <label>Email</label>
      <input id="sup-email" type="email" placeholder="supplier@email.com"/>
    </div>
    <div class="form-group">
      <label>Website</label>
      <input id="sup-web" placeholder="https://..."/>
    </div>
    <div class="form-group">
      <label>Notes</label>
      <textarea id="sup-notes" rows="3" placeholder="Any approval notes..."></textarea>
    </div>
    <div class="modal-actions">
      <button class="btn" style="background:#e5e7eb;color:#374151;" onclick="closeModal('addSupModal')">Cancel</button>
      <button class="btn btn-green" onclick="saveSupplier()">Save Supplier</button>
    </div>
  </div>
</div>

<!-- ADD CATEGORY MODAL -->
<div class="modal-overlay" id="addCatModal">
  <div class="modal">
    <h2>🗂 Add New Category</h2>
    <div class="form-group">
      <label>Category Name *</label>
      <input id="cat-name" placeholder="e.g. ELECTRONICS"/>
    </div>
    <div class="modal-actions">
      <button class="btn" style="background:#e5e7eb;color:#374151;" onclick="closeModal('addCatModal')">Cancel</button>
      <button class="btn btn-purple" onclick="saveCategory()">Save Category</button>
    </div>
  </div>
</div>

<!-- IMPORT MODAL -->
<div class="modal-overlay" id="importModal">
  <div class="modal">
    <h2>⬇ Import Data (JSON)</h2>
    <div class="form-group">
      <label>Paste your JSON data below</label>
      <textarea id="import-json" rows="10" placeholder='{"categories":[...],"suppliers":[...]}'></textarea>
    </div>
    <div class="modal-actions">
      <button class="btn" style="background:#e5e7eb;color:#374151;" onclick="closeModal('importModal')">Cancel</button>
      <button class="btn btn-blue" onclick="doImport()">Import</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
// ─── DEFAULT DATA ───────────────────────────────────────────────────────────
const DEFAULT_DATA = {
  categories: [
    "CASTINGS","Cable gland","E&E","EARTH BAR","FABRICATION",
    "FASTENERS","Gasket/Rubber","MACHINING","PANEL ACCESSORIES",
    "PCB","SHEET METAL","SPRINGS","STAMPINGS","SWITCHGEAR",
    "WIRES & CABLES","PLASTICS","RUBBER"
  ],
  suppliers: [
    {id:1,name:"General foundries",category:"CASTINGS",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:2,name:"Spectrum tools",category:"CASTINGS",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:3,name:"New cast die casting",category:"CASTINGS",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:4,name:"Investment precision casting ltd",category:"CASTINGS",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:5,name:"NNF - MIM",category:"CASTINGS",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:6,name:"LGC",category:"CASTINGS",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:7,name:"123",category:"CASTINGS",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:8,name:"1234",category:"CASTINGS",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:9,name:"Alpha Cables",category:"Cable gland",status:"approved",address:"Mumbai",phone:"+91 9000000001",email:"alpha@cables.com",website:"",notes:"",approvedBy:"Admin",approvalDate:"2024-01-10"},
    {id:10,name:"Beta Gland Co",category:"Cable gland",status:"notapproved",address:"",phone:"",email:"",website:"",notes:"Failed audit",approvedBy:"",approvalDate:""},
    {id:11,name:"EE Supplies",category:"E&E",status:"approved",address:"Chennai",phone:"",email:"",website:"",notes:"",approvedBy:"Admin",approvalDate:""},
    {id:12,name:"Volta E&E",category:"E&E",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:13,name:"GroundBar Ltd",category:"EARTH BAR",status:"approved",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"QA",approvalDate:""},
    {id:14,name:"SafeGround Inc",category:"EARTH BAR",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:15,name:"FabWorks",category:"FABRICATION",status:"approved",address:"Pune",phone:"",email:"",website:"",notes:"",approvedBy:"Admin",approvalDate:""},
    {id:16,name:"MetalCraft",category:"FABRICATION",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:17,name:"FastFix",category:"FASTENERS",status:"approved",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"QA",approvalDate:""},
    {id:18,name:"BoltPro",category:"FASTENERS",status:"notapproved",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:19,name:"RubberTech",category:"Gasket/Rubber",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""},
    {id:20,name:"GasketPlus",category:"Gasket/Rubber",status:"approved",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"Admin",approvalDate:""},
    {id:21,name:"PrecisionMach",category:"MACHINING",status:"approved",address:"Coimbatore",phone:"",email:"",website:"",notes:"",approvedBy:"QA",approvalDate:""},
    {id:22,name:"TurboMill",category:"MACHINING",status:"pending",address:"",phone:"",email:"",website:"",notes:"",approvedBy:"",approvalDate:""}
  ]
};

// ─── STATE ───────────────────────────────────────────────────────────────────
let state = loadState();
let activeCat = null;
let activeSupId = null;
let activeFilter = 'all';
let nextId = Math.max(...state.suppliers.map(s=>s.id),0)+1;

function loadState(){
  try{
    const s = localStorage.getItem('nvent_data');
    if(s) return JSON.parse(s);
  }catch(e){}
  return JSON.parse(JSON.stringify(DEFAULT_DATA));
}
function saveState(){
  localStorage.setItem('nvent_data', JSON.stringify(state));
  renderAll();
}

// ─── RENDER ──────────────────────────────────────────────────────────────────
function renderAll(){
  renderCategories();
  renderSuppliers();
  updateStats();
}

function renderCategories(){
  const q = document.getElementById('catSearch').value.toLowerCase();
  const el = document.getElementById('catList');
  const counts = {};
  state.suppliers.forEach(s=>{ counts[s.category]=(counts[s.category]||0)+1; });
  el.innerHTML = state.categories
    .filter(c=>c.toLowerCase().includes(q))
    .map(c=>`
      <div class="cat-item${activeCat===c?' active':''}" onclick="selectCat('${c.replace(/'/g,"\\'")}')">
        <span>${c}</span>
        <span class="badge">${counts[c]||0}</span>
      </div>
    `).join('');
}

function renderSuppliers(){
  const el = document.getElementById('supList');
  let sups = activeCat ? state.suppliers.filter(s=>s.category===activeCat) : state.suppliers;
  if(activeFilter!=='all') sups = sups.filter(s=>s.status===activeFilter);
  document.getElementById('activeCatLabel').textContent = activeCat || 'ALL CATEGORIES';
  el.innerHTML = sups.length ? sups.map((s,i)=>`
    <div class="sup-item${activeSupId===s.id?' active':''}" onclick="selectSup(${s.id})">
      <span class="dot ${s.status}"></span>
      <span>${i+1}. ${s.name}</span>
    </div>
  `).join('') : '<div style="padding:20px 16px;font-size:13px;color:#9ca3af;">No suppliers found.</div>';
}

function updateStats(){
  const cats = state.categories.length;
  const sups = state.suppliers.length;
  const app = state.suppliers.filter(s=>s.status==='approved').length;
  const notapp = state.suppliers.filter(s=>s.status==='notapproved').length;
  document.getElementById('stat-cats').textContent=`Categories: ${cats}`;
  document.getElementById('stat-sups').textContent=`Suppliers: ${sups}`;
  document.getElementById('stat-app').textContent=`✓ Approved: ${app}`;
  document.getElementById('stat-notapp').textContent=`✗ Not Approved: ${notapp}`;
}

function selectCat(cat){
  activeCat = activeCat===cat ? null : cat;
  activeSupId = null;
  renderAll();
  showEmptyDet();
}

function setFilter(f, btn){
  activeFilter = f;
  document.querySelectorAll('.filter-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  renderSuppliers();
}

function selectSup(id){
  activeSupId = id;
  const s = state.suppliers.find(x=>x.id===id);
  if(!s) return;
  renderSuppliers();
  const pill = `<span class="status-pill ${s.status}">${s.status==='notapproved'?'Not Approved':s.status.charAt(0).toUpperCase()+s.status.slice(1)}</span>`;
  const icons = {address:'📍',phone:'📞',email:'✉',website:'🌐'};
  document.getElementById('detPanel').innerHTML=`
    <div class="det-header">
      <h2>🏭 ${s.name}</h2>
      ${pill}
    </div>
    <div class="det-section">
      <h3>📋 Approval Information</h3>
      <div class="det-row"><span class="det-label">Status:</span><span class="det-value">${pill}</span></div>
      <div class="det-row"><span class="det-label">Date:</span><span class="det-value">${s.approvalDate||'Not specified'}</span></div>
      <div class="det-row"><span class="det-label">Approved By:</span><span class="det-value">${s.approvedBy||'Not specified'}</span></div>
      <div class="det-row"><span class="det-label">Notes:</span><span class="det-value">${s.notes||'No notes'}</span></div>
    </div>
    <div class="det-section">
      <h3>📞 Contact Information</h3>
      <div class="det-row"><span class="det-label">📍 Address:</span><span class="det-value">${s.address||'Not specified'}</span></div>
      <div class="det-row"><span class="det-label">📞 Phone:</span><span class="det-value">${s.phone||'Not specified'}</span></div>
      <div class="det-row"><span class="det-label">✉ Email:</span><span class="det-value">${s.email||'Not specified'}</span></div>
      <div class="det-row"><span class="det-label">🌐 Website:</span><span class="det-value">${s.website||'Not specified'}</span></div>
    </div>
    <div class="det-section">
      <h3>⚙ Actions</h3>
      <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:4px;">
        <button class="btn btn-teal" style="font-size:12px;padding:6px 12px;" onclick="openEditModal(${s.id})">✏ Edit</button>
        <button class="btn" style="font-size:12px;padding:6px 12px;background:#fee2e2;color:#991b1b;" onclick="deleteSup(${s.id})">🗑 Delete</button>
        ${s.status!=='approved'?`<button class="btn btn-green" style="font-size:12px;padding:6px 12px;" onclick="quickStatus(${s.id},'approved')">✓ Approve</button>`:''}
        ${s.status!=='notapproved'?`<button class="btn" style="font-size:12px;padding:6px 12px;background:#fee2e2;color:#991b1b;" onclick="quickStatus(${s.id},'notapproved')">✗ Reject</button>`:''}
      </div>
    </div>
  `;
}

function showEmptyDet(){
  document.getElementById('detPanel').innerHTML='<div style="color:#9ca3af;font-size:14px;text-align:center;margin-top:60px;">Select a supplier to view details</div>';
}

// ─── MODALS ──────────────────────────────────────────────────────────────────
function openAddSupplierModal(){
  const sel = document.getElementById('sup-cat');
  sel.innerHTML = state.categories.map(c=>`<option value="${c}">${c}</option>`).join('');
  if(activeCat) sel.value=activeCat;
  ['sup-name','sup-address','sup-phone','sup-email','sup-web','sup-notes'].forEach(id=>document.getElementById(id).value='');
  document.getElementById('sup-status').value='pending';
  document.getElementById('addSupModal').classList.add('open');
}

function openAddCategoryModal(){
  document.getElementById('cat-name').value='';
  document.getElementById('addCatModal').classList.add('open');
}

function closeModal(id){ document.getElementById(id).classList.remove('open'); }

function saveSupplier(){
  const name = document.getElementById('sup-name').value.trim();
  if(!name){ toast('Please enter a supplier name.'); return; }
  state.suppliers.push({
    id: nextId++,
    name,
    category: document.getElementById('sup-cat').value,
    status: document.getElementById('sup-status').value,
    address: document.getElementById('sup-address').value.trim(),
    phone: document.getElementById('sup-phone').value.trim(),
    email: document.getElementById('sup-email').value.trim(),
    website: document.getElementById('sup-web').value.trim(),
    notes: document.getElementById('sup-notes').value.trim(),
    approvedBy:'', approvalDate:''
  });
  closeModal('addSupModal');
  saveState();
  toast('Supplier added successfully!');
}

function saveCategory(){
  const name = document.getElementById('cat-name').value.trim().toUpperCase();
  if(!name){ toast('Please enter a category name.'); return; }
  if(state.categories.includes(name)){ toast('Category already exists!'); return; }
  state.categories.push(name);
  closeModal('addCatModal');
  saveState();
  toast('Category added!');
}

function openEditModal(id){
  const s = state.suppliers.find(x=>x.id===id);
  if(!s) return;
  const sel = document.getElementById('sup-cat');
  sel.innerHTML = state.categories.map(c=>`<option value="${c}">${c}</option>`).join('');
  document.getElementById('sup-name').value=s.name;
  sel.value=s.category;
  document.getElementById('sup-status').value=s.status;
  document.getElementById('sup-address').value=s.address||'';
  document.getElementById('sup-phone').value=s.phone||'';
  document.getElementById('sup-email').value=s.email||'';
  document.getElementById('sup-web').value=s.website||'';
  document.getElementById('sup-notes').value=s.notes||'';
  document.getElementById('addSupModal').classList.add('open');
  // Replace save to update
  const saveBtn = document.querySelector('#addSupModal .btn-green');
  saveBtn.textContent='Update Supplier';
  saveBtn.onclick=()=>{
    s.name=document.getElementById('sup-name').value.trim()||s.name;
    s.category=sel.value;
    s.status=document.getElementById('sup-status').value;
    s.address=document.getElementById('sup-address').value.trim();
    s.phone=document.getElementById('sup-phone').value.trim();
    s.email=document.getElementById('sup-email').value.trim();
    s.website=document.getElementById('sup-web').value.trim();
    s.notes=document.getElementById('sup-notes').value.trim();
    closeModal('addSupModal');
    saveBtn.textContent='Save Supplier';
    saveBtn.onclick=saveSupplier;
    saveState();
    selectSup(id);
    toast('Supplier updated!');
  };
}

function deleteSup(id){
  if(!confirm('Delete this supplier?')) return;
  state.suppliers=state.suppliers.filter(s=>s.id!==id);
  activeSupId=null;
  saveState();
  showEmptyDet();
  toast('Supplier deleted.');
}

function quickStatus(id,status){
  const s=state.suppliers.find(x=>x.id===id);
  if(!s) return;
  s.status=status;
  if(status==='approved'){ s.approvedBy='Admin'; s.approvalDate=new Date().toISOString().slice(0,10); }
  saveState();
  selectSup(id);
  toast(`Supplier marked as ${status}.`);
}

// ─── EXPORT / IMPORT / RESET ─────────────────────────────────────────────────
function exportData(){
  const blob=new Blob([JSON.stringify(state,null,2)],{type:'application/json'});
  const a=document.createElement('a');
  a.href=URL.createObjectURL(blob);
  a.download='nvent_vendors.json';
  a.click();
  toast('Data exported!');
}

function importData(){
  document.getElementById('import-json').value='';
  document.getElementById('importModal').classList.add('open');
}

function doImport(){
  try{
    const data=JSON.parse(document.getElementById('import-json').value);
    if(!data.categories||!data.suppliers) throw new Error('Invalid format');
    state=data;
    nextId=Math.max(...state.suppliers.map(s=>s.id),0)+1;
    closeModal('importModal');
    saveState();
    toast('Data imported successfully!');
  }catch(e){
    toast('Invalid JSON. Please check your data.');
  }
}

function resetToDefault(){
  if(!confirm('Reset all data to default? This cannot be undone.')) return;
  state=JSON.parse(JSON.stringify(DEFAULT_DATA));
  activeCat=null; activeSupId=null; activeFilter='all';
  nextId=Math.max(...state.suppliers.map(s=>s.id),0)+1;
  saveState();
  showEmptyDet();
  toast('Reset to default data.');
}

// ─── TOAST ───────────────────────────────────────────────────────────────────
function toast(msg){
  const t=document.getElementById('toast');
  t.textContent=msg;
  t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),2800);
}

// Close modal on overlay click
document.querySelectorAll('.modal-overlay').forEach(el=>{
  el.addEventListener('click',e=>{ if(e.target===el) el.classList.remove('open'); });
});

// ─── INIT ────────────────────────────────────────────────────────────────────
renderAll();
</script>
</body>
</html>
