<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>EM BREVE - Universidade Movecta</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

  body {
    font-family: 'Roboto', sans-serif;
    background-color: #ffffff;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    color: #0A0532;
    position: relative;
    overflow: hidden;
    text-align: center;
  }

  h1.title {
    font-weight: 700;
    font-size: 3rem;
    margin-bottom: 10px;
  }

  h2.subtitle {
    font-weight: 400;
    font-size: 2rem;
    margin: 20px 0;
  }

  .countdown {
    font-size: 2rem;
    background: #e1e1e1;
    padding: 20px 30px;
    border-radius: 12px;
    display: flex;
    gap: 20px;
    user-select: none;
    align-items: center;
    justify-content: center;
  }

  .countdown div {
    text-align: center;
  }

  .countdown div span {
    display: block;
    font-weight: 700;
    font-size: 3rem;
  }

  .label {
    font-size: 1rem;
    margin-top: 5px;
  }

  .logo-top-left {
    position: fixed;
    top: 20px;
    left: 20px;
    max-height: 120px;
    max-width: 120px;
    z-index: 1000;
  }

  @media (max-width: 600px) {
    h1.title {
      font-size: 2.5rem;
    }
    h2.subtitle {
      font-size: 1.5rem;
    }
    .countdown {
      font-size: 1.5rem;
      padding: 15px;
      gap: 10px;
      flex-wrap: wrap;
    }
    .countdown div span {
      font-size: 2.5rem;
    }
    .logo-top-left {
      max-height: 80px;
      max-width: 80px;
      top: 10px;
      left: 10px;
    }
  }
</style>
</head>
<body>
  <img src="https://raw.githubusercontent.com/AninhaaCarol/UniversidadeMovecta/refs/heads/main/4.png" alt="Logo Universidade Movecta" class="logo-top-left" />
  <h1 class="title">EM BREVE</h1>

  <div class="countdown" aria-label="Contagem regressiva para lançamento da Universidade Movecta" aria-live="polite">
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

  <h2 class="subtitle">Movimento que conecta</h2>

  <script>
    const targetDate = new Date(new Date().getFullYear(), 5, 1, 0, 0, 0); // 1 de junho

    function updateCountdown() {
      const now = new Date();
      const diff = targetDate - now;

      if (diff <= 0) {
        ['days', 'hours', 'minutes', 'seconds'].forEach(id => {
          document.getElementById(id).textContent = "00";
        });
        clearInterval(timerInterval);
        return;
      }

      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((diff % (1000 * 60)) / 1000);

      document.getElementById('days').textContent = String(days).padStart(2, '0');
      document.getElementById('hours').textContent = String(hours).padStart(2, '0');
      document.getElementById('minutes').textContent = String(minutes).padStart(2, '0');
      document.getElementById('seconds').textContent = String(seconds).padStart(2, '0');
    }

    updateCountdown();
    const timerInterval = setInterval(updateCountdown, 1000);
  </script>
</body>
</html>
