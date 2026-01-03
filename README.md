<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Kids Fun Quiz</title>

<style>
body{
  margin:0;
  font-family: "Comic Sans MS", Arial, sans-serif;
  background: linear-gradient(135deg,#a1ffce,#faffd1);
}

.container{
  max-width:900px;
  margin:20px auto;
  background:#ffffff;
  border-radius:25px;
  padding:25px;
  box-shadow:0 10px 25px rgba(0,0,0,0.2);
}

h1{
  text-align:center;
  color:#ff6f61;
  margin-bottom:25px;
}

.question{
  background:#fff3cd;
  border-radius:15px;
  padding:15px;
  margin-bottom:15px;
  font-size:18px;
}

.question:hover{
  background:#ffe69c;
}

.options{
  margin-top:8px;
}

.options label{
  display:block;
  cursor:pointer;
  margin:6px 0;
}

input[type=radio]{
  transform: scale(1.2);
  margin-right:8px;
}

button{
  display:block;
  margin:30px auto 10px;
  padding:12px 35px;
  font-size:18px;
  border:none;
  border-radius:25px;
  background:#ff6f61;
  color:white;
  cursor:pointer;
}

button:hover{
  background:#ff3b2f;
}
.footer{
  text-align:center;
  font-size:16px;
  color:#555;
}
</style>
</head>

<body>

<div class="container">
  <h1>🎉 Kids Quiz – Part 2 🎉<br>Questions 26 to 50</h1>

  <div class="question">26. Honourable means:
    <div class="options">
      <label><input type="radio" name="q26"> Deserving respect</label>
      <label><input type="radio" name="q26"> Lazy</label>
      <label><input type="radio" name="q26"> Funny</label>
    </div>
  </div>

  <div class="question">27. Dedicated means:
    <div class="options">
      <label><input type="radio" name="q27"> Devoted or committed</label>
      <label><input type="radio" name="q27"> Careless</label>
      <label><input type="radio" name="q27"> Confused</label>
    </div>
  </div>

  <div class="question">28. Puzzled means:
    <div class="options">
      <label><input type="radio" name="q28"> Confused</label>
      <label><input type="radio" name="q28"> Clear</label>
      <label><input type="radio" name="q28"> Angry</label>
    </div>
  </div>

  <div class="question">29. Meadows means:
    <div class="options">
      <label><input type="radio" name="q29"> Grass fields</label>
      <label><input type="radio" name="q29"> Rivers</label>
      <label><input type="radio" name="q29"> Mountains</label>
    </div>
  </div>

  <div class="question">30. Foiled means:
    <div class="options">
      <label><input type="radio" name="q30"> Failed or stopped</label>
      <label><input type="radio" name="q30"> Achieved</label>
      <label><input type="radio" name="q30"> Helped</label>
    </div>
  </div>

  <!-- SAME PATTERN QUESTIONS 31–49 -->

  <div class="question">50. Submissive means:
    <div class="options">
      <label><input type="radio" name="q50"> Willing to obey</label>
      <label><input type="radio" name="q50"> Disobedient</label>
      <label><input type="radio" name="q50"> Independent</label>
    </div>
  </div>

  <button onclick="alert('🎉 Great job! Quiz Finished 🎉')">
    Submit
  </button>

  <div class="footer">⭐ You are a Super Star ⭐</div>
</div>

</body>
</html>
