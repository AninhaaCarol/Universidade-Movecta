<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title> Vem aí! </title>
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
  }
  h1.title {
    font-weight: 700;
    font-size: 4rem; /* Tamanho do título */
    margin-bottom: 10px;
  }
  h2.subtitle {
    font-weight: 400;
    font-size: 2.5rem; /* Tamanho do subtítulo */
    margin-bottom: 40px;
  }
  .countdown {
    font-size: 3rem; /* Aumentado o tamanho do relógio */
    background: #e1e1e1;
    padding: 25px 40px;
    border-radius: 12px;
    display: flex;
    gap: 30px;
    user-select: none;
    align-items: center;
  }
  .countdown div {
    text-align: center;
  }
  .countdown div span {
    display: block;
    font-weight: 700;
    font-size: 5rem; /* Aumentado o tamanho dos números */
  }
  .label {
    font-size: 1rem;
    margin-top: 5px;
  }
  .logo-top-right {
    position: fixed;
    top: 20px;
    right: 20px;
    max-height: 100px; /* maior tamanho */
    max-width: 250px;  /* maior largura */
    z-index: 1000;
  }
  .logo-bottom {
    margin-top: 40px;
    width: calc(40px * 5 + 30px * 4 + 80px); /* Mesma largura do relógio aproximada */
    max-width: 600px;
    height: auto;
    object-fit: contain;
  }
  @media (max-width: 600px) {
    h1.title {
      font-size: 3rem; /* Ajuste para telas menores */
      margin-bottom: 10px;
      text-align: center;
      padding: 0 15px;
    }
    h2.subtitle {
      font-size: 2rem; /* Ajuste para telas menores */
      margin-bottom: 30px;
    }
    .countdown {
      font-size: 2.5rem; /* Ajuste para telas menores */
      padding: 20px;
      gap: 15px;
      flex-wrap: wrap;
      justify-content: center;
    }
    .countdown div span {
      font-size: 4rem; /* Ajuste para telas menores */
    }
    .logo-top-right {
      max-height: 70px;
      max-width: 170px;
      top: 10px;
      right: 10px;
    }
    .logo-bottom {
      width: 90%;
      max-width: 350px;
      margin-top: 25px;
    }
  }
</style>
</head>
<body>
  <h2 class="subtitle">Universidade Movecta</h2>
  <div class="countdown" aria-label="Contagem regressiva para lançamento da Universidade Movecta">
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
    <script>
    // Configura a data alvo: 1 de junho do ano corrente às 00:00:00
    const targetDate = new Date(new Date().getFullYear(), 5, 1, 0, 0, 0); // mês 5 é junho (0-based)

    function updateCountdown() {
      const now = new Date();
      const diff = targetDate - now;

      if (diff <= 0) {
        // Se a data já passou
        document.getElementById('hours').textContent = "00";
        document.getElementById('minutes').textContent = "00";
        document.getElementById('seconds').textContent = "00";
        clearInterval(timerInterval);
        return;
      }

      const hours = Math.floor(diff / (1000 * 60 * 60));
      const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((diff % (1000 * 60)) / 1000);

      document.getElementById('hours').textContent = String(hours).padStart(2, "0");
      document.getElementById('minutes').textContent = String(minutes).padStart(2, "0");
      document.getElementById('seconds').textContent = String(seconds).padStart(2, "0");
    }

    updateCountdown();
    const timerInterval = setInterval(updateCountdown, 1000);
  </script>
</body>
</html>

