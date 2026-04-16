<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vendor Master List</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #ffffff;
            min-height: 100vh;
            padding: 15px;
        }

        .container {
            max-width: 1500px;
            margin: 0 auto;
        }

        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 15px;
            font-size: 1.4em;
            border-bottom: 2px solid #4a90d9;
            padding-bottom: 10px;
        }

        /* Top Action Bar */
        .action-bar {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
            flex-wrap: wrap;
            padding: 12px;
            background: #f0f7ff;
            border-radius: 8px;
            border: 1px solid #d0e3ff;
        }

        .action-bar button {
            padding: 8px 16px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.85em;
            transition: all 0.2s;
        }

        .btn-add {
            background: #28a745;
            color: white;
        }
        .btn-add:hover {
            background: #218838;
        }

        .btn-export {
            background: #17a2b8;
            color: white;
        }
        .btn-export:hover {
            background: #138496;
        }

        .btn-reset {
            background: #dc3545;
            color: white;
        }
        .btn-reset:hover {
            background: #c82333;
        }

        .btn-category {
            background: #6f42c1;
            color: white;
        }
        .btn-category:hover {
            background: #5a32a3;
        }

        /* Main Layout */
        .main-content {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        .categories-panel {
            flex: 0.7;
            min-width: 180px;
            background: #f8f9fa;
            border-radius: 6px;
            padding: 10px;
            border: 1px solid #e0e0e0;
            max-height: 70vh;
            overflow-y: auto;
        }

        .suppliers-panel {
            flex: 1;
            min-width: 220px;
            background: #f8f9fa;
            border-radius: 6px;
            padding: 10px;
            border: 1px solid #e0e0e0;
            max-height: 70vh;
            overflow-y: auto;
        }

        .details-panel {
            flex: 1.3;
            min-width: 280px;
            background: #f8f9fa;
            border-radius: 6px;
            padding: 10px;
            border: 1px solid #e0e0e0;
            max-height: 70vh;
            overflow-y: auto;
        }

        .panel-title {
            font-size: 0.9em;
            color: #333;
            margin-bottom: 10px;
            padding-bottom: 6px;
            border-bottom: 2px solid #4a90d9;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .category-btn {
            display: block;
            width: 100%;
            padding: 6px 10px;
            margin-bottom: 4px;
            background: #ffffff;
            border: 1px solid #ddd;
            border-radius: 4px;
            cursor: pointer;
            text-align: left;
            font-size: 0.75em;
            color: #333;
            transition: all 0.2s ease;
            position: relative;
        }

        .category-btn:hover {
            background: #4a90d9;
            color: white;
            border-color: #4a90d9;
        }

        .category-btn.active {
            background: #4a90d9;
            color: white;
            border-color: #4a90d9;
        }

        .category-btn .count {
            position: absolute;
            right: 6px;
            background: rgba(0,0,0,0.08);
            padding: 1px 5px;
            border-radius: 8px;
            font-size: 0.7em;
        }

        .category-btn.active .count,
        .category-btn:hover .count {
            background: rgba(255,255,255,0.25);
        }

        .supplier-list {
            list-style: none;
        }

        .supplier-item {
            padding: 6px 10px;
            margin-bottom: 4px;
            background: #ffffff;
            border-radius: 4px;
            border: 1px solid #ddd;
            border-left: 3px solid #4a90d9;
            cursor: pointer;
            font-size: 0.8em;
            transition: all 0.2s ease;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .supplier-item:hover {
            background: #e8f4ff;
            border-left-color: #2e6da4;
        }

        .supplier-item.active {
            background: #e8f4ff;
            border-left-color: #2e6da4;
            font-weight: bold;
        }

        .supplier-item.approved {
            border-left-color: #28a745;
        }

        .supplier-item.not-approved {
            border-left-color: #dc3545;
        }

        .supplier-item.pending {
            border-left-color: #ffc107;
        }

        .supplier-item .delete-btn {
            background: #dc3545;
            color: white;
            border: none;
            border-radius: 3px;
            padding: 2px 6px;
            font-size: 0.7em;
            cursor: pointer;
            opacity: 0;
            transition: opacity 0.2s;
        }

        .supplier-item:hover .delete-btn {
            opacity: 1;
        }

        .no-selection {
            text-align: center;
            color: #999;
            padding: 25px 10px;
            font-style: italic;
            font-size: 0.8em;
        }

        .selected-category {
            color: #4a90d9;
            font-weight: bold;
            margin-bottom: 8px;
            font-size: 0.85em;
        }

        .search-box {
            width: 100%;
            padding: 6px 8px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 0.75em;
            transition: border-color 0.2s;
        }

        .search-box:focus {
            outline: none;
            border-color: #4a90d9;
        }

        /* Supplier Details */
        .supplier-details {
            background: #ffffff;
            border-radius: 6px;
            padding: 12px;
            border: 1px solid #ddd;
        }

        .supplier-name {
            font-size: 1em;
            color: #333;
            font-weight: bold;
            margin-bottom: 12px;
            padding-bottom: 8px;
            border-bottom: 2px solid #4a90d9;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .detail-row {
            display: flex;
            margin-bottom: 8px;
            font-size: 0.8em;
        }

        .detail-label {
            font-weight: bold;
            color: #555;
            min-width: 80px;
            margin-right: 8px;
        }

        .detail-value {
            color: #333;
            flex: 1;
        }

        .detail-value a {
            color: #4a90d9;
            text-decoration: none;
        }

        .detail-value a:hover {
            text-decoration: underline;
        }

        /* Approval Status Badges */
        .status-badge {
            display: inline-block;
            padding: 3px 10px;
            border-radius: 12px;
            font-size: 0.75em;
            font-weight: bold;
            text-transform: uppercase;
        }

        .status-approved {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }

        .status-not-approved {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }

        .status-pending {
            background: #fff3cd;
            color: #856404;
            border: 1px solid #ffeeba;
        }

        .status-indicator {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            display: inline-block;
            margin-right: 5px;
        }

        .status-indicator.approved {
            background: #28a745;
        }

        .status-indicator.not-approved {
            background: #dc3545;
        }

        .status-indicator.pending {
            background: #ffc107;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            padding: 20px;
            border-radius: 10px;
            width: 90%;
            max-width: 500px;
            max-height: 80vh;
            overflow-y: auto;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px solid #4a90d9;
        }

        .modal-header h2 {
            font-size: 1.1em;
            color: #333;
        }

        .modal-close {
            background: none;
            border: none;
            font-size: 1.5em;
            cursor: pointer;
            color: #999;
        }

        .modal-close:hover {
            color: #333;
        }

        .form-group {
            margin-bottom: 12px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-size: 0.85em;
            font-weight: bold;
            color: #555;
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 8px 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 0.85em;
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #4a90d9;
        }

        .form-actions {
            display: flex;
            gap: 10px;
            margin-top: 15px;
        }

        .form-actions button {
            flex: 1;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.9em;
        }

        .btn-save {
            background: #28a745;
            color: white;
        }

        .btn-cancel {
            background: #6c757d;
            color: white;
        }

        /* Toast Notification */
        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            padding: 12px 20px;
            background: #28a745;
            color: white;
            border-radius: 5px;
            font-size: 0.85em;
            opacity: 0;
            transition: opacity 0.3s;
            z-index: 2000;
        }

        .toast.show {
            opacity: 1;
        }

        .toast.error {
            background: #dc3545;
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 5px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb {
            background: #c1c1c1;
            border-radius: 3px;
        }

        .edit-btn {
            background: #ffc107;
            color: #333;
            border: none;
            border-radius: 3px;
            padding: 2px 6px;
            font-size: 0.7em;
            cursor: pointer;
            opacity: 0;
            transition: opacity 0.2s;
            margin-right: 4px;
        }

        .supplier-item:hover .edit-btn {
            opacity: 1;
        }

        .stats-bar {
            display: flex;
            gap: 15px;
            margin-left: auto;
            font-size: 0.75em;
            color: #666;
        }

        .stats-bar span {
            background: #e9ecef;
            padding: 3px 8px;
            border-radius: 4px;
        }

        .stats-bar .approved-count {
            background: #d4edda;
            color: #155724;
        }

        .stats-bar .not-approved-count {
            background: #f8d7da;
            color: #721c24;
        }

        /* Filter Buttons */
        .filter-bar {
            display: flex;
            gap: 5px;
            margin-bottom: 10px;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 4px 10px;
            border: 1px solid #ddd;
            border-radius: 15px;
            background: white;
            font-size: 0.7em;
            cursor: pointer;
            transition: all 0.2s;
        }

        .filter-btn:hover {
            background: #e9ecef;
        }

        .filter-btn.active {
            background: #4a90d9;
            color: white;
            border-color: #4a90d9;
        }

        .filter-btn.filter-approved.active {
            background: #28a745;
            border-color: #28a745;
        }

        .filter-btn.filter-not-approved.active {
            background: #dc3545;
            border-color: #dc3545;
        }

        .filter-btn.filter-pending.active {
            background: #ffc107;
            border-color: #ffc107;
            color: #333;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🏭 nVent -Master List of Vendors</h1>
        
        <!-- Action Bar -->
        <div class="action-bar">
            <button class="btn-add" onclick="openAddSupplierModal()">➕ Add New Supplier</button>
            <button class="btn-category" onclick="openAddCategoryModal()">📁 Add New Category</button>
            <button class="btn-export" onclick="exportData()">📤 Export Data (JSON)</button>
            <button class="btn-export" onclick="importData()">📥 Import Data</button>
            <button class="btn-reset" onclick="resetToDefault()">🔄 Reset to Default</button>
            <input type="file" id="importFile" style="display:none" accept=".json" onchange="handleImport(event)">
            
            <div class="stats-bar">
                <span id="totalCategories">Categories: 0</span>
                <span id="totalSuppliers">Suppliers: 0</span>
                <span class="approved-count" id="approvedCount">✓ Approved: 0</span>
                <span class="not-approved-count" id="notApprovedCount">✗ Not Approved: 0</span>
            </div>
        </div>
        
        <!-- Main Content -->
        <div class="main-content">
            <div class="categories-panel">
                <h2 class="panel-title">📁 Categories</h2>
                <input type="text" class="search-box" id="searchCategory" placeholder="🔍 Search categories...">
                <div id="categoryList"></div>
            </div>

            <div class="suppliers-panel">
                <h2 class="panel-title">👥 Suppliers</h2>
                <div class="selected-category" id="selectedCategory"></div>
                
                <!-- Filter Buttons -->
                <div class="filter-bar" id="filterBar" style="display:none;">
                    <button class="filter-btn active" onclick="filterSuppliers('all', this)">All</button>
                    <button class="filter-btn filter-approved" onclick="filterSuppliers('approved', this)">✓ Approved</button>
                    <button class="filter-btn filter-not-approved" onclick="filterSuppliers('not-approved', this)">✗ Not Approved</button>
                    <button class="filter-btn filter-pending" onclick="filterSuppliers('pending', this)">⏳ Pending</button>
                </div>
                
                <ul class="supplier-list" id="supplierList">
                    <li class="no-selection">← Select a category</li>
                </ul>
            </div>

            <div class="details-panel">
                <h2 class="panel-title">📋 Supplier Details</h2>
                <div id="supplierDetails">
                    <p class="no-selection">← Click a supplier to see details</p>
                </div>
            </div>
        </div>
    </div>

    <!-- Add Supplier Modal -->
    <div class="modal" id="addSupplierModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2 id="supplierModalTitle">➕ Add New Supplier</h2>
                <button class="modal-close" onclick="closeModal('addSupplierModal')">&times;</button>
            </div>
            <form id="supplierForm" onsubmit="saveSupplier(event)">
                <input type="hidden" id="editMode" value="false">
                <input type="hidden" id="editOriginalName" value="">
                <input type="hidden" id="editOriginalCategory" value="">
                
                <div class="form-group">
                    <label>Category *</label>
                    <select id="supplierCategory" required>
                        <option value="">-- Select Category --</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Supplier Name *</label>
                    <input type="text" id="supplierName" required placeholder="Enter supplier name">
                </div>
                <div class="form-group">
                    <label>Approval Status *</label>
                    <select id="supplierApprovalStatus" required>
                        <option value="pending">⏳ Pending Review</option>
                        <option value="approved">✓ Approved</option>
                        <option value="not-approved">✗ Not Approved</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Approval Date</label>
                    <input type="date" id="supplierApprovalDate">
                </div>
                <div class="form-group">
                    <label>Approved By</label>
                    <input type="text" id="supplierApprovedBy" placeholder="Name of approver">
                </div>
                <div class="form-group">
                    <label>Approval Notes</label>
                    <textarea id="supplierApprovalNotes" rows="2" placeholder="Any notes regarding approval"></textarea>
                </div>
                <div class="form-group">
                    <label>Address</label>
                    <textarea id="supplierAddress" rows="2" placeholder="Enter full address"></textarea>
                </div>
                <div class="form-group">
                    <label>Phone</label>
                    <input type="text" id="supplierPhone" placeholder="Enter phone number">
                </div>
                <div class="form-group">
                    <label>Email</label>
                    <input type="email" id="supplierEmail" placeholder="Enter email address">
                </div>
                <div class="form-group">
                    <label>Website</label>
                    <input type="text" id="supplierWebsite" placeholder="www.example.com">
                </div>
                <div class="form-group">
                    <label>Contact Person</label>
                    <input type="text" id="supplierContact" placeholder="Enter contact person name">
                </div>
                <div class="form-actions">
                    <button type="button" class="btn-cancel" onclick="closeModal('addSupplierModal')">Cancel</button>
                    <button type="submit" class="btn-save">💾 Save Supplier</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Add Category Modal -->
    <div class="modal" id="addCategoryModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>📁 Add New Category</h2>
                <button class="modal-close" onclick="closeModal('addCategoryModal')">&times;</button>
            </div>
            <form onsubmit="saveCategory(event)">
                <div class="form-group">
                    <label>Category Name *</label>
                    <input type="text" id="newCategoryName" required placeholder="Enter category name">
                </div>
                <div class="form-actions">
                    <button type="button" class="btn-cancel" onclick="closeModal('addCategoryModal')">Cancel</button>
                    <button type="submit" class="btn-save">💾 Save Category</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Toast Notification -->
    <div class="toast" id="toast"></div>

    <script>
        // ============ DEFAULT DATA (from your Excel) ============
        const DEFAULT_DATA = {
            "RAW MATERIAL - SS": ["Minox", "Ramdev metalex", "ASPL", "Riddhi Siddhi", "Ryan alloys", "Labdhi"],
            "RAW MATERIAL - CRCA": ["BMC", "Meenakshi", "Metcraft", "JR&CO", "GKI"],
            "RAW MATERIAL - GI": ["BMC", "Meenakshi", "JR&CO", "JK Steels", "Max global"],
            "RAW MATERIAL - AL": ["Akash akuminium", "Metal extrusion"],
            "FABRICATION": ["Synergy punch", "Fabionix", "GR Enterprises", "Cloud wave", "Metafin technology - Pune", "System Rack", "GI Autocomponets", "HD Sheet metals", "PMT", "VOM"],
            "MACHINING": ["Ace inotec", "Cloudwave", "Econ machineries", "Alpha creative", "Savya sachin", "Arun Enginering", "Team-D(Bidadi)", "Byraveshwara Engineering Enterprises", "RS CNC"],
            "FASTENERS": ["LPS", "MVD", "Kapasi", "SL Fastners", "Mcmaster", "MK Fasteners", "Shiom fasteners"],
            "PANEL ACCESSORIES": ["EMKA", "Arihant", "Nrack", "GRS Panel systems", "Dirak"],
            "E&E": ["FCI", "AMAR RADIO", "MICRONOVA", "BNR CONNEX", "SULOCHANA", "SAMYUKTHA"],
            "PDU": ["Elcom", "Ace power", "Metal trim", "Networkzone"],
            "POWDER": ["Varna Coats", "Lakshmi engineering", "Southfield", "Akzonobel", "Nerolac"],
            "EARTH BAR": ["Excel metals", "Samyuktha", "Networkzone", "Protech", "Samarth Technologies"],
            "PLATING - Zinc/Anodizing": ["Balambiga", "BEC", "Allied industries", "Sharadha", "Modern lights"],
            "Gasket/Rubber": ["Nandi Industries", "DVG Polymers", "Benaka rubber products", "Propac - UL", "Neostic tapes", "MNM", "Multibond", "Parker", "Networkzone"],
            "Cable gland": ["Lapp", "Hummel", "Trinity", "Element 14", "Symuktha", "Altronic", "MJ Trader"],
            "PLASTICS": ["Polymet", "Spectrum tools", "Industrial plastics", "Primex"],
            "CASTINGS": ["General foundries", "Spectrum tools", "New cast die casting", "Investment precision casting ltd", "NNF - MIM", "LGC"]
        };

        // ============ GLOBAL VARIABLES ============
        let supplierData = {};
        let supplierDetails = {};
        let currentCategory = null;
        let currentSupplier = null;
        let currentFilter = 'all';

        // ============ INITIALIZATION ============
        function init() {
            loadData();
            renderCategories();
            updateStats();
        }

        // ============ LOCAL STORAGE FUNCTIONS ============
        function loadData() {
            const savedData = localStorage.getItem('supplierData');
            const savedDetails = localStorage.getItem('supplierDetails');
            
            if (savedData) {
                supplierData = JSON.parse(savedData);
            } else {
                supplierData = JSON.parse(JSON.stringify(DEFAULT_DATA));
                saveData();
            }
            
            if (savedDetails) {
                supplierDetails = JSON.parse(savedDetails);
            }
        }

        function saveData() {
            localStorage.setItem('supplierData', JSON.stringify(supplierData));
            localStorage.setItem('supplierDetails', JSON.stringify(supplierDetails));
            updateStats();
        }

        // ============ RENDER FUNCTIONS ============
        function renderCategories(filter = '') {
            const categoryList = document.getElementById('categoryList');
            categoryList.innerHTML = '';

            const categories = Object.keys(supplierData).sort();
            
            if (categories.length === 0) {
                categoryList.innerHTML = '<p class="no-selection">No categories found</p>';
                return;
            }

            categories.forEach(category => {
                if (category.toLowerCase().includes(filter.toLowerCase())) {
                    const btn = document.createElement('button');
                    btn.className = 'category-btn' + (currentCategory === category ? ' active' : '');
                    btn.innerHTML = `${category} <span class="count">${supplierData[category].length}</span>`;
                    btn.onclick = () => showSuppliers(category, btn);
                    categoryList.appendChild(btn);
                }
            });
        }

        function showSuppliers(category, btnElement) {
            currentCategory = category;
            currentSupplier = null;
            currentFilter = 'all';
            
            document.querySelectorAll('.category-btn').forEach(btn => btn.classList.remove('active'));
            if (btnElement) btnElement.classList.add('active');

            document.getElementById('selectedCategory').textContent = `📌 ${category}`;
            document.getElementById('supplierDetails').innerHTML = '<p class="no-selection">← Click a supplier to see details</p>';
            document.getElementById('filterBar').style.display = 'flex';
            
            // Reset filter buttons
            document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
            document.querySelector('.filter-btn').classList.add('active');

            renderSupplierList(category);
        }

        function renderSupplierList(category, filter = 'all') {
            const supplierList = document.getElementById('supplierList');
            supplierList.innerHTML = '';

            if (!supplierData[category] || supplierData[category].length === 0) {
                supplierList.innerHTML = '<li class="no-selection">No suppliers in this category</li>';
                return;
            }

            let suppliers = supplierData[category];
            
            // Apply filter
            if (filter !== 'all') {
                suppliers = suppliers.filter(supplier => {
                    const details = supplierDetails[supplier] || {};
                    const status = details.approvalStatus || 'pending';
                    return status === filter;
                });
            }

            if (suppliers.length === 0) {
                supplierList.innerHTML = `<li class="no-selection">No ${filter.replace('-', ' ')} suppliers</li>`;
                return;
            }

            suppliers.forEach((supplier, index) => {
                const details = supplierDetails[supplier] || {};
                const status = details.approvalStatus || 'pending';
                
                const li = document.createElement('li');
                li.className = `supplier-item ${status}`;
                li.innerHTML = `
                    <span onclick="showSupplierDetails('${supplier.replace(/'/g, "\\'")}', this.parentElement)">
                        <span class="status-indicator ${status}"></span>
                        ${index + 1}. ${supplier}
                    </span>
                    <div>
                        <button class="edit-btn" onclick="editSupplier('${category.replace(/'/g, "\\'")}', '${supplier.replace(/'/g, "\\'")}')">✏️</button>
                        <button class="delete-btn" onclick="deleteSupplier('${category.replace(/'/g, "\\'")}', '${supplier.replace(/'/g, "\\'")}')">🗑️</button>
                    </div>
                `;
                supplierList.appendChild(li);
            });
        }

        function filterSuppliers(filter, btnElement) {
            currentFilter = filter;
            
            document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
            btnElement.classList.add('active');
            
            if (currentCategory) {
                renderSupplierList(currentCategory, filter);
            }
        }

        function showSupplierDetails(supplierName, liElement) {
            currentSupplier = supplierName;
            
            document.querySelectorAll('.supplier-item').forEach(item => item.classList.remove('active'));
            if (liElement) liElement.classList.add('active');

            const detailsDiv = document.getElementById('supplierDetails');
            const details = supplierDetails[supplierName] || {};
            const searchQuery = encodeURIComponent(`${supplierName} company address contact India`);
            
            // Determine status display
            const status = details.approvalStatus || 'pending';
            let statusBadge = '';
            if (status === 'approved') {
                statusBadge = '<span class="status-badge status-approved">✓ Approved</span>';
            } else if (status === 'not-approved') {
                statusBadge = '<span class="status-badge status-not-approved">✗ Not Approved</span>';
            } else {
                statusBadge = '<span class="status-badge status-pending">⏳ Pending</span>';
            }
            
            detailsDiv.innerHTML = `
                <div class="supplier-details">
                    <div class="supplier-name">
                        <span>🏢 ${supplierName}</span>
                        ${statusBadge}
                    </div>
                    
                    <div style="background: #f8f9fa; padding: 10px; border-radius: 5px; margin-bottom: 15px;">
                        <div style="font-weight: bold; margin-bottom: 8px; color: #333; font-size: 0.85em;">📋 Approval Information</div>
                        <div class="detail-row">
                            <span class="detail-label">Status:</span>
                            <span class="detail-value">${status === 'approved' ? '✓ Approved' : status === 'not-approved' ? '✗ Not Approved' : '⏳ Pending Review'}</span>
                        </div>
                        <div class="detail-row">
                            <span class="detail-label">Date:</span>
                            <span class="detail-value">${details.approvalDate || 'Not specified'}</span>
                        </div>
                        <div class="detail-row">
                            <span class="detail-label">Approved By:</span>
                            <span class="detail-value">${details.approvedBy || 'Not specified'}</span>
                        </div>
                        <div class="detail-row">
                            <span class="detail-label">Notes:</span>
                            <span class="detail-value">${details.approvalNotes || 'No notes'}</span>
                        </div>
                    </div>
                    
                    <div style="font-weight: bold; margin-bottom: 8px; color: #333; font-size: 0.85em;">📞 Contact Information</div>
                    <div class="detail-row">
                        <span class="detail-label">📍 Address:</span>
                        <span class="detail-value">${details.address || 'Not specified'}</span>
                    </div>
                    <div class="detail-row">
                        <span class="detail-label">📞 Phone:</span>
                        <span class="detail-value">${details.phone || 'Not specified'}</span>
                    </div>
                    <div class="detail-row">
                        <span class="detail-label">📧 Email:</span>
                        <span class="detail-value">${details.email ? `<a href="mailto:${details.email}">${details.email}</a>` : 'Not specified'}</span>
                    </div>
                    <div class="detail-row">
                        <span class="detail-label">🌐 Website:</span>
                        <span class="detail-value">${details.website ? `<a href="https://${details.website}" target="_blank">${details.website}</a>` : 'Not specified'}</span>
                    </div>
                    <div class="detail-row">
                        <span class="detail-label">👤 Contact:</span>
                        <span class="detail-value">${details.contact || 'Not specified'}</span>
                    </div>
                    
                    <div style="margin-top: 15px; padding-top: 10px; border-top: 1px solid #ddd;">
                        <a href="https://www.google.com/search?q=${searchQuery}" target="_blank" 
                           style="display: inline-block; padding: 6px 12px; background: #4a90d9; color: white; 
                                  text-decoration: none; border-radius: 4px; font-size: 0.8em; margin-right: 8px;">
                            🔍 Google Search
                        </a>
                        <a href="https://www.indiamart.com/search.mp?ss=${encodeURIComponent(supplierName)}" target="_blank"
                           style="display: inline-block; padding: 6px 12px; background: #ff9800; color: white; 
                                  text-decoration: none; border-radius: 4px; font-size: 0.8em;">
                            🏭 IndiaMART
                        </a>
                    </div>
                </div>
            `;
        }

        // ============ MODAL FUNCTIONS ============
        function openAddSupplierModal() {
            document.getElementById('supplierModalTitle').textContent = '➕ Add New Supplier';
            document.getElementById('editMode').value = 'false';
            document.getElementById('supplierForm').reset();
            document.getElementById('supplierApprovalStatus').value = 'pending';
            populateCategoryDropdown();
            
            if (currentCategory) {
                document.getElementById('supplierCategory').value = currentCategory;
            }
            
            document.getElementById('addSupplierModal').classList.add('active');
        }

        function openAddCategoryModal() {
            document.getElementById('newCategoryName').value = '';
            document.getElementById('addCategoryModal').classList.add('active');
        }

        function closeModal(modalId) {
            document.getElementById(modalId).classList.remove('active');
        }

        function populateCategoryDropdown() {
            const select = document.getElementById('supplierCategory');
            select.innerHTML = '<option value="">-- Select Category --</option>';
            
            Object.keys(supplierData).sort().forEach(category => {
                const option = document.createElement('option');
                option.value = category;
                option.textContent = category;
                select.appendChild(option);
            });
        }

        // ============ SAVE FUNCTIONS ============
        function saveSupplier(event) {
            event.preventDefault();
            
            const category = document.getElementById('supplierCategory').value;
            const name = document.getElementById('supplierName').value.trim();
            const isEdit = document.getElementById('editMode').value === 'true';
            const originalName = document.getElementById('editOriginalName').value;
            const originalCategory = document.getElementById('editOriginalCategory').value;
            
            if (!category || !name) {
                showToast('Please fill in required fields', true);
                return;
            }

            if (!isEdit || name !== originalName || category !== originalCategory) {
                if (supplierData[category] && supplierData[category].includes(name)) {
                    showToast('Supplier already exists in this category!', true);
                    return;
                }
            }

            if (isEdit && originalCategory && originalName) {
                const idx = supplierData[originalCategory].indexOf(originalName);
                if (idx > -1) {
                    supplierData[originalCategory].splice(idx, 1);
                }
                if (originalName !== name && supplierDetails[originalName]) {
                    supplierDetails[name] = supplierDetails[originalName];
                    delete supplierDetails[originalName];
                }
            }

            if (!supplierData[category]) {
                supplierData[category] = [];
            }
            if (!supplierData[category].includes(name)) {
                supplierData[category].push(name);
            }

            // Save supplier details with approval information
            supplierDetails[name] = {
                approvalStatus: document.getElementById('supplierApprovalStatus').value,
                approvalDate: document.getElementById('supplierApprovalDate').value,
                approvedBy: document.getElementById('supplierApprovedBy').value.trim(),
                approvalNotes: document.getElementById('supplierApprovalNotes').value.trim(),
                address: document.getElementById('supplierAddress').value.trim(),
                phone: document.getElementById('supplierPhone').value.trim(),
                email: document.getElementById('supplierEmail').value.trim(),
                website: document.getElementById('supplierWebsite').value.trim(),
                contact: document.getElementById('supplierContact').value.trim()
            };

            saveData();
            closeModal('addSupplierModal');
            renderCategories(document.getElementById('searchCategory').value);
            
            if (currentCategory === category || currentCategory === originalCategory) {
                renderSupplierList(category, currentFilter);
            }
            
            showToast(isEdit ? 'Supplier updated successfully!' : 'Supplier added successfully!');
        }

        function saveCategory(event) {
            event.preventDefault();
            
            const name = document.getElementById('newCategoryName').value.trim();
            
            if (!name) {
                showToast('Please enter category name', true);
                return;
            }

            if (supplierData[name]) {
                showToast('Category already exists!', true);
                return;
            }

            supplierData[name] = [];
            saveData();
            closeModal('addCategoryModal');
            renderCategories(document.getElementById('searchCategory').value);
            showToast('Category added successfully!');
        }

        // ============ EDIT & DELETE FUNCTIONS ============
        function editSupplier(category, supplierName) {
            event.stopPropagation();
            
            document.getElementById('supplierModalTitle').textContent = '✏️ Edit Supplier';
            document.getElementById('editMode').value = 'true';
            document.getElementById('editOriginalName').value = supplierName;
            document.getElementById('editOriginalCategory').value = category;
            
            populateCategoryDropdown();
            
            document.getElementById('supplierCategory').value = category;
            document.getElementById('supplierName').value = supplierName;
            
            const details = supplierDetails[supplierName] || {};
            document.getElementById('supplierApprovalStatus').value = details.approvalStatus || 'pending';
            document.getElementById('supplierApprovalDate').value = details.approvalDate || '';
            document.getElementById('supplierApprovedBy').value = details.approvedBy || '';
            document.getElementById('supplierApprovalNotes').value = details.approvalNotes || '';
            document.getElementById('supplierAddress').value = details.address || '';
            document.getElementById('supplierPhone').value = details.phone || '';
            document.getElementById('supplierEmail').value = details.email || '';
            document.getElementById('supplierWebsite').value = details.website || '';
            document.getElementById('supplierContact').value = details.contact || '';
            
            document.getElementById('addSupplierModal').classList.add('active');
        }

        function deleteSupplier(category, supplierName) {
            event.stopPropagation();
            
            if (!confirm(`Are you sure you want to delete "${supplierName}"?`)) {
                return;
            }

            const idx = supplierData[category].indexOf(supplierName);
            if (idx > -1) {
                supplierData[category].splice(idx, 1);
            }

            delete supplierDetails[supplierName];

            saveData();
            renderCategories(document.getElementById('searchCategory').value);
            
            if (currentCategory === category) {
                renderSupplierList(category, currentFilter);
            }
            
            showToast('Supplier deleted successfully!');
        }

        // ============ IMPORT/EXPORT FUNCTIONS ============
        function exportData() {
            const data = {
                supplierData: supplierData,
                supplierDetails: supplierDetails,
                exportDate: new Date().toISOString()
            };
            
            const blob = new Blob([JSON.stringify(data, null, 2)], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `supplier_data_${new Date().toISOString().split('T')[0]}.json`;
            a.click();
            URL.revokeObjectURL(url);
            
            showToast('Data exported successfully!');
        }

        function importData() {
            document.getElementById('importFile').click();
        }

        function handleImport(event) {
            const file = event.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = function(e) {
                try {
                    const data = JSON.parse(e.target.result);
                    
                    if (data.supplierData) {
                        Object.keys(data.supplierData).forEach(category => {
                            if (!supplierData[category]) {
                                supplierData[category] = [];
                            }
                            data.supplierData[category].forEach(supplier => {
                                if (!supplierData[category].includes(supplier)) {
                                    supplierData[category].push(supplier);
                                }
                            });
                        });
                    }
                    
                    if (data.supplierDetails) {
                        Object.assign(supplierDetails, data.supplierDetails);
                    }
                    
                    saveData();
                    renderCategories();
                    showToast('Data imported successfully!');
                    
                } catch (error) {
                    showToast('Error importing file: ' + error.message, true);
                }
            };
            reader.readAsText(file);
            event.target.value = '';
        }

        function resetToDefault() {
            if (!confirm('This will reset all data to default. Any added suppliers will be lost. Continue?')) {
                return;
            }

            supplierData = JSON.parse(JSON.stringify(DEFAULT_DATA));
            supplierDetails = {};
            saveData();
            currentCategory = null;
            currentSupplier = null;
            renderCategories();
            document.getElementById('supplierList').innerHTML = '<li class="no-selection">← Select a category</li>';
            document.getElementById('supplierDetails').innerHTML = '<p class="no-selection">← Click a supplier to see details</p>';
            document.getElementById('selectedCategory').textContent = '';
            document.getElementById('filterBar').style.display = 'none';
            showToast('Data reset to default!');
        }

        // ============ UTILITY FUNCTIONS ============
        function updateStats() {
            const totalCats = Object.keys(supplierData).length;
            let totalSupps = 0;
            let approvedCount = 0;
            let notApprovedCount = 0;
            
            Object.values(supplierData).forEach(arr => {
                totalSupps += arr.length;
                arr.forEach(supplier => {
                    const details = supplierDetails[supplier] || {};
                    if (details.approvalStatus === 'approved') approvedCount++;
                    else if (details.approvalStatus === 'not-approved') notApprovedCount++;
                });
            });
            
            document.getElementById('totalCategories').textContent = `Categories: ${totalCats}`;
            document.getElementById('totalSuppliers').textContent = `Suppliers: ${totalSupps}`;
            document.getElementById('approvedCount').textContent = `✓ Approved: ${approvedCount}`;
            document.getElementById('notApprovedCount').textContent = `✗ Not Approved: ${notApprovedCount}`;
        }

        function showToast(message, isError = false) {
            const toast = document.getElementById('toast');
            toast.textContent = message;
            toast.className = 'toast show' + (isError ? ' error' : '');
            
            setTimeout(() => {
                toast.className = 'toast';
            }, 3000);
        }

        // ============ EVENT LISTENERS ============
        document.getElementById('searchCategory').addEventListener('input', function() {
            renderCategories(this.value);
        });

        document.querySelectorAll('.modal').forEach(modal => {
            modal.addEventListener('click', function(e) {
                if (e.target === this) {
                    this.classList.remove('active');
                }
            });
        });

        // ============ INITIALIZE APP ============
        init();
    </script>
</body>
</html>
