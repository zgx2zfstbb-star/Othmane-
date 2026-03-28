<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Wach Katbghini?</title>
<style>
    /* الخلفية وردية وقلوب عائمة */
    body {
        margin: 0;
        padding: 0;
        font-family: 'Arial', sans-serif;
        background: linear-gradient(to bottom, #ffe6f0, #ffcce0);
        overflow-x: hidden;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100vh;
        position: relative;
    }

    h1 {
        font-size: 2.5rem;
        font-weight: bold;
        color: #d42c6b;
        margin-bottom: 30px;
        text-align: center;
    }

    /* دب كبير */
    .bear {
        font-size: 120px;
        text-align: center;
        animation: bounce 2s infinite;
        margin-bottom: 20px;
    }

    @keyframes bounce {
        0%, 100% { transform: translateY(0); }
        50% { transform: translateY(-20px); }
    }

    /* الأزرار */
    .buttons {
        display: flex;
        gap: 20px;
        margin-top: 20px;
    }

    .btn {
        font-size: 1.2rem;
        font-weight: bold;
        padding: 15px 30px;
        border-radius: 50px;
        border: none;
        cursor: pointer;
        color: white;
        display: flex;
        align-items: center;
        gap: 10px;
        box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        transition: transform 0.2s, box-shadow 0.2s;
        position: relative;
        overflow: hidden;
    }

    .btn:hover {
        transform: scale(1.1);
        box-shadow: 0 8px 20px rgba(0,0,0,0.3);
    }

    .btn.ah { background-color: #ff4d6d; }
    .btn.la { background-color: #6c6c6c; }

    /* الرسائل الرومانسية */
    .messages {
        margin-top: 30px;
        text-align: center;
        font-size: 1.5rem;
        font-weight: bold;
        color: #d42c6b;
        min-height: 60px;
    }

    /* قلوب الطيران */
    .heart {
        position: absolute;
        font-size: 20px;
        color: #ff4d6d;
        animation: floatUp 4s linear forwards;
        opacity: 0;
    }

    @keyframes floatUp {
        0% { transform: translateY(0) scale(1); opacity: 1; }
        100% { transform: translateY(-300px) scale(1.5); opacity: 0; }
    }
</style>
</head>
<body>

<div class="bear">🧸</div>
<h1>Wach Katbghini?</h1>

<div class="buttons">
    <button class="btn ah">AH ❤️</button>
    <button class="btn la">LA 😢</button>
</div>

<div class="messages" id="messages"></div>

<script>
    const ahButton = document.querySelector('.btn.ah');
    const laButton = document.querySelector('.btn.la');
    const messagesDiv = document.getElementById('messages');

    // القلوب الطائرة
    function createHeart(x, y) {
        const heart = document.createElement('div');
        heart.classList.add('heart');
        heart.style.left = x + 'px';
        heart.style.top = y + 'px';
        heart.textContent = '💖';
        document.body.appendChild(heart);
        setTimeout(() => {
            heart.remove();
        }, 4000);
    }

    function floatHearts(count=10) {
        for(let i=0; i<count; i++){
            const x = Math.random() * window.innerWidth;
            const y = window.innerHeight - 50;
            setTimeout(() => createHeart(x, y), i * 200);
        }
    }

    // AH button interactions
    const ahMessages = [
        "ta ana kanbghik ALI 💌",
        "3arfa katsta eliya 😘",
        "ga3 hada hob 💖",
        "ALI hbiba🥹"
    ];

    ahButton.addEventListener('click', () => {
        let i = 0;
        messagesDiv.textContent = '';
        const interval = setInterval(() => {
            if(i < ahMessages.length){
                messagesDiv.textContent = ahMessages[i];
                floatHearts(5);
                i++;
            } else {
                clearInterval(interval);
            }
        }, 1000);
    });

    // LA button interactions
    const laMessages = [
        "Wax Mat2akad🥺",
        "Nslkhek Gol AH"
    ];

    laButton.addEventListener('click', () => {
        let i = 0;
        messagesDiv.textContent = '';
        const interval = setInterval(() => {
            if(i < laMessages.length){
                messagesDiv.textContent = laMessages[i];
                floatHearts(3);
                i++;
            } else {
                messagesDiv.textContent = '';
                clearInterval(interval);
            }
        }, 1000);
    });
</script>

</body>
</html>

  
