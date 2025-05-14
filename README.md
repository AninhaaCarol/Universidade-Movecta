<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Vem aí... - Universidade Movecta</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

    body {
      font-family: 'Roboto', sans-serif;
      background-color: #fff;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      text-align: center;
      color: #0A0532;
    }

    h1.title {
      font-size: 3.5rem;
      margin: 0;
      font-weight: bold;
    }

    h2.subtitle {
      font-size: 2rem;
      margin: 10px 0 40px 0;
      font-weight: 400;
    }

    .countdown {
      display: flex;
      gap: 30px;
      background: #e1e1e1;
      padding: 25px 40px;
      border-radius: 12px;
      font-size: 1.5rem;
    }

    .countdown div {
      text-align: center;
    }

    .countdown span {
      display: block;
      font-size: 4rem;
      font-weight: bold;
    }

    .slogan {
      margin-top: 30px;
      font-size: 1.5rem;
      font-weight: 500;
    }

    .logo-footer {
      margin-top: 30px;
      max-height: 80px;
      width: auto;
    }

    @media (max-width: 600px) {
      .countdown {
        flex-wrap: wrap;
        justify-content: center;
        gap: 15px;
        padding: 20px;
      }

      .countdown span {
        font-size: 3rem;
      }

      h1.title {
        font-size: 2.5rem;
      }

      h2.subtitle {
        font-size: 1.5rem;
      }
    }
  </style>
</head>
<body>
  <h1 class="title">Universidade Movecta</h1>
  <h2 class="subtitle">EM BREVE</h2>

  <div class="countdown" aria-live="polite">
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

  <p class="slogan">Movimento que conecta</p>
  <img src="logo-movecta.png" alt="Logo Universidade Movecta" class="logo-footer" />

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

      document.getElementById('days').textContent = String(days).padStart(2, "0");
      document.getElementById('hours').textContent = String(hours).padStart(2, "0");
      document.getElementById('minutes').textContent = String(minutes).padStart(2, "0");
      document.getElementById('seconds').textContent = String(seconds).padStart(2, "0");
    }

    updateCountdown();
    const timerInterval = setInterval(updateCountdown, 1000);
  </script>
</body>
</html>
