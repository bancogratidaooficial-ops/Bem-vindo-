<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Banco Gratidão - Bem-vindo</title>
<script src="https://sdk.mercadopago.com/js/v2"></script>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family: Inter, sans-serif}
body{background:#111;color:#fff;min-height:100vh}
.container{max-width:420px;margin:0 auto;padding:20px}
.header{text-align:center;padding:30px 0}
.logo{font-size:32px;font-weight:800;color:#8A05BE}
.card{background:#1c1c1e;border-radius:16px;padding:20px;margin-bottom:16px}
.btn{width:100%;padding:16px;border:none;border-radius:12px;font-size:16px;font-weight:700;cursor:pointer;margin-top:12px}
.btn-primary{background:#8A05BE;color:#fff}
.btn-dark{background:#2c2c2e;color:#fff}
.btn-outline{background:transparent;border:1px solid #8A05BE;color:#8A05BE}
.hidden{display:none}
.input{width:100%;padding:14px;border-radius:10px;border:1px solid #333;background:#2c2c2e;color:#fff;margin-top:10px}
.pix-key{background:#2c2c2e;padding:12px;border-radius:10px;text-align:center;margin:10px 0;font-weight:bold;color:#00E676}
.saldo{font-size:32px;font-weight:800;margin:10px 0}
</style>
</head>
<body>
<div class="container">

<div id="tela-inicial">
<div class="header">
<div class="logo">BANCO GRATIDÃO</div>
<p>Escolha uma opção para continuar</p>
</div>

<button class="btn btn-primary" onclick="abrirTela('tela-mensagens')">1 - Abrir Conta de Mensagens</button>
<button class="btn btn-primary" onclick="abrirTela('tela-cadastro')">2 - Entrar no Banco Gratidão Real</button>
<button class="btn btn-primary" onclick="abrirTela('tela-convite')">3 - Convidar Membros e Ganhar R$3</button>

<div class="card" style="margin-top:20px">
<p style="font-size:13px;color:#aaa">Pix oficial: 41 99893-6718 - Mercado Pago</p>
</div>
</div>

<div id="tela-mensagens" class="hidden">
<h2>Como quer receber?</h2>
<button class="btn btn-dark" onclick="alert('Ativado: Receber em ÁUDIO')">Receber em Áudio</button>
<button class="btn btn-dark" onclick="alert('Ativado: Receber em TEXTO')">Receber em Texto</button>
<button class="btn btn-dark" onclick="alert('Ativado: Receber em AMBAS')">Receber em Áudio + Texto</button>
<button class="btn btn-outline" onclick="abrirTela('tela-inicial')">Voltar</button>
</div>

<div id="tela-cadastro" class="hidden">
<h2>Cadastro - Banco Real</h2>
<div class="card">
<input class="input" placeholder="Nome completo">
<input class="input" placeholder="CPF">
<input class="input" placeholder="RG / CNH">
<input class="input" type="file" id="doc">
<p style="font-size:12px;color:#aaa;margin-top:8px">Envie foto do documento</p>
<button class="btn btn-primary" onclick="abrirTela('tela-banco')">Criar Conta Gratidão</button>
</div>
<button class="btn btn-outline" onclick="abrirTela('tela-inicial')">Voltar</button>
</div>

<div id="tela-banco" class="hidden">
<div class="header"><div class="logo">Nubank Style</div></div>
<div class="card">
<p>Saldo disponível</p>
<div class="saldo">R$ 0,00</div>
</div>
<div class="card">
<h3>Área Pix</h3>
<div class="pix-key" id="pixkey">Chave: 41 99893-6718</div>
<button class="btn btn-dark" onclick="copiarPix()">Copiar Chave Pix</button>
<button class="btn btn-primary" onclick="pagarMercadoPago()">Receber via Mercado Pago</button>
<button class="btn btn-dark" onclick="alert('Pix enviado! (simulação)')">Fazer Pix</button>
<div id="mp-checkout" style="margin-top:15px"></div>
</div>
<button class="btn btn-outline" onclick="abrirTela('tela-inicial')">Sair</button>
</div>

<div id="tela-convite" class="hidden">
<h2>Convide e Ganhe R$3</h2>
<div class="card">
<p>Ganhe <b style="color:#00E676">R$3,00</b> por cada amigo que criar conta!</p>
<p style="margin-top:10px;font-size:13px">Seu link:</p>
<div class="pix-key">https://bancogratidaooficial-ops.github.io/Bem-vindo-/?ref=VOCE</div>
<button class="btn btn-primary" onclick="alert('Link copiado!')">Copiar Link de Convite</button>
<div class="card" style="margin-top:15px">
<p>Saldo de indicações: <b>R$ 0,00</b></p>
<p style="font-size:12px;color:#aaa">Pagamento via Pix - chave 41 99893-6718 - Mercado Pago</p>
</div>
</div>
<button class="btn btn-outline" onclick="abrirTela('tela-inicial')">Voltar</button>
</div>

</div>

<script>
function abrirTela(id){
document.querySelectorAll('[id^=tela-]').forEach(t=>t.classList.add('hidden'));
document.getElementById(id).classList.remove('hidden');
window.scrollTo(0,0);
}
function copiarPix(){
navigator.clipboard.writeText('41998936718');
alert('Chave Pix 41 99893-6718 copiada!');
}
function pagarMercadoPago(){
// Integração Mercado Pago - Pix
// Sua chave Pix: 41 99893-6718 está configurada no painel do Mercado Pago
// Aqui cria botão de pagamento - você só precisa colocar seu Public Key do MP
alert('Aqui o Mercado Pago vai gerar o QR Code Pix para a chave 41 99893-6718\n\nPara ativar de verdade:\n1. Crie conta no Mercado Pago\n2. Cadastre a chave 41 99893-6718\n3. Cole seu Public Key aqui no código na linha do Mp()');
// Exemplo: const mp = new MercadoPago('SEU_PUBLIC_KEY', {locale: 'pt-BR'});
}
</script>
</body>
</html>
