<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Burguesão — Hamburgueria Artesanal em Altos, PI</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Alfa+Slab+One&family=Karla:ital,wght@0,400;0,500;0,600;0,700;0,800;1,400&display=swap" rel="stylesheet">
<style>
  :root{
    --char:#1c130d;
    --char-2:#2a1c13;
    --char-3:#3a2818;
    --paper:#f4e9d3;
    --paper-2:#ecdbb3;
    --ember:#d1540f;
    --ember-dark:#a83e0a;
    --crust:#e8ac3e;
    --cream:#f7ecd9;
    --line: rgba(247,236,217,0.14);
    --maxw: 1180px;
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--char);
    color:var(--cream);
    font-family:'Karla', sans-serif;
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
  }
  h1,h2,h3,.slab{
    font-family:'Alfa Slab One', serif;
    font-weight:400;
    line-height:1;
    margin:0;
    color:var(--cream);
    letter-spacing:0.5px;
  }
  a{color:inherit; text-decoration:none;}
  img,svg{display:block; max-width:100%;}
  .wrap{max-width:var(--maxw); margin:0 auto; padding:0 28px;}
  .eyebrow{
    font-family:'Karla',sans-serif;
    font-weight:800;
    letter-spacing:2.5px;
    text-transform:uppercase;
    font-size:12.5px;
    color:var(--crust);
    display:flex;
    align-items:center;
    gap:10px;
  }
  .eyebrow::before{
    content:"";
    width:22px; height:3px;
    background:var(--ember);
    display:inline-block;
    border-radius:2px;
  }
  section{position:relative;}

  /* charred texture overlay */
  .grain{
    position:absolute; inset:0;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='140' height='140'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.05'/%3E%3C/svg%3E");
    pointer-events:none;
    mix-blend-mode:overlay;
  }

  /* grill-mark signature divider */
  .grill-line{
    height:10px;
    background:repeating-linear-gradient(
      -35deg,
      var(--ember) 0 10px,
      var(--ember-dark) 10px 20px
    );
  }
  .grill-line.thin{height:6px;}

  /* ---------- header ---------- */
  header{
    position:sticky; top:0; z-index:50;
    background:rgba(28,19,13,0.92);
    backdrop-filter:blur(6px);
    border-bottom:1px solid var(--line);
  }
  .nav{
    display:flex; align-items:center; justify-content:space-between;
    padding:16px 28px;
    max-width:var(--maxw); margin:0 auto;
  }
  .brand{
    font-family:'Alfa Slab One',serif;
    font-size:22px;
    color:var(--cream);
    display:flex; align-items:center; gap:10px;
  }
  .brand .dot{color:var(--ember);}
  .navlinks{display:flex; gap:30px; font-weight:700; font-size:14.5px;}
  .navlinks a{opacity:0.85; transition:opacity .2s, color .2s;}
  .navlinks a:hover{opacity:1; color:var(--crust);}
  .btn{
    display:inline-flex; align-items:center; gap:8px;
    padding:12px 22px;
    border-radius:6px;
    font-weight:800;
    font-size:14.5px;
    cursor:pointer;
    border:2px solid transparent;
    position:relative;
    overflow:hidden;
    transition:transform .18s ease;
  }
  .btn:active{transform:scale(0.97);}
  .btn-primary{
    background:var(--ember);
    color:var(--cream);
  }
  .btn-primary::before{
    content:"";
    position:absolute; inset:0;
    background:repeating-linear-gradient(-35deg, rgba(0,0,0,0.18) 0 8px, transparent 8px 16px);
    transform:translateX(-100%);
    transition:transform .35s ease;
  }
  .btn-primary:hover::before{transform:translateX(0);}
  .btn-ghost{
    background:transparent;
    border-color:var(--line);
    color:var(--cream);
  }
  .btn-ghost:hover{border-color:var(--crust); color:var(--crust);}
  .navcta{display:none;}
  @media(min-width:860px){.navcta{display:inline-flex;}}
  .navlinks{display:none;}
  @media(min-width:860px){.navlinks{display:flex;}}

  /* ---------- hero ---------- */
  .hero{
    padding:86px 0 70px;
    background:
      radial-gradient(ellipse at 80% -10%, rgba(209,84,15,0.30), transparent 55%),
      linear-gradient(180deg, var(--char) 0%, var(--char) 100%);
    overflow:hidden;
  }
  .hero-inner{
    display:grid; grid-template-columns:1fr; gap:46px;
    align-items:center;
  }
  @media(min-width:900px){
    .hero-inner{grid-template-columns:1.05fr 0.95fr;}
  }
  .hero h1{
    font-size:clamp(46px, 8.5vw, 92px);
    color:var(--cream);
  }
  .hero h1 span{color:var(--ember);}
  .hero-sub{
    font-family:'Alfa Slab One', serif;
    font-size:clamp(16px,2.4vw,22px);
    color:var(--crust);
    margin-top:10px;
    line-height:1.3;
  }
  .hero p.desc{
    margin-top:22px;
    font-size:17px;
    line-height:1.7;
    color:rgba(247,236,217,0.82);
    max-width:480px;
  }
  .hero-ctas{
    margin-top:34px;
    display:flex; flex-wrap:wrap; gap:14px;
  }
  .hero-art{position:relative; display:flex; justify-content:center;}
  .plate-glow{
    position:absolute;
    width:340px; height:340px;
    background:radial-gradient(circle, rgba(232,172,62,0.35), transparent 70%);
    filter:blur(10px);
  }
  .burger-svg{position:relative; width:min(360px, 78vw);}
  .float-tag{
    position:absolute;
    background:var(--crust);
    color:var(--char);
    font-family:'Alfa Slab One',serif;
    font-size:13px;
    padding:9px 14px;
    border-radius:40px;
    box-shadow:0 8px 18px rgba(0,0,0,0.35);
    transform:rotate(-6deg);
  }

.burger-photo{
    width:100%;
    max-width:500px;
    border-radius:20px;
    filter:drop-shadow(0 25px 35px rgba(0,0,0,.45));
    animation:floatBurger 4s ease-in-out infinite;
}

@keyframes floatBurger{
    50%{
        transform:translateY(-15px);
    }
}
  /* ---------- marquee ---------- */
  .marquee-wrap{
    background:var(--ember);
    color:var(--char);
    overflow:hidden;
    border-top:1px solid rgba(0,0,0,0.15);
    border-bottom:1px solid rgba(0,0,0,0.15);
  }
  .marquee{
    display:flex;
    white-space:nowrap;
    animation:scroll 22s linear infinite;
    width:max-content;
  }
  .marquee span{
    font-family:'Alfa Slab One',serif;
    font-size:17px;
    padding:14px 26px;
    display:inline-block;
  }
  @keyframes scroll{
    from{transform:translateX(0);}
    to{transform:translateX(-50%);}
  }

  /* ---------- sobre ---------- */
  .sobre{
    padding:90px 0;
    background:var(--paper);
    color:var(--char-2);
  }
  .sobre h2, .sobre .eyebrow{color:var(--char-2);}
  .sobre .eyebrow{color:var(--ember-dark);}
  .sobre-grid{
    display:grid; grid-template-columns:1fr; gap:50px;
  }
  @media(min-width:880px){
    .sobre-grid{grid-template-columns:1.1fr 0.9fr;}
  }
  .sobre h2{
    font-size:clamp(30px,4vw,44px);
    margin-top:12px;
    color:var(--char-2);
  }
  .sobre p{
    margin-top:20px;
    font-size:16.5px;
    line-height:1.8;
    color:#4a3826;
    max-width:520px;
  }
  .stat-row{
    display:grid; grid-template-columns:repeat(3,1fr); gap:0;
    border-top:2px solid var(--char-2);
    border-bottom:2px solid var(--char-2);
  }
  .stat{
    padding:26px 14px;
    text-align:center;
    border-left:2px solid var(--char-2);
  }
  .stat:first-child{border-left:none;}
  .stat b{
    display:block;
    font-family:'Alfa Slab One',serif;
    font-size:clamp(26px,4vw,38px);
    color:var(--ember-dark);
  }
  .stat span{
    font-size:12.5px;
    font-weight:700;
    text-transform:uppercase;
    letter-spacing:1px;
    color:#5c4632;
  }

  /* ---------- cardápio ---------- */
  .menu{
    padding:90px 0;
    background:var(--char);
  }
  .menu-head{
    display:flex; flex-wrap:wrap; align-items:flex-end; justify-content:space-between; gap:16px;
    margin-bottom:44px;
  }
  .menu h2{font-size:clamp(30px,4vw,44px); margin-top:12px;}
  .menu-note{font-size:13px; color:rgba(247,236,217,0.55); max-width:260px;}
  .menu-grid{
    display:grid; grid-template-columns:1fr; gap:18px;
  }
  .menu-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
gap:30px;
}

.food-card{
background:#2a1c13;
border-radius:18px;
overflow:hidden;
transition:.4s;
box-shadow:0 10px 30px rgba(0,0,0,.3);
}

.food-card:hover{
transform:translateY(-10px);
box-shadow:0 20px 40px rgba(209,84,15,.35);
}

.food-card img{
width:100%;
height:240px;
object-fit:cover;
transition:.5s;
}

.food-card:hover img{
transform:scale(1.08);
}

.food-content{
padding:25px;
}

.food-content h3{
margin-bottom:10px;
}

.food-content p{
margin-bottom:20px;
color:#ddd;
}

.food-bottom{
display:flex;
justify-content:space-between;
align-items:center;
}

.food-bottom span{
font-family:'Alfa Slab One';
font-size:24px;
color:#e8ac3e;
}
  @media(min-width:700px){.menu-grid{grid-template-columns:1fr 1fr;}}
  .menu-grid{

display:grid;

grid-template-columns:repeat(auto-fit,minmax(320px,1fr));

gap:35px;

}

.food-card{

background:#24150f;

border-radius:22px;

overflow:hidden;

transition:.4s;

box-shadow:0 15px 35px rgba(0,0,0,.30);

}

.food-card:hover{

transform:translateY(-12px);

box-shadow:0 25px 45px rgba(255,110,0,.25);

}

.food-image{

position:relative;

overflow:hidden;

}

.food-image img{

width:100%;

height:240px;

object-fit:cover;

transition:.5s;

}

.food-card:hover img{

transform:scale(1.08);

}

.tag{

position:absolute;

top:15px;

left:15px;

background:#d1540f;

padding:8px 14px;

border-radius:30px;

font-size:12px;

font-weight:700;

}

.new{

background:#e8ac3e;

color:#111;

}

.food-content{

padding:25px;

}

.food-content h3{

font-size:25px;

margin-bottom:12px;

}

.food-content p{

color:#ddd;

line-height:1.7;

margin-bottom:25px;

}

.food-bottom{

display:flex;

justify-content:space-between;

align-items:center;

}

.price{

font-size:28px;

font-weight:bold;

color:#e8ac3e;

}

.food-bottom .btn{

padding:12px 22px;

border-radius:50px;

background:#d1540f;

transition:.3s;

}

.food-bottom .btn:hover{

background:#e8ac3e;

color:#111;

}
  
  .menu-price{
    font-family:'Alfa Slab One',serif;
    font-size:20px;
    color:var(--crust);
    white-space:nowrap;
  }

  /* ---------- como pedir ---------- */
  .steps{
    padding:90px 0;
    background:var(--paper-2);
    color:var(--char-2);
  }
  .steps h2{color:var(--char-2); font-size:clamp(30px,4vw,44px); margin-top:12px;}
  .steps .eyebrow{color:var(--ember-dark);}
  .steps-grid{
    margin-top:44px;
    display:grid; grid-template-columns:1fr; gap:26px;
  }
  @media(min-width:760px){.steps-grid{grid-template-columns:repeat(3,1fr);}}
  .step{
    background:var(--paper);
    border:2px solid var(--char-2);
    border-radius:10px;
    padding:28px 24px;
  }
  .step .num{
    font-family:'Alfa Slab One',serif;
    font-size:34px;
    color:var(--ember);
  }
  .step h3{
    font-family:'Karla',sans-serif;
    font-weight:800;
    font-size:17px;
    margin-top:10px;
    color:var(--char-2);
  }
  .step p{
    margin-top:8px; font-size:14.5px; line-height:1.6; color:#5c4632;
  }

  /* ---------- localização ---------- */
  .local{
    padding:90px 0 100px;
    background:var(--char);
  }
  .local-grid{
    display:grid; grid-template-columns:1fr; gap:40px;
  }
  @media(min-width:900px){.local-grid{grid-template-columns:0.9fr 1.1fr;}}
  .local h2{font-size:clamp(30px,4vw,44px); margin-top:12px;}
  .info-list{margin-top:26px; display:flex; flex-direction:column; gap:20px;}
  .info-item{display:flex; gap:14px; align-items:flex-start;}
  .info-icon{
    width:38px; height:38px; flex:none;
    border-radius:8px;
    background:var(--char-2);
    border:1px solid var(--line);
    display:flex; align-items:center; justify-content:center;
    color:var(--crust);
  }
  .info-item h4{
    font-size:14px; font-weight:800; margin:0 0 4px;
    text-transform:uppercase; letter-spacing:0.6px; color:var(--crust);
  }
  .info-item p{margin:0; font-size:15px; line-height:1.6; color:rgba(247,236,217,0.82);}
  .info-item .tiny{font-size:12px; color:rgba(247,236,217,0.45); margin-top:4px;}
  .map-frame{
    border-radius:12px; overflow:hidden;
    border:1px solid var(--line);
    min-height:340px;
  }
  .map-frame iframe{width:100%; height:100%; min-height:340px; border:0; filter:grayscale(0.15) contrast(1.05);}

  /* ---------- footer ---------- */
  footer{
    background:var(--char-2);
    padding:40px 0 26px;
    border-top:1px solid var(--line);
  }
  .foot-row{
    display:flex; flex-wrap:wrap; justify-content:space-between; align-items:center; gap:18px;
  }
  .foot-brand{font-family:'Alfa Slab One',serif; font-size:18px;}
  .foot-links{display:flex; gap:22px; font-size:14px; font-weight:700;}
  .foot-links a:hover{color:var(--crust);}
  .foot-bottom{
    margin-top:26px; padding-top:20px; border-top:1px solid var(--line);
    font-size:12.5px; color:rgba(247,236,217,0.45);
    display:flex; flex-wrap:wrap; justify-content:space-between; gap:10px;
  }

  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.01ms !important; animation-iteration-count:1 !important; transition-duration:0.01ms !important;}
    html{scroll-behavior:auto;}
  }

  .reveal{
    opacity:0; transform:translateY(18px);
    transition:opacity .6s ease, transform .6s ease;
  }
  .reveal.in{opacity:1; transform:translateY(0);}
</style>
</head>
<body>

<header>
  <div class="nav">
    <div class="brand">BURGUES<span class="dot">Ã</span>O</div>
    <nav class="navlinks">
      <a href="#cardapio">Cardápio</a>
      <a href="#sobre">Sobre</a>
      <a href="#local">Localização</a>
    </nav>
    <a class="btn btn-primary navcta" href="#local">Peça agora</a>
  </div>
</header>

<section class="hero">
  <div class="grain"></div>
  <div class="wrap hero-inner">
    <div class="reveal in">
      <div class="eyebrow">Hamburgueria artesanal · Altos, PI</div>
      <h1>BURGUES<span>Ã</span>O</h1>
      <div class="hero-sub">O sabor que virou ponto de encontro no Centro de Altos</div>
      <p class="desc">Pão selado na chapa, carne 100% artesanal e molhos feitos em casa. Desde 2020 servindo o hambúrguer que a cidade não troca por nenhum outro.</p>
      <div class="hero-ctas">
        <a class="btn btn-primary" href="#local">🔥 Pedir no WhatsApp</a>
        <a class="btn btn-ghost" href="#cardapio">Ver cardápio</a>
      </div>
    </div>
    <div class="hero-art reveal in">

    <div class="plate-glow"></div>

    <img
        class="burger-photo"
        src="https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&w=900&q=80"
        alt="Hambúrguer Artesanal">

</div>
    </div>
  </div>
</section>

<div class="marquee-wrap">
  <div class="marquee">
    <span>CARNE 100% ARTESANAL &nbsp;•&nbsp; PÃO SELADO NA CHAPA &nbsp;•&nbsp; MOLHOS DA CASA &nbsp;•&nbsp; RETIRADA E ENTREGA &nbsp;•&nbsp; DESDE 2020 &nbsp;•&nbsp; CENTRO DE ALTOS &nbsp;•&nbsp;</span>
    <span>CARNE 100% ARTESANAL &nbsp;•&nbsp; PÃO SELADO NA CHAPA &nbsp;•&nbsp; MOLHOS DA CASA &nbsp;•&nbsp; RETIRADA E ENTREGA &nbsp;•&nbsp; DESDE 2020 &nbsp;•&nbsp; CENTRO DE ALTOS &nbsp;•&nbsp;</span>
  </div>
</div>

<section class="sobre" id="sobre">
  <div class="wrap sobre-grid">
    <div class="reveal">
      <div class="eyebrow">Nossa história</div>
      <h2>Feito à moda da casa, do jeito que Altos gosta</h2>
      <p>O Burguesão nasceu no Centro de Altos com uma proposta simples: fazer o hambúrguer bem feito, sem pressa, do jeito que a casa gosta. Pão selado na chapa, carne temperada na hora e molhos que só existem aqui. Desde então, virou point da cidade.</p>
    </div>
    <div class="reveal">
      <div class="stat-row">
        <div class="stat"><b>2020</b><span>Desde</span></div>
        <div class="stat"><b>100%</b><span>Artesanal</span></div>
        <div class="stat"><b>Centro</b><span>Altos · PI</span></div>
      </div>
    </div>
  </div>
</section>

<section class="menu" id="cardapio">
  <div class="wrap">
    <div class="menu-head reveal">
      <div>
        <div class="eyebrow">Cardápio</div>
        <h2>Os destaques da casa</h2>
      </div>
      <div class="menu-note">*Itens e preços ilustrativos.</div>
    </div>
    
        <div class="menu-grid">

    <div class="food-card">

        <div class="food-image">

            <img src="https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&w=900&q=80" alt=>

            <span class="tag">
                Mais Vendido
            </span>

        </div>

        <div class="food-content">

            <h3>Burguesão Especial</h3>

            <p>
                Pão brioche, carne artesanal, cheddar, bacon crocante e molho especial.
            </p>

            <div class="food-bottom">

                <span class="price">
                    R$39,90
                </span>

                <a href="#" class="btn btn-primary">
                    Pedir
                </a>

            </div>

        </div>

    </div>

    <div class="food-card">

        <div class="food-image">

            <img src="https://as2.ftcdn.net/v2/jpg/06/31/30/57/1000_F_631305744_a6iFiqLzAeuOiNXiK3Z9FCliyXM3FpDZ.jpg" alt="">

        </div>

        <div class="food-content">

            <h3>Duplo Bacon</h3>

            <p>
                Dois hambúrgueres artesanais, cheddar e muito bacon.
            </p>

            <div class="food-bottom">

                <span class="price">
                    R$44,90
                </span>

                <a href="#" class="btn btn-primary">
                    Pedir
                </a>

            </div>

        </div>

    </div>

    <div class="food-card">

        <div class="food-image">

            <img src="https://img.freepik.com/premium-photo/sensational-cheddar-cheese-burger-temptation-cheesy_960396-8540.jpg" alt=>

            <span class="tag new">
                Novo
            </span>

        </div>

        <div class="food-content">

            <h3>Cheddar Supreme</h3>

            <p>
                Cheddar cremoso, cebola caramelizada e carne artesanal.
            </p>

            <div class="food-bottom">

                <span class="price">
                    R$42,90
                </span>

                <a href="#" class="btn btn-primary">
                    Pedir
                </a>

            </div>

        </div>

    </div>

</div>
</section>

<section class="steps">
  <div class="wrap">
    <div class="reveal">
      <div class="eyebrow">Como pedir</div>
      <h2>Do pedido à mesa em 3 passos</h2>
    </div>
    <div class="steps-grid">
      <div class="step reveal">
        <div class="num">1</div>
        <h3>Escolha seu lanche</h3>
        <p>Veja o cardápio e escolha o Burguesão que mais combina com sua fome.</p>
      </div>
      <div class="step reveal">
        <div class="num">2</div>
        <h3>Chame no WhatsApp</h3>
        <p>Envie seu pedido direto para a gente e confirme o horário de retirada ou entrega.</p>
      </div>
      <div class="step reveal">
        <div class="num">3</div>
        <h3>Retire ou receba</h3>
        <p>Busque no balcão, quentinho, ou espere a entrega chegar até você.</p>
      </div>
    </div>
  </div>
</section>

<section class="local" id="local">
  <div class="grain"></div>
  <div class="wrap local-grid">
    <div class="reveal">
      <div class="eyebrow">Localização</div>
      <h2>Vem pro Burguesão</h2>
      <div class="info-list">
        <div class="info-item">
          <div class="info-icon">📍</div>
          <div>
            <h4>Endereço</h4>
            <p>Av. Francisco Raulino, 1427 — Centro, Altos - PI, 64290-000</p>
          </div>
        </div>
        <div class="info-item">
          <div class="info-icon">🕒</div>
          <div>
            <h4>Horário</h4>
            <p>Terça a domingo · 18h às 23h</p>
            <p class="tiny">*horário ilustrativo — confirme o horário real de funcionamento</p>
          </div>
        </div>
        <div class="info-item">
          <div class="info-icon">💬</div>
          <div>
            <h4>WhatsApp</h4>
            <p>(86) 99999-9999</p>
            <p class="tiny">*número ilustrativo — substitua pelo WhatsApp real</p>
          </div>
        </div>
      </div>
      <div class="hero-ctas" style="margin-top:30px;">
        <a class="btn btn-primary" href="#">🔥 Chamar no WhatsApp</a>
      </div>
    </div>
    <div class="map-frame reveal">
      <iframe
        src="https://www.google.com/maps?q=Av.+Francisco+Raulino,+1427+-+Centro,+Altos+-+PI,+64290-000&output=embed"
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        title="Mapa - Burguesão, Altos PI">
      </iframe>
    </div>
  </div>
</section>

<div class="grill-line thin"></div>

<footer>
  <div class="wrap">
    <div class="foot-row">
      <div class="foot-brand">BURGUESÃO</div>
      <div class="foot-links">
        <a href="#cardapio">Cardápio</a>
        <a href="#sobre">Sobre</a>
        <a href="#local">Localização</a>
      </div>
    </div>
    <div class="foot-bottom">
      <span>Av. Francisco Raulino, 1427 — Centro, Altos - PI</span>
      <span>Feito com 🔥 para o Burguesão</span>
    </div>
  </div>
</footer>

<script>
  const io = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{ if(e.isIntersecting){ e.target.classList.add('in'); } });
  }, {threshold:0.15});
  document.querySelectorAll('.reveal').forEach(el=>io.observe(el));
</script>

</body>
</html>
