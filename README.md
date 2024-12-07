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
            <ul>
                <li><b>Good morning:</b> Selamat pagi</li>
                <li><b>Breakfast:</b> Sarapan</li>
                <li><b>Safety:</b> Keamanan</li>
                <li><b>Teamwork:</b> Kerja sama</li>
                <li><b>Helmet:</b> Helm</li>
                <li><b>Inspection:</b> Inspeksi</li>
                <li><b>Friendship:</b> Persahabatan</li>
                <li><b>Conversation:</b> Percakapan</li>
                <li><b>Responsibility:</b> Tanggung jawab</li>
                <li><b>Job Interview:</b> Wawancara kerja</li>
            </ul>
            <button class="button" onclick="backToMenu()">Kembali</button>
        </section>

        <section id="conversation" class="hidden">
            <h3>Simulasi Percakapan</h3>
            <p><b>Daily Routine:</b></p>
            <p><b>A:</b> Good morning! Did you sleep well?</p>
            <p><b>B:</b> Yes, thank you! What about you?</p>
            <p><b>A:</b> I'm feeling great. Let's start the day!</p>
            
            <p><b>Workplace Safety Discussion:</b></p>
            <p><b>A:</b> Did you inspect the safety equipment?</p>
            <p><b>B:</b> Yes, everything is in good condition.</p>
            <p><b>A:</b> Great! Let's proceed with the meeting.</p>

            <p><b>Job Interview:</b></p>
            <p><b>Interviewer:</b> Can you tell me about your experience in safety management?</p>
            <p><b>Candidate:</b> I have worked as a safety officer for 3 years and specialize in hazard assessment.</p>

            <button class="button" onclick="backToMenu()">Kembali</button>
        </section>

        <section id="quiz" class="hidden">
            <h3>Kuis Bahasa Inggris</h3>
            <p>Pertanyaan: Apa arti 'Teamwork'?</p>
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

        function checkQuiz() {
            const input = document.getElementById("quizInput").value.toLowerCase();
            const response = document.getElementById("quizResponse");
            if (input === "kerja sama") {
                response.innerText = "Benar! 'Teamwork' berarti Kerja sama.";
            } else {
                response.innerText = "Salah. Coba lagi!";
            }
        }
    </script>
</body>
</html>


