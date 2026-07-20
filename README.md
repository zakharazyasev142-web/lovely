[Для моего Ангелочка.html](https://github.com/user-attachments/files/30205394/default.html)
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Для моего Ангелочка ❤️</title>
    <!-- Подключаем красивые шрифты -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@700&family=Montserrat:wght@400;600;700&display=swap" rel="stylesheet">
    
    <style>
        /* БАЗОВЫЕ НАСТРОЙКИ */
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { font-family: 'Montserrat', sans-serif; background: linear-gradient(135deg, #ffeef2 0%, #ffd6e0 100%); display: flex; justify-content: center; align-items: center; min-height: 100vh; overflow-x: hidden; padding: 20px; }
        .main-container { width: 100%; display: flex; justify-content: center; align-items: center; position: relative; }
        .screen { background: rgba(255, 255, 255, 0.85); backdrop-filter: blur(10px); padding: 35px 25px; border-radius: 30px; box-shadow: 0 20px 40px rgba(255, 105, 180, 0.15), inset 0 0 0 2px rgba(255, 255, 255, 0.6); max-width: 430px; width: 100%; text-align: center; transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1); position: absolute; border: 1px solid rgba(255, 182, 193, 0.5); z-index: 1; }
        .hidden { display: none !important; opacity: 0; transform: scale(0.9) translateY(20px); z-index: 0; }
        h2 { color: #d6336c; font-size: 24px; font-weight: 700; margin-bottom: 25px; line-height: 1.4; text-shadow: 1px 1px 0px rgba(255,255,255,0.8); }

        /* АНИМАЦИЯ СЕРДЕЧЕК */
        .gif-container { position: relative; height: 160px; margin-bottom: 25px; display: flex; justify-content: center; align-items: center; }
        .gif-container img { max-height: 100%; z-index: 2; }
        .hearts-emitter { position: absolute; width: 100%; height: 100%; top: 0; left: 0; pointer-events: none; z-index: 1; }
        .floating-heart { position: absolute; color: #ff4d6d; font-size: 20px; bottom: 20px; opacity: 0; animation: floatUp 2.5s ease-in-out infinite; }
        @keyframes floatUp { 0% { transform: translateY(0) scale(0.5) rotate(0deg); opacity: 0; } 20% { opacity: 0.8; } 80% { opacity: 0.8; } 100% { transform: translateY(-120px) scale(1.2) rotate(30deg); opacity: 0; } }

        /* КНОПКИ */
        button { padding: 14px 35px; font-size: 18px; font-weight: 700; border: none; border-radius: 50px; cursor: pointer; box-shadow: 0 8px 15px rgba(0,0,0,0.07); transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        button:active { transform: scale(0.95); }
        .btn-wrapper { display: flex; justify-content: center; gap: 20px; height: 90px; align-items: center; position: relative; }
        #yesBtn { background: linear-gradient(135deg, #42e695 0%, #3bb2b8 100%); color: white; z-index: 10; }
        #yesBtn:hover { box-shadow: 0 10px 20px rgba(66, 230, 149, 0.3); }
        #noBtn { background: linear-gradient(135deg, #ff4b2b 0%, #ff416c 100%); color: white; position: relative; }

        /* ПОДАРКИ */
        .gifts-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin-top: 15px; }
        .gift-card { background: linear-gradient(145deg, #ffffff, #fff0f3); padding: 20px 15px; border-radius: 22px; border: 2px dashed #ffb3c1; cursor: pointer; box-shadow: 0 10px 20px rgba(255, 182, 193, 0.2); transition: all 0.3s ease; display: flex; flex-direction: column; align-items: center; }
        .gift-card:hover { transform: translateY(-5px); border-color: #ff4d6d; background: linear-gradient(145deg, #fff0f3, #ffe3e8); box-shadow: 0 15px 25px rgba(255, 77, 109, 0.25); }
        .gift-card.full-width { grid-column: span 2; flex-direction: row; justify-content: center; gap: 15px; padding: 15px; }
        .gift-card img { width: 65px; height: 65px; filter: drop-shadow(0 4px 8px rgba(255, 77, 109, 0.2)); transition: transform 0.3s ease; }
        .gift-card:hover img { transform: scale(1.1) rotate(5deg); }
        .gift-label { font-size: 15px; color: #ff4d6d; font-weight: 700; margin-top: 10px; letter-spacing: 0.5px; }
        .gift-card.full-width .gift-label { margin-top: 0; }
        .back-btn-wrapper { margin-top: 30px; }
        .back-btn { background: linear-gradient(135deg, #ff85a2 0%, #ff4d6d 100%); color: white; padding: 12px 40px; font-size: 15px; border-radius: 50px; }
        .back-btn:hover { box-shadow: 0 8px 20px rgba(255, 77, 109, 0.4); transform: translateY(-2px); }

        /* ПЛЕЕР */
        .player-container { background: linear-gradient(180deg, #fff5f7 0%, #ffffff 100%); padding: 10px; border-radius: 24px; }
        .vinyl-record { width: 180px; height: 180px; background: radial-gradient(circle, #2c2c2c 20%, #1a1a1a 40%, #2c2c2c 50%, #111 60%, #222 70%); border-radius: 50%; margin: 0 auto 30px auto; position: relative; box-shadow: 0 15px 35px rgba(0,0,0,0.4), inset 0 0 10px rgba(255,255,255,0.2); animation: spin 4s linear infinite paused; }
        .vinyl-record::before { content: ''; position: absolute; top: 0; left: 0; right: 0; bottom: 0; border-radius: 50%; background: radial-gradient(transparent 35%, rgba(255,255,255,0.05) 40%, transparent 45%, rgba(255,255,255,0.05) 60%, transparent 70%); }
        .vinyl-record.playing { animation-play-state: running; }
        .vinyl-record .vinyl-center { width: 60px; height: 60px; background: linear-gradient(135deg, #ffb6c1, #ff85a2); border-radius: 50%; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); display: flex; justify-content: center; align-items: center; color: white; font-size: 10px; font-weight: 700; border: 3px solid #1a1a1a; box-shadow: 0 0 5px rgba(0,0,0,0.2); text-shadow: 0 1px 2px rgba(0,0,0,0.2); }
        audio { width: 100%; margin-top: 10px; border-radius: 50px; background-color: #fff0f3; }

        /* ПИСЬМО */
        .letter-screen { background-image: url('https://cdn-icons-png.flaticon.com/512/3596/3596000.png'), url('https://cdn-icons-png.flaticon.com/512/3596/3596000.png'), url('https://cdn-icons-png.flaticon.com/512/3596/3596000.png'); background-position: 8% 12%, 88% 30%, 25% 88%; background-size: 70px, 90px, 60px; background-repeat: no-repeat; max-width: 460px; background-color: #fff; }
        .letter-content { background: rgba(255, 255, 255, 0.95); padding: 25px 20px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.05); border: 1px solid #ffe3e8; position: relative; }
        .letter-heading { font-family: 'Caveat', cursive; font-size: 36px; color: #d6336c; margin-bottom: 15px; }
        .letter-text { font-size: 16px; line-height: 1.7; color: #4f4f4f; text-align: justify; font-weight: 500; }

        /* ЕДИНСТВЕННОЕ ВОСПОМИНАНИЕ (image_14) */
        .single-memory-container { margin-top: 25px; display: flex; justify-content: center; }
        .polaroid-confession { background: white; padding: 15px 15px 35px 15px; box-shadow: 0 15px 35px rgba(0,0,0,0.18); border-radius: 4px; border: 1px solid #eee; transform: rotate(-1deg); width: 100%; max-width: 400px; transition: all 0.3s ease; }
        .polaroid-confession:hover { transform: rotate(0deg) scale(1.02); box-shadow: 0 20px 45px rgba(255, 77, 109, 0.25); }
        .polaroid-confession img { width: 100%; height: auto; object-fit: contain; border-radius: 2px; border: 1px solid #f0f0f0; }
        .polaroid-caption { font-family: 'Caveat', cursive; font-size: 24px; color: #d6336c; margin-top: 20px; font-weight: 700; letter-spacing: 1px; }

        @keyframes spin { 100% { transform: rotate(360deg); } }
    </style>
</head>
<body>

<div class="main-container">

    <!-- ЭКРАН 1: ВОПРОС -->
    <div class="screen" id="screen1">
        <div class="gif-container">
            <div class="hearts-emitter" id="emitter1"></div>
            <img id="mainGif" img src="https://media1.tenor.com/m/0J8H1cBCnYsAAAAC/%D8%A8%D9%88%D8%B3%D9%87-%D9%85%D8%B3%D8%A7%D8%A1-%D8%A7%D9%84%D9%88%D8%B1%D8%AF.gif" alt="Анимированный кот" width="300">
        </div>
        <h2 id="questionText">Ты меня любишь, Ангелок? ❤️</h2>
        <div class="btn-wrapper">
            <button id="yesBtn">ДА</button>
            <button id="noBtn">НЕТ</button>
        </div>
    </div>

    <!-- ЭКРАН 2: ВЫБОР ПОДАРКА (image_10) -->
    <div class="screen hidden" id="screen2">
        <div class="gif-container">
            <div class="hearts-emitter" id="emitter2"></div>
            <img src="https://media.tenor.com/le2ex44ur5sAAAAi/mochi-mochi-peach-cat-cat.gif" alt="Happy Cat">
        </div>
        <h2>Тогда выбирай подарок, Ангелок 🥰</h2>
        <div class="gifts-grid">
            <div class="gift-card" onclick="openGift('music')">
                <img src="https://cdn-icons-png.flaticon.com/512/4213/4213958.png" alt="Music Gift">
                <div class="gift-label">МУЗЫКА</div>
            </div>
            <div class="gift-card" onclick="openGift('letter')">
                <img src="https://cdn-icons-png.flaticon.com/512/4213/4213958.png" alt="Letter Gift">
                <div class="gift-label">ПИСЬМО</div>
            </div>
            <div class="gift-card full-width" onclick="openGift('memories')">
                <img src="https://cdn-icons-png.flaticon.com/512/4213/4213958.png" alt="Confession Gift">
                <div class="gift-label">ТОТ САМЫЙ ДЕНЬ</div>
            </div>
        </div>
    </div>

    <!-- ЭКРАН 3: МУЗЫКАЛЬНЫЙ ПЛЕЕР -->
    <div class="screen hidden" id="screenMusic">
        <div class="player-container">
            <!-- Название песни обновлено -->
            <div class="song-title">Наша особенная песня:<br><strong>no cute anymore</strong> 🎧</div>
            
            <div class="vinyl-record" id="vinyl">
                <div class="vinyl-center">для Ангелка</div>
            </div>

            <!-- !!! ВСТАВЬ СЮДА ПРЯМУЮ ССЫЛКУ НА MP3 ФАЙЛ ПЕСНИ "no cute anymore" !!! -->
            <audio id="remindSong" controls>
                <source src="ССЫЛКА_НА_ВАШЕ_MP3_NO_CUTE_ANYMORE.mp3" type="audio/mpeg">
                Твой браузер не поддерживает плеер.
            </audio>

            <div class="back-btn-wrapper">
                <button class="back-btn" onclick="goBackToGifts()">НАЗАД</button>
            </div>
        </div>
    </div>

    <!-- ЭКРАН 4: ПИСЬМО -->
    <div class="screen hidden letter-screen" id="screenLetter">
        <div class="letter-content">
            <div class="letter-heading">Мой любимый Ангелок...</div>
            <div class="letter-text">
                Ты — самое лучшее, теплое и прекрасное, что случилось в моей жизни. Твоя улыбка мгновенно делает любой мой день счастливым, а твой голос — самая любимая музыка. Спасибо тебе за твою бесконечную нежность, теплоту и заботу. Я безумно счастлив быть рядом с тобой. Мое сердце бьется только для тебя! ❤️
            </div>
        </div>
        <div class="back-btn-wrapper">
            <button class="back-btn" onclick="goBackToGifts()">НАЗАД</button>
        </div>
    </div>

    <!-- ЭКРАН 5: ОДНО ВОСПОМИНАНИЕ (image_14) -->
    <div class="screen hidden memories-screen" id="screenMemories">
        <h2>Момент, когда всё началось... ✨</h2>
        
        <div class="single-memory-container">
            <div class="polaroid-confession">
                <!-- Твоя ссылка на фото уже вставлена! -->
                <img src="https://wertigo.ru/shared-files/7d17a9f0-7711-4b1f-a039-af01e33a7788.png" alt="Наше признание">
                <div class="polaroid-caption">Тот самый день. Навсегда. ❤️</div>
            </div>
        </div>

        <div class="back-btn-wrapper">
            <button class="back-btn" onclick="goBackToGifts()">НАЗАД</button>
        </div>
    </div>

</div>

<script>
    // Весь JavaScript код остался прежним
    const yesBtn = document.getElementById('yesBtn');
    const noBtn = document.getElementById('noBtn');
    const questionText = document.getElementById('questionText');
    const mainGif = document.getElementById('mainGif');
    const screens = document.querySelectorAll('.screen');
    const remindSong = document.getElementById('remindSong');
    const vinyl = document.getElementById('vinyl');

    const noPhrases = ["Ты уверена? 🥺", "Подумай еще раз... 🥺", "Ну пожалуйстааа 😜", "Пожалуйста, нажми ДА! 🧐", "Ай, ну перестань тыкать туда! 😂", "Ладно, последний шанс... 😡"];
    const sadGifs = ["https://media.tenor.com/yE7z1Asw7pUAAAAi/peach-goma-peach-and-goma.gif", "https://media.tenor.com/U0n-1q78g4sAAAAi/goma-crying.gif"];
    let noCount = 0;

    function createHeartsAnimation(emitterId) {
        const emitter = document.getElementById(emitterId);
        if (!emitter) return;
        setInterval(() => {
            const heart = document.createElement('div');
            heart.className = 'floating-heart';
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 80 + 10 + '%';
            heart.style.fontSize = Math.random() * 15 + 12 + 'px';
            heart.style.animationDelay = Math.random() * 0.5 + 's';
            emitter.appendChild(heart);
            setTimeout(() => { heart.remove(); }, 2500);
        }, 400);
    }

    createHeartsAnimation('emitter1');
    createHeartsAnimation('emitter2');

    noBtn.addEventListener('click', () => {
        noCount++;
        let phraseIndex = Math.min(noCount - 1, noPhrases.length - 1);
        questionText.innerText = noPhrases[phraseIndex];
        if (noCount <= 2) mainGif.src = sadGifs[noCount - 1];
        if (noCount >= 3) {
            let offset = noCount * 5;
            let currentYesScale = 1 + (noCount * 0.25);
            let currentNoScale = Math.max(0.1, 1 - (noCount * 0.15));
            yesBtn.style.transform = `scale(${currentYesScale})`;
            noBtn.style.transform = `translate(${offset}px, ${offset}px) scale(${currentNoScale})`;
        }
        if (noCount >= 7) noBtn.classList.add('hidden');
    });

    function showScreen(screenId) {
        screens.forEach(screen => {
            screen.classList.add('hidden');
            screen.style.position = 'absolute';
        });
        const target = document.getElementById(screenId);
        target.classList.remove('hidden');
        target.style.position = 'relative';
    }

    yesBtn.addEventListener('click', () => { showScreen('screen2'); });

    function openGift(giftType) {
        if (giftType === 'music') showScreen('screenMusic');
        else if (giftType === 'letter') showScreen('screenLetter');
        else if (giftType === 'memories') showScreen('screenMemories');
    }

    function goBackToGifts() {
        showScreen('screen2');
        if (!remindSong.paused) remindSong.pause();
    }

    remindSong.addEventListener('play', () => { vinyl.classList.add('playing'); });
    remindSong.addEventListener('pause', () => { vinyl.classList.remove('playing'); });
    remindSong.addEventListener('ended', () => { vinyl.classList.remove('playing'); });
</script>

</body>
</html>
