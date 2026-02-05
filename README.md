# walentynka
dla bejbusia
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zostaniesz moją Walentynką?</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffe6e6; /* Jasny różowy tł */
            font-family: 'Arial', sans-serif;
            flex-direction: column;
            text-align: center;
            overflow: hidden; /* Żeby przycisk nie rozwalił strony jak urośnie */
        }
        
        h1 {
            color: #d32f2f;
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .img-container img {
            width: 200px;
            height: auto;
            border-radius: 15px;
            margin-bottom: 20px;
        }

        .buttons {
            display: flex;
            gap: 20px;
            align-items: center;
        }

        button {
            padding: 15px 30px;
            font-size: 1.2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        #yesBtn {
            background-color: #4CAF50; /* Zielony */
            color: white;
            font-weight: bold;
        }

        #noBtn {
            background-color: #f44336; /* Czerwony */
            color: white;
        }

        /* Ukryta sekcja na start */
        #success-screen {
            display: none;
        }
    </style>
</head>
<body>

    <div id="question-screen">
        <div class="img-container">
            <img id="main-img" src="https://media.tenor.com/f_rWjZ5dZ4oAAAAi/cute-bear.gif" alt="Cute bear">
        </div>
        <h1>Zostaniesz moją Walentynką? 💖</h1>
        <div class="buttons">
            <button id="yesBtn" onclick="accept()">Tak</button>
            <button id="noBtn" onclick="reject()">Nie</button>
        </div>
    </div>

    <div id="success-screen">
        <div class="img-container">
            <img src="https://media.tenor.com/J3iYqK3sQxYAAAAi/cute-bear-love.gif" alt="Happy bear">
        </div>
        <h1>Jej! Wiedziałem! Kocham Cię! 🥰</h1>
    </div>

    <script>
        let scale = 1;
        const noTexts = [
            "Na pewno nie?", 
            "Zastanów się...", 
            "Złamiesz mi serce! 💔", 
            "Będę płakać...", 
            "Obiecuję być grzeczny!", 
            "Proszęęęęę!",
            "To przycisk 'Nie' nie działa!"
        ];
        let textIndex = 0;

        function reject() {
            // Zwiększ przycisk TAK
            scale += 0.5; 
            const yesBtn = document.getElementById("yesBtn");
            yesBtn.style.transform = `scale(${scale})`;

            // Zmień tekst na przycisku NIE
            const noBtn = document.getElementById("noBtn");
            noBtn.innerText = noTexts[textIndex];
            
            // Przejdź do kolejnego tekstu (i zapętl jak się skończą)
            textIndex = (textIndex + 1) % noTexts.length;
        }

        function accept() {
            // Ukryj pytanie, pokaż sukces
            document.getElementById("question-screen").style.display = "none";
            document.getElementById("success-screen").style.display = "block";
            
            // Opcjonalnie: Dodaj konfetti (wymagałoby biblioteki, ale to prosta wersja)
        }
    </script>
</body>
</html>
