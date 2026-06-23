<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Gemini Nano - Diagnóstico Completo</title>
    <style>
        body { font-family: system-ui, sans-serif; background: #0d1117; color: #c9d1d9; padding: 20px; }
        .card { background: #161b22; padding: 20px; border-radius: 12px; border: 1px solid #30363d; max-width: 600px; margin: auto; box-shadow: 0 8px 24px rgba(0,0,0,0.5); }
        button { background: #2f81f7; color: white; border: none; padding: 10px 16px; border-radius: 6px; cursor: pointer; font-weight: bold; margin-right: 10px; }
        button:disabled { background: #21262d; color: #8b949e; cursor: not-allowed; }
        pre { background: #000; padding: 15px; border-radius: 6px; white-space: pre-wrap; border: 1px solid #30363d; font-family: monospace; }
        .badge { padding: 4px 8px; border-radius: 4px; font-size: 0.85rem; font-weight: bold; display: inline-block; margin-bottom: 10px; }
        .available { background: #238636; color: #7ee787; }
        .missing { background: #da3633; color: #f85149; }
    </style>
</head>
<body>

<div class="card">
    <h2>Estado de las APIs de IA Locales</h2>
    <div id="apis-list">Detectando ecosistema...</div>
    
    <hr style="border-color: #30363d; margin: 20px 0;">
    
    <h3>Probar Modelo de Formato Local</h3>
    <textarea id="inputText" style="width:100%; height:70px; background:#0d1117; color:#fff; border:1px solid #30363d; border-radius:6px; padding:10px; box-sizing:border-box; resize:none;">JavaScript es un lenguaje de programación interpretado, dialecto de la especificación ECMAScript. Se define como orientado a objetos, basado en prototipos, imperativo, débilmente tipado y dinámico.</textarea>
    <br><br>
    <button id="btnPrompt" onclick="probarPrompt()" disabled>Ejecutar Prompt Completo</button>
    <button id="btnSummarize" onclick="probarSummarizer()" disabled>Ejecutar Resumen (Summarizer)</button>
    
    <h3>Output del Modelo:</h3>
    <pre id="output">Esperando acción...</pre>
</div>

<script>
    const output = document.getElementById('output');
    const apisList = document.getElementById('apis-list');
    const btnPrompt = document.getElementById('btnPrompt');
    const btnSummarize = document.getElementById('btnSummarize');
    let promptMethod = null;

    function ejecutarDiagnostico() {
        let html = "";
        
        if (!window.ai) {
            html += "<div class='badge missing'>❌ window.ai NO DISPONIBLE</div><br>" +
                    "<p style='color:#f85149; font-size:0.9rem;'>Chrome bloquea el objeto si entras por IP. <strong>Usa estrictamente http://localhost:5500/IA.html</strong> en la barra de direcciones.</p>";
            apisList.innerHTML = html;
            return;
        }
        
        html += "<div class='badge available'>✔ window.ai inyectado en el DOM</div><br><br>";

        // Validar Prompt API (Espec nueva o vieja)
        if (window.ai.languageModel) {
            html += "• Prompt API (<code>ai.languageModel</code>): <strong style='color:#7ee787'>ACTIVA</strong><br>";
            promptMethod = 'languageModel';
            btnPrompt.disabled = false;
        } else if (window.ai.assistant) {
            html += "• Prompt API (<code>ai.assistant</code> - Legacy): <strong style='color:#7ee787'>ACTIVA</strong><br>";
            promptMethod = 'assistant';
            btnPrompt.disabled = false;
        } else {
            html += "• Prompt API (Texto general): <strong style='color:#f85149'>DESACTIVADA</strong> (Falta activar la flag <code>#prompt-api-for-gemini-nano</code>)<br>";
        }

        // Validar Summarizer API
        if (window.ai.summarizer) {
            html += "• Summarizer API (<code>ai.summarizer</code>): <strong style='color:#7ee787'>ACTIVA</strong><br>";
            btnSummarize.disabled = false;
        } else {
            html += "• Summarizer API: <strong style='color:#f85149'>DESACTIVADA</strong><br>";
        }

        apisList.innerHTML = html;
    }

    async function probarPrompt() {
        output.innerText = "Instanciando sesión de LLM y procesando...";
        try {
            const texto = document.getElementById('inputText').value;
            const session = promptMethod === 'languageModel' ? await ai.languageModel.create() : await ai.assistant.create();
            output.innerText = "Pensando...";
            const res = await session.prompt("Responde brevemente: " + texto);
            output.innerText = res;
            session.destroy();
        } catch(e) {
            output.innerText = "Error en Prompt API: " + e.message;
        }
    }

    async function probarSummarizer() {
        output.innerText = "Instanciando módulo de resumen nativo...";
        try {
            const texto = document.getElementById('inputText').value;
            const summarizer = await ai.summarizer.create();
            output.innerText = "Generando abstract local...";
            const res = await summarizer.summarize(texto);
            output.innerText = res;
            summarizer.destroy();
        } catch(e) {
            output.innerText = "Error en Summarizer API: " + e.message;
        }
    }

    // Retardo mínimo para asegurar la carga del objeto global de Chromium
    setTimeout(ejecutarDiagnostico, 200);
</script>
</body>
</html>
