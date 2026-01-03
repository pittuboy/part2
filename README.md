<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Kids Vocabulary Quiz (26–50)</title>

<style>
body{
  font-family: Comic Sans MS, Arial;
  background: linear-gradient(135deg,#ffecd2,#fcb69f);
  display:flex;
  justify-content:center;
  align-items:center;
  min-height:100vh;
}
.card{
  background:white;
  width:380px;
  padding:25px;
  border-radius:20px;
  box-shadow:0 10px 25px rgba(0,0,0,0.2);
}
h2{
  text-align:center;
  color:#ff6f61;
}
.option{
  margin:8px 0;
}
button{
  width:100%;
  margin-top:15px;
  padding:10px;
  border:none;
  border-radius:15px;
  background:#ff6f61;
  color:white;
  font-size:16px;
  cursor:pointer;
}
button:hover{ background:#ff3b2f; }
.result{
  font-size:14px;
}
.correct{ color:green; }
.wrong{ color:red; }
</style>
</head>

<body>

<div class="card" id="quizBox">
  <h2 id="qno"></h2>
  <p id="question"></p>
  <div id="options"></div>
  <button onclick="nextQuestion()">Next</button>
</div>

<script>
const quiz = [
{q:"Honourable means?", o:["Deserving respect","Weak","Grass field"], a:0},
{q:"Dedicated means?", o:["Devoted or committed","Ashamed","Barrier"], a:0},
{q:"Puzzled means?", o:["Confused","Prepared","Soldier"], a:0},
{q:"Meadows means?", o:["Grass fields","Argument","Blanket"], a:0},
{q:"Foiled means?", o:["Failed or stopped","Moved suddenly","Patriot"], a:0},

{q:"Dirked means?", o:["Stabbed with a knife","Weak","Area"], a:0},
{q:"Faint means?", o:["Weak or light","Fence","Soldier"], a:0},
{q:"Migrated means?", o:["Moved from one place to another","Begged","Prepared"], a:0},
{q:"Glib means?", o:["Speaking smoothly but not sincerely","Beautiful","Blanket"], a:0},
{q:"Headed means?", o:["Went towards","Confused","Pain"], a:0},

{q:"Pleaded means?", o:["Begged","Pinched","Region"], a:0},
{q:"Fence means?", o:["Barrier or boundary","Think deeply","Meet suddenly"], a:0},
{q:"Quilt means?", o:["Thick blanket","Patriot","Weak"], a:0},
{q:"Nipped means?", o:["Pinched lightly","Prepared","Area"], a:0},
{q:"Brood means?", o:["Think deeply","Grass field","Begged"], a:0},

{q:"Drafted means?", o:["Prepared","Weak","Met suddenly"], a:0},
{q:"Patriot means?", o:["One who loves his country","Soldier","Fence"], a:0},
{q:"Sepoy means?", o:["Indian soldier","Weak","Area"], a:0},
{q:"Torments means?", o:["Great pains or sufferings","Happiness","Field"], a:0},
{q:"Infirm means?", o:["Weak or ill","Strong","Boundary"], a:0},

{q:"Encounter means?", o:["Meet suddenly","Beg","Field"], a:0},
{q:"Regions means?", o:["Areas","Pain","Weakness"], a:0},
{q:"Hell means?", o:["Place of suffering","Fence","Blanket"], a:0},
{q:"Embarrassed means?", o:["Feeling ashamed","Prepared","Soldier"], a:0},
{q:"Submissive means?", o:["Willing to obey","Think deeply","Area"], a:0}
];

let index = 0;
let score = 0;
let wrong = [];

function loadQuestion(){
  document.getElementById("qno").innerText =
    "Question " + (index + 26);
  document.getElementById("question").innerText = quiz[index].q;

  let html = "";
  quiz[index].o.forEach((opt,i)=>{
    html += `
      <div class="option">
        <label>
          <input type="radio" name="opt" value="${i}">
          ${opt}
        </label>
      </div>`;
  });
  document.getElementById("options").innerHTML = html;
}

function nextQuestion(){
  const selected = document.querySelector('input[name="opt"]:checked');
  if(!selected){
    alert("Select an answer 😊");
    return;
  }

  if(parseInt(selected.value) === quiz[index].a){
    score++;
  }else{
    wrong.push({
      q: quiz[index].q,
      ans: quiz[index].o[quiz[index].a]
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
    <h2>🎉 Quiz Completed 🎉</h2>
    <p><b>Score:</b> ${score} / ${quiz.length}</p>
    <div class="result">
  `;

  if(wrong.length > 0){
    html += "<h3>Correct Answers:</h3>";
    wrong.forEach(w=>{
      html += `<p class="wrong">${w.q}<br>
      <span class="correct">Correct: ${w.ans}</span></p>`;
    });
  }

  html += "</div>";
  document.getElementById("quizBox").innerHTML = html;
}

loadQuestion();
</script>

</body>
</html>
