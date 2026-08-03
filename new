<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Control de Mantenimiento Vehicular (+15 Años)</title>
    <style>
        :root {
            --primary: #1e3a8a;
            --primary-dark: #1e293b;
            --accent: #2563eb;
            --success: #16a34a;
            --warning: #d97706;
            --danger: #dc2626;
            --bg: #f8fafc;
            --card-bg: #ffffff;
            --text: #334155;
            --border: #cbd5e1;
        }
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }
        body {
            background-color: var(--bg);
            color: var(--text);
            padding: 12px;
            max-width: 600px;
            margin: 0 auto;
            font-size: 15px;
            padding-bottom: 70px;
        }
        header {
            background: var(--primary);
            color: white;
            padding: 16px;
            border-radius: 12px;
            text-align: center;
            margin-bottom: 16px;
            box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1);
        }
        header h1 {
            font-size: 1.25rem;
            margin-bottom: 4px;
        }
        header p {
            font-size: 0.85rem;
            opacity: 0.9;
        }
        .nav-tabs {
            display: flex;
            gap: 4px;
            margin-bottom: 16px;
            overflow-x: auto;
            padding-bottom: 4px;
        }
        .nav-tabs button {
            flex: 1;
            padding: 8px 6px;
            border: none;
            background: #e2e8f0;
            color: var(--text);
            font-weight: 600;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.78rem;
            white-space: nowrap;
            transition: all 0.2s;
        }
        .nav-tabs button.active {
            background: var(--accent);
            color: white;
            box-shadow: 0 2px 4px rgba(37,99,235,0.3);
        }
        .tab-content {
            display: none;
        }
        .tab-content.active {
            display: block;
        }
        .card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 16px;
            margin-bottom: 16px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            border: 1px solid var(--border);
        }
        h2 {
            font-size: 1.1rem;
            color: var(--primary-dark);
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 8px;
            border-bottom: 2px solid #f1f5f9;
            padding-bottom: 6px;
        }
        .alert-box {
            background: #fef2f2;
            border-left: 4px solid var(--danger);
            padding: 12px;
            border-radius: 6px;
            margin-bottom: 16px;
            font-size: 0.9rem;
        }
        .alert-box.warning {
            background: #fffbeb;
            border-left-color: var(--warning);
        }
        .alert-box.info {
            background: #eff6ff;
            border-left-color: var(--accent);
        }
        .alert-title {
            font-weight: bold;
            margin-bottom: 4px;
            display: flex;
            align-items: center;
            gap: 6px;
        }
        form {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }
        .form-group {
            display: flex;
            flex-direction: column;
            gap: 4px;
        }
        label {
            font-weight: 600;
            font-size: 0.85rem;
            color: var(--primary-dark);
        }
        input, select, textarea {
            padding: 10px;
            border: 1px solid var(--border);
            border-radius: 8px;
            font-size: 0.95rem;
            width: 100%;
            background: #fff;
        }
        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--accent);
            box-shadow: 0 0 0 3px rgba(37,99,235,0.1);
        }
        .btn {
            background: var(--accent);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            font-size: 0.95rem;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
        }
        .btn-success { background: var(--success); }
        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 0.85rem;
            margin-top: 8px;
        }
        th, td {
            padding: 8px 6px;
            text-align: left;
            border-bottom: 1px solid #e2e8f0;
        }
        th {
            background: #f1f5f9;
            color: var(--primary-dark);
            font-weight: 700;
        }
        .badge {
            padding: 3px 6px;
            border-radius: 4px;
            font-size: 0.75rem;
            font-weight: bold;
            display: inline-block;
        }
        .badge-ok { background: #dcfce7; color: var(--success); }
        .badge-warning { background: #fef3c7; color: var(--warning); }
        .badge-danger { background: #fee2e2; color: var(--danger); }
        .table-responsive {
            overflow-x: auto;
        }
        .actions-bar {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(255, 255, 255, 0.98);
            backdrop-filter: blur(5px);
            padding: 10px 16px;
            box-shadow: 0 -4px 10px rgba(0,0,0,0.08);
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-top: 1px solid var(--border);
            z-index: 1000;
            max-width: 600px;
            margin: 0 auto;
        }
        .save-status {
            font-size: 0.75rem;
            color: #64748b;
        }
        .delete-btn {
            background: none;
            border: none;
            color: var(--danger);
            cursor: pointer;
            font-size: 0.9rem;
            padding: 4px;
        }
        .suggestion-box {
            background: #f8fafc;
            border: 1px dashed var(--accent);
            padding: 10px;
            border-radius: 8px;
            font-size: 0.85rem;
            color: #1e293b;
            margin-top: 4px;
        }
    </style>
</head>
<body>

    <header>
        <h1>CarCare 15+ Pro</h1>
        <p>Mantenimiento y Diagnóstico OBD-II</p>
    </header>

    <!-- Pestañas de Navegación -->
    <div class="nav-tabs">
        <button class="active" onclick="switchTab('alerts')">🔔 Alertas</button>
        <button onclick="switchTab('scanner')">📟 Scanner</button>
        <button onclick="switchTab('preventive')">🛡️ Preventivo</button>
        <button onclick="switchTab('corrective')">🔧 Correctivo</button>
        <button onclick="switchTab('history')">📊 Historial</button>
    </div>

    <!-- PESTAÑA 1: ALERTAS E IA -->
    <div id="tab-alerts" class="tab-content active">
        <div class="card">
            <h2>🧠 Diagnóstico Inteligente & Patrones</h2>
            <div id="smart-alerts-container"></div>
        </div>

        <div class="card">
            <h2>⏳ Próximos Chequeos Preventivos</h2>
            <div class="table-responsive">
                <table>
                    <thead>
                        <tr>
                            <th>Componente</th>
                            <th>Última Rev.</th>
                            <th>Próxima</th>
                            <th>Estado</th>
                        </tr>
                    </thead>
                    <tbody id="upcoming-schedule-body"></tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- PESTAÑA 2: NUEVO MÓDULO SCANNER / CÓDIGOS DE FALLA -->
    <div id="tab-scanner" class="tab-content">
        <div class="card">
            <h2>📟 Registro de Códigos de Falla (OBD-II)</h2>
            <form id="scanner-form" onsubmit="saveScannerCode(event)">
                <div class="form-group">
                    <label for="scan-code">Código de Falla (Ej. P0300, P0171):</label>
                    <input type="text" id="scan-code" placeholder="Ej. P0135" required style="text-transform: uppercase;" oninput="lookupOBDCode(this.value)">
                </div>

                <div class="suggestion-box" id="obd-suggestion">
                    <i>💡 Ingresa un código OBD-II para ver la descripción sugerida y acciones correctivas recomendadas automáticamente.</i>
                </div>

                <div class="form-group" style="margin-top:8px;">
                    <label for="scan-desc">Descripción del Problema:</label>
                    <input type="text" id="scan-desc" placeholder="Descripción de la falla..." required>
                </div>

                <div class="form-group">
                    <label for="scan-action">Acción Correctiva Sugerida:</label>
                    <textarea id="scan-action" rows="2" placeholder="Acciones a realizar..." required></textarea>
                </div>

                <div class="form-group">
                    <label for="scan-date">Fecha de Diagnóstico:</label>
                    <input type="date" id="scan-date" required>
                </div>

                <div class="form-group">
                    <label for="scan-km">Kilometraje:</label>
                    <input type="number" id="scan-km" placeholder="Ej. 165000" required>
                </div>

                <button type="submit" class="btn btn-success">➕ Guardar Código de Falla</button>
            </form>
        </div>

        <div class="card">
            <h2>📈 Historial de Códigos de Falla</h2>
            <div class="table-responsive">
                <table>
                    <thead>
                        <tr>
                            <th>Código</th>
                            <th>Fecha</th>
                            <th>Descripción / Solución</th>
                            <th>Acción</th>
                        </tr>
                    </thead>
                    <tbody id="history-scanner-body"></tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- PESTAÑA 3: PREVENTIVO -->
    <div id="tab-preventive" class="tab-content">
        <div class="card">
            <h2>🛠️ Registrar Chequeo Preventivo</h2>
            <form id="preventive-form" onsubmit="savePreventive(event)">
                <div class="form-group">
                    <label for="prev-component">Componente / Sistema:</label>
                    <select id="prev-component" required onchange="updatePrevDefaults()">
                        <option value="">-- Seleccione componente --</option>
                        <option value="Nivel de Aceite de Motor">Nivel de Aceite de Motor (Cada 15 días)</option>
                        <option value="Líquido Refrigerante">Líquido Refrigerante (Mensual)</option>
                        <option value="Batería y Terminales">Batería y Terminales (Cada 2 meses)</option>
                        <option value="Filtro de Aire Acondicionado">Filtro A/C Cabina (Cada 3 meses)</option>
                        <option value="Filtro de Aire de Motor">Filtro de Aire Motor (Cada 6 meses)</option>
                        <option value="Bujías (Resistencia/Gap)">Bujías (Cada 2 meses / medición)</option>
                        <option value="Pastillas y Bandas de Freno">Frenos (10,000 km / 10 meses)</option>
                        <option value="Correa de Tiempo">Correa de Tiempo (Cada 50,000 km)</option>
                        <option value="Neumáticos y Presión">Neumáticos (Quincenal)</option>
                        <option value="Personalizado">⚙️ Otro componente personalizado...</option>
                    </select>
                </div>

                <div class="form-group" id="custom-comp-group" style="display:none;">
                    <label for="prev-custom-name">Nombre del Componente:</label>
                    <input type="text" id="prev-custom-name" placeholder="Ej. Aceite de transmisión">
                </div>

                <div class="form-group">
                    <label for="prev-date">Fecha de Realización:</label>
                    <input type="date" id="prev-date" required>
                </div>

                <div class="form-group">
                    <label for="prev-km">Kilometraje:</label>
                    <input type="number" id="prev-km" placeholder="Ej. 165000" required>
                </div>

                <div class="form-group">
                    <label for="prev-value">Variable Medida / Lectura:</label>
                    <input type="text" id="prev-value" placeholder="Ej. 12.6V / 500ml agregados" required>
                </div>

                <div class="form-group">
                    <label for="prev-notes">Observaciones:</label>
                    <textarea id="prev-notes" rows="2" placeholder="Detalles de la medición..."></textarea>
                </div>

                <button type="submit" class="btn btn-success">➕ Guardar Preventivo</button>
            </form>
        </div>
    </div>

    <!-- PESTAÑA 4: CORRECTIVO -->
    <div id="tab-corrective" class="tab-content">
        <div class="card">
            <h2>🚨 Registrar Avería o Correctivo</h2>
            <form id="corrective-form" onsubmit="saveCorrective(event)">
                <div class="form-group">
                    <label for="corr-id">ID del Evento:</label>
                    <input type="text" id="corr-id" readonly style="background:#e2e8f0; font-weight:bold;">
                </div>

                <div class="form-group">
                    <label for="corr-date">Fecha:</label>
                    <input type="date" id="corr-date" required>
                </div>

                <div class="form-group">
                    <label for="corr-km">Kilometraje:</label>
                    <input type="number" id="corr-km" placeholder="Ej. 165200" required>
                </div>

                <div class="form-group">
                    <label for="corr-system">Sistema Afectado:</label>
                    <select id="corr-system" required>
                        <option value="">-- Seleccionar sistema --</option>
                        <option value="Motor">Motor</option>
                        <option value="Sistema Eléctrico">Sistema Eléctrico / Arranque</option>
                        <option value="Frenos">Frenos</option>
                        <option value="Suspensión y Dirección">Suspensión y Dirección</option>
                        <option value="Transmisión / Embrague">Transmisión / Embrague</option>
                        <option value="Enfriamiento">Enfriamiento</option>
                        <option value="Otro">Otro</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="corr-symptom">Síntoma / Falla:</label>
                    <textarea id="corr-symptom" rows="2" placeholder="Descripción de la falla..." required></textarea>
                </div>

                <div class="form-group">
                    <label for="corr-solution">Diagnóstico y Solución:</label>
                    <textarea id="corr-solution" rows="2" placeholder="Solución aplicada..." required></textarea>
                </div>

                <div class="form-group">
                    <label for="corr-parts">Repuestos Utilizados:</label>
                    <input type="text" id="corr-parts" placeholder="Ej. Alternador reconstruido">
                </div>

                <div class="form-group">
                    <label for="corr-cost">Costo Total ($):</label>
                    <input type="number" step="0.01" id="corr-cost" placeholder="Ej. 45.00" required>
                </div>

                <button type="submit" class="btn btn-success">💾 Registrar Avería</button>
            </form>
        </div>
    </div>

    <!-- PESTAÑA 5: HISTORIAL -->
    <div id="tab-history" class="tab-content">
        <div class="card">
            <h2>📜 Historial General</h2>
            <div class="table-responsive">
                <table>
                    <thead>
                        <tr>
                            <th>Fecha/ID</th>
                            <th>Tipo / Componente</th>
                            <th>Detalle / Lectura</th>
                            <th>Acción</th>
                        </tr>
                    </thead>
                    <tbody id="history-general-body"></tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- Barra fija de guardado inferior -->
    <div class="actions-bar">
        <span class="save-status" id="save-status-text">💾 Cambios guardados localmente</span>
        <button class="btn" style="padding: 8px 14px; font-size: 0.85rem;" onclick="manualSave()">Guardar Cambios</button>
    </div>

    <script>
        // Base de datos OBD-II común orientativa
        const obdDatabase = {
            "P0100": { desc: "Flujo de masa o volumen de aire mal funcionamiento", action: "Limpiar sensor MAF con líquido dieléctrico o revisar cableado." },
            "P0101": { desc: "Problema de rango/rendimiento en circuito de masa de aire (MAF)", action: "Revisar posibles fugas de vacío en la admisión y limpiar sensor MAF." },
            "P0130": { desc: "Circuito del sensor de oxígeno (O2) defectuoso (Banco 1, Sensor 1)", action: "Revisar conexiones del sensor de oxígeno delantero o reemplazarlo por desgaste." },
            "P0135": { desc: "Calefactor del sensor de oxígeno defectuoso (Banco 1, Sensor 1)", action: "Revisar fusible del calefactor o cambiar el sensor O2." },
            "P0171": { desc: "Sistema demasiado pobre (Banco 1)", action: "Revisar presión de combustible, filtro de gasolina tapado o fugas de aire en mangueras de vacío." },
            "P0300": { desc: "Fallas aleatorias/múltiples en cilindros", action: "Revisar bujías, cables de bujía, bobina de encendido y compresión de los cilindros." },
            "P0301": { desc: "Falla de encendido detectada en Cilindro 1", action: "Inspeccionar bujía e inyector del cilindro 1." },
            "P0302": { desc: "Falla de encendido detectada en Cilindro 2", action: "Inspeccionar bujía e inyector del cilindro 2." },
            "P0303": { desc: "Falla de encendido detectada en Cilindro 3", action: "Inspeccionar bujía e inyector del cilindro 3." },
            "P0304": { desc: "Falla de encendido detectada en Cilindro 4", action: "Inspeccionar bujía e inyector del cilindro 4." },
            "P0335": { desc: "Sensor de posición del cigüeñal - circuito defectuoso", action: "Limpiar o reemplazar el sensor CKP y revisar cableado." },
            "P0420": { desc: "Eficiencia del sistema de catalizador por debajo del umbral", action: "Revisar estado del convertidor catalítico o fugas en el tubo de escape." },
            "P0500": { desc: "Sensor de velocidad del vehículo defectuoso", action: "Revisar conector o reemplazar sensor de velocidad en la caja/rueda." },
            "P0505": { desc: "Sistema de control de aire en ralentí (IAC) averiado", action: "Limpiar válvula IAC y cuerpo de aceleración." }
        };

        let db = JSON.parse(localStorage.getItem('carCareDBV2')) || {
            preventive: [],
            corrective: [],
            scanner: []
        };

        document.addEventListener('DOMContentLoaded', () => {
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('prev-date').value = today;
            document.getElementById('corr-date').value = today;
            document.getElementById('scan-date').value = today;
            updateCorrectiveID();
            renderAll();
        });

        function switchTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.remove('active'));
            document.querySelectorAll('.nav-tabs button').forEach(el => el.classList.remove('active'));
            document.getElementById('tab-' + tabId).classList.add('active');
            event.currentTarget.classList.add('active');
        }

        function updatePrevDefaults() {
            const val = document.getElementById('prev-component').value;
            const customGroup = document.getElementById('custom-comp-group');
            customGroup.style.display = (val === 'Personalizado') ? 'flex' : 'none';
        }

        function updateCorrectiveID() {
            const count = db.corrective.length + 1;
            document.getElementById('corr-id').value = 'MC-' + String(count).padStart(3, '0');
        }

        function lookupOBDCode(code) {
            const cleanCode = code.trim().toUpperCase();
            const box = document.getElementById('obd-suggestion');
            if (obdDatabase[cleanCode]) {
                const info = obdDatabase[cleanCode];
                box.innerHTML = `<b>🔍 Coincidencia Encontrada (${cleanCode}):</b><br>• <b>Problema:</b> ${info.desc}<br>• <b>Acción sugerida:</b> ${info.action}`;
                document.getElementById('scan-desc').value = info.desc;
                document.getElementById('scan-action').value = info.action;
            } else {
                box.innerHTML = `<i>💡 Código no predefinido en la memoria interna. Puedes escribir la descripción y la acción correctiva manualmente.</i>`;
            }
        }

        function saveScannerCode(e) {
            e.preventDefault();
            const record = {
                id: Date.now(),
                type: 'scanner',
                code: document.getElementById('scan-code').value.toUpperCase(),
                desc: document.getElementById('scan-desc').value,
                action: document.getElementById('scan-action').value,
                date: document.getElementById('scan-date').value,
                km: parseInt(document.getElementById('scan-km').value)
            };
            db.scanner.push(record);
            manualSave();
            document.getElementById('scanner-form').reset();
            document.getElementById('scan-date').value = new Date().toISOString().split('T')[0];
            document.getElementById('obd-suggestion').innerHTML = `<i>💡 Código guardado con éxito.</i>`;
            alert('¡Código de falla registrado correctamente!');
            switchTab('history');
            document.querySelectorAll('.nav-tabs button')[4].classList.add('active');
            document.querySelectorAll('.nav-tabs button')[1].classList.remove('active');
        }

        function savePreventive(e) {
            e.preventDefault();
            let compName = document.getElementById('prev-component').value;
            if (compName === 'Personalizado') compName = document.getElementById('prev-custom-name').value;

            const record = {
                id: Date.now(),
                type: 'preventive',
                component: compName,
                date: document.getElementById('prev-date').value,
                km: parseInt(document.getElementById('prev-km').value),
                value: document.getElementById('prev-value').value,
                notes: document.getElementById('prev-notes').value
            };
            db.preventive.push(record);
            manualSave();
            document.getElementById('preventive-form').reset();
            document.getElementById('prev-date').value = new Date().toISOString().split('T')[0];
            alert('¡Preventivo guardado!');
            switchTab('history');
            document.querySelectorAll('.nav-tabs button')[4].classList.add('active');
            document.querySelectorAll('.nav-tabs button')[2].classList.remove('active');
        }

        function saveCorrective(e) {
            e.preventDefault();
            const record = {
                id: document.getElementById('corr-id').value,
                type: 'corrective',
                date: document.getElementById('corr-date').value,
                km: parseInt(document.getElementById('corr-km').value),
                system: document.getElementById('corr-system').value,
                symptom: document.getElementById('corr-symptom').value,
                solution: document.getElementById('corr-solution').value,
                parts: document.getElementById('corr-parts').value,
                cost: parseFloat(document.getElementById('corr-cost').value)
            };
            db.corrective.push(record);
            updateCorrectiveID();
            manualSave();
            document.getElementById('corrective-form').reset();
            document.getElementById('corr-date').value = new Date().toISOString().split('T')[0];
            alert('¡Correctivo guardado!');
            switchTab('history');
            document.querySelectorAll('.nav-tabs button')[4].classList.add('active');
            document.querySelectorAll('.nav-tabs button')[3].classList.remove('active');
        }

        function manualSave() {
            localStorage.setItem('carCareDBV2', JSON.stringify(db));
            document.getElementById('save-status-text').textContent = '✅ Guardado localmente a las ' + new Date().toLocaleTimeString();
            renderAll();
        }

        function deleteRecord(type, id) {
            if(confirm('¿Eliminar este registro?')) {
                if(type === 'preventive') db.preventive = db.preventive.filter(i => i.id !== id);
                if(type === 'corrective') { db.corrective = db.corrective.filter(i => i.id !== id); updateCorrectiveID(); }
                if(type === 'scanner') db.scanner = db.scanner.filter(i => i.id !== id);
                manualSave();
            }
        }

        function analyzeIntelligenceAndAlerts() {
            const container = document.getElementById('smart-alerts-container');
            let html = '';

            // Alerta por códigos de falla repetidos
            const codeCounts = {};
            db.scanner.forEach(s => {
                codeCounts[s.code] = (codeCounts[s.code] || 0) + 1;
                if(codeCounts[s.code] >= 2) {
                    html += `<div class="alert-box warning"><div class="alert-title">⚠️ Falla Recurrente (${s.code})</div><p>El código <b>${s.code}</b> se ha registrado múltiples veces. La solución aplicada anteriormente podría no haber resuelto la raíz del problema.</p></div>`;
                }
            });

            if(db.scanner.length > 0 && html === '') {
                html += `<div class="alert-box info"><div class="alert-title">📟 Scanner Activo</div><p>Tienes ${db.scanner.length} códigos de falla registrados en el historial.</p></div>`;
            }

            if(html === '') {
                html = `<div class="alert-box info" style="background:#f0fdf4; border-left-color:var(--success);"><div class="alert-title">✨ Sistema Estable</div><p>No hay alertas críticas en este momento.</p></div>`;
            }
            container.innerHTML = html;
        }

        function renderSchedule() {
            const tbody = document.getElementById('upcoming-schedule-body');
            tbody.innerHTML = '';
            const tracked = [
                { name: 'Nivel de Aceite de Motor', days: 15 },
                { name: 'Líquido Refrigerante', days: 30 },
                { name: 'Batería y Terminales', days: 60 },
                { name: 'Filtro de Aire Acondicionado', days: 90 },
                { name: 'Neumáticos y Presión', days: 15 }
            ];
            const today = new Date();

            tracked.forEach(t => {
                const history = db.preventive.filter(i => i.component === t.name);
                let last = 'Nunca', next = 'Programar', badge = '<span class="badge badge-warning">Pendiente</span>';
                if(history.length > 0) {
                    history.sort((a,b) => new Date(b.date) - new Date(a.date));
                    last = history[0].date;
                    const nextDate = new Date(new Date(last).getTime() + (t.days * 86400000));
                    next = nextDate.toISOString().split('T')[0];
                    const diff = Math.ceil((nextDate - today) / 86400000);
                    badge = diff < 0 ? `<span class="badge badge-danger">Vencido (${Math.abs(diff)}d)</span>` : (diff <= 3 ? `<span class="badge badge-warning">Próximo (${diff}d)</span>` : `<span class="badge badge-ok">Al día</span>`);
                }
                tbody.innerHTML += `<tr><td><b>${t.name}</b></td><td>${last}</td><td>${next}</td><td>${badge}</td></tr>`;
            });
        }

        function renderHistory() {
            const body = document.getElementById('history-general-body');
            body.innerHTML = '';
            let all = [];
            db.preventive.forEach(i => all.push({...i, category: '🛡️ Preventivo', label: i.component, detail: i.value}));
            db.corrective.forEach(i => all.push({...i, category: '🔧 Correctivo', label: i.system, detail: `$${i.cost} - ${i.symptom}`}));
            db.scanner.forEach(i => all.push({...i, category: '📟 Scanner', label: i.code, detail: i.desc}));

            all.sort((a,b) => new Date(b.date) - new Date(a.date));

            if(all.length === 0) {
                body.innerHTML = `<tr><td colspan="4" style="text-align:center; color:#94a3b8;">Sin registros todavía.</td></tr>`;
                return;
            }

            all.forEach(item => {
                body.innerHTML += `
                    <tr>
                        <td>${item.date}<br><small>${item.id || item.km + ' km'}</small></td>
                        <td><b>${item.category}</b><br>${item.label}</td>
                        <td>${item.detail}</td>
                        <td><button class="delete-btn" onclick="deleteRecord('${item.type}', ${item.id})">❌</button></td>
                    </tr>
                `;
            });
        }

        function renderAll() {
            renderSchedule();
            analyzeIntelligenceAndAlerts();
            renderHistory();
        }
    </script>
</body>
</html>
