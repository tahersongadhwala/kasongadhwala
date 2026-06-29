<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>K.A Songadhwala — Utensils & Hotel Appliances</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet"/>
  <style>
    *,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
    :root{
      --cream:#F9F6F1;--charcoal:#1C1C1E;--copper:#B5622A;--copper-light:#D4855A;
      --muted:#7A7670;--border:#E4DDD4;--white:#FFFFFF;--green:#2E6B4F;--red:#C0392B;
    }
    html{scroll-behavior:smooth}
    body{font-family:'DM Sans',sans-serif;background:var(--cream);color:var(--charcoal);font-size:15px;line-height:1.6}

    /* NAV */
    nav{position:sticky;top:0;z-index:100;background:var(--charcoal);display:flex;align-items:center;justify-content:space-between;padding:0 5%;height:64px;box-shadow:0 2px 20px rgba(0,0,0,.25)}
    .nav-logo{font-family:'Playfair Display',serif;font-size:1.1rem;font-weight:700;color:var(--white);letter-spacing:.5px;line-height:1.2}
    .nav-logo span{color:var(--copper-light);font-size:.75rem;display:block;font-family:'DM Sans',sans-serif;font-weight:400;letter-spacing:1px}
    .nav-links{display:flex;gap:28px;list-style:none}
    .nav-links a{color:rgba(255,255,255,.75);text-decoration:none;font-size:.9rem;font-weight:500;transition:color .2s}
    .nav-links a:hover{color:var(--copper-light)}
    .cart-btn{position:relative;background:var(--copper);border:none;color:#fff;padding:9px 18px;border-radius:8px;font-weight:600;font-size:.88rem;cursor:pointer;display:flex;align-items:center;gap:7px;transition:background .2s}
    .cart-btn:hover{background:var(--copper-light)}
    .cart-count{background:#fff;color:var(--copper);border-radius:50%;width:20px;height:20px;font-size:.75rem;font-weight:700;display:flex;align-items:center;justify-content:center}

    /* HERO */
    .hero{background:var(--charcoal);padding:72px 5% 64px;display:flex;align-items:center;gap:60px;flex-wrap:wrap}
    .hero-text{flex:1;min-width:280px}
    .hero-eyebrow{text-transform:uppercase;letter-spacing:3px;font-size:.75rem;color:var(--copper-light);font-weight:600;margin-bottom:16px}
    .hero-headline{font-family:'Playfair Display',serif;font-size:clamp(2rem,5vw,3.2rem);font-weight:700;color:#fff;line-height:1.2;margin-bottom:8px}
    .hero-headline em{color:var(--copper-light);font-style:normal}
    .hero-address{color:rgba(255,255,255,.45);font-size:.82rem;margin-bottom:18px;display:flex;align-items:center;gap:6px}
    .hero-sub{color:rgba(255,255,255,.6);max-width:440px;font-size:1rem;margin-bottom:32px}
    .hero-cta{display:inline-block;background:var(--copper);color:#fff;padding:14px 32px;border-radius:10px;text-decoration:none;font-weight:600;font-size:.95rem;transition:background .2s}
    .hero-cta:hover{background:var(--copper-light)}
    .hero-stats{display:flex;gap:32px;margin-top:40px;flex-wrap:wrap}
    .stat{text-align:center}
    .stat-num{font-size:1.6rem;font-weight:700;color:var(--copper-light);font-family:'Playfair Display',serif}
    .stat-label{font-size:.75rem;color:rgba(255,255,255,.5);letter-spacing:1px;text-transform:uppercase}

    /* CATEGORIES */
    .categories{padding:56px 5% 16px}
    .section-title{font-family:'Playfair Display',serif;font-size:1.8rem;font-weight:700;color:var(--charcoal);margin-bottom:6px}
    .section-sub{color:var(--muted);font-size:.92rem;margin-bottom:24px}
    .cat-tabs{display:flex;flex-wrap:wrap;gap:10px}
    .cat-tab{padding:8px 20px;border-radius:50px;border:1.5px solid var(--border);background:transparent;cursor:pointer;font-size:.88rem;font-weight:500;color:var(--muted);transition:all .2s;font-family:'DM Sans',sans-serif}
    .cat-tab.active,.cat-tab:hover{background:var(--charcoal);border-color:var(--charcoal);color:#fff}

    /* PRODUCTS */
    #products{padding:24px 5% 64px}
    .product-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:24px}
    .product-card{background:var(--white);border-radius:16px;border:1px solid var(--border);overflow:hidden;transition:box-shadow .25s,transform .25s;display:flex;flex-direction:column}
    .product-card:hover{box-shadow:0 12px 40px rgba(0,0,0,.1);transform:translateY(-4px)}

    /* PRODUCT IMAGE — supports real photos */
    .product-image{height:200px;position:relative;overflow:hidden;background:#f0ece6;display:flex;align-items:center;justify-content:center}
    .product-image img{width:100%;height:100%;object-fit:cover;display:block}
    .product-image .emoji-placeholder{font-size:4.5rem}

    .product-badge{position:absolute;top:10px;left:10px;background:var(--copper);color:#fff;font-size:.7rem;font-weight:700;padding:3px 9px;border-radius:50px;text-transform:uppercase;letter-spacing:.5px;z-index:1}

    .product-body{padding:16px;flex:1;display:flex;flex-direction:column}
    .product-category{font-size:.72rem;font-weight:600;color:var(--copper);text-transform:uppercase;letter-spacing:1px;margin-bottom:5px}
    .product-name{font-family:'Playfair Display',serif;font-size:1rem;font-weight:600;color:var(--charcoal);margin-bottom:6px;line-height:1.3}
    .product-desc{font-size:.82rem;color:var(--muted);flex:1;margin-bottom:14px;line-height:1.5}
    .product-footer{display:flex;align-items:center;justify-content:space-between}
    .product-price{font-size:1.15rem;font-weight:700;color:var(--charcoal)}
    .product-price small{font-size:.75rem;font-weight:400;color:var(--muted)}
    .add-to-cart{background:var(--charcoal);color:#fff;border:none;border-radius:8px;padding:9px 16px;font-size:.85rem;font-weight:600;cursor:pointer;transition:background .2s;font-family:'DM Sans',sans-serif}
    .add-to-cart:hover{background:var(--copper)}
    .add-to-cart.added{background:var(--green)}

    /* CART SIDEBAR */
    .cart-overlay{position:fixed;inset:0;background:rgba(0,0,0,.45);z-index:200;opacity:0;pointer-events:none;transition:opacity .3s}
    .cart-overlay.open{opacity:1;pointer-events:all}
    .cart-sidebar{position:fixed;top:0;right:-420px;width:420px;max-width:100vw;height:100%;background:var(--white);z-index:201;transition:right .35s cubic-bezier(.4,0,.2,1);display:flex;flex-direction:column;box-shadow:-8px 0 40px rgba(0,0,0,.15)}
    .cart-sidebar.open{right:0}
    .cart-header{padding:24px 24px 16px;border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between}
    .cart-header h2{font-family:'Playfair Display',serif;font-size:1.3rem}
    .close-btn{background:var(--cream);border:none;border-radius:8px;width:36px;height:36px;cursor:pointer;font-size:1.1rem;display:flex;align-items:center;justify-content:center;transition:background .2s}
    .close-btn:hover{background:var(--border)}
    .cart-items{flex:1;overflow-y:auto;padding:16px 24px}
    .cart-item{display:flex;gap:14px;align-items:flex-start;padding:14px 0;border-bottom:1px solid var(--border)}
    .cart-item-icon{width:60px;height:60px;border-radius:10px;background:var(--cream);display:flex;align-items:center;justify-content:center;font-size:1.7rem;flex-shrink:0;overflow:hidden}
    .cart-item-icon img{width:100%;height:100%;object-fit:cover}
    .cart-item-info{flex:1}
    .cart-item-name{font-weight:600;font-size:.9rem;margin-bottom:2px}
    .cart-item-price{color:var(--copper);font-weight:700;font-size:.9rem}
    .qty-controls{display:flex;align-items:center;gap:10px;margin-top:6px}
    .qty-btn{width:26px;height:26px;border-radius:6px;border:1.5px solid var(--border);background:transparent;cursor:pointer;font-size:1rem;font-weight:700;display:flex;align-items:center;justify-content:center;transition:all .15s}
    .qty-btn:hover{border-color:var(--charcoal);background:var(--charcoal);color:#fff}
    .qty-num{font-weight:600;min-width:20px;text-align:center}
    .remove-btn{background:none;border:none;cursor:pointer;color:var(--red);font-size:1rem;padding:4px;transition:opacity .2s}
    .remove-btn:hover{opacity:.7}
    .cart-empty{text-align:center;padding:60px 20px;color:var(--muted)}
    .cart-empty .empty-icon{font-size:3.5rem;margin-bottom:12px}
    .cart-footer{padding:20px 24px;border-top:1px solid var(--border)}
    .cart-total{display:flex;justify-content:space-between;font-weight:700;font-size:1.1rem;margin-bottom:16px}
    .checkout-btn{width:100%;background:var(--copper);color:#fff;border:none;border-radius:12px;padding:16px;font-size:1rem;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif;transition:background .2s}
    .checkout-btn:hover{background:var(--copper-light)}

    /* MODAL */
    .modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,.55);z-index:300;display:flex;align-items:center;justify-content:center;opacity:0;pointer-events:none;transition:opacity .3s;padding:20px}
    .modal-overlay.open{opacity:1;pointer-events:all}
    .modal{background:var(--white);border-radius:20px;width:100%;max-width:480px;padding:36px;position:relative;box-shadow:0 30px 80px rgba(0,0,0,.2);transform:translateY(20px);transition:transform .3s;max-height:90vh;overflow-y:auto}
    .modal-overlay.open .modal{transform:translateY(0)}
    .modal-close{position:absolute;top:16px;right:16px;background:var(--cream);border:none;border-radius:8px;width:34px;height:34px;cursor:pointer;font-size:1.1rem;display:flex;align-items:center;justify-content:center}
    .modal h2{font-family:'Playfair Display',serif;font-size:1.5rem;margin-bottom:6px}
    .modal p.modal-sub{color:var(--muted);font-size:.88rem;margin-bottom:24px}
    .order-summary{background:var(--cream);border-radius:12px;padding:14px 16px;margin-bottom:22px;font-size:.88rem}
    .order-summary-row{display:flex;justify-content:space-between;padding:4px 0}
    .order-summary-row.total{font-weight:700;border-top:1px solid var(--border);margin-top:6px;padding-top:8px}
    label{display:block;font-size:.85rem;font-weight:600;margin-bottom:5px;color:var(--charcoal)}
    input,textarea,select{width:100%;padding:11px 14px;border:1.5px solid var(--border);border-radius:10px;font-size:.92rem;font-family:'DM Sans',sans-serif;color:var(--charcoal);background:var(--white);outline:none;transition:border-color .2s;margin-bottom:14px}
    input:focus,textarea:focus{border-color:var(--copper)}
    textarea{resize:vertical;min-height:80px}
    .form-row{display:grid;grid-template-columns:1fr 1fr;gap:12px}
    .submit-btn{width:100%;background:var(--copper);color:#fff;border:none;border-radius:12px;padding:16px;font-size:1rem;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif;transition:background .2s;margin-top:4px}
    .submit-btn:hover{background:var(--copper-light)}
    .submit-btn:disabled{background:var(--border);cursor:not-allowed;color:var(--muted)}

    /* SUCCESS */
    .success-screen{text-align:center;padding:10px 0}
    .success-icon{font-size:3.5rem;margin-bottom:16px}
    .success-screen h2{font-family:'Playfair Display',serif;font-size:1.6rem;margin-bottom:10px}
    .success-screen p{color:var(--muted);font-size:.92rem;line-height:1.6}

    /* FEATURES */
    .features{background:var(--charcoal);padding:40px 5%;display:flex;flex-wrap:wrap;justify-content:center;gap:40px}
    .feature{display:flex;align-items:center;gap:14px;color:rgba(255,255,255,.75)}
    .feature-icon{font-size:1.8rem}
    .feature-text strong{display:block;color:#fff;font-size:.95rem}
    .feature-text span{font-size:.8rem}

    /* FOOTER */
    footer{padding:32px 5%;text-align:center;border-top:1px solid var(--border);color:var(--muted);font-size:.82rem}
    footer strong{color:var(--copper)}

    /* TOAST */
    .toast{position:fixed;bottom:28px;left:50%;transform:translateX(-50%) translateY(20px);background:var(--charcoal);color:#fff;padding:12px 24px;border-radius:50px;font-size:.88rem;font-weight:500;z-index:400;opacity:0;transition:all .3s;pointer-events:none;white-space:nowrap}
    .toast.show{opacity:1;transform:translateX(-50%) translateY(0)}

    /* NO RESULTS */
    .no-results{grid-column:1/-1;text-align:center;padding:60px 20px;color:var(--muted)}
    .no-results .nr-icon{font-size:3rem;margin-bottom:12px}

    @media(max-width:640px){
      .nav-links{display:none}
      .hero{padding:48px 5%}
      .cart-sidebar{width:100%}
      .form-row{grid-template-columns:1fr}
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    K.A Songadhwala
    <span>Zampa Bazar · Surat</span>
  </div>
  <ul class="nav-links">
    <li><a href="#products">Products</a></li>
    <li><a href="#features">Why Us</a></li>
    <li><a href="#footer">Contact</a></li>
  </ul>
  <button class="cart-btn" onclick="openCart()">
    🛒 Cart
    <span class="cart-count" id="cartCount">0</span>
  </button>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-text">
    <p class="hero-eyebrow">Trusted Since 1970 · Surat</p>
    <h1 class="hero-headline">
      <em>K.A Songadhwala</em><br>Premium Utensils &<br>Hotel Appliances
    </h1>
    <p class="hero-address">📍 Zampa Bazar, Tower Road, Surat – 295003</p>
    <p class="hero-sub">Your trusted destination for professional cookware, hotel supplies, tableware and appliances — all under one roof in Surat.</p>
    <a href="#products" class="hero-cta">Shop Now →</a>
    <div class="hero-stats">
      <div class="stat"><div class="stat-num">500+</div><div class="stat-label">Products</div></div>
      <div class="stat"><div class="stat-num">5K+</div><div class="stat-label">Happy Clients</div></div>
      <div class="stat"><div class="stat-num">55+</div><div class="stat-label">Years Trusted</div></div>
    </div>
  </div>
</section>

<!-- CATEGORIES -->
<section class="categories">
  <h2 class="section-title">Our Collection</h2>
  <p class="section-sub">Browse by category or explore everything we offer</p>
  <div class="cat-tabs">
    <button class="cat-tab active" onclick="filterProducts('all',this)">All Products</button>
    <button class="cat-tab" onclick="filterProducts('cookware',this)">Cookware</button>
    <button class="cat-tab" onclick="filterProducts('cutlery',this)">Cutlery & Tools</button>
    <button class="cat-tab" onclick="filterProducts('tableware',this)">Tableware</button>
    <button class="cat-tab" onclick="filterProducts('appliances',this)">Appliances</button>
    <button class="cat-tab" onclick="filterProducts('hotel',this)">Hotel Supplies</button>
    <button class="cat-tab" onclick="filterProducts('beverage',this)">Beverages</button>
  </div>
</section>

<!-- PRODUCTS -->
<section id="products">
  <div class="product-grid" id="productGrid"></div>
</section>

<!-- FEATURES -->
<section class="features" id="features">
  <div class="feature"><div class="feature-icon">🚚</div><div class="feature-text"><strong>Fast Delivery</strong><span>Across Surat & Gujarat</span></div></div>
  <div class="feature"><div class="feature-icon">🛡️</div><div class="feature-text"><strong>Quality Assured</strong><span>Every product tested & certified</span></div></div>
  <div class="feature"><div class="feature-icon">🔄</div><div class="feature-text"><strong>Easy Returns</strong><span>30-day hassle-free returns</span></div></div>
  <div class="feature"><div class="feature-icon">📞</div><div class="feature-text"><strong>WhatsApp Support</strong><span>+91 88665 37046</span></div></div>
</section>

<!-- FOOTER -->
<footer id="footer">
  <p><strong>K.A Songadhwala</strong></p>
  <p style="margin-top:6px">📍 K.A Songadhwala, Zampa Bazar, Tower Road, Surat – 295003</p>
  <p style="margin-top:4px">📞 <a href="https://wa.me/918866537046" style="color:var(--copper);text-decoration:none">+91 88665 37046</a> &nbsp;|&nbsp; © 2026 All rights reserved</p>
</footer>

<!-- CART SIDEBAR -->
<div class="cart-overlay" id="cartOverlay" onclick="closeCart()"></div>
<div class="cart-sidebar" id="cartSidebar">
  <div class="cart-header">
    <h2>🛒 Your Cart</h2>
    <button class="close-btn" onclick="closeCart()">✕</button>
  </div>
  <div class="cart-items" id="cartItems"></div>
  <div class="cart-footer" id="cartFooter" style="display:none">
    <div class="cart-total"><span>Total</span><span id="cartTotal">₹0</span></div>
    <button class="checkout-btn" onclick="openOrderModal()">Place Order →</button>
  </div>
</div>

<!-- ORDER MODAL -->
<div class="modal-overlay" id="modalOverlay">
  <div class="modal">
    <button class="modal-close" onclick="closeModal()">✕</button>
    <div id="modalContent"></div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
  /* ── PRODUCTS — Replace with your real products ── */
  const products = [
    {
      id:1, name:"Enamel Frying Bowl – Set of 3", cat:"cookware",
      img:"", emoji:"🥣",
      price:500, desc:"Available in Red & Blue. Heats up quickly, gas saver, even heat distribution. Perfect for shallow frying. Lightweight, toxin-free & long lasting. Trusted quality since 1970.", badge:"Bestseller"
    },
  ];

  /* ── STATE ── */
  let cart = [];

  /* ── RENDER ── */
  function renderProducts(data) {
    const grid = document.getElementById('productGrid');
    if (!data.length) {
      grid.innerHTML = `<div class="no-results"><div class="nr-icon">🔍</div><p>No products in this category.</p></div>`;
      return;
    }
    grid.innerHTML = data.map(p => `
      <div class="product-card" id="card-${p.id}">
        <div class="product-image">
          ${p.badge ? `<span class="product-badge">${p.badge}</span>` : ''}
          <span class="emoji-placeholder" id="emoji-${p.id}">${p.emoji}</span>
          <img id="img-${p.id}" src="" alt="${p.name}" style="display:none"/>
        </div>
        <div class="product-body">
          <div class="product-category">${p.cat}</div>
          <div class="product-name">${p.name}</div>
          <div class="product-desc">${p.desc}</div>
          <div class="product-footer">
            <div class="product-price">₹${p.price.toLocaleString('en-IN')}<small>/unit</small></div>
            <button class="add-to-cart" id="btn-${p.id}" onclick="addToCart(${p.id})">Add to Cart</button>
          </div>
        </div>
      </div>`).join('');
  }

  function filterProducts(cat, el) {
    document.querySelectorAll('.cat-tab').forEach(t => t.classList.remove('active'));
    el.classList.add('active');
    renderProducts(cat === 'all' ? products : products.filter(p => p.cat === cat));
    updateCartBtns();
  }

  /* ── CART ── */
  function addToCart(id) {
    const p = products.find(x => x.id === id);
    const ex = cart.find(x => x.id === id);
    if (ex) ex.qty++; else cart.push({...p, qty:1});
    updateCartUI();
    const btn = document.getElementById(`btn-${id}`);
    if (btn) { btn.textContent='✓ Added'; btn.classList.add('added'); setTimeout(()=>{btn.textContent='Add to Cart';btn.classList.remove('added');},1800); }
    showToast(`🛒 ${p.name} added to cart`);
  }

  function changeQty(id, d) {
    const item = cart.find(x => x.id === id);
    if (!item) return;
    item.qty += d;
    if (item.qty <= 0) cart = cart.filter(x => x.id !== id);
    updateCartUI();
  }

  function removeItem(id) { cart = cart.filter(x => x.id !== id); updateCartUI(); }

  function updateCartUI() {
    const count = cart.reduce((s,x) => s+x.qty, 0);
    document.getElementById('cartCount').textContent = count;
    const total = cart.reduce((s,x) => s+x.price*x.qty, 0);
    document.getElementById('cartTotal').textContent = `₹${total.toLocaleString('en-IN')}`;
    const itemsEl = document.getElementById('cartItems');
    const footerEl = document.getElementById('cartFooter');
    if (!cart.length) {
      itemsEl.innerHTML = `<div class="cart-empty"><div class="empty-icon">🛒</div><p>Your cart is empty.</p></div>`;
      footerEl.style.display = 'none';
    } else {
      footerEl.style.display = 'block';
      itemsEl.innerHTML = cart.map(item => `
        <div class="cart-item">
          <div class="cart-item-icon">
            ${item.img ? `<img src="${item.img}" alt="$
