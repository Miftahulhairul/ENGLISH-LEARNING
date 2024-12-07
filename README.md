# ENGLISH-LEARNING
ENGLISH LEARNING FOR BEGINNERS
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Learn English</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
            color: #333;
        }
        header {
            background-color: #007BFF;
            color: white;
            padding: 15px;
            text-align: center;
        }
        main {
            padding: 20px;
        }
        .button {
            display: inline-block;
            margin: 10px 5px;
            padding: 10px 20px;
            background-color: #007BFF;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .button:hover {
            background-color: #0056b3;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <header>
        <h1>Learn English Everyday</h1>
    </header>
    <main>
        <h2>Pilih Aktivitas:</h2>
        <button class="button" onclick="showSection('vocab')">Kosa Kata</button>
        <button class="button" onclick="showSection('conversation')">Simulasi Percakapan</button>
        <button class="button" onclick="showSection('quiz')">Kuis</button>
        
        <section id="vocab" class="hidden">
            <h3>Kosa Kata Harian</h3>
            <p>- Good morning: Selamat pagi</p>
            <p>- Breakfast: Sarapan</p>
            <p>- Safety: Keamanan</p>
            <button class="button" onclick="backToMenu()">Kembali</button>
        </section>

        <section id="conversation" class="hidden">
            <h3>Simulasi Percakapan</h3>
            <p><b>A:</b> Good morning! How are you?</p>
            <input type="text" id="conversationInput" placeholder="Balas di sini..." />
            <button class="button" onclick="checkConversation()">Kirim</button>
            <p id="conversationResponse"></p>
            <button class="button" onclick="backToMenu()">Kembali</button>
        </section>

        <section id="quiz" class="hidden">
            <h3>Kuis Bahasa Inggris</h3>
            <p>Pertanyaan: Apa arti 'Safety'?</p>
            <input type="text" id="quizInput" placeholder="Jawabanmu..." />
            <button class="button" onclick="checkQuiz()">Kirim</button>
            <p id="quizResponse"></p>
            <button class="button" onclick="backToMenu()">Kembali</button>
        </section>
    </main>

    <script>
        function showSection(sectionId) {
            document.querySelectorAll("section").forEach(sec => sec.classList.add("hidden"));
            document.getElementById(sectionId).classList.remove("hidden");
        }

        function backToMenu() {
            document.querySelectorAll("section").forEach(sec => sec.classList.add("hidden"));
        }

        function checkConversation() {
            const input = document.getElementById("conversationInput").value.toLowerCase();
            const response = document.getElementById("conversationResponse");
            if (input === "i'm fine" || input === "i am good") {
                response.innerText = "B: I'm glad to hear that!";
            } else {
                response.innerText = "B: That doesn't sound right. Try again!";
            }
        }

        function checkQuiz() {
            const input = document.getElementById("quizInput").value.toLowerCase();
            const response = document.getElementById("quizResponse");
            if (input === "keamanan") {
                response.innerText = "Benar! 'Safety' berarti Keamanan.";
            } else {
                response.innerText = "Salah. Coba lagi!";
            }
        }
    </script>
</body>
</html>
