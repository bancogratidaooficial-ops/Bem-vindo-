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
    <div style="margin-top:8px;font-size:14px;color:#222;font-weight:700">Roxinho Virtual •••• 7447 • Gold</div>
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
