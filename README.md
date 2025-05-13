<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Universidade Movecta</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
  body {
    font-family: 'Roboto', sans-serif;
    background-color: #f5f5f5;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    color: #0A0532;
  }
  h1 {
    font-weight: 700;
    font-size: 3rem;
    margin-bottom: 40px;
  }
  .countdown {
    font-size: 2.5rem;
    background: #e1e1e1;
    padding: 25px 40px;
    border-radius: 12px;
    display: flex;
    gap: 30px;
    user-select: none;
  }
  .countdown div {
    text-align: center;
  }
  .countdown div span {
    display: block;
    font-weight: 700;
    font-size: 4rem;
  }
  .label {
    font-size: 1rem;
    margin-top: 5px;
  }
  @media (max-width: 600px) {
    h1 {
      font-size: 2.2rem;
      margin-bottom: 30px;
      text-align: center;
      padding: 0 15px;
    }
    .countdown {
      font-size: 1.8rem;
      padding: 20px;
      gap: 15px;
      flex-wrap: wrap;
      justify-content: center;
    }
    .countdown div span {
      font-size: 3rem;
    }
  }
</style>
</head>
<body>
  <h1>Está chegando!</h1>
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

