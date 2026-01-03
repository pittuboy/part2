<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Vocabulary Quiz</title>

<style>
body{
  font-family: Arial, sans-serif;
  background: linear-gradient(to right,#ffecd2,#fcb69f);
  display:flex;
  justify-content:center;
  align-items:center;
  height:100vh;
}
.quiz-box{
  background:#fff;
  width:90%;
  max-width:500px;
  padding:20px;
  border-radius:15px;
}
h2{
  text-align:center;
  color:#ff5722;
}
.option{
  margin:8px 0;
}
button{
  width:100%;
  margin-top:15px;
  padding:10px;
  background:#4caf50;
  color:#fff;
  border:none;
  border-radius:8px;
  font-size:16px;
  cursor:pointer;
}
button:hover{
  background:#43a047;
}
.result{
  text-align:center;
}
.correct{
  color:green;
}
.wrong{
  color:red;
}
</style>
</head>

<body>

<div class="quiz-box">
  <h2 id="question"></h2>
  <div id="options"></div>
  <button onclick="nextQuestion()">Next</button>
</div>

<script>
const quiz = [
 {q:"Honourable means?", o:["Deserving respect","Weak or ill","Grass field"], a:0},
 {q:"Dedicated means?", o:["Devoted or committed","Feeling ashamed","Barrier"], a:0},
 {q:"Puzzled means?", o:["Confused","Prepared","Soldier"], a:0},
 {q:"Meadows means?", o:["Grass fields","Argument","Blanket"], a:0},
 {q:"Foiled means?", o:["Failed or stopped","Moved suddenly","Patriot"], a:0},
 {q:"Dirked means?", o:["Stabbed with a knife","Weak","Area"], a:0},
 {q:"Faint means?", o:["Weak or light","Barrier","Soldier"], a:0},
 {q:"Migrated means?", o:["Moved from one place to another","Begged","Prepared"], a:0},
 {q:"Glib means?", o:["Speaking smoothly but not sincerely","Very beautiful","Blanket"], a:0},
 {q:"Headed means?", o:["Went towards","Confused","Pain"], a:0},
 {q:"Pleaded means?", o:["Begged","Pinched","Area"], a:0},
 {q:"Fence means?", o:["Barrier or boundary","Think deeply","Meet suddenly"], a:0},
 {q:"Quilt means?", o:["Thick blanket","Patriot","Weak"], a:0},
 {q:"Nipped means?", o:["Pinched or bitten lightly","Prepared","Area"], a:0},
 {q:"Brood means?", o:["Think deeply","Grass field","Begged"], a:0},
 {q:"Drafted means?", o:["Prepared","Weak","Meet suddenly"], a:0},
 {q:"Patriot means?", o:["One who loves his country","Soldier","Barrier"], a:0},
 {q:"Sepoy means?", o:["Indian soldier","Weak","Area"], a:0},
 {q:"Torments means?", o:["Great pains or sufferings","Prepared","Field"], a:0},
 {q:"Infirm means?", o:["Weak or ill","Think deeply","Barrier"], a:0},
 {q:"Encounter means?", o:["Meet suddenly","Begged","Field"], a:0},
 {q:"Regions means?", o:["Areas","Pain","Weak"], a:0},
 {q:"Hell means?", o:["Place of suffering","Barrier","Blanket"], a:0},
 {q:"Embarrassed means?", o:["Feeling ashamed","Prepared","Soldier"], a:0},
 {q:"Submissive means?", o:["Willing to obey","Think deeply","Area"], a:0}
];

let index = 0;
let score = 0;
let wrongAnswers = [];

function loadQuestion(){
  const q = quiz[index];
  document.getElementById("question").innerText = 
  `Q${index+26}. ${q.q}`;

  let optionsHTML = "";
  q.o.forEach((opt,i)=>{
    optionsHTML += `
    <div class="option">
      <label>
        <input type="radio" name="option" value="${i}">
        ${opt}
      </label>
    </div>`;
  });
  document.getElementById("options").innerHTML = optionsHTML;
}

function nextQuestion(){
  const selected = document.querySelector('input[name="option"]:checked');
  if(!selected){
    alert("Select an answer!");
    return;
  }

  if(parseInt(selected.value) === quiz[index].a){
    score++;
  }else{
    wrongAnswers.push({
      question: quiz[index].q,
      correct: quiz[index].o[quiz[index].a]
    });
  }

  index++;
  if(index < quiz.length){
    loadQuestion();
  }else{
    showResult();
  }
}

function showResult(){
  let html = `
    <div class="result">
      <h2>Quiz Completed 🎉</h2>
      <p><b>Your Score:</b> ${score} / ${quiz.length}</p>
  `;

  if(wrongAnswers.length > 0){
    html += "<h3>Correct Answers:</h3>";
    wrongAnswers.forEach(w=>{
      html += `<p class="wrong">
      ${w.question} <br>
      <span class="correct">Correct: ${w.correct}</span>
      </p>`;
    });
  }
  html += "</div>";

  document.querySelector(".quiz-box").innerHTML = html;
}

loadQuestion();
</script>

</body>
</html>
