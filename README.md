<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>EM BREVE - Universidade Movecta</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
  body {
    font-family: 'Roboto', sans-serif;
    background-color: #ffffff; /* Fundo totalmente branco */
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    color: #0A0532;
    position: relative;
    overflow: hidden; /* Para evitar scroll indesejado */
  }
  h1.title {
    font-weight: 700;
    font-size: 3rem; /* Ajustado o tamanho do título */
    margin-bottom: 10px;
  }
  h2.subtitle {
    font-weight: 400;
    font-size: 2rem; /* Tamanho do subtítulo */
    margin-bottom: 20px;
  }
  .countdown {
    font-size: 2rem; /* Ajustado o tamanho do relógio */
    background: #e1e1e1;
    padding: 20px 30px;
    border-radius: 12px;
    display: flex;
    gap: 20px;
    user-select: none;
    align-items: center;
  }
  .countdown div {
    text-align: center;
  }
  .countdown div span {
    display: block;
    font-weight: 700;
    font-size: 3rem; /* Ajustado o tamanho dos números */
  }
  .label {
    font-size: 1rem;
    margin-top: 5px;
  }
  .logo-top-left {
    position: fixed;
    top: 20px;
    left: 20px;
    max-height: 120px; /* Aumentado o tamanho */
    max-width: 250px;  /* Aumentado a largura */
    z-index: 1000;
  }
  .logo-bottom {
    margin-top: 10px; /* Subindo a imagem para mais perto do texto */
    width: calc(40px * 5 + 30px * 4 + 80px); /* Mesma largura do relógio aproximada */
    max-width: 600px;
    height: auto;
    object-fit: contain;
  }
  @media (max-width: 600px) {
    h1.title {
      font-size: 2.5rem; /* Ajuste para telas menores */
      margin-bottom: 10px;
      text-align: center;
      padding: 0 15px;
    }
    h2.subtitle {
      font-size: 1.5rem; /* Ajuste para telas menores */
      margin-bottom: 20px;
    }
    .countdown {
      font-size: 1.5rem; /* Ajuste para telas menores */
      padding: 15px;
      gap: 10px;
      flex-wrap: wrap;
      justify-content: center;
    }
    .countdown div span {
      font-size: 2.5rem; /* Ajuste para telas menores */
    }
    .logo-top-left {
      max-height: 80px;
      max-width: 170px;
      top: 10px;
      left: 10px;
    }
    .logo-bottom {
      width: 90%;
      max-width: 350px;
      margin-top: 10px; /* Ajuste para telas menores */
    }
  }
</style>
</head>
<body>
  <img src="https://raw.githubusercontent.com/AninhaaCarol/UniversidadeMovecta/refs/heads/main/4.png" alt="Logo Universidade Movecta" class="logo-top-left" />
  <h1 class="title">EM BREVE</h1>
  <div class="countdown" aria-label="Contagem regressiva para lançamento da Universidade Movecta">
    <div>
      <span id="days">00</span>
      <div class="label">Dias</div>
    </div>
    <div>
      <span id="hours">00</span>
      <div class="label">Horas</div>
    </div>
    <div>
      <span id="minutes">00</span>
      <div class="label">Minutos</div>
    </div>
    <div>
      <span id="seconds">00</span>
      <div class="label">Segundos</div>
    </div>
  </div>
  <h2 class="subtitle">Movimento que conecta</h
