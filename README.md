<!-- ... até à parte do <div class="countdown" ... permanece igual -->

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

<!-- ... logo-bottom permanece igual -->

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
    document.getElementById('minutes').textContent = String(minutes).
