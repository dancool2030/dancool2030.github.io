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

/* BACKGROUND GLOW */

body::before{
  content:"";
  position:fixed;
  width:350px;
  height:350px;
  background:radial-gradient(circle,#ff2d55,transparent 60%);
  top:-120px;
  left:-120px;
  filter:blur(70px);
  opacity:.2;
  z-index:-1;
}

body::after{
  content:"";
  position:fixed;
  width:350px;
  height:350px;
  background:radial-gradient(circle,#0BA3FF,transparent 60%);
  bottom:-120px;
  right:-120px;
  filter:blur(70px);
  opacity:.2;
  z-index:-1;
}

/* NAV */

nav{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  padding:15px 6%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  background:rgba(255,255,255,.75);
  backdrop-filter:blur(15px);
  border-bottom:1px solid #eee;
  z-index:1000;
}

.logo{
  font-size:42px;
  color:#ff2d55;
  letter-spacing:3px;
}

nav a{
  text-decoration:none;
  color:#111;
  font-size:18px;
  margin-left:20px;
  transition:.3s;
}

nav a:hover{
  color:#0BA3FF;
}

/* HERO */

.hero{
  min-height:100vh;
  display:flex;
  align-items:center;
  justify-content:center;
  padding:120px 6% 60px;
}

.container{
  display:flex;
  align-items:center;
  justify-content:center;
  gap:50px;
  flex-wrap:wrap;
  max-width:1200px;
}

/* MAIN IMAGE */

.product-image img{
  width:100%;
  max-width:420px;
  border-radius:25px;
  padding:10px;
  background:white;
  box-shadow:0 12px 30px rgba(0,0,0,.10);
  transition:.4s;
  cursor:pointer;
}

.product-image img:hover{
  transform:scale(1.03);
}

/* INFO */

.tag{
  background:#0BA3FF;
  color:white;
  padding:8px 16px;
  border-radius:999px;
  font-size:18px;
  display:inline-block;
  margin-bottom:15px;
}

h1{
  font-size:55px;
  line-height:1;
}

.subtitle{
  font-size:18px;
  color:#555;
  margin:15px 0 25px;
  max-width:450px;
}

/* PRICE */

.price{
  display:flex;
  align-items:center;
  gap:15px;
  margin-bottom:25px;
}

.new-price{
  font-size:42px;
  color:#ff2d55;
}

.old-price{
  font-size:24px;
  color:#aaa;
  text-decoration:line-through;
}

/* SIZES */

.size-title{
  font-size:20px;
  margin-bottom:10px;
}

.size-buttons{
  display:flex;
  gap:10px;
  margin-bottom:25px;
}

.size{
  width:55px;
  height:55px;
  border:none;
  border-radius:14px;
  font-size:22px;
  cursor:pointer;
  transition:.3s;
}

.size:nth-child(1){background:#0BA3FF;color:white;}
.size:nth-child(2){background:#ff2d55;color:white;}
.size:nth-child(3){background:#19c37d;color:white;}

.size:hover{
  transform:translateY(-4px);
}

/* BUTTONS */

.buttons{
  display:flex;
  gap:12px;
  margin-bottom:30px;
}

.btn{
  padding:14px 28px;
  font-size:20px;
  border:none;
  border-radius:14px;
  cursor:pointer;
  transition:.3s;
}

.btn:hover{
  transform:translateY(-4px);
}

.buy{
  background:#ff2d55;
  color:white;
}

.cart{
  background:#19c37d;
  color:white;
}

/* FEATURES */

.features{
  display:flex;
  gap:10px;
  flex-wrap:wrap;
}

.feature{
  background:white;
  padding:15px;
  border-radius:14px;
  border:1px solid #eee;
  min-width:160px;
  box-shadow:0 6px 18px rgba(0,0,0,.06);
}

.feature h4{
  font-size:20px;
}

.feature p{
  font-size:14px;
  color:#666;
}

/* GALLERY */

.gallery{
  padding:70px 6%;
}

.gallery-title{
  text-align:center;
  font-size:45px;
  margin-bottom:40px;
}

.gallery-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
  gap:20px;
}

.gallery-grid img{
  width:100%;
  border-radius:16px;
  padding:8px;
  background:white;
  box-shadow:0 10px 25px rgba(0,0,0,.10);
  transition:.4s;
  cursor:pointer;
}

.gallery-grid img:hover{
  transform:scale(1.03) translateY(-5px);
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
  border-radius:20px;
}

/* FOOTER */

footer{
  text-align:center;
  padding:30px;
  font-size:18px;
  border-top:1px solid #eee;
}

/* MOBILE */

@media(max-width:950px){

  h1{font-size:40px;}
  .logo{font-size:32px;}
  nav a{font-size:14px;margin-left:12px;}
  .btn{font-size:16px;}

}

</style>
</head>

<body>

<nav>
<div class="logo">DWOCK</div>
<div>
  <a href="#">Home</a>
  <a href="#">Shop</a>
  <a href="#">Drops</a>
  <a href="#">Contact</a>
</div>
</nav>

<section class="hero">
<div class="container">

<div class="product-image">
<img class="clickable"
src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png">
</div>

<div class="product-info">

<div class="tag">YOUR STYLE STARTS NOW</div>

<h1>DWOCK STREETWEAR</h1>

<p class="subtitle">
Premium streetwear made for riders and everyday fits.
Clean colors, bold graphics, and comfortable material.
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
<h4>FAST</h4>
<p>24h shipping.</p>
</div>
<div class="feature">
<h4>PREMIUM</h4>
<p>Heavyweight comfort fit.</p>
</div>
<div class="feature">
<h4>LIMITED</h4>
<p>Exclusive drops.</p>
</div>
</div>

</div>
</div>
</section>

<section class="gallery">
<h2 class="gallery-title">LATEST DROPS</h2>

<div class="gallery-grid">
<img class="clickable" src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png">
<img class="clickable" src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png">
<img class="clickable" src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png">
<img class="clickable" src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/182ea8c6-dc6e-4fb3-aeb1-209ef47e9f9a.png">
</div>

</section>

<div class="lightbox" id="lightbox">
<img id="lightbox-img">
</div>

<footer>
© 2026 DWOCK Official Store
</footer>

<script>

const images = document.querySelectorAll('.clickable');
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

const sizes = document.querySelectorAll('.size');

sizes.forEach(size => {
  size.addEventListener('click', () => {
    sizes.forEach(btn => btn.style.opacity = ".5");
    size.style.opacity = "1";
  });
});

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
