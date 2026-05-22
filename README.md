<!-- REPLACE ONLY THE HERO SECTION WITH THIS -->

<section class="hero">
<div class="container">

<!-- MAIN PRODUCT AREA -->

<div>

<img 
id="mainProduct"
src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png"
onclick="openImg(this.src)"
>

<!-- COLOR SWITCH BUTTONS -->

<div style="
display:flex;
gap:12px;
margin-top:15px;
justify-content:center;
flex-wrap:wrap;
">

<button onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png')"
style="
width:28px;
height:28px;
border-radius:50%;
border:none;
cursor:pointer;
background:#0BA3FF;
box-shadow:0 0 10px rgba(0,0,0,.2);
"></button>

<button onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png')"
style="
width:28px;
height:28px;
border-radius:50%;
border:none;
cursor:pointer;
background:#ff2d55;
box-shadow:0 0 10px rgba(0,0,0,.2);
"></button>

<button onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png')"
style="
width:28px;
height:28px;
border-radius:50%;
border:none;
cursor:pointer;
background:#19c37d;
box-shadow:0 0 10px rgba(0,0,0,.2);
"></button>

<button onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png')"
style="
width:28px;
height:28px;
border-radius:50%;
border:none;
cursor:pointer;
background:#111;
box-shadow:0 0 10px rgba(0,0,0,.2);
"></button>

</div>

</div>

<!-- PRODUCT INFO -->

<div>

<h1>DWOCK STREETWEAR</h1>

<p style="font-size:26px;margin:10px 0 20px;">
Premium streetwear made for everyday fits.
</p>

<p style="font-size:34px;color:#ff2d55;margin-bottom:20px;">
$30
</p>

<button class="btn buy" onclick="addToCart('Main Shirt',30)">
BUY NOW
</button>

<button class="btn cart" onclick="addToCart('Main Shirt',30)">
ADD TO CART
</button>

</div>

</div>
</section>

<!-- ADD THIS INSIDE YOUR SCRIPT AT THE BOTTOM -->

<script>

function changeMainImage(src){

document.getElementById("mainProduct").src = src;

}

</script>
