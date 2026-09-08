<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Banco Gratidão Gold</title>
<style>
body{background:#0a0a0a;color:#fff;font-family:system-ui;margin:0}
.header{background:#820ad1;padding:30px 20px 70px;border-radius:0 0 30px 30px;text-align:center}
.card-wrap{margin:-45px 16px 0}
.card{background:linear-gradient(135deg,#FFD700 0%,#D4AF37 25%,#FFC300 50%,#B8860B 100%);border-radius:22px;padding:22px;color:#000;box-shadow:0 15px 40px rgba(255,215,0,.3);border:2px solid #FFD700}
.box{background:#171717;border:1px solid #2a2a2a;border-radius:20px;padding:18px;margin:14px 16px}
.btn{width:100%;padding:16px;border-radius:14px;border:0;font-weight:800;margin-top:10px;background:#fff;color:#000}
</style>
</head>
<body>
<div class="header"><h1 style="color:white;font-size:26px">Cartões virtuais</h1></div>
<div class="card-wrap">
  <div class="card">
    <div style="font-size:24px;font-weight:900;color:#000;letter-spacing:1px">Banco Gratidão</div>
    <div style="margin-top:8px;font-size:14px;color:#222;font-weight:700">dourado Virtual •••• 
• Gold</div>
    <div style="display:flex;justify-content:space-between;align-items:end;margin-top:22px">
      <div style="width:44px;height:34px;background:linear-gradient(135deg,#ffe27a,#c9a227);border-radius:6px;border:1px solid #8a6d00"></div>
      <div style="width:46px;height:46px;background:radial-gradient(circle at 30% 30%, #ff5f00, #eb001b 40%, #f79e1b);border-radius:50%"></div>
    </div>
  </div>
</div>
<div class="box">
  <div style="color:#888;font-size:11px">SALDO DISPONÍVEL - COFRE MERCADO PAGO</div>
  <div style="font-size:42px;font-weight:900;margin:6px 0">R$ 1.247,83</div>
  <div style="color:#9a9a9a;font-size:13px">Pix: 41998936718 • Mercado Pago</div>
  <button class="btn" onclick="navigator.clipboard.writeText('41998936718');alert('Chave PIX copiada!')">Copiar Pix 41998936718</button>
</div>
</body>
</html>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Banco Gratidão Gold</title>
<style>
body{margin:0;background:#050505;color:#fff;font-family:system-ui}
.header{background:#820ad1;padding:28px 20px 65px;border-radius:0 0 28px 28px;text-align:center;font-weight:800;font-size:24px}
.wrap{margin:-45px 14px 0}
.card-gold{
  background:url('cartao-gold.png') no-repeat center/cover;
  background-color:#D4AF37;
  border-radius:20px;min-height:210px;position:relative;
  box-shadow:0 15px 40px rgba(212,175,55,.4);border:2px solid #FFD700;
  overflow:hidden;
}
.fallback{
  background:linear-gradient(135deg,#FFD700,#D4AF37,#B8860B);
  border-radius:20px;padding:18px;color:#000;min-height:210px
}
.emblem{
  width:72px;height:72px;border:2px solid #FFD700;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  font-size:42px;font-weight:900;color:#FFD700;
  background:rgba(0,0,0,.15)
}
.box{background:#171717;border:1px solid #2a2a2a;border-radius:18px;padding:16px;margin:14px}
</style>
</head>
<body>
<div class="header">Cartões virtuais</div>
<div class="wrap">
  <div class="card-gold">
    <!-- Se a imagem não carregar, mostra o fallback dourado com G -->
    <div style="padding:18px;display:flex;flex-direction:column;height:100%;min-height:210px;box-sizing:border-box">
      <div style="display:flex;align-items:center;gap:12px">
        <div class="emblem">G</div>
        <div style="font-size:18px;font-weight:900;line-height:1;color:#fff;text-shadow:0 1px 3px #000">
          Banco<br><span style="color:#FFD700">Gratidão</span>
        </div>
      </div>
      <div style="margin-top:auto">
        <div style="width:46px;height:34px;background:linear-gradient(135deg,#ffe27a,#c9a227);border-radius:5px;border:1px solid #000"></div>
        <div style="margin-top:12px;font-size:18px;font-weight:800;color:#fff;text-shadow:0 1px 2px #000">Bem-vindo</div>
      </div>
    </div>
  </div>
</div>
<div class="box">
  <div style="color:#888;font-size:11px">SALDO DISPONÍVEL - COFRE MERCADO PAGO</div>
  <div style="font-size:38px;font-weight:900">R$ 1.247,83</div>
  <div style="color:#777;font-size:12px">Pix: 41998936718</div>
</div>
</body>
</html>
