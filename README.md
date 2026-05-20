                                          YOUR STYLE STARTS NOW!!!
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<title>DWOCK Official Store</title>

<style>

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:Arial, Helvetica, sans-serif;
}

body{
  background:white;
  color:#111;
  overflow-x:hidden;
}

/* NAVBAR */

nav{
  width:100%;
  padding:25px 8%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  position:fixed;
  top:0;
  left:0;
  z-index:1000;
  background:white;
  border-bottom:2px solid #ececec;
}

.logo{
  font-size:34px;
  font-weight:900;
  letter-spacing:3px;
  color:#ff2d55;
}

nav ul{
  display:flex;
  gap:35px;
  list-style:none;
}

nav a{
  color:#111;
  text-decoration:none;
  font-size:15px;
  font-weight:bold;
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
  padding:140px 8% 80px;
  background:
  linear-gradient(135deg,#ffffff,#f8f8f8);
}

.container{
  display:flex;
  align-items:center;
  justify-content:center;
  gap:80px;
  flex-wrap:wrap;
  width:100%;
  max-width:1400px;
}

/* IMAGE */

.product-image{
  flex:1;
  min-width:320px;
  display:flex;
  justify-content:center;
}

.product-image img{
  width:100%;
  max-width:520px;
  border-radius:30px;
  transition:.4s;
  background:white;
  padding:20px;
  box-shadow:0 10px 40px rgba(0,0,0,.12);
}

.product-image img:hover{
  transform:scale(1.03);
}

/* PRODUCT INFO */

.product-info{
  flex:1;
  min-width:320px;
}

.tag{
  display:inline-block;
  background:#0BA3FF;
  color:white;
  padding:10px 18px;
  border-radius:999px;
  font-size:13px;
  margin-bottom:20px;
  font-weight:bold;
}

h1{
  font-size:72px;
  line-height:1;
  margin-bottom:20px;
  color:#111;
}

.subtitle{
  color:#555;
  font-size:18px;
  line-height:1.7;
  max-width:550px;
  margin-bottom:30px;
}

.price{
  display:flex;
  align-items:center;
  gap:15px;
  margin-bottom:30px;
}

.new-price{
  font-size:52px;
  font-weight:900;
  color:#ff2d55;
}

.old-price{
  font-size:24px;
  color:#888;
  text-decoration:line-through;
}

/* SIZES */

.sizes{
  margin-bottom:35px;
}

.sizes h3{
  margin-bottom:15px;
  color:#222;
}

.size-buttons{
  display:flex;
  gap:15px;
  flex-wrap:wrap;
}

.size{
  width:65px;
  height:65px;
  border-radius:16px;
  border:none;
  background:#f2f2f2;
  color:#111;
  font-size:18px;
  font-weight:bold;
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
  transform:translateY(-5px);
}

/* BUTTONS */

.buttons{
  display:flex;
  gap:20px;
  flex-wrap:wrap;
  margin-bottom:40px;
}

.btn{
  padding:18px 38px;
  border:none;
  border-radius:16px;
  font-size:17px;
  font-weight:bold;
  cursor:pointer;
  transition:.3s;
}

.buy{
  background:#ff2d55;
  color:white;
  box-shadow:0 10px 25px rgba(255,45,85,.25);
}

.buy:hover{
  transform:translateY(-4px);
}

.cart{
  background:#19c37d;
  color:white;
  box-shadow:0 10px 25px rgba(25,195,125,.25);
}

.cart:hover{
  transform:translateY(-4px);
}

/* FEATURES */

.features{
  display:flex;
  gap:20px;
  flex-wrap:wrap;
}

.feature{
  background:white;
  border:2px solid #efefef;
  padding:18px 24px;
  border-radius:18px;
  flex:1;
  min-width:180px;
  box-shadow:0 5px 20px rgba(0,0,0,.06);
}

.feature:nth-child(1) h4{
  color:#0BA3FF;
}

.feature:nth-child(2) h4{
  color:#ff2d55;
}

.feature:nth-child(3) h4{
  color:#19c37d;
}

.feature p{
  color:#666;
  font-size:14px;
  line-height:1.5;
}

/* GALLERY */

.gallery{
  padding:80px 8%;
  background:white;
}

.gallery-title{
  text-align:center;
  font-size:50px;
  margin-bottom:50px;
  color:#111;
}

.gallery-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
  gap:25px;
}

.gallery-grid img{
  width:100%;
  border-radius:25px;
  background:white;
  padding:15px;
  box-shadow:0 10px 30px rgba(0,0,0,.08);
  transition:.4s;
}

.gallery-grid img:hover{
  transform:translateY(-8px);
}

/* FOOTER */

footer{
  text-align:center;
  padding:35px;
  border-top:2px solid #ececec;
  color:#666;
  background:white;
}

/* MOBILE */

@media(max-width:950px){

  h1{
    font-size:52px;
  }

  .container{
    gap:50px;
  }

  nav ul{
    display:none;
  }

}

</style>
</head>

<body>

<!-- NAV -->

<nav>

<div class="logo">DWOCK</div>

<ul>
  <li><a href="#">Home</a></li>
  <li><a href="#">Shop</a></li>
  <li><a href="#">Drops</a></li>
  <li><a href="#">Contact</a></li>
</ul>

</nav>

<!-- HERO -->

<section class="hero">

<div class="container">

  <!-- MAIN PRODUCT IMAGE -->

  <div class="product-image">

    <img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/22c3e4d4-1a52-479a-9fcb-2de86f1bf029.png" alt="DWOCK Clothing">

  </div>

  <!-- INFO -->

  <div class="product-info">

    <div class="tag">YOUR STYLE STARTS NOW</div>

    <h1>DWOCK STREETWEAR</h1>

    <p class="subtitle">
      Premium streetwear made for riders and everyday fits.
      Bright colors, clean style, lightweight comfort, and bold designs.
    </p>

    <div class="price">
      <div class="new-price">$30</div>
      <div class="old-price">$65</div>
    </div>

    <!-- SIZES -->

    <div class="sizes">

      <h3>Select Size</h3>

      <div class="size-buttons">
        <button class="size">S</button>
        <button class="size">M</button>
        <button class="size">L</button>
      </div>

    </div>

    <!-- BUTTONS -->

    <div class="buttons">

      <button class="btn buy">
        BUY NOW
      </button>

      <button class="btn cart">
        ADD TO CART
      </button>

    </div>

    <!-- FEATURES -->

    <div class="features">

      <div class="feature">
        <h4>Fast Shipping</h4>
        <p>Ships within 24 hours.</p>
      </div>

      <div class="feature">
        <h4>Trending Style</h4>
        <p>Bright streetwear inspired colors.</p>
      </div>

      <div class="feature">
        <h4>Premium Quality</h4>
        <p>Comfortable and lightweight material.</p>
      </div>

    </div>

  </div>

</div>

</section>

<!-- GALLERY -->

<section class="gallery">

<h2 class="gallery-title">LATEST DROPS</h2>

<div class="gallery-grid">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/182ea8c6-dc6e-4fb3-aeb1-209ef47e9f9a.png">

</div>

</section>

<!-- FOOTER -->

<footer>
© 2026 DWOCK Official Store. All Rights Reserved.
</footer>

</body>
</html>
