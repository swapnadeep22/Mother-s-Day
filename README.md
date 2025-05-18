<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8" />
  <title>শুভ মাতৃদিবস!</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Hind+Siliguri&family=Great+Vibes&display=swap');

    body {
      margin: 0;
      background: linear-gradient(135deg, #ffe0e9, #ffbad2);
      height: 100vh;
      overflow: hidden;
      font-family: 'Hind Siliguri', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      color: #b0003a;
      position: relative;
      text-align: center;
      padding: 20px;
    }

    h1 {
      font-family: 'Great Vibes', cursive;
      font-size: 4rem;
      margin-bottom: 0;
      text-shadow: 2px 2px 6px #ff4d6d;
    }

    p {
      font-size: 1.5rem;
      margin-top: 5px;
      margin-bottom: 40px;
      font-weight: 600;
    }

    button {
      background: #ff4d6d;
      border: none;
      padding: 15px 30px;
      font-size: 1.2rem;
      color: white;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(255, 77, 109, 0.5);
      transition: background 0.3s ease;
    }

    button:hover {
      background: #ff2e52;
    }

    .quote {
      margin-top: 30px;
      font-style: italic;
      font-size: 1.4rem;
      max-width: 600px;
      line-height: 1.4;
      opacity: 0;
      transition: opacity 0.5s ease;
      user-select: none;
    }

    .quote.show {
      opacity: 1;
    }

    .heart {
      position: fixed;
      bottom: -50px;
      width: 20px;
      height: 20px;
      background: #ff4d6d;
      transform: rotate(45deg);
      animation: floatUp 6s linear infinite;
      opacity: 0.8;
      z-index: 1;
    }

    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background: #ff4d6d;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      left: 10px;
      top: 0;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) rotate(45deg);
        opacity: 0.8;
      }
      100% {
        transform: translateY(-700px) rotate(45deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <h1>শুভ মাতৃদিবস!</h1>
  <p>সর্বশ্রেষ্ঠ মায়ের প্রতি ভালোবাসা ও কৃতজ্ঞতা 💖</p>
  <button id="showQuoteBtn">বিশেষ একটি উক্তি দেখুন</button>

  <div class="quote" id="quote"></div>

  <script>
    const quotes = [
      "মায়ের ভালোবাসা হল পরিবারের হৃদয়।",
      "জীবন কোন ম্যানুয়াল নিয়ে আসে না, এটি মায়ের ভালোবাসা নিয়ে আসে।",
      "আমি যা কিছু, বা হতে চাই, সবই owe করি আমার মায়ের কাছে।",
      "মা, তুমি আমার প্রথম বন্ধু, সেরা বন্ধু, এবং চিরকালীন বন্ধু।",
      "মায়ের আলিঙ্গন অনেকক্ষণ পর্যন্ত থাকে, তার পরও সে ছেড়ে দেয়।"
    ];

    const button = document.getElementById('showQuoteBtn');
    const quoteDiv = document.getElementById('quote');

    button.addEventListener('click', () => {
      const randomQuote = quotes[Math.floor(Math.random() * quotes.length)];
      quoteDiv.textContent = randomQuote;
      quoteDiv.classList.add('show');
    });

    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * window.innerWidth + 'px';
      heart.style.animationDuration = 4 + Math.random() * 3 + 's';
      heart.style.opacity = Math.random();
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 7000);
    }

    setInterval(createHeart, 300);
  </script>
</body>
</html>
