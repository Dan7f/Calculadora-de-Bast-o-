<!DOCTYPE html><html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculadora de Bastão</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f2f2f2;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }
    .container {
      background-color: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      width: 300px;
      text-align: center;
    }
    input[type="number"] {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      padding: 10px 20px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #0056b3;
    }
    .resultado {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Calculadora de Bastão</h2>
    <label for="pressao">Pressão desejada (bar):</label>
    <input type="number" id="pressao" step="0.1" placeholder="Digite a pressão">
    <button onclick="calcularComprimento()">Calcular</button>
    <div class="resultado" id="resultado"></div>
  </div>  <script>
    function calcularComprimento() {
      const pressao = parseFloat(document.getElementById('pressao').value);
      if (isNaN(pressao)) {
        document.getElementById('resultado').innerText = 'Por favor, insira uma pressão válida.';
        return;
      }
      const comprimento = (pressao + 9672.5) / 225;
      document.getElementById('resultado').innerText = `Comprimento do bastão: ${comprimento.toFixed(2)} mm`;
    }
  </script></body>
</html>
