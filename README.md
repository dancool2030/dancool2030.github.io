<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<title>DWOCK Official Store</title>

<link href="https://fonts.googleapis.com/css2?family=Modak&display=swap" rel="stylesheet">

<style>

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Modak', cursive;
}

body{
  background:white;
  overflow-x:hidden;
  color:#111;
}

/* GLOW BACKGROUND */

body::before{
  content:"";
  position:fixed;
  width:600px;
  height:600px;
  background:radial-gradient(circle,#ff2d55,transparent 60%);
  top:-200px;
  left:-200px;
  filter:blur(80px);
  opacity:.25;
  animation:floatGlow 6s infinite alternate;
  z-index:-1;
}

body::after{
  content:"";
  position:fixed;
  width:600px;
  height:600px;
  background:radial-gradient(circle,#0BA3FF,transparent 60%);
  bottom:-200px;
  right:-200px;
  filter:blur(90px);
  opacity:.25;
  animation:floatGlow2 7s infinite alternate;
  z-index:-1;
}

@keyframes floatGlow{
  from{transform:translate(0,0);}
  to{transform:translate(80px,60px);}
}

@keyframes floatGlow2{
  from{transform:translate(0,0);}
  to{transform:translate(-80px,-60px);}
}

/* NAV */

nav{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  padding:30px 10%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  background:rgba(255,255,255,.75);
  backdrop-filter:blur(15px);
  border-bottom:1px solid #eee;
  z-index:1000;
}

.logo{
  font-size:85px;
  color:#ff2d55;
  letter-spacing:4px;
}

nav a{
  text-decoration:none;
  color:#111;
  font-size:30px;
  margin-left:40px;
  transition:.3s;
}

nav a:hover{
  color:#0BA3FF;
  transform:scale(1.1);
}

/* HERO */

.hero{
  min-height:100vh;
  display:flex;
  align-items:center;
  justify-content:center;
  padding:180px 10% 100px;
}

.container{
  display:flex;
  align-items:center;
  justify-content:center;
  gap:120px;
  flex-wrap:wrap;
  max-width:1600px;
}

.product-image img{
  width:100%;
  max-width:850px;
  border-radius:40px;
  padding:20px;
  background:white;
  box-shadow:0 20px 60px rgba(0,0,0,.15);
  transition:.5s;
}

.product-image img:hover{
  transform:scale(1.04) rotate(-1deg);
}

.tag{
  background:#0BA3FF;
  color:white;
  padding:15px 25px;
  border-radius:999px;
  font-size:32px;
  display:inline-block;
  margin-bottom:20px;
}

h1{
  font-size:120px;
  line-height:1;
}

.subtitle{
  font-size:32px;
  color:#555;
  margin:25px 0 40px;
  max-width:650px;
}

/* PRICE */

.price{
  display:flex;
  align-items:center;
  gap:25px;
  margin-bottom:40px;
}

.new-price{
  font-size:90px;
  color:#ff2d55;
}

.old-price{
  font-size:45px;
  color:#aaa;
  text-decoration:line-through;
}

/* SIZES */

.size-title{
  font-size:35px;
  margin-bottom:20px;
}

.size-buttons{
  display:flex;
  gap:20px;
  margin-bottom:40px;
}

.size{
  width:95px;
  height:95px;
  border:none;
  border-radius:20px;
  font-size:40px;
  cursor:pointer;
  transition:.3s;
}

.size:nth-child(1){
  background:#0BA3FF;
  color:white;
}

.size:nth-child(2){
  background:#ff2d55;
  color:white;
}

.size:nth-child(3){
  background:#19c37d;
  color:white;
}

.size:hover{
  transform:translateY(-8px);
}

/* BUTTONS */

.buttons{
  display:flex;
  gap:25px;
  margin-bottom:45px;
}

.btn{
  padding:25px 55px;
  font-size:38px;
  border:none;
  border-radius:20px;
  cursor:pointer;
  transition:.3s;
}

.btn:hover{
  transform:translateY(-6px);
}

.buy{
  background:#ff2d55;
  color:white;
  box-shadow:0 10px 30px rgba(255,45,85,.3);
}

.cart{
  background:#19c37d;
  color:white;
  box-shadow:0 10px 30px rgba(25,195,125,.3);
}

/* FEATURES */

.features{
  display:flex;
  gap:20px;
  flex-wrap:wrap;
}

.feature{
  background:white;
  padding:25px;
  border-radius:20px;
  border:1px solid #eee;
  min-width:220px;
  box-shadow:0 10px 30px rgba(0,0,0,.08);
  transition:.3s;
}

.feature:hover{
  transform:translateY(-10px);
}

.feature h4{
  font-size:35px;
}

.feature p{
  font-size:24px;
  color:#666;
}

/* GALLERY */

.gallery{
  padding:120px 10%;
}

.gallery-title{
  text-align:center;
  font-size:90px;
  margin-bottom:70px;
}

.gallery-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(320px,1fr));
  gap:40px;
}

.gallery-grid img{
  width:100%;
  border-radius:25px;
  padding:15px;
  background:white;
  box-shadow:0 20px 50px rgba(0,0,0,.12);
  transition:.4s;
  cursor:pointer;
}

.gallery-grid img:hover{
  transform:scale(1.05) translateY(-10px);
}

/* LIGHTBOX */

.lightbox{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:100%;
  background:rgba(0,0,0,.92);
  display:none;
  align-items:center;
  justify-content:center;
  z-index:5000;
}

.lightbox img{
  max-width:90%;
  max-height:90%;
  border-radius:25px;
}

/* FOOTER */

footer{
  text-align:center;
  padding:60px;
  font-size:28px;
  border-top:1px solid #eee;
  margin-top:80px;
}

/* MOBILE */

@media(max-width:950px){

  h1{
    font-size:75px;
  }

  .logo{
    font-size:60px;
  }

  nav a{
    font-size:22px;
    margin-left:20px;
  }

  .btn{
    font-size:28px;
  }

}

</style>
</head>

<body>

<!-- NAV -->

<nav>

<div class="logo">DWOCK</div>

<div>
  <a href="#">Home</a>
  <a href="#">Shop</a>
  <a href="#">Drops</a>
  <a href="#">Contact</a>
</div>

</nav>

<!-- HERO -->

<section class="hero">

<div class="container">

  <div class="product-image">
    <img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/22c3e4d4-1a52-479a-9fcb-2de86f1bf029.png">
  </div>

  <div class="product-info">

    <div class="tag">YOUR STYLE STARTS NOW</div>

    <h1>DWOCK STREETWEAR</h1>

    <p class="subtitle">
      Premium streetwear made for riders and everyday fits.
      Clean colors, bold graphics, and comfortable material made for every ride.
    </p>

    <div class="price">
      <div class="new-price">$30</div>
      <div class="old-price">$65</div>
    </div>

    <div class="size-title">SELECT SIZE</div>

    <div class="size-buttons">
      <button class="size">S</button>
      <button class="size">M</button>
      <button class="size">L</button>
    </div>

    <div class="buttons">
      <button class="btn buy">BUY NOW</button>
      <button class="btn cart">ADD TO CART</button>
    </div>

    <div class="features">

      <div class="feature">
        <h4>FAST SHIPPING</h4>
        <p>Ships in 24 hours.</p>
      </div>

      <div class="feature">
        <h4>PREMIUM</h4>
        <p>Heavyweight comfort fit.</p>
      </div>

      <div class="feature">
        <h4>LIMITED</h4>
        <p>Exclusive streetwear drops.</p>
      </div>

    </div>

  </div>

</div>

</section>

<!-- GALLERY -->

<section class="gallery">

<h2 class="gallery-title">LATEST DROPS</h2>

<div class="gallery-grid">
<img scr="https://raw.github.com/dancool2030/dancool2030.github.io/blob/2e4acb1c6cc0ff07bd872b18b9e1ebe76b7faf16/IMG_0591%20(1).jpeg">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/182ea8c6-dc6e-4fb3-aeb1-209ef47e9f9a.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2449.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0597.png">
<img scr="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0597.png">
</div>

</section>

<!-- LIGHTBOX -->

<div class="lightbox" id="lightbox">
  <img id="lightbox-img">
</div>

<!-- FOOTER -->

<footer>
© 2026 DWOCK Official Store
</footer>

<script>

/* LIGHTBOX */

const images = document.querySelectorAll('.gallery-grid img');
const lightbox = document.getElementById('lightbox');
const lightboxImg = document.getElementById('lightbox-img');

images.forEach(img => {

  img.addEventListener('click', () => {

    lightbox.style.display = 'flex';
    lightboxImg.src = img.src;

  });

});

lightbox.addEventListener('click', () => {
  lightbox.style.display = 'none';
});

/* SIZE SELECTOR */

const sizes = document.querySelectorAll('.size');

sizes.forEach(size => {

  size.addEventListener('click', () => {

    sizes.forEach(btn => btn.style.opacity = ".5");

    size.style.opacity = "1";

  });

});

/* ADD TO CART */

const cartBtn = document.querySelector('.cart');

cartBtn.addEventListener('click', () => {

  cartBtn.innerHTML = "ADDED ✓";

  setTimeout(() => {
    cartBtn.innerHTML = "ADD TO CART";
  },2000);

});

</script>

</body>
</html>
