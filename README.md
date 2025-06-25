<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Свадьба Олега и Марины</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Playfair Display', serif;
      margin: 0;
      background-color: #fdfdfd;
      color: #1c1c1c;
    }
    header {
      padding: 60px 20px;
      text-align: center;
      border-bottom: 2px solid gold;
    }
    header h1 {
      font-size: 3em;
      color: #000;
      margin: 0;
    }
    header p {
      font-size: 1.2em;
      color: #555;
    }
    section {
      padding: 40px 20px;
      max-width: 900px;
      margin: auto;
    }
    h2 {
      color: #000;
      border-bottom: 1px solid gold;
      padding-bottom: 10px;
    }
    .countdown {
      font-size: 2em;
      color: gold;
      text-align: center;
    }
    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
    }
    .gallery img {
      width: 100%;
      max-width: 300px;
      border: 2px solid #ddd;
      border-radius: 8px;
    }
    .rsvp-form {
      margin-top: 20px;
    }
    .rsvp-form input, .rsvp-form button {
      padding: 10px;
      margin-top: 10px;
      font-size: 1em;
    }
    footer {
      text-align: center;
      padding: 20px;
      color: #999;
    }
    .leaves {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image: url('https://www.transparenttextures.com/patterns/green-gobbler.png');
      opacity: 0.03;
      z-index: -1;
    }
  </style>
</head>
<body>
<div class="leaves"></div>

<header>
  <h1>Олег & Марина</h1>
  <p>С радостью приглашаем вас на нашу свадьбу!</p>
</header>

<section>
  <h2>Дата и место</h2>
  <p>📅 4 октября 2025 года</p>
  <p>📍 Улица Заводская 1В, станица Гривенская</p>
</section>

<section>
  <h2>Программа дня</h2>
  <ul>
    <li>17:00 — Выкуп невесты</li>
    <li>18:00 — Сбор гостей, приветствие, фотосессия</li>
    <li>18:30 — Регистрация</li>
    <li>19:00 — Веселые конкурсы и танцы</li>
    <li>23:00 — Торт</li>
    <li>01:00 — Окончание вечера</li>
  </ul>
</section>

<section>
  <h2>До свадьбы осталось:</h2>
  <div class="countdown" id="countdown"></div>
</section>

<section>
  <h2>Галерея</h2>
  <div class="gallery">
    <img src="photo_1.jpeg" alt="Фото 1">
    <img src="photo_2.jpeg" alt="Фото 2">
    <img src="photo_3.jpeg" alt="Фото 3">
    <img src="photo_4.jpeg" alt="Фото 4">
  </div>
</section>

<section>
  <h2>Подтвердите участие</h2>
  <form class="rsvp-form">
    <input type="text" placeholder="Ваше имя" required><br>
    <button type="submit">Я приду!</button>
  </form>
</section>

<footer>
  © 2025 Олег & Марина
</footer>

<audio autoplay loop>
  <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mp3">
</audio>

<script>
  // Счётчик
  const countDownDate = new Date("Oct 4, 2025 00:00:00").getTime();
  const countdown = document.getElementById("countdown");

  const x = setInterval(function() {
    const now = new Date().getTime();
    const distance = countDownDate - now;

    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

    countdown.innerHTML = days + "д " + hours + "ч " + minutes + "м " + seconds + "с ";

    if (distance < 0) {
      clearInterval(x);
      countdown.innerHTML = "Сегодня свадьба!";
    }
  }, 1000);
</script>

</body>
</html>

      

      
