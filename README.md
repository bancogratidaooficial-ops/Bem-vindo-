<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BANCO GRATIDÃO OFICIAL</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{background:#0a0a0a;color:#fff;font-family:system-ui,sans-serif;min-height:100vh}
.header{padding:25px;text-align:center;background:linear-gradient(180deg,#1a1a1a,#000);border-bottom:1px solid #222}
.header h1{font-size:28px}
.header p{color:#8a8a8a;margin-top:6px;font-size:13px}
.container{max-width:500px;margin:0 auto;padding:20px}
.card{background:#17171a;border:1px solid #2a2a2a;border-radius:24px;padding:22px;margin-bottom:16px}
.btn-main{width:100%;padding:22px;border-radius:20px;border:0;font-size:18px;font-weight:800;cursor:pointer;display:flex;justify-content:space-between;text-align:left;margin-bottom:14px}
.btn1{background:#fff;color:#000} .btn2{background:#820ad1;color:#fff} .btn3{background:#00d26a;color:#000}
.btn-sub{width:100%;padding:16px;border-radius:14px;border:1px solid #333;background:#212124;color:#fff;font-size:15px;margin-top:10px;cursor:pointer;text-align:left}
.btn-sub.ativo{background:#fff;color:#000;font-weight:bold}
.btn-action{background:#820ad1;color:#fff;border:0;width:100%;padding:18px;border-radius:14px;font-weight:800;font-size:16px;margin-top:18px;cursor:pointer}
.input{width:100%;padding:16px;border-radius:12px;border:1px solid #333;background:#111;color:#fff;margin-top:10px;font-size:15px}
.view{display:none} .view.ativa{display:block}
.topbar{display:flex;align-items:center;gap:12px;margin-bottom:20px}
.back{width:40px;height:40px;border-radius:12px;background:#222;border:1px solid #333;color:#fff;font-size:20px}
.saldo{font-size:42px;font-weight:900;margin:10px 0}
.pix-grid{display:grid;grid-template-columns:1fr 1fr 1fr 1fr;gap:10px;margin:18px 0}
.pix-item{background:#212124;border:1px solid #333;border-radius:18px;padding:14px 5px;text-align:center;font-size:12px;cursor:pointer}
.tag{background:#00d26a;color:#000;font-size:11px;padding:4px 8px;border-radius:20px;font-weight:800;display:inline-block;margin-bottom:8px}
.invite-box{background:linear-gradient(135deg,#820ad1,#4a0080);border-radius:20px;padding:20px;text-align:center}
.link-box{background:#000;border:1px dashed #444;padding:12px;border-radius:10px;margin:12px 0;color:#aaa;font-size:13px;word-break:break-all}
.pix-key{background:#000;border:1px solid #00d26a;color:#00d26a;padding:12px;border-radius:10px;margin:10px 0;text-align:center;font-weight:bold;letter-spacing:1px}
</style>
</head>
<body>
<div class="header"><h1>BANCO GRATIDÃO</h1><p>Banco Oficial • Pix Mercado Pago • 41 99893-6718</p></div>
<div class="container">

<div id="home" class="view ativa">
<div class="card">
<p style="color:#888;font-size:13px;margin-bottom:14px">ESCOLHA UMA OPÇÃO</p>
<button class="btn-main btn1" onclick="abrir('msg')">💬 Abrir Conta de Mensagens <span>→</span></button>
<button class="btn-main btn2" onclick="abrir('banco')">🏦 Entrar no Banco Real <span>→</span></button>
<button class="btn-main btn3" onclick="abrir('convite')">🎁 Convidar e Ganhar R$3 <span>→</span></button>
</div>
</div>

<div id="msg" class="view">
<div class="topbar"><button class="back" onclick="abrir('home')">‹</button><b>Conta de Mensagens</b></div>
<div class="card">
<h3>Como quer receber?</h3>
<button class="btn-sub" onclick="setMsg(this,'audio')">🎙️ Mensagens em ÁUDIO</button>
<button class="btn-sub" onclick="setMsg(this,'texto')">💬 Mensagens em TEXTO</button>
<button class="btn-sub" onclick="setMsg(this,'ambos')">🔊💬 ÁUDIO + TEXTO</button>
<button class="btn-action" onclick="salvarMsg()">Salvar Preferência</button>
<p id="msgOk" style="display:none;color:#00d26a;text-align:center;margin-top:12px;font-weight:bold">✅ Salvo! Você vai receber diariamente.</p>
</div>
</div>

<div id="banco" class="view">
<div class="topbar"><button class="back" onclick="abrir('home')">‹</button><b>Banco Gratidão Real</b></div>
<div id="cadastro" class="card">
<span class="tag">CADASTRO SEGURO</span>
<h3>Crie sua conta digital</h3>
<input class="input" id="nome" placeholder="Nome completo">
<input class="input" id="cpf" placeholder="CPF">
<input class="input" placeholder="RG ou CNH">
<input class="input" placeholder="WhatsApp">
<input class="input" type="file"><p style="color:#666;font-size:11px;margin-top:6px">Foto do documento</p>
<button class="btn-action" onclick="abrirBanco()">Criar Conta e Entrar →</button>
</div>

<div id="bancoReal" style="display:none">
<div class="card" style="background:#820ad1;border:0">
<p style="opacity:.8;font-size:13px">Saldo disponível</p>
<div class="saldo">R$ 1.247,83</div>
<p style="opacity:.8;font-size:12px">Ag: 0001 • Conta: 887412-3</p>
<p style="opacity:.8;font-size:12px;margin-top:4px" id="nomeBanco">Titular: Banco Gratidão</p>
</div>
<div class="card">
<h4>Pix Mercado Pago</h4>
<div class="pix-key">CHAVE PIX: (41) 99893-6718</div>
<p style="color:#888;font-size:12px;text-align:center">Banco Gratidão Oficial • Recebimentos via Mercado Pago</p>
<div class="pix-grid">
<div class="pix-item" onclick="pix('enviar')">💸<br>Enviar</div>
<div class="pix-item" onclick="pix('receber')">📥<br>Receber</div>
<div class="pix-item" onclick="alert('QR Code Pix gerado para (41) 99893-6718')">🔳<br>QR Code</div>
<div class="pix-item" onclick="alert('Link Mercado Pago: mpago.la/bancogratidao-'+Date.now())">🔗<br>Link MP</div>
</div>
<button class="btn-action" style="background:#fff;color:#000" onclick="copiarPix()">📋 Copiar Chave Pix (41) 99893-6718</button>
<button class="btn-sub" onclick="alert('Chave Pix copiada! Cole no seu banco para fazer um Pix para o Banco Gratidão')">Gerar Código Copia e Cola Mercado Pago</button>
</div>
<div class="card"><h4>Extrato</h4><p style="margin-top:10px;font-size:14px">✅ Pix recebido - R$ 250,00 - via Mercado Pago</p><p style="font-size:14px;color:#888;margin-top:8px">✅ Recompensa - R$ 3,00 - Convite</p></div>
</div>
</div>

<div id="convite" class="view">
<div class="topbar"><button class="back" onclick="abrir('home')">‹</button><b>Convidar e Ganhar</b></div>
<div class="invite-box">
<h2>GANHE R$ 3 POR AMIGO</h2>
<p style="margin:10px 0;opacity:.9">Quando ele abrir a conta, você ganha na hora via Pix (41) 99893-6718</p>
<div class="link-box" id="linkConvite">https://bancogratidaooficial-ops.github.io/BANCO-GRATIDAO/?convite=GRATIDAO3</div>
<button class="btn-action" style="background:#fff;color:#820ad1" onclick="copiar()">Copiar Link e Compartilhar</button>
</div>
<div class="card" style="margin-top:16px">
<h4>Suas recompensas</h4>
<p style="margin-top:10px">👥 3 amigos convidados</p>
<p>💰 R$ 9,00 ganhos (3 x R$ 3,00)</p>
<p style="color:#888;font-size:13px;margin-top:8px">Pagamento via Pix Mercado Pago para sua chave cadastrada. Chave do banco: 41 99893-6718</p>
</div>
</div>

</div>
<script>
function abrir(id){document.querySelectorAll('.view').forEach(v=>v.classList.remove('ativa'));document.getElementById(id).classList.add('ativa');window.scrollTo(0,0)}
function setMsg(el,t){document.querySelectorAll('#msg .btn-sub').forEach(b=>b.classList.remove('ativo'));el.classList.add('ativo');localStorage.setItem('tipoMsg',t)}
function salvarMsg(){if(!localStorage.getItem('tipoMsg')){alert('Escolha uma opção');return}document.getElementById('msgOk').style.display='block'}
function abrirBanco(){
let n=document.getElementById('nome').value||'Cliente';document.getElementById('nomeBanco').innerText='Titular: '+n;
document.getElementById('cadastro').style.display='none';document.getElementById('bancoReal').style.display='block';
}
function copiarPix(){navigator.clipboard.writeText('41998936718');alert('Chave Pix 41 99893-6718 copiada!');}
function pix(t){if(t=='receber'){copiarPix()}else{alert('Para enviar Pix, use a chave (41) 99893-6718 no seu banco ou Mercado Pago')}}
function copiar(){navigator.clipboard.writeText(document.getElementById('linkConvite').innerText);alert('Link copiado! Ganhe R$3 por amigo');}
</script>
</body>
</html><button onclick="window.print()">Salvar Comprovante / Autenticação</button>
