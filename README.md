
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Banco Gratidão v2.0 - Áudio + Texto</title>
<style>
body{font-family:system-ui;background:#0f0f0f;color:#fff;margin:0;padding:16px}
h1{color:#facc15;text-align:center;margin:10px 0}
.card{background:#1a1a1a;border-radius:16px;padding:16px;margin:12px 0;border:1px solid #333}
button{background:#facc15;color:#000;border:none;padding:14px 18px;border-radius:10px;font-weight:bold;width:100%;margin:6px 0;font-size:16px}
input,textarea{width:100%;background:#222;color:#fff;border:1px solid #444;border-radius:8px;padding:12px;margin:6px 0;box-sizing:border-box;font-size:15px}
audio{width:100%;margin-top:8px}
.saldo{font-size:28px;text-align:center;color:#4ade80;font-weight:bold}
</style>
</head>
<body><div style="display:flex;justify-content:center;gap:8px;margin:10px 0;flex-wrap:wrap">
<button onclick="location.href='https://bancogratidaooficial-ops.github.io/Gratidao-Sonora/'" style="background:#FFD700;color:#000;border:none;padding:10px 16px;border-radius:20px;font-weight:bold">🎵 Sonora</button>
<button onclick="location.href='https://bancogratidaooficial-ops.github.io/BANCO-GRATIDAO/'" style="background:#fff;color:#000;border:none;padding:10px 16px;border-radius:20px;font-weight:bold">🏦 Banco</button>
<button onclick="location.href='https://bancogratidaooficial-ops.github.io/Bem-vindo-/'" style="background:#fff;color:#000;border:none;padding:10px 16px;border-radius:20px;font-weight:bold">👋 Bem-vindo</button>
</div>
<h1>Banco Gratidão v2.0</h1>
<div class="card"><div class="saldo">R$ 1.247,33</div><div style="text-align:center;opacity:.7">Projeto Gratidão - Barco</div></div>

<div class="card">
<h3>Nova Gratidão</h3>
<textarea id="texto" rows="3" placeholder="Ex: Hoje vendi 2 passeios, obrigado!"></textarea>
<button onclick="salvarTexto()">Salvar Texto</button>
<hr style="border-color:#333;margin:14px 0">
<button id="recBtn" onclick="gravarAudio()">🎙️ Gravar Áudio de Gratidão</button>
<div id="statusAudio" style="text-align:center;margin-top:8px;opacity:.8"></div>
</div>

<div class="card">
<h3>Histórico v2.0</h3>
<div id="lista"></div>
</div>

<div class="card" style="text-align:center;font-size:12px;opacity:.6">
PIX: 41998936718<br>CONTROLE INTERNO - Uso Pessoal
</div>

<script>
let gratidoes = JSON.parse(localStorage.getItem('bancoGratidao_v2')||'[]');
let mediaRecorder, audioChunks=[];
function atualizarLista(){
 let html='';
 gratidoes.slice().reverse().forEach((g)=>{
  html+=`<div style="border-bottom:1px solid #333;padding:10px 0">
  <b>${g.data}</b> - ${g.tipo}<br>${g.texto||''}
  ${g.audio?`<audio controls src="${g.audio}"></audio>`:''}
  </div>`;
 });
 document.getElementById('lista').innerHTML = html||'Nenhuma gratidão ainda.';
}
function salvarTexto(){
 const txt = document.getElementById('texto').value.trim();
 if(!txt){alert('Escreva algo!');return}
 gratidoes.push({data:new Date().toLocaleString(),tipo:'TEXTO',texto:txt});
 localStorage.setItem('bancoGratidao_v2',JSON.stringify(gratidoes));
 document.getElementById('texto').value='';
 atualizarLista();
}
async function gravarAudio(){
 const btn = document.getElementById('recBtn');
 const status = document.getElementById('statusAudio');
 if(mediaRecorder && mediaRecorder.state=='recording'){
   mediaRecorder.stop();
   btn.textContent='🎙️ Gravar Áudio de Gratidão';
   status.textContent='';
   return;
 }
 try{
  const stream = await navigator.mediaDevices.getUserMedia({audio:true});
  mediaRecorder = new MediaRecorder(stream);
  audioChunks=[];
  mediaRecorder.ondataavailable=e=>audioChunks.push(e.data);
  mediaRecorder.onstop=()=>{
    const blob = new Blob(audioChunks,{type:'audio/webm'});
    const reader = new FileReader();
    reader.onload=()=>{
      gratidoes.push({data:new Date().toLocaleString(),tipo:'ÁUDIO',texto:'Gratidão em áudio',audio:reader.result});
      localStorage.setItem('bancoGratidao_v2',JSON.stringify(gratidoes));
      atualizarLista();
    };
    reader.readAsDataURL(blob);
  };
  mediaRecorder.start();
  btn.textContent='Parar Gravação';
  status.textContent='Gravando... fale sua gratidão';
 }catch(e){alert('Permita o microfone!')}
}
atualizarLista();
</script>
</body>
</html>
