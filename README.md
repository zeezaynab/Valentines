<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Quicksand:wght@500&display=swap" rel="stylesheet">
    <style>
        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #f3e1e1;
            font-family: 'Quicksand', sans-serif;
        }

        .container {
            background: #f5d7d7;
            padding: 2rem 4rem;
            border-radius: 30px;
            box-shadow: 0 0 20px rgba(195, 145, 145, 0.3);
            width: 600px;
            text-align: center;
            position: relative;
        }

        .gif-container {
            margin: -20px auto 20px;
            width: 300px;
            height: 300px;
            overflow: hidden;
            border-radius: 15px;
        }

        #mainGif {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        h1 {
            color: #4a4a4a;
            font-family: 'Playfair Display', serif;
            font-size: 2.2em;
            margin: 0 0 1.5rem 0;
            font-weight: 600;
        }

        #newText {
            color: #5e3a3a;
            font-size: 2em;
            margin: 1rem 0;
            display: none;
            font-family: 'Playfair Display', serif;
        }

        .buttons {
            display: flex;
            gap: 2rem;
            justify-content: center;
            margin-top: 1rem;
        }

        .btn {
            border: none;
            padding: 1.2rem 2.5rem;
            border-radius: 50px;
            font-family: 'Quicksand', sans-serif;
            font-size: 1.2em;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        #yesBtn {
            background: #d88d9d;
            color: #ffffff;
        }

        #noBtn {
            background: #b87a87;
            color: #ffffff;
        }

        #responseMessage {
            color: #6b4b4b;
            font-size: 1.4em;
            margin: 1.5rem 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="gif-container">
            <img id="mainGif" src="images/askingOut.gif" alt="Valentine's GIF">
        </div>
        <h1 id="mainQuestion">Will You Be My Valentine?</h1>
        <div id="newText">Yay omw to hug you! 🏃♀️💨</div>
        <div class="buttons">
            <button class="btn" id="yesBtn">YES</button>
            <button class="btn" id="noBtn">NO</button>
        </div>
        <div id="responseMessage"></div>
    </div>

    <script>
        const yesBtn = document.getElementById('yesBtn');
        const noBtn = document.getElementById('noBtn');
        const responseMessage = document.getElementById('responseMessage');
        const mainGif = document.getElementById('mainGif');
        const mainQuestion = document.getElementById('mainQuestion');
        const newText = document.getElementById('newText');

        // GIF configuration
        const gifs = {
            initial: "images/askingOut.gif",
            please: "images/please2.gif",
            yay: "images/yay-Copy.gif"
        };

        // Initialize with first GIF
        mainGif.src = gifs.initial;

        yesBtn.addEventListener('click', () => {
            mainGif.src = gifs.yay;
            mainQuestion.style.display = 'none';
            newText.style.display = 'block';
            document.querySelector('.buttons').style.display = 'none';
            responseMessage.innerHTML = '';
        });

        noBtn.addEventListener('mouseover', () => {
            mainGif.src = gifs.please;
            const randomX = Math.random() * 200 - 100;
            const randomY = Math.random() * 200 - 100;
            noBtn.style.transform = `translate(${randomX}px, ${randomY}px)`;
        });

        noBtn.addEventListener('mouseout', () => {
            mainGif.src = gifs.initial;
        });

        noBtn.addEventListener('click', () => {
            responseMessage.innerHTML = 'pookie please🥺';
        });
    </script>
</body>
</html>
