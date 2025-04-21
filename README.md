# Membuat file HTML dengan tampilan awal dan fungsi lengkap untuk game matematika kelas 9 (tema: Aljabar)
html_code = '''
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Math Quiz Land</title>
  <link href="https://fonts.googleapis.com/css2?family=Comic+Neue:wght@700&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #fff7e6;
      font-family: 'Comic Neue', cursive;
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      min-height: 100vh;
    }

    h1 {
      margin-top: 40px;
      color: #d6659a;
      font-size: 40px;
    }

    .shapes {
      margin: 30px auto;
      max-width: 300px;
    }

    .shapes img {
      width: 100%;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 15px;
      margin-bottom: 30px;
    }

    .buttons button {
      background-color: #f9c4d2;
      border: none;
      border-radius: 20px;
      padding: 12px 20px;
      font-size: 16px;
      cursor: pointer;
      color: #333;
      transition: 0.3s;
    }

    .buttons button:hover {
      background-color: #f48fb1;
    }

    .footer {
      font-size: 12px;
      color: #777;
      margin-top: auto;
      padding: 20px;
      max-width: 300px;
    }

    .quiz-box {
      display: none;
      flex-direction: column;
      align-items: center;
      margin-top: 20px;
    }

    .question {
      font-size: 18px;
      margin: 15px 0;
    }

    input[type="text"] {
      padding: 8px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    #result {
      margin-top: 10px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Math Quiz Land</h1>

  <div class="shapes">
    <img src="https://cdn-icons-png.flaticon.com/512/8982/8982147.png" alt="Ikon Kalkulator Kawaii" />
  </div>

  <div class="buttons">
    <button onclick="startGame()">Start</button>
    <button onclick="showHelp()">?</button>
    <button onclick="showScores()">Skor</button>
  </div>

  <div class="quiz-box" id="quizBox">
    <div class="question" id="questionText">x + 5 = 12, berapa nilai x?</div>
    <input type="text" id="answerInput" placeholder="Jawaban kamu" />
    <button onclick="checkAnswer()">Submit</button>
    <div id="result"></div>
  </div>

  <div class="footer">
    Game ini dibuat untuk hiburan dan latihan matematika. Grafik dan kode dapat disesuaikan untuk keperluan personal.
    <br><br>
    &copy; 2025 MathQuiz by Kamu
  </div>

  <script>
    let currentScore = 0;

    const question = {
      text: "x + 5 = 12, berapa nilai x?",
      correctAnswer: "7"
    };

    function startGame() {
      document.getElementById("quizBox").style.display = "flex";
      document.getElementById("result").innerText = "";
      document.getElementById("answerInput").value = "";
    }

    function showHelp() {
      alert("Petunjuk:\nJawab soal aljabar yang muncul di layar. Ketik jawabanmu lalu klik Submit!");
    }

    function showScores() {
      alert("Skor kamu saat ini: " + currentScore);
    }

    function checkAnswer() {
      const userAnswer = document.getElementById("answerInput").value.trim();
      const resultBox = document.getElementById("result");

      if (userAnswer === question.correctAnswer) {
        resultBox.innerText = "Benar! Hebat!";
        currentScore += 1;
      } else {
        resultBox.innerText = "Salah. Jawaban yang benar adalah " + question.correctAnswer;
      }
    }
  </script>
</body>
</html>
'''

# Simpan file HTML
file_path = "/mnt/data/math-quiz-land.html"
with open(file_path, "w", encoding="utf-8") as f:
    f.write(html_code)

file_path
