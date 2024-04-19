<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>عداد النقاط</title>
<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
        position: relative;
    }
    #score {
        font-size: 24px;
        margin-bottom: 20px;
    }
    #button {
        width: 150px;
        height: 150px;
        background-color: red;
        color: white;
        font-size: 18px;
        border: none;
        border-radius: 50%;
        cursor: pointer;
    }
    #movingText {
        position: absolute;
        bottom: 10px;
        left: 50%;
        transform: translateX(-50%);
        background-color: rgba(0, 0, 0, 0.5);
        color: white;
        padding: 5px 10px;
        border-radius: 5px;
        animation: moveText 5s infinite;
    }
    
    @keyframes moveText {
        0% { left: 50%; }
        50% { left: 0; }
        100% { left: 50%; }
    }
</style>
</head>
<body>
    <h1>عداد النقاط</h1>
    <label for="username">الاسم:</label>
    <input type="text" id="username" placeholder="ادخل اسمك">

    <div id="score">النقاط: 0</div>
    <button id="button" onclick="increaseScore()">+</button>

    <div id="leaderboard"></div>

    <div id="movingText">حقوق. ABAAS BW.</div>

    <script>
        let score = 0;
        const scoreDisplay = document.getElementById('score');
        const usernameInput = document.getElementById('username');
        const leaderboard = document.getElementById('leaderboard');
        const users = [];

        function increaseScore() {
            score++;
            scoreDisplay.textContent = 'النقاط: ' + score;

            const username = usernameInput.value.trim();
            if (username !== '') {
                const userIndex = users.findIndex(user => user.name === username);
                if (userIndex !== -1) {
                    users[userIndex].score += 1;
                } else {
                    users.push({ name: username, score: 1 });
                }
                updateLeaderboard();
            }
        }

        function updateLeaderboard() {
            users.sort((a, b) => b.score - a.score);
            leaderboard.innerHTML = '';
            for (let i = 0; i < Math.min(5, users.length); i++) {
                const user = users[i];
                const listItem = document.createElement('li');
                listItem.textContent = `${user.name}: ${user.score}`;
                leaderboard.appendChild(listItem);
            }
        }
    </script>
</body>
</html>
