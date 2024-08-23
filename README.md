<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Você me ama?</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f2f2f2;
            font-family: Arial, sans-serif;
        }

        #container {
            text-align: center;
        }

        button {
            margin: 10px;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }

        #no {
            position: relative;
        }
    </style>
</head>
<body>
    <div id="container">
        <h1>Você me ama?</h1>
        <button id="yes">Sim</button>
        <button id="no">Não</button>
        <p id="response"></p>
    </div>

    <script>
        const noButton = document.getElementById('no');
        const yesButton = document.getElementById('yes');
        const response = document.getElementById('response');

        yesButton.addEventListener('click', function() {
            response.textContent = 'Eu também te amo!';
        });

        noButton.addEventListener('mouseover', function() {
            const container = document.getElementById('container');
            const containerRect = container.getBoundingClientRect();
            const noButtonRect = noButton.getBoundingClientRect();

            const newLeft = Math.random() * (containerRect.width - noButtonRect.width);
            const newTop = Math.random() * (containerRect.height - noButtonRect.height);

            noButton.style.position = 'absolute';
            noButton.style.left = `${newLeft}px`;
            noButton.style.top = `${newTop}px`;
        });

        noButton.addEventListener('click', function() {
            alert("Ops, você não pode clicar em 'Não'!");
        });
    </script>
</body>
</html>
