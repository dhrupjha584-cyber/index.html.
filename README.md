<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Khushi ❤️</title>
    <style>
        body { background: #ffccd5; display: flex; flex-direction: column; align-items: center; justify-content: center; height: 100vh; font-family: 'Poppins', sans-serif; margin: 0; overflow: hidden; }
        .container { text-align: center; background: rgba(255, 255, 255, 0.9); padding: 40px; border-radius: 30px; box-shadow: 0 15px 35px rgba(255, 77, 109, 0.3); z-index: 10; border: 2px solid #ff4d6d; }
        h1 { color: #ff4d6d; font-size: 2rem; margin-bottom: 20px; }
        .buttons { margin-top: 20px; position: relative; height: 60px; width: 100%; display: flex; justify-content: center; gap: 20px; }
        button { padding: 12px 25px; font-size: 1.2rem; border: none; border-radius: 50px; cursor: pointer; transition: 0.3s; font-weight: bold; }
        #yesBtn { background-color: #ff4d6d; color: white; box-shadow: 0 5px 15px rgba(255, 77, 109, 0.4); }
        #noBtn { background-color: #6c757d; color: white; position: absolute; }
        #success { display: none; }
        .floating-heart { position: absolute; color: #ff4d6d; animation: float 4s linear infinite; font-size: 20px; pointer-events: none; }
        @keyframes float { 0% { transform: translateY(100vh) rotate(0deg); opacity: 1; } 100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; } }
    </style>
</head>
<body>

    <div class="container" id="quiz">
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpwaG5yZzB6Z3R6bm1qZ3R6bm1qZ3R6bm1qZ3R6bm1qZ3R6JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/K676fG87bV1L3yS5j8/giphy.gif" width="150">
        <h1>Khushi, will you be my Valentine? ❤️</h1>
        <div class="buttons">
            <button id="yesBtn" onclick="celebrate()">Yes!</button>
            <button id="noBtn" onmouseover="moveButton()">No</button>
        </div>
    </div>

    <div class="container" id="success">
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOXpwaG5yZzB6Z3R6bm1qZ3R6bm1qZ3R6bm1qZ3R6bm1qZ3R6JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/v3p3CtSrNYNLa/giphy.gif" width="150">
        <h1>I knew it! ❤️ I Love You, Khushi! ✨</h1>
    </div>

    <script>
        function moveButton() {
            const btn = document.getElementById('noBtn');
            const x = Math.random() * (window.innerWidth - 150);
            const y = Math.random() * (window.innerHeight - 100);
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
        }

        function celebrate() {
            document.getElementById('quiz').style.display = 'none';
            document.getElementById('success').style.display = 'block';
            setInterval(createHeart, 200);
        }

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('floating-heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
            heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 4000);
        }
    </script>
</body>
</html>
