<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Фотосессия в івана Токарья</title>
  <style>
    :root {
      --main-color: #d43f57;
    }

    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #fff;
      color: #333;
      overflow-x: hidden;
    }

    header {
      position: relative;
      background: url('https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=1400&q=80') center/cover no-repeat;
      height: 70vh;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      text-shadow: 0 2px 6px rgba(0,0,0,0.7);
      font-size: 2.8rem;
      font-weight: 700;
      text-align: center;
      padding: 0 20px;
      animation: fadeInHeader 2s ease-out;
    }

    @keyframes fadeInHeader {
      0% {
        opacity: 0;
        transform: translateY(-40px);
      }
      100% {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .scroll-indicator {
      position: absolute;
      bottom: 30px;
      left: 50%;
      transform: translateX(-50%);
      text-align: center;
      color: #fff;
      font-size: 1rem;
      animation: fadeIn 2s ease 1.5s forwards;
      opacity: 0;
    }

    .scroll-indicator span {
      display: block;
      margin-bottom: 8px;
      font-weight: 500;
      letter-spacing: 1px;
      animation: pulse 2s infinite;
    }

    .arrow-down {
      width: 20px;
      height: 20px;
      border-left: 2px solid #fff;
      border-bottom: 2px solid #fff;
      transform: rotate(45deg);
      margin: 0 auto;
      animation: bounce 1.5s infinite;
    }

    @keyframes bounce {
      0%, 100% {
        transform: rotate(45deg) translateY(0);
      }
      50% {
        transform: rotate(45deg) translateY(8px);
      }
    }

    @keyframes pulse {
      0%, 100% {
        opacity: 0.8;
      }
      50% {
        opacity: 1;
      }
    }

    @keyframes fadeIn {
      to {
        opacity: 1;
      }
    }

    main {
      max-width: 700px;
      margin: 40px auto;
      padding: 0 20px;
    }

    h2 {
      text-align: center;
      margin-bottom: 20px;
      color: var(--main-color);
      opacity: 0;
      transform: translateY(30px);
      transition: all 1s ease;
    }

    p.description {
      font-size: 1.1rem;
      line-height: 1.5;
      margin-bottom: 30px;
      text-align: center;
      opacity: 0;
      transform: translateY(30px);
      transition: all 1s ease 0.3s;
    }

    .fade-in {
      opacity: 1 !important;
      transform: translateY(0) !important;
    }

    form {
      background: #f8f1f3;
      padding: 25px;
      border-radius: 8px;
      box-shadow: 0 4px 10px rgba(212, 63, 87, 0.2);
      opacity: 0;
      transform: translateY(30px);
      transition: all 1s ease 0.6s;
    }о

    label {
      display: block;
      margin-bottom: 6px;
      font-weight: 600;
    }

    input, textarea, select {
      width: 100%;
      padding: 10px;
      margin-bottom: 16px;
      border: 1px solid #d4d4d4;
      border-radius: 5px;
      font-size: 1rem;
      box-sizing: border-box;
      transition: border 0.3s;
    }

    input:focus, textarea:focus, select:focus {
      border-color: var(--main-color);
      outline: none;
    }

    button {
      background-color: var(--main-color);
      border: none;
      color: white;
      font-size: 1.2rem;
      padding: 12px 0;
      width: 100%;
      bord<img src="" alt="" title="" />er-radius: 6px;
      cursor: pointer;
      transition: background-color 0.3s ease, transform 0.3s;
    }

    button:hover {
      background-color: #b53346;
      transform: scale(1.02);
    }

    @media (max-width: 480px) {
      header {
        font-size: 1.8rem;
        height: 50vh;
      }
    }
  </style>
</head>
<body>

  <header>
    Фотосессия в Івана Токарья  — Ваш лучший момент!
    <div class="scroll-indicator">
      <span>Гортай вниз</span>
      <div class="arrow-down"></div>
    </div>
  </header>

  <main>
    <h2 id="heading">Закажите профессиональную фотосессию</h2>
    <p class="description" id="desc">
      Мы создадим для вас красивые и незабываемые фотографии, которые останутся на память навсегда.  
      Выберите удобное время и оставьте заявку — мы свяжемся с вами!
    </p>

    <form id="form" action="mailto:your-email@example.com" method="post" enctype="text/plain">
      <label for="name">Ваше имя</label>
      <input type="text" id="name" name="Имя" required />

      <label for="phone">Телефон</label>
      <input type="tel" id="phone" name="Телефон" required />

      <label for="date">Дата фотосессии</label>
      <input type="date" id="date" name="Дата" required />

      <label for="time">Время</label>
      <select id="time" name="Время" required>
        <option value="">Выберите время</option>
        <option>10:00 - 12:00</option>
        <option>13:00 - 15:00</option>
        <option>16:00 - 18:00</option>
      </select>

      <label for="comments">Комментарий (необязательно)</label>
      <textarea id="comments" name="Комментарий" rows="3"></textarea>

      <button type="submit">Отправить заявку</button>
    </form>
  </main>

  <script>
    // Плавное появление блоков при прокрутке
    window.addEventListener('scroll', () => {
      const heading = document.getElementById('heading');
      const desc = document.getElementById('desc');
      const form = document.getElementById('form');
      const scrollY = window.scrollY + window.innerHeight;

      if (scrollY > heading.offsetTop + 50) {
        heading.classList.add('fade-in');
      }
      if (scrollY > desc.offsetTop + 50) {
        desc.classList.add('fade-in');
      }
      if (scrollY > form.offsetTop + 50) {
        form.classList.add('fade-in');
      }
    });
  </script>

</body>
</html>
