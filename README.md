# KartonnikiTV2D.github.io
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🎄 Мой Новогодний Супер-Сайт</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI',Roboto,sans-serif}
:root{--card:rgba(255,255,255,.09);--text:#fff;--accent:#f59e0b;--accent2:#38bdf8}
body{min-height:100vh;background:linear-gradient(160deg,#0b1d3a,#14405f,#0b3d2e);background-attachment:fixed;color:var(--text);padding:60px 16px 30px;transition:.4s;overflow-x:hidden}
#snow{position:fixed;inset:0;z-index:1;pointer-events:none}
.tree{position:fixed;bottom:-6px;font-size:62px;z-index:2;pointer-events:none;filter:drop-shadow(0 0 14px rgba(90,255,160,.45))}
.t1{left:6px}.t2{right:6px}
#shapeBtn{position:fixed;top:10px;right:10px;z-index:9;font-size:1.25em;padding:7px 12px;border-radius:50%;border:1px solid rgba(255,255,255,.3);background:rgba(0,0,0,.35);color:#fff;cursor:pointer}
.garland{position:fixed;top:0;left:0;right:0;z-index:8;pointer-events:none;display:flex;justify-content:space-around;padding:2px 6px}
.bulb{width:11px;height:15px;border-radius:50% 50% 60% 60%;animation:blink 1.6s infinite}
@keyframes blink{0%,100%{opacity:1;box-shadow:0 0 12px 2px currentColor}50%{opacity:.2;box-shadow:none}}
header{text-align:center;padding:14px 0 8px;position:relative;z-index:3}
h1{font-size:clamp(1.6em,5vw,2.4em);background:linear-gradient(90deg,var(--accent),var(--accent2));-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;margin-bottom:6px}
nav{display:flex;flex-wrap:wrap;gap:7px;justify-content:center;margin:14px 0;position:relative;z-index:3}
nav button{padding:9px 14px;border:none;border-radius:20px;background:var(--card);color:var(--text);font-size:.92em;cursor:pointer;backdrop-filter:blur(10px);border:1px solid rgba(255,255,255,.15);transition:.2s}
nav button:hover,.tab.active{background:rgba(245,158,11,.25)}
.tab{display:none;max-width:620px;margin:0 auto 20px;padding:20px;background:var(--card);border-radius:20px;backdrop-filter:blur(12px);box-shadow:0 8px 32px rgba(0,0,0,.25);position:relative;z-index:3;animation:fade .3s}
.tab.active{display:block}
@keyframes fade{from{opacity:0;transform:translateY(10px)}to{opacity:1}}
.big-btn{width:100%;padding:13px;border:none;border-radius:12px;background:linear-gradient(90deg,var(--accent),var(--accent2));color:#08131f;font-weight:600;font-size:1.02em;cursor:pointer;margin-top:10px;transition:.2s}
.big-btn:active{transform:scale(.97)}
.ghost{background:rgba(255,255,255,.14)!important;color:#fff!important}
input,textarea,select{width:100%;padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,.25);background:rgba(255,255,255,.1);color:var(--text);font-size:1em;margin:6px 0;outline:none}
textarea{resize:vertical}
.item{display:flex;justify-content:space-between;align-items:center;gap:8px;padding:10px 14px;background:rgba(255,255,255,.07);border-radius:10px;margin:6px 0}
.item.done span{text-decoration:line-through;opacity:.5}
.income{border-left:3px solid #4ade80}.expense{border-left:3px solid #f87171}
.x{background:none;border:none;color:#f87171;font-size:1.15em;cursor:pointer}
.calc{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;margin-top:10px}
.calc button{padding:15px;border:none;border-radius:12px;background:rgba(255,255,255,.12);color:var(--text);font-size:1.2em;cursor:pointer}
.calc button.op{background:rgba(245,158,11,.5)}
.calc button.eq{background:var(--accent2);grid-column:span 2;color:#08131f;font-weight:700}
#calcOut{font-size:1.7em;text-align:right;padding:14px;background:rgba(0,0,0,.25);border-radius:12px;min-height:56px;word-break:break-all}
.dice{font-size:4em;text-align:center;margin:8px}
.timer{font-size:2.8em;text-align:center;font-variant-numeric:tabular-nums;margin:8px 0}
.row{display:flex;gap:8px}.row>*{flex:1}
.hint{opacity:.65;font-size:.85em;margin-top:10px}
.result{text-align:center;font-size:1.1em;margin-top:12px;min-height:46px}
.countdown{font-size:1.25em;text-align:center;padding:14px;background:rgba(245,158,11,.15);border:1px solid rgba(245,158,11,.4);border-radius:14px;margin:12px 0;font-variant-numeric:tabular-nums}
canvas#paint{width:100%;border-radius:12px;touch-action:none;background:#fff;display:block}
.palette{display:grid;grid-template-columns:repeat(9,1fr);gap:6px;margin-top:8px}
.palette div{aspect-ratio:1;border-radius:8px;cursor:pointer;border:2px solid transparent}
.palette div.sel{border-color:var(--accent2)}
.chat{display:flex;flex-direction:column;height:340px;overflow-y:auto;background:rgba(0,0,0,.2);border-radius:12px;padding:10px;margin-bottom:8px}
.msg{max-width:85%;padding:8px 12px;border-radius:14px;margin:4px 0;font-size:.95em;word-break:break-word}
.msg.me{align-self:flex-end;background:var(--accent2);color:#08131f;border-bottom-right-radius:4px}
.msg.bot{align-self:flex-start;background:rgba(255,255,255,.12);border-bottom-left-radius:4px}
.quizItem{background:rgba(255,255,255,.06);border-radius:12px;padding:12px;margin:10px 0}
.quizItem p{margin-bottom:8px;font-weight:600}
.opt{display:block;width:100%;text-align:left;padding:9px 12px;margin:5px 0;border:none;border-radius:10px;background:rgba(255,255,255,.1);color:var(--text);cursor:pointer;font-size:.95em}
.opt.right{background:rgba(74,222,128,.45)}
.opt.wrong{background:rgba(248,113,113,.45)}
details.diaryItem{background:rgba(255,255,255,.06);border-radius:10px;padding:10px 12px;margin:6px 0}
details.diaryItem summary{cursor:pointer;font-weight:600}
footer{text-align:center;opacity:.55;margin:26px 0 8px;font-size:.85em;position:relative;z-index:3}
h3{margin:16px 0 6px}
label.chk{display:flex;align-items:center;gap:8px;margin:8px 0;font-size:.95em}
label.chk input{width:auto;margin:0}
</style>
</head>
<body>
<div class="garland" id="garland"></div>
<canvas id="snow"></canvas>
<div class="tree t1">🎄</div><div class="tree t2">🎄</div>
<button id="shapeBtn" onclick="toggleShape()">❄</button>

<header>
  <h1>🎄 Мой Новогодний Супер-Сайт 🎅</h1>
  <p style="opacity:.75">Снег идёт, гирлянды горят — и всё без интернета ✨</p>
</header>

<nav id="nav">
  <button data-tab="main" class="active">🏠 Главное</button>
  <button data-tab="chat">💬 Чат</button>
  <button data-tab="calc">🧮 Калькулятор</button>
  <button data-tab="todo">✅ Дела</button>
  <button data-tab="notes">📝 Заметки</button>
  <button data-tab="timer">⏱ Таймер</button>
  <button data-tab="fun">🎲 Игры</button>
  <button data-tab="quiz">🧠 Викторина</button>
  <button data-tab="draw">🎨 Рисовалка</button>
  <button data-tab="pass">🔐 Пароли</button>
  <button data-tab="conv">🔄 Конвертер</button>
  <button data-tab="diary">📔 Дневник</button>
  <button data-tab="budget">💰 Бюджет</button>
</nav>

<div class="tab active" id="main">
  <div class="countdown" id="nyCount">Считаю до Нового года…</div>
  <p style="margin-bottom:10px">Привет! Это твой новогодний мультисайт: снег, гирлянды, ёлочки и куча инструментов. Всё сохраняется в браузере.</p>
  <div class="row">
    <button class="big-btn" style="margin:0" onclick="magic()">✨ Магия</button>
    <button class="big-btn ghost" style="margin:0" onclick="toggleTheme()">🌗 Тема</button>
  </div>
  <div class="row">
    <button class="big-btn" style="margin:0" onclick="snowSalute()">❄️ Снежный салют!</button>
    <button class="big-btn ghost" style="margin:0" onclick="toggleShape()">⛄/❄ Форма снежинок</button>
  </div>
  <div class="result" id="magicOut"></div>
  <p class="hint">Вкладки сверху: чат, калькулятор, дела, заметки, таймер, игры, викторина, рисовалка, пароли, конвертер, дневник и бюджет.</p>
</div>

<div class="tab" id="chat">
  <div class="chat" id="chatLog"></div>
  <div class="row">
    <input id="chatIn" placeholder="Напиши что-нибудь…" style="margin:0" onkeydown="if(event.key==='Enter')sendChat()">
    <button class="big-btn" style="margin:0;width:auto;padding:13px 18px" onclick="sendChat()">➤</button>
  </div>
  <p class="hint">Попроси: «шутку», «факт», «мем», «стишок», «время», «новый год», «подбодри» — или просто поболтаем. И я считаю примеры!</p>
</div>

<div class="tab" id="calc">
  <div id="calcOut">0</div>
  <div class="calc">
    <button onclick="calc('C')">C</button><button onclick="calc('del')">⌫</button><button onclick="calc('%')">%</button><button class="op" onclick="calc('/')">÷</button>
    <button onclick="calc('7')">7</button><button onclick="calc('8')">8</button><button onclick="calc('9')">9</button><button class="op" onclick="calc('*')">×</button>
    <button onclick="calc('4')">4</button><button onclick="calc('5')">5</button><button onclick="calc('6')">6</button><button class="op" onclick="calc('-')">−</button>
    <button onclick="calc('1')">1</button><button onclick="calc('2')">2</button><button onclick="calc('3')">3</button><button class="op" onclick="calc('+')">+</button>
    <button onclick="calc('(')">(</button><button onclick="calc('0')">0</button><button onclick="calc(',')">,</button><button class="op" onclick="calc(')')">)</button>
    <button class="eq" onclick="calc('=')">=</button>
  </div>
</div>

<div class="tab" id="todo">
  <input id="todoIn" placeholder="Новое дело..." onkeydown="if(event.key==='Enter')addTodo()">
  <button class="big-btn" onclick="addTodo()">Добавить</button>
  <div id="todoList"></div>
  <p class="hint" id="todoStat"></p>
</div>

<div class="tab" id="notes">
  <textarea id="noteArea" rows="10" placeholder="Пиши сюда что угодно — сохранится автоматически" oninput="saveNotes()"></textarea>
  <p class="hint">Сохранено ✅ Символов: <span id="noteCount">0</span></p>
</div>

<div class="tab" id="timer">
  <div class="timer" id="timerOut">00:00</div>
  <div class="row">
    <button class="big-btn" style="margin:0" onclick="startTimer(60)">1 мин</button>
    <button class="big-btn" style="margin:0" onclick="startTimer(300)">5 мин</button>
    <button class="big-btn" style="margin:0" onclick="startTimer(600)">10 мин</button>
  </div>
  <div class="row">
    <button class="big-btn" style="margin:0" onclick="toggleStop()">▶️/⏸ Пуск/Пауза</button>
    <button class="big-btn ghost" style="margin:0" onclick="stopTimer()">Сброс</button>
  </div>
  <label class="chk"><input type="checkbox" id="chimesOn" checked> Бой курантов, когда таймер дотикает 🔔</label>
  <h3>Секундомер</h3>
  <div class="timer" id="swOut" style="font-size:2.1em">00:00.0</div>
  <div class="row">
    <button class="big-btn" style="margin:0" onclick="swStart()">Старт</button>
    <button class="big-btn ghost" style="margin:0" onclick="swStop()">Стоп</button>
  </div>
</div>

<div class="tab" id="fun">
  <h3>🎲 Кубик</h3>
  <div class="dice" id="diceOut">🎲</div>
  <button class="big-btn" onclick="rollDice()">Бросить кубик</button>
  <h3>🪙 Монетка</h3>
  <button class="big-btn" onclick="flipCoin()">Подбросить монетку</button>
  <div class="result" id="coinOut"></div>
  <h3>🔢 Случайное число</h3>
  <div class="row">
    <input id="rndFrom" type="number" value="1" placeholder="от">
    <input id="rndTo" type="number" value="100" placeholder="до">
  </div>
  <button class="big-btn" onclick="rndNum()">Выпало число</button>
  <div class="result" id="rndOut"></div>
  <h3>🔢 Угадай число (1–100)</h3>
  <input id="guessIn" type="number" placeholder="Твоя догадка" onkeydown="if(event.key==='Enter')guess()">
  <button class="big-btn" onclick="guess()">Проверить</button>
  <div class="result" id="guessOut"></div>
  <h3>✊ Камень-ножницы-бумага</h3>
  <div class="row">
    <button class="big-btn" style="margin:0" onclick="rps('✊')">✊</button>
    <button class="big-btn" style="margin:0" onclick="rps('✌️')">✌️</button>
    <button class="big-btn" style="margin:0" onclick="rps('✋')">✋</button>
  </div>
  <div class="result" id="rpsOut"></div>
</div>

<div class="tab" id="quiz">
  <p>Отвечай на вопросы — правильные подсветятся зелёным. Никакого интернета не нужно: вопросы уже внутри.</p>
  <div id="quizScore" class="result" style="font-weight:700"></div>
  <div id="quizList"></div>
  <button class="big-btn ghost" onclick="resetQuiz()">🔄 Начать заново</button>
</div>

<div class="tab" id="draw">
  <canvas id="paint" width="560" height="380"></canvas>
  <div class="palette" id="palette"></div>
  <div class="row">
    <button class="big-btn" style="margin:0" onclick="clearPaint()">🗑 Очистить</button>
    <button class="big-btn ghost" style="margin:0" onclick="saveImg()">💾 Сохранить PNG</button>
  </div>
  <p class="hint">Рисуй пальцем или мышкой. Можно нарисовать ёлочку Деду Морозу 🎄</p>
</div>

<div class="tab" id="pass">
  <label class="chk">Длина пароля: <b id="passLenOut">14</b></label>
  <input id="passLen" type="range" min="6" max="40" value="14" oninput="document.getElementById('passLenOut').textContent=this.value">
  <label class="chk"><input type="checkbox" id="pUpper" checked> Заглавные буквы</label>
  <label class="chk"><input type="checkbox" id="pDigits" checked> Цифры</label>
  <label class="chk"><input type="checkbox" id="pSpec" checked> Спецсимволы (!@#...)</label>
  <button class="big-btn" onclick="genPass()">🎲 Сгенерировать</button>
  <div id="passOut" class="result" style="word-break:break-all">—</div>
  <button class="big-btn ghost" onclick="copyPass()">📋 Скопировать</button>
</div>

<div class="tab" id="conv">
  <select id="convCat" onchange="fillConv()">
    <option value="len">Длина</option>
    <option value="mass">Масса</option>
    <option value="vol">Объём</option>
    <option value="speed">Скорость</option>
    <option value="area">Площадь</option>
    <option value="temp">Температура</option>
  </select>
  <input id="convVal" placeholder="Сколько?" oninput="convert()" inputmode="decimal">
  <div class="row">
    <select id="convFrom" onchange="convert()"></select>
    <span style="align-self:center">→</span>
    <select id="convTo" onchange="convert()"></select>
  </div>
  <div id="convOut" class="result" style="font-size:1.4em;font-weight:700">—</div>
  <p class="hint">Живой пересчёт при вводе, запятая работает, температура считается по настоящим формулам.</p>
</div>

<div class="tab" id="diary">
  <label>Запись за сегодня:</label>
  <textarea id="diaryIn" rows="5" placeholder="Как прошёл день?"></textarea>
  <button class="big-btn" onclick="saveDiaryEntry()">💾 Сохранить запись</button>
  <h3>Прошлые записи</h3>
  <div id="diaryList"></div>
</div>

<div class="tab" id="budget">
  <input id="budgetText" placeholder="Например: мандарины">
  <input id="budgetAmt" type="number" placeholder="Сумма, ₽" inputmode="decimal">
  <div class="row">
    <button class="big-btn" style="margin:0" onclick="addBudget('in')">➕ Доход</button>
    <button class="big-btn ghost" style="margin:0" onclick="addBudget('out')">➖ Расход</button>
  </div>
  <div id="budgetBal" class="result" style="font-weight:700"></div>
  <div id="budgetList"></div>
  <p class="hint">Данные хранятся только в твоём браузере.</p>
</div>

<footer>🎄 Сделано с ❤️ и снегом · 2026</footer>

<script>
// ===== ВКЛАДКИ =====
function initTabs(){
  document.querySelectorAll('#nav button').forEach(function(b){
    b.onclick=function(){
      document.querySelectorAll('#nav button').forEach(function(x){x.classList.remove('active')});
      document.querySelectorAll('.tab').forEach(function(x){x.classList.remove('active')});
      b.classList.add('active');
      var el=document.getElementById(b.dataset.tab); if(el)el.classList.add('active');
    };
  });
}

// ===== ТЕМА =====
function toggleTheme(){document.body.classList.toggle('light');localStorage.setItem('theme',document.body.classList.contains('light')?'light':'dark');}
function initTheme(){if(localStorage.getItem('theme')==='light')document.body.classList.add('light');}

// ===== МАГИЯ =====
var praises=['Ты прекрасен! ✨','Сегодня твой день! 🌟','Ты круче всех! 🔥','Галактика гордится тобой 🚀','Ты — чистая магия 💫','Ты справишься, я проверяла 🔮'];
function magic(){
  var c=['#1a2a6c','#42275a','#0f3443','#654ea3','#2193b0','#5f2c82','#16222a','#14532d'];
  document.body.style.background='linear-gradient(160deg,'+c[Math.floor(Math.random()*8)]+','+c[Math.floor(Math.random()*8)]+','+c[Math.floor(Math.random()*8)]+')';
  document.getElementById('magicOut').textContent=praises[Math.floor(Math.random()*praises.length)];
}

// ===== ГИРЛЯНДА =====
function initGarland(){
  var g=document.getElementById('garland');
  var colors=['#ef4444','#f59e0b','#facc15','#4ade80','#38bdf8','#a78bfa'];
  for(var i=0;i<28;i++){
    var b=document.createElement('div');b.className='bulb';
    b.style.background=colors[i%6];b.style.color=colors[i%6];
    b.style.animationDelay=(Math.random()*1.6).toFixed(2)+'s';
    b.style.animationDuration=(1.2+Math.random()*1.2).toFixed(2)+'s';
    g.appendChild(b);
  }
}

// ===== СНЕГ =====
var snowCv,sxCtx,flakes=[],snowShape=localStorage.getItem('snowShape')||'flake',snowBoost=1;
function resizeSnow(){snowCv.width=innerWidth;snowCv.height=innerHeight;}
function initSnow(){
  snowCv=document.getElementById('snow');sxCtx=snowCv.getContext('2d');
  resizeSnow();addEventListener('resize',resizeSnow);
  for(var i=0;i<130;i++)flakes.push({x:Math.random()*innerWidth,y:Math.random()*innerHeight,r:1+Math.random()*3,s:.5+Math.random()*1.6,a:Math.random()*6.28,spin:(Math.random()-.5)*.05});
  document.getElementById('shapeBtn').textContent=snowShape==='flake'?'❄':'⛄';
  snowLoop();
}
function drawFlakeShape(x,y,r,a){
  sxCtx.save();sxCtx.translate(x,y);sxCtx.rotate(a);
  sxCtx.strokeStyle='rgba(255,255,255,.85)';sxCtx.lineWidth=1;sxCtx.beginPath();
  for(var i=0;i<6;i++){
    sxCtx.moveTo(0,0);sxCtx.lineTo(0,-r);
    sxCtx.moveTo(0,-r*.55);sxCtx.lineTo(r*.32,-r*.82);
    sxCtx.moveTo(0,-r*.55);sxCtx.lineTo(-r*.32,-r*.82);
    sxCtx.rotate(Math.PI/3);
  }
  sxCtx.stroke();sxCtx.restore();
}
function snowLoop(){
  sxCtx.clearRect(0,0,snowCv.width,snowCv.height);
  for(var i=0;i<flakes.length;i++){
    var f=flakes[i];
    f.y+=f.s*snowBoost;f.a+=f.spin;
    if(f.y>snowCv.height){f.y=-12;f.x=Math.random()*snowCv.width;}
    if(snowShape==='circle'){
      sxCtx.beginPath();sxCtx.fillStyle='rgba(255,255,255,.8)';
      sxCtx.arc(f.x,f.y,f.r,0,6.283);sxCtx.fill();
    }else{drawFlakeShape(f.x,f.y,f.r*3.2,f.a);}
  }
  requestAnimationFrame(snowLoop);
}
function toggleShape(){
  snowShape=snowShape==='flake'?'circle':'flake';
  localStorage.setItem('snowShape',snowShape);
  document.getElementById('shapeBtn').textContent=snowShape==='flake'?'❄':'⛄';
}
function snowSalute(){snowBoost=3;setTimeout(function(){snowBoost=1;},5000);}

// ===== ОТСЧЁТ ДО НГ =====
function nyTick(){
  var now=new Date(),el=document.getElementById('nyCount');
  if(now.getMonth()===0&&now.getDate()===1){el.textContent='🎉 С Новым годом! Ура! 🎉';return;}
  var ny=new Date(now.getFullYear()+1,0,1,0,0,0);
  var diff=ny-now;
  var d=Math.floor(diff/86400000),h=Math.floor(diff/3600000)%24,m=Math.floor(diff/60000)%60,s=Math.floor(diff/1000)%60;
  el.innerHTML='До Нового года: '+d+' д '+h+' ч '+m+' мин '+s+' с ⏳';
}

// ===== КАЛЬКУЛЯТОР =====
var expr='';
function calc(v){
  if(v==='C')expr='';
  else if(v==='del')expr=expr.slice(0,-1);
  else if(v==='='){
    try{expr=String(Function('return('+expr.replace(/,/g,'.')+')')());}catch(e){expr='Ошибка';}
  }else expr+=v;
  document.getElementById('calcOut').textContent=expr||'0';
}

// ===== ДЕЛА =====
var todos=[];
function renderTodos(){
  var l=document.getElementById('todoList');l.innerHTML='';
  todos.forEach(function(t,i){
    var d=document.createElement('div');d.className='item'+(t.done?' done':'');
    d.innerHTML='<span onclick="toggleTodo('+i+')" style="cursor:pointer">'+t.text+'</span><button class="x" onclick="delTodo('+i+')">✕</button>';
    l.appendChild(d);
  });
  document.getElementById('todoStat').textContent='Всего: '+todos.length+', сделано: '+todos.filter(function(t){return t.done}).length;
}
function saveTodos(){localStorage.setItem('todos',JSON.stringify(todos));renderTodos();}
function addTodo(){var i=document.getElementById('todoIn');if(i.value.trim()){todos.push({text:i.value.trim(),done:false});i.value='';saveTodos();}}
function delTodo(i){todos.splice(i,1);saveTodos();}
function toggleTodo(i){todos[i].done=!todos[i].done;saveTodos();}

// ===== ЗАМЕТКИ =====
function initNotes(){document.getElementById('noteArea').value=localStorage.getItem('note')||'';saveNotes();}
function saveNotes(){var v=document.getElementById('noteArea').value;localStorage.setItem('note',v);document.getElementById('noteCount').textContent=v.length;}

// ===== ТАЙМЕР + КУРАНТЫ =====
var tLeft=0,tInt=null;
function startTimer(s){stopTimer();tLeft=s;document.getElementById('timerOut').textContent=fmt(s);tInt=setInterval(tick,1000);}
function fmt(t){return String(Math.floor(t/60)).padStart(2,'0')+':'+String(t%60).padStart(2,'0');}
function tick(){
  tLeft--;
  if(tLeft<=0){stopTimer(true);return;}
  document.getElementById('timerOut').textContent=fmt(tLeft);
}
function stopTimer(chime){
  clearInterval(tInt);tInt=null;
  document.getElementById('timerOut').textContent='00:00';
  if(chime&&document.getElementById('chimesOn').checked)playChime();
}
function toggleStop(){
  if(tInt){clearInterval(tInt);tInt=null;}
  else if(tLeft>0){tInt=setInterval(tick,1000);}
  else{tLeft=60;tInt=setInterval(tick,1000);}
}
function playChime(){
  try{
    var ac=new (window.AudioContext||window.webkitAudioContext)();
    var notes=[659,523,587,392,659,523,587,392,659,784,659,523,587,392];
    notes.forEach(function(f,i){
      var o=ac.createOscillator(),g=ac.createGain();
      o.type='sine';o.frequency.value=f;o.connect(g);g.connect(ac.destination);
      var t=ac.currentTime+i*.4;
      g.gain.setValueAtTime(0,t);
      g.gain.linearRampToValueAtTime(.3,t+.02);
      g.gain.exponentialRampToValueAtTime(.001,t+.38);
      o.start(t);o.stop(t+.42);
    });
  }catch(e){}
}
var swT=0,swInt=null;
function swStart(){
  clearInterval(swInt);swT=0;
  swInt=setInterval(function(){
    swT+=.1;
    document.getElementById('swOut').textContent=String(Math.floor(swT/60)).padStart(2,'0')+':'+String(Math.floor(swT%60)).padStart(2,'0')+'.'+Math.floor(swT*10%10);
  },100);
}
function swStop(){clearInterval(swInt);}

// ===== КОНТЕНТ =====
var jokes=[
'— Почему программисты путают Хэллоуин и Рождество? Потому что OCT 31 = DEC 25.',
'Программист ставит на тумбочку два стакана: полный — на случай если захочет пить, пустой — на случай если не захочет.',
'— Сколько программистов нужно, чтобы вкрутить лампочку? — Ни одного: это аппаратная проблема.',
'— Как дела? — Да как в коде: вроде работает, а трогать страшно.',
'Нормальный герой всегда идёт напролом. Ненормальный — всегда падает в… норм.',
'Есть только два типа задач: те, что решаются за пять минут, и те, что не решаются вообще.',
'Мой код не работает, и я не знаю почему. Мой код работает, и я тоже не знаю почему.',
'— Слушай, а как там у тебя с кредитами? — О, просто: 99 маленьких багов в коде, 99 маленьких багов…',
'— Доктор, я не могу заснуть! — Считайте до трёх. — До трёх? — Максимум до трёх: половина — это уже ночная смена.',
'Я не ленивый. Я в энергосберегающем режиме.',
'— Пап, а что такое дилемма? — Дилемма — это когда не знаешь, спасать кота или сначала снять видео.',
'Оптимист изучает английский, пессимист — китайский, а реалист — инструкцию к пульту.',
'Будильник — единственное устройство, которое прерывает самые интересные сны планеты.',
'— Ты чего такой грустный? — Компилятор ругается: 99 ошибок. — Показывай… ой, у тебя точка с запятой потерялась.',
'— Купил новую клавиатуру! — И как? — Не знаю, пока тестирую кнопку «пробел».',
'Лучшая диета: съесть всё до того, как об этом узнают весы.',
'— Что общего у понедельника и HTML? — Всё выглядит просто, пока не начинаешь с этим работать.',
'Гравитация — это не ответственность, это привычка: Земля просто привыкла крутиться.',
'— Почему ты не сделал домашку? — Сделал в уме. — А в тетрадь? — В тетрадь не влезет: там нет Wi-Fi.',
'Учёные выяснили: 99% людей откладывают дела на потом. Остальные 1% — тоже, но позже.',
'— Заходит Дед Мороз в IT-компанию… — И что? — Улыбается: подарки бонусами — пятого января.',
'Ёлочные гирлянды — единственная техника, которую чинят, просто пощёлкав по лампочкам. И это работает!',
'Мандаринки — новогодний лимит: съел больше десяти — уже не гостей, а соучастник.',
'— Кем ты работаешь? — Дед Морозом в декабре. — А в остальное время? — А в остальное время жду декабря.',
'— Как называются каникулы, которые продлили? — Каникулы. Просто без конца.',
'Снеговик пошёл в спортзал. Его приняли: «Кардио у вас уже есть — вы же таяли».',
'Оливье — это салат, который нельзя готовить в одиночестве: все должны помочь съесть тазик.',
'— Почему снегири зимой не мёрзнут? — Потому что красные грудки греют изнутри. Это наука, между прочим.',
'Часы пробили двенадцать. Хлопнули бокалы. Прозвучало: «А давай каждый месяц как этот!»… до третьего января.',
'— Что подарить на Новый год человеку, у которого всё есть? — Сон до обеда 1 января.'
];
var facts=[
'У осьминогов три сердца и голубая кровь.',
'Первый «компьютерный баг» был настоящим: в 1947 году из компьютера вытащили моль.',
'На МКС космонавты видят 16 рассветов и закатов в сутки.',
'Мёд не портится: археологи находили съедобный мёд возрастом в тысячи лет.',
'Бананы слабо радиоактивны из-за природного калия-40 — это безопасно.',
'Сердце синего кита бьётся примерно 10 раз в минуту.',
'Молния разогревает воздух примерно до 30 000 °C — в пять раз горячее поверхности Солнца.',
'Улитки умеют спать до трёх лет.',
'На Венере сутки длятся дольше, чем год.',
'Язык синего кита весит до трёх тонн — больше, чем слон.',
'Ацтеки платили какао-бобами: шоколад когда-то был валютой.',
'Первая компьютерная мышь была деревянной.',
'Стрекозы живут на планете больше 300 миллионов лет — они старше динозавров.',
'Снежинки всегда шестигранные — так устроена кристаллическая решётка льда.',
'Медузы почти на 95% состоят из воды.',
'Треть своей жизни человек проводит во сне.',
'Дрессированные крысы ищут мины и спасают жизни: крыса Магава получила медаль за отвагу.',
'Деревья «общаются» через корневую сеть грибов, передавая друг другу сигналы.',
'Внутрь Юпитера поместилось бы больше 1300 планет размером с Землю.',
'Первое SMS отправили в 1992 году — оно гласило «Merry Christmas».',
'Кошки мяукают в основном для людей: между собой они так почти не общаются.',
'Самая короткая война в истории длилась около 38 минут.',
'Акулы existed до появления деревьев: они древнее деревьев.',
'В Швейцарии нельзя держать морскую свинку одну — им нужна компания.',
'На МКС космонавты вырастают на несколько сантиметров из-за отсутствия гравитации.',
'Пингвины делают предложение «руки и крыла», принося избраннице самый красивый камешек.',
'Слово «алгоритм» произошло от имени математика аль-Хорезми.',
'Бамбук может расти быстрее метра в сутки.',
'Когда снег хрустит под ногами — это ломаются кристаллики льда.',
'Звезда Вифлеема по одной из гипотез была кометой или соединением планет.'
];
var memes=[
'«Лягу пораньше» — самая смешная шутка, которую ты сам себе рассказал.',
'Будильник: «Подъём!» Я: «А можно не сегодня?»',
'Открыл холодильник в третий раз за пять минут — а там всё то же самое.',
'План на день: всё сделать. Я: «а давай ещё одно видео».',
'Когда учитель сказал «это будет на контрольной» — и это единственное, что ты запомнил за год.',
'«Я подумаю об этом завтра» — каждый студент за ночь до сдачи.',
'Дедлайн сегодня? Значит, за час сделаешь то, что откладывал месяц.',
'Wi-Fi работает: 🌍. Wi-Fi лежит: 🧟.',
'«Я просто полежу пять минут» — легендарные последние слова.',
'Зашёл за хлебом — вышел с чипсами, мороженым и без хлеба.',
'Начал чистить телефон от фото и нашёл 2000 скриншотов «на потом».',
'Пн: новая жизнь! Вт: ну ладно, со следующего понедельника.',
'Когда попросили «просто быстро глянуть почту» на выходных.',
'«Тише, не дышите» — я ищу свои наушники, которые на мне.',
'Уровень взрослости: искренне радуешься новому мусорному ведру.',
'Лёг «на пять минут» днём — проснулся ночью в полных штанах непонимания.',
'Диета начнётся с понедельника. Понедельник отменён.',
'Пчёлы делают мёд. Мёд — это нектар плюс труд. Значит мёд — это нектар в квадрате? (Мышление в 3 часа ночи.)',
'Когда мандарины доели, а Новый год ещё не наступил: тревога на физиологическом уровне.',
'Оливье в тазике на третий день — это уже не салат, а член семьи.'
];
var verses=[
'Ёлочка, ёлочка, колкая иголочка — где ты взяла столько света? Наверное, у Нового года это пособие.',
'Мандарины на тарелке, снег летит за окном — я сижу и жду подарков, тихо, мирно, с холодным чаем и потом…',
'Дед Мороз, скажи на милость: где мой подарок за труды? Я весь год себя не жалел(а) — почти весь год, почти. Увы.',
'Снег кружится, снег искрится, гирлянда подмигивает мне: «Дерзай, мечтай — и всё случится!» Ну, хотя бы по одной. Хоть во сне.',
'Куранты бьют двенадцать, и оливье дрожит в тазу: начинается самое главное — салат уходит к годовому визиту деда-мороза в тазу.',
'Снежинка на варежке — звёздочка шестигранная: природа — лучший дизайнер, и это не оспаривается.',
'Год уходит на цыпочках, год грядёт на каблуках: посреди зимней переклички мы зажигаем в ёлках огоньки.',
'Час до боя, час до чуда: стол накрыт, салат стоит. Даже кот уселся важно — он сегодня босс-оливье.'
];
var quiz=[
{q:'Сколько сердец у осьминога?',o:['Одно','Три','Четыре'],a:1},
{q:'Кто такой «первый компьютерный баг»?',o:['Моль','Жук-короед','Мышь'],a:0},
{q:'Сколько рассветов в сутки видят космонавты на МКС?',o:['1','8','16'],a:2},
{q:'Какой формы снежинки?',o:['Круглые','Шестигранные','Квадратные'],a:1},
{q:'Какое слово произошло от имени аль-Хорезми?',o:['Алгебра','Алгоритм','Атлас'],a:1},
{q:'Что гласило первое SMS в истории?',o:['Hello world','Merry Christmas','Привет'],a:1},
{q:'Сколько длится самая короткая война в истории?',o:['38 минут','3 часа','2 дня'],a:0},
{q:'Кто древнее?',o:['Акулы','Динозавры','Деревья'],a:0},
{q:'Как медузы спасаются от хищников?',o:['Маскируются под камни','Прозрачны и на 95% вода','Светятся'],a:1},
{q:'Как пингвины делают предложение?',o:['Пением','Камешком','Танцем'],a:1},
{q:'Где сутки длиннее года?',o:['Меркурий','Венера','Марс'],a:1},
{q:'Что чаще всего лежит в новогоднем оливье?',o:['Ананасы','Картошка','Апельсины'],a:1},
{q:'Сколько сердец у дождевого червя?',o:['Ни одного','Пять','Десять'],a:1},
{q:'Какая планета самая большая в Солнечной системе?',o:['Сатурн','Юпитер','Нептун'],a:1},
{q:'Кто разучил «мяу» специально для людей?',o:['Собаки','Кошки','Попугаи'],a:1}
];
function renderQuiz(){
  var l=document.getElementById('quizList');l.innerHTML='';qScore=0;qDone=0;updateQScore();
  quiz.forEach(function(item){
    var d=document.createElement('div');d.className='quizItem';
    d.innerHTML='<p>'+item.q+'</p>';
    item.o.forEach(function(opt,j){
      var b=document.createElement('button');b.className='opt';b.textContent=opt;
      b.onclick=function(){
        if(d.dataset.done)return;d.dataset.done='1';qDone++;
        if(j===item.a){b.classList.add('right');qScore++;}
        else{b.classList.add('wrong');d.querySelectorAll('.opt')[item.a].classList.add('right');}
        updateQScore();
      };
      d.appendChild(b);
    });
    l.appendChild(d);
  });
}
function updateQScore(){document.getElementById('quizScore').textContent='Очки: '+qScore+' из '+quiz.length+' (отвечено: '+qDone+')';}
function resetQuiz(){renderQuiz();}
var qScore=0,qDone=0;

// ===== ИГРЫ =====
function rollDice(){
  var n=1+Math.floor(Math.random()*6);
  document.getElementById('diceOut').textContent=['⚀','⚁','⚂','⚃','⚄','⚅'][n-1]+' = '+n;
}
function flipCoin(){
  document.getElementById('coinOut').textContent=Math.random()<.5?'Орёл! 🦅':'Решка! 🪙';
}
function rndNum(){
  var a=+document.getElementById('rndFrom').value,b=+document.getElementById('rndTo').value;
  if(isNaN(a)||isNaN(b)||b<a){document.getElementById('rndOut').textContent='Проверь границы: «до» должно быть больше «от»';return;}
  document.getElementById('rndOut').textContent='Выпало: '+(a+Math.floor(Math.random()*(b-a+1)));
}
var secret=0,tries=0;
function newSecret(){secret=1+Math.floor(Math.random()*100);tries=0;}
function guess(){
  var g=+document.getElementById('guessIn').value,out=document.getElementById('guessOut');
  if(!g)return;tries++;
  if(g<secret)out.textContent='⬆️ Больше! Попытка '+tries;
  else if(g>secret)out.textContent='⬇️ Меньше! Попытка '+tries;
  else{out.textContent='🎉 Угадал за '+tries+' попыток! Загадал новое';newSecret();}
  document.getElementById('guessIn').value='';
}
var beats={'✊':'✌️','✌️':'✋','✋':'✊'};
function rps(u){
  var c=['✊','✌️','✋'][Math.floor(Math.random()*3)];
  document.getElementById('rpsOut').textContent='Ты: '+u+' · ИИ: '+c+' — '+(u===c?'Ничья! 🤝':beats[u]===c?'Ты победил! 🎉':'ИИ победил 😎');
}

// ===== РИСОВАЛКА =====
var cv,cx,color='#2c3e50',drawing=false,lastP=null;
function initPaint(){
  cv=document.getElementById('paint');cx=cv.getContext('2d');
  cx.fillStyle='#fff';cx.fillRect(0,0,cv.width,cv.height);cx.lineCap='round';
  var cols=['#2c3e50','#e74c3c','#e67e22','#f1c40f','#2ecc71','#3498db','#9b59b6','#000','#fff'];
  var pal=document.getElementById('palette');
  cols.forEach(function(c,i){
    var d=document.createElement('div');d.style.background=c;
    if(i===0)d.classList.add('sel');
    d.onclick=function(){color=c;pal.querySelectorAll('div').forEach(function(x){x.classList.remove('sel')});d.classList.add('sel');};
    pal.appendChild(d);
  });
  cv.addEventListener('mousedown',down);cv.addEventListener('mousemove',move);
  addEventListener('mouseup',function(){drawing=false});
  cv.addEventListener('touchstart',down);cv.addEventListener('touchmove',move);
  addEventListener('touchend',function(){drawing=false});
}
function pos(e){
  var r=cv.getBoundingClientRect(),t=e.touches?e.touches[0]:e;
  return{x:(t.clientX-r.left)*cv.width/r.width,y:(t.clientY-r.top)*cv.height/r.height};
}
function down(e){drawing=true;lastP=pos(e);e.preventDefault();}
function move(e){
  if(!drawing)return;
  var p=pos(e);
  cx.strokeStyle=color;cx.lineWidth=innerWidth<600?4:3;
  cx.beginPath();cx.moveTo(lastP.x,lastP.y);cx.lineTo(p.x,p.y);cx.stroke();
  lastP=p;e.preventDefault();
}
function clearPaint(){cx.fillStyle='#fff';cx.fillRect(0,0,cv.width,cv.height);}
function saveImg(){var a=document.createElement('a');a.download='рисунок.png';a.href=cv.toDataURL();a.click();}

// ===== ПАРОЛИ =====
var lastPass='';
function genPass(){
  var len=+document.getElementById('passLen').value;
  var chars='abcdefghijkmnopqrstuvwxyz';
  if(document.getElementById('pUpper').checked)chars+='ABCDEFGHJKLMNPQRSTUVWXYZ';
  if(document.getElementById('pDigits').checked)chars+='23456789';
  if(document.getElementById('pSpec').checked)chars+='!@#$%&*?+-=';
  var out='';
  for(var i=0;i<len;i++)out+=chars[Math.floor(Math.random()*chars.length)];
  lastPass=out;
  document.getElementById('passOut').textContent=out;
}
function copyPass(){
  if(!lastPass)return;
  if(navigator.clipboard)navigator.clipboard.writeText(lastPass);
  else{var t=document.createElement('textarea');t.value=lastPass;document.body.appendChild(t);t.select();document.execCommand('copy');t.remove();}
  document.getElementById('passOut').textContent='Скопировано ✅';
  setTimeout(function(){document.getElementById('passOut').textContent=lastPass;},1200);
}

// ===== КОНВЕРТЕР =====
var convData={
  len:{u:{'км':1000,'м':1,'см':0.01,'миля':1609.344,'фут':0.3048,'дюйм':0.0254}},
  mass:{u:{'кг':1,'г':0.001,'т':1000,'фунт':0.45359237,'унция':0.0283495}},
  vol:{u:{'л':1,'мл':0.001,'м³':1000,'галлон':3.785412,'пинта':0.473176}},
  speed:{u:{'км/ч':1,'м/с':3.6,'миля/ч':1.609344,'узел':1.852}},
  area:{u:{'м²':1,'км²':1000000,'гектар':10000,'сотка':100}},
  temp:{special:true}
};
function fillConv(){
  var cat=document.getElementById('convCat').value;
  var f=document.getElementById('convFrom'),t=document.getElementById('convTo');
  f.innerHTML='';t.innerHTML='';
  var units=convData[cat].special?['°C','°F','K']:Object.keys(convData[cat].u);
  units.forEach(function(u){f.add(new Option(u,u));t.add(new Option(u,u));});
  t.selectedIndex=1;
  convert();
}
function toC(v,from){return from==='°C'?v:from==='°F'?(v-32)*5/9:v-273.15;}
function fromC(c,to){return to==='°C'?c:to==='°F'?c*9/5+32:c+273.15;}
function convert(){
  var cat=document.getElementById('convCat').value;
  var v=parseFloat((document.getElementById('convVal').value||'').replace(',','.'));
  var from=document.getElementById('convFrom').value,to=document.getElementById('convTo').value;
  var out=document.getElementById('convOut');
  if(isNaN(v)){out.textContent='—';return;}
  var res;
  if(convData[cat].special)res=fromC(toC(v,from),to);
  else res=v*convData[cat].u[from]/convData[cat].u[to];
  out.textContent=res.toLocaleString('ru-RU',{maximumFractionDigits:6})+' '+to;
}

// ===== ДНЕВНИК =====
var diary={};
function saveDiaryEntry(){
  var d=new Date().toISOString().slice(0,10);
  var t=document.getElementById('diaryIn').value.trim();
  if(!t)return;
  diary[d]=t;localStorage.setItem('diary',JSON.stringify(diary));
  document.getElementById('diaryIn').value='';
  renderDiary();
}
function renderDiary(){
  var l=document.getElementById('diaryList');l.innerHTML='';
  var dates=Object.keys(diary).sort().reverse();
  if(!dates.length){l.innerHTML='<p class="hint">Пока пусто. Напиши что-нибудь за сегодня 🙂</p>';return;}
  dates.forEach(function(d){
    var div=document.createElement('details');div.className='diaryItem';
    div.innerHTML='<summary>'+d+'</summary><p>'+diary[d].replace(/</g,'&lt;').replace(/\n/g,'<br>')+'</p>';
    l.appendChild(div);
  });
}

// ===== БЮДЖЕТ =====
var budget=[];
function renderBudget(){
  var l=document.getElementById('budgetList');l.innerHTML='';var bal=0;
  budget.forEach(function(b,i){
    bal+=b.type==='in'?b.amt:-b.amt;
    var d=document.createElement('div');d.className='item '+(b.type==='in'?'income':'expense');
    d.innerHTML='<span>'+b.text+'</span><b>'+(b.type==='in'?'+':'−')+b.amt+' ₽</b><button class="x" onclick="delBudget('+i+')">✕</button>';
    l.appendChild(d);
  });
  var el=document.getElementById('budgetBal');
  el.textContent='Баланс: '+bal+' ₽';
  el.style.color=bal>=0?'#4ade80':'#f87171';
}
function addBudget(type){
  var t=document.getElementById('budgetText'),a=document.getElementById('budgetAmt');
  var amt=parseFloat((a.value||'').replace(',','.'));
  if(!t.value.trim()||!amt)return;
  budget.push({type:type,text:t.value.trim(),amt:Math.abs(amt)});
  t.value='';a.value='';
  localStorage.setItem('budget',JSON.stringify(budget));
  renderBudget();
}
function delBudget(i){budget.splice(i,1);localStorage.setItem('budget',JSON.stringify(budget));renderBudget();}

// ===== ЧАТ-БОТ =====
function botReply(raw){
  var t=raw.toLowerCase();
  if(t.indexOf('меня зовут')!==-1||t.indexOf('моё имя')!==-1){
    var name=raw.split(/зовут|имя/)[1];
    if(name){name=name.trim().split(' ')[0];localStorage.setItem('username',name);return 'Приятно познакомиться, '+name+'! 🎅 Запомнил тебя.';}
  }
  if(t.indexOf('запомни:')!==-1||t.indexOf('запомни ')===0){
    var mem=raw.replace(/.*запомни:?\s*/i,'');
    if(mem){localStorage.setItem('memo_'+Date.now(),mem);return 'Запомнил: '+mem+' 📝';}
  }
  if(t.indexOf('что ты помнишь')!==-1){
    var parts=[];
    if(localStorage.getItem('username'))parts.push('тебя зовут '+localStorage.getItem('username'));
    Object.keys(localStorage).forEach(function(k){
      if(k.indexOf('memo_')===0)parts.push(localStorage.getItem(k));
    });
    return parts.length?'Я помню: '+parts.join('; '):'Пока ничего не запоминал. Скажи «меня зовут …» или «запомни: …»';
  }
  if(t.indexOf('привет')!==-1||t.indexOf('здравств')!==-1)return 'Привет! 🎄 Снег идёт, настроение праздничное. Чем помочь?';
  if(t.indexOf('как дела')!==-1)return 'Отлично! Гирлянды мигают, снежинки падают — жизнь удалась ❄';
  if(t.indexOf('шутк')!==-1||t.indexOf('анекдот')!==-1)return jokes[Math.floor(Math.random()*jokes.length)];
  if(t.indexOf('факт')!==-1)return facts[Math.floor(Math.random()*facts.length)];
  if(t.indexOf('мем')!==-1)return memes[Math.floor(Math.random()*memes.length)];
  if(t.indexOf('стиш')!==-1||t.indexOf('стих')!==-1)return verses[Math.floor(Math.random()*verses.length)];
  if(t.indexOf('подбодр')!==-1||t.indexOf('грустн')!==-1)return praises[Math.floor(Math.random()*praises.length)];
  if(t.indexOf('время')!==-1)return 'Сейчас '+new Date().toLocaleTimeString('ru-RU');
  if(t.indexOf('дата')!==-1)return 'Сегодня '+new Date().toLocaleDateString('ru-RU',{weekday:'long',day:'numeric',month:'long',year:'numeric'});
  if(t.indexOf('новый год')!==-1||t.indexOf('нг')!==-1){
    var now=new Date(),ny=new Date(now.getFullYear()+1,0,1);
    var d=Math.floor((ny-now)/86400000);
    return now.getMonth()===0&&now.getDate()===1?'С Новым годом! 🎉 Осталось только доесть оливье.':'До Нового года осталось '+d+' дней ⏳';
  }
  if(/^[\d\s.,()+\-*/]+$/.test(t)&&/\d/.test(t)){
    try{
      var res=Function('return('+t.replace(/,/g,'.')+')')();
      return 'Считаю: '+t+' = '+res+' 🧮';
    }catch(e){}
  }
  if(t.indexOf('спасибо')!==-1)return 'Всегда пожалуйста! 🎅';
  if(t.indexOf('пока')!==-1)return 'До встречи! Снег не тает, гирлянды не гаснут ❄';
  var small=['Расскажи подробнее! А я пока подкину факт: '+facts[Math.floor(Math.random()*facts.length)],'Интересно! Кстати: '+jokes[Math.floor(Math.random()*jokes.length)],'Хм, звучит загадочно ✨ Спроси меня про «факт», «шутку», «мем» или «время»!'];
  return small[Math.floor(Math.random()*small.length)];
}
function addMsg(text,who){
  var d=document.createElement('div');d.className='msg '+who;d.textContent=text;
  chatLog.appendChild(d);chatLog.scrollTop=chatLog.scrollHeight;
}
var chatLog;
function sendChat(){
  var inp=document.getElementById('chatIn'),v=inp.value.trim();
  if(!v)return;
  addMsg(v,'me');inp.value='';
  var typing=document.createElement('div');typing.className='msg bot';typing.textContent='…';
  chatLog.appendChild(typing);chatLog.scrollTop=chatLog.scrollHeight;
  setTimeout(function(){typing.remove();addMsg(botReply(v),'bot');},600+Math.random()*700);
}

// ===== ЗАПУСК =====
initTabs();initTheme();initGarland();initSnow();nyTick();setInterval(nyTick,1000);
try{todos=JSON.parse(localStorage.getItem('todos')||'[]');renderTodos();}catch(e){}
try{initNotes();}catch(e){}
try{newSecret();}catch(e){}
try{renderQuiz();}catch(e){}
try{initPaint();}catch(e){}
try{diary=JSON.parse(localStorage.getItem('diary')||'{}');renderDiary();}catch(e){}
try{budget=JSON.parse(localStorage.getItem('budget')||'[]');renderBudget();}catch(e){}
try{chatLog=document.getElementById('chatLog');addMsg('Привет! 🎅 Тут уютно: снег идёт, гирлянды мигают, ёлочки стоят. Всё сохраняется в браузере — закрывай и возвращайся.','bot');}catch(e){}
try{fillConv();}catch(e){}
try{genPass();}catch(e){}
</script>
</body>
</html>
