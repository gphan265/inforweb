<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Editor de HTML y CSS</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #1e1e1e; /* Fondo negro */
            margin: 0;
            padding: 20px;
            color: #f4f4f4; /* Texto claro */
        }
        h1 {
            text-align: center;
            color: #4CAF50; /* Color verde para el título */
        }
        p {
            text-align: center;
            margin-bottom: 20px;
        }
        form {
            background: #2a2a2a; /* Fondo gris oscuro para el formulario */
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
            margin-bottom: 20px;
        }
        label {
            font-weight: bold;
            margin-top: 10px;
            display: block;
            color: #f4f4f4; /* Texto claro para las etiquetas */
        }
        textarea {
            width: 100%;
            height: 150px;
            padding: 10px;
            border: 1px solid #444; /* Borde gris oscuro */
            border-radius: 4px;
            resize: vertical;
            margin-bottom: 10px;
            font-family: monospace;
            background-color: #333; /* Fondo oscuro para el textarea */
            color: #f4f4f4; /* Texto claro en el textarea */
        }
        button {
            background-color: #4CAF50; /* Color verde para el botón */
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #45a049; /* Color verde más oscuro al pasar el mouse */
        }
        h2 {
            margin-top: 20px;
            text-align: center;
            color: #f4f4f4; /* Texto claro para el subtítulo */
        }
        iframe {
            width: 100%;
            height: 300px;
            border: 1px solid #444; /* Borde gris oscuro */
            border-radius: 4px;
            background-color: #fff; /* Fondo blanco para el iframe */
        }
    </style>
</head>
<body>

<h1>Editor de HTML y CSS</h1>
<p>Introduce tu código HTML y CSS a continuación:</p>

<form id="codeForm">
    <label for="htmlCode">Código HTML:</label>
    <textarea id="htmlCode" placeholder="Escribe tu código HTML aquí..."></textarea>
    
    <label for="cssCode">Código CSS:</label>
    <textarea id="cssCode" placeholder="Escribe tu código CSS aquí..."></textarea>
    
    <button type="submit">Ejecutar</button>
</form>

<h2>Resultado:</h2>
<iframe id="resultFrame"></iframe>

<script>
    document.getElementById('codeForm').addEventListener('submit', function(event) {
        event.preventDefault(); // Evita que el formulario se envíe de la manera tradicional

        const htmlCode = document.getElementById('htmlCode').value;
        const cssCode = document.getElementById('cssCode').value;

        const resultFrame = document.getElementById('resultFrame');
        const resultDocument = resultFrame.contentDocument || resultFrame.contentWindow.document;

        // Escribe el código HTML y CSS en el iframe
        resultDocument.open();
        resultDocument.write(`
            <html>
                <head>
                    <style>${cssCode}</style>
                </head>
                <body>${htmlCode}</body>
            </html>
        `);
        resultDocument.close();
    });
</script>

</body>
</html>
