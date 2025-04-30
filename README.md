# html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Generation Quiz</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    .quiz-container {
      max-width: 600px;
      margin: 0 auto;
    }
    .question {
      margin-bottom: 1em;
    }
    .submit-btn {
      background-color: #4CAF50;
      border: none;
      color: white;
      padding: 15px 32px;
      text-align: center;
      text-decoration: none;
      display: inline-block;
      font-size: 16px;
      margin: 20px 0;
      cursor: pointer;
    }
    .result {
      font-size: 24px;
      font-weight: bold;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <div class="quiz-container">
    <h1>Generation Quiz</h1>
    <form id="quiz-form">
      <div class="question">
        <p>1. What is your favorite video game console?</p>
        <input type="radio" name="q1" value="1"> Atari 2600<br>
        <input type="radio" name="q1" value="2"> Nintendo Entertainment System<br>
        <input type="radio" name="q1" value="3"> PlayStation<br>
        <input type="radio" name="q1" value="4"> Xbox One
      </div>
      <div class="question">
        <p>2. What type of game do you prefer?</p>
        <input type="radio" name="q2" value="1"> Arcade<br>
        <input type="radio" name="q2" value="2"> Platformer<br>
        <input type="radio" name="q2" value="3"> First-person shooter<br>
        <input type="radio" name="q2" value="4"> Battle Royale
      </div>
      <div class="question">
        <p>3. Which of these games have you played the most?</p>
        <input type="radio" name="q3" value="1"> Pong<br>
        <input type="radio" name="q3" value="2"> Super Mario Bros.<br>
        <input type="radio" name="q3" value="3"> Final Fantasy VII<br>
        <input type="radio" name="q3" value="4"> Fortnite
      </div>
      <div class="question">
        <p>4. What is your preferred method of playing games?</p>
        <input type="radio" name="q4" value="1"> Arcade cabinet<br>
        <input type="radio" name="q4" value="2"> Home console<br>
        <input type="radio" name="q4" value="3"> PC<br>
        <input type="radio" name="q4" value="4"> Mobile device
      </div>
      <div class="question">
        <p>5. Which of these game characters do you recognize the most?</p>
        <input type="radio" name="q5" value="1"> Pac-Man<br>
        <input type="radio" name="q5" value="2"> Mario<br>
        <input type="radio" name="q5" value="3"> Lara Croft<br>
        <input type="radio" name="q5" value="4"> Master Chief
      </div>
      <button type="button" class="submit-btn" onclick="submitQuiz()">Submit</button>
    </form>
    <div class="result" id="result"></div>
  </div>
  <script>
    function submitQuiz() {
      const form = document.getElementById('quiz-form');
      let score = 0;
      for (let i = 1; i <= 5; i++) {
        const selectedOption = form['q' + i].value;
        if (selectedOption) {
          score += parseInt(selectedOption);
        }
      }
      let generation = '';
      if (score >= 5 && score <= 9) {
        generation = 'Baby Boomer';
      } else if (score >= 10 && score <= 14) {
        generation = 'Generation X';
      } else if (score >= 15 && score <= 19) {
        generation = 'Millennial';
      } else {
        generation = 'Generation Z';
      }
      document.getElementById('result').innerHTML = 'You are likely from the ' + generation + ' generation!';
    }
  </script>
</body>
</html>
