
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Олег & Марина | Приглашение на свадьбу</title>
  <style>
    body {
      margin: 0;
      font-family: 'Helvetica Neue', sans-serif;
      background-color: #ffffff;
      color: #2e2e2e;
    }

    header {
      background-color: #f5f5f5;
      text-align: center;
      padding: 60px 20px;
      border-bottom: 2px solid #e0e0e0;
    }

    header h1 {
      font-size: 48px;
      margin-bottom: 10px;
      color: #2e2e2e;
    }

    header p {
      font-size: 20px;
      color: #777;
    }

    section {
      padding: 40px 20px;
      max-width: 800px;
      margin: 0 auto;
    }

    .invite {
      background-color: #fdfdfd;
      border-left: 5px solid #a5c9a1;
      padding: 20px;
      font-size: 18px;
      line-height: 1.6;
      color: #333;
    }

    .date-location {
      margin-top: 30px;
      font-size: 20px;
      color: #4e7d49;
    }

    .names {
      color: #bfa06f;
      font-weight: bold;
      font-size: 24px;
      margin-top: 40px;
    }

    .timer {
      text-align: center;
      margin-top: 40px;
      font-size: 24px;
      color: #2e2e2e;
    }

    .form-section {
      background: #f9f9f9;
      padding: 30px;
      margin-top: 40px;
      border: 1px solid #ddd;
      border-radius: 8px;
    }

    .form-section input,
    .form-section textarea {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      margin-bottom: 20px;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 16px;
    }

    .form-section button {
      background-color: #4e7d49;
      color: white;
      border: none;
      padding: 10px 20px;
      font-size: 16px;
      border-radius: 4px;
      cursor: pointer;
    }

    .footer {
      text-align: center;
      padding: 30px;
      background-color: #fafafa;
      font-size: 14px;
      color: #aaa;
    }

    .music-control {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: white;
      border: 1px solid #ccc;
      border-radius: 50%;
      width: 50px;
      height: 50px;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
  </style>
</head>
<body>

<!-- Фоновая музыка -->
<audio id="bg-music" loop>
  <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mp3">
</audio>
<div class="music-control" onclick="toggleMusic()" title="Включить/выключить музыку">🎵</div>

<header>
  <h1>Олег & Марина</h1>
  <p>04 октября 2025</p>
</header>

<section>
  <div class="invite">
    <p>
      Дорогие наши друзья и родные!<br><br>
      Мы рады и счастливы пригласить вас на наше волшебное событие — день, когда две души станут единым целым! В этот особенный момент мы хотим разделить с вами нашу любовь и радость.
    </p>

    <div class="date-location">
      📅 Дата: <strong>04.10.2025</strong><br>
      ⏰ Время: <strong>17:00</strong><br>
      📍 Место: <strong>станица Гривенская, ул. Заводская 1В</strong>
    </div>

    <p style="margin-top: 30px;">
      Пусть ваши сердца наполнятся теплом, а наши счастливые улыбки станут отражением того, как важны для нас вы. Мы будем рады видеть вас в этот день, чтобы вместе создать незабываемые воспоминания и отметить начало нашего совместного пути.
    </p>

    <p class="names">
      С любовью,<br>
      Олег и Марина
    </p>
  </div>

  <!-- Таймер -->
  <div class="timer">
    До свадьбы осталось: <br>
    <span id="countdown"></span>
  </div>

  <!-- RSVP форма -->
  <div class="form-section">
    <h2>Подтверждение участия</h2>
    <form action="https://formspree.io/f/your-form-id" method="POST">
      <label for="name">Имя:</label>
      <input type="text" name="name" required />

      <label for="guests">Количество гостей:</label>
      <input type="number" name="guests" min="1" required />

      <label for="message">Пожелания / Комментарии:</label>
      <textarea name="message" rows="4"></textarea>

      <button type="submit">Отправить</button>
    </form>
  </div>
</section>

<div class="footer">
  © 2025 Олег & Марина
</div>

<!-- СКРИПТЫ -->
<script>
  // Таймер
  const countDownDate = new Date("Oct 4, 2025 17:00:00").getTime();
  const countdown = document.getElementById("countdown");
  setInterval(function() {
    const now = new Date().getTime();
    const distance = countDownDate - now;

    if (distance < 0) {
      countdown.innerHTML = "💍 Свадьба уже началась!";
      return;
    }

    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

    countdown.innerHTML = `${days}д ${hours}ч ${minutes}м ${seconds}с`;
  }, 1000);

  // Музыка
  const music = document.getElementById("bg-music");
  let isPlaying = false;

  function toggleMusic() {
    if (isPlaying) {
      music.pause();
    } else {
      music.play();
    }
    isPlaying = !isPlaying;
  }
</script>

</body>
</html>
