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
from kivy.app import App
from kivy.uix.boxlayout import BoxLayout
from kivy.uix.button import Button
from kivy.uix.label import Label
from kivy.uix.scrollview import ScrollView


class MainScreen(BoxLayout):
    def __init__(self, **kwargs):
        super().__init__(orientation="vertical", **kwargs)

        # Header
        self.header = Label(
            text="Learn English Everyday",
            font_size=24,
            size_hint=(1, 0.1)
        )
        self.add_widget(self.header)

        # Scrollable content
        self.scroll = ScrollView(size_hint=(1, 0.8))
        self.content = BoxLayout(orientation="vertical", size_hint_y=None)
        self.content.bind(minimum_height=self.content.setter('height'))

        # Add categories
        categories = [
            "Morning Routine",
            "Talking with Friends",
            "Workplace Conversations",
            "Safety Discussions",
            "Grammar Tips"
        ]

        for category in categories:
            btn = Button(
                text=category,
                size_hint_y=None,
                height=50,
                on_press=self.open_category
            )
            self.content.add_widget(btn)

        self.scroll.add_widget(self.content)
        self.add_widget(self.scroll)

        # Footer
        self.footer = Label(
            text="Developed for Easy Learning",
            font_size=14,
            size_hint=(1, 0.1)
        )
        self.add_widget(self.footer)

    def open_category(self, instance):
        # Logic for handling category click
        self.header.text = f"Selected: {instance.text}"


class LearnEnglishApp(App):
    def build(self):
        return MainScreen()


if __name__ == "__main__":
    LearnEnglishApp().run()
