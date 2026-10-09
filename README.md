# reset-app
RESET - build better habits and take back your time 

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>RESET | Take Back Control</title>
<style>
body{margin:0;background:#0b1020;color:#fff;font-family:Arial,sans-serif;padding:24px}
h1{font-size:44px}span{color:#68f0b0}
p{color:#bdc6d9;line-height:1.7}
.card{background:#151e32;padding:20px;border-radius:16px;margin:20px 0}
button{background:#68f0b0;border:0;border-radius:9px;padding:14px;font-weight:bold;margin:8px 0}
li{padding:12px 0}
</style>
</head>
<body>
<h2><span>RESET.</span></h2>
<p>YOUR LIFE. YOUR CONTROL.</p>
<h1>Break the cycle.<br><span>Build yourself.</span></h1>
<p>Less scrolling. Fewer bad habits. More focus on the life you actually want.</p>
<div class="card">
<h2>🎯 Your daily reset</h2>
<p>Complete these small steps today:</p>
<label><input type="checkbox" onchange="count()"> Work on my main goal for 10 minutes</label><br><br>
<label><input type="checkbox" onchange="count()"> Take a break from social media</label><br><br>
<label><input type="checkbox" onchange="count()"> Do one task I've been avoiding</label><br><br>
<h3 id="progress">0 tasks completed</h3>
</div>
<div class="card">
<h2>🧠 Beat the urge</h2>
<p>Pause. Breathe. You can choose your next action.</p>
<button onclick="pause()">Start 60-second pause</button>
<h2 id="timer">60 seconds</h2>
</div>
<div class="card">
<h2>📵 My screen-time goal</h2>
<p>Set a daily goal in minutes:</p>
<input id="limit" type="number" value="60" min="1">
<button onclick="save()">Save goal</button>
<p id="result"></p>
</div>
<div class="card">
<h2>💚 Remember your reason</h2>
<textarea id="reason" placeholder="What are you working towards?" rows="4"></textarea><br>
<button onclick="remember()">Save my reason</button>
<p id="saved"></p>
</div>
<p>RESET. — Progress, not perfection.</p>
<script>
function count(){
let n=[...document.querySelectorAll('input[type=checkbox]')].filter(x=>x.checked).length;
document.getElementById('progress').textContent=n+' tasks completed';
}
let interval;
function pause(){
clearInterval(interval);
let n=60;
document.getElementById('timer').textContent=n+' seconds';
interval=setInterval(()=>{
n--;
document.getElementById('timer').textContent=n+' seconds';
if(n<=0){clearInterval(interval);document.getElementById('timer').textContent='Pause complete!';}
},1000);
}
function save(){
document.getElementById('result').textContent='Your daily goal: '+document.getElementById('limit').value+' minutes. Keep going!';
}
function remember(){
document.getElementById('saved').textContent='Your reason: '+document.getElementById('reason').value;
}
</script>
</body>
</html>
