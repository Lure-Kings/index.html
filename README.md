<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lure Kings - Premium Fishing Lures</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* [Previous CSS remains unchanged] */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #f5f5f5; color: #333; line-height: 1.6; }
        .header { background-color: #1a365d; padding: 1rem 2rem; position: sticky; top: 0; z-index: 1000; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
        .nav { display: flex; justify-content: space-between; align-items: center; max-width: 1200px; margin: 0 auto; }
        .logo { font-size: 2rem; font-weight: bold; color: white; display: flex; align-items: center; gap: 0.5rem; cursor: pointer; }
        /* Style for the new header logo image */
        #mainHeaderLogo { max-height: 50px; display: none; /* Hidden by default */ }
        #logoText { display: flex; align-items: center; gap: 0.5rem; }
        .logo i { font-size: 1.8rem; color: #f8d56b; }
        .nav-buttons { display: flex; gap: 1rem; align-items: center; }
        .btn { padding: 0.5rem 1rem; border: none; border-radius: 4px; cursor: pointer; font-weight: 600; transition: all 0.2s ease; }
        .btn-primary { background-color: #1a365d; color: white; }
        .btn-secondary { background-color: transparent; color: white; border: 1px solid white; }
        .btn:hover { opacity: 0.9; }
        .cart-icon { position: relative; }
        .cart-count { position: absolute; top: -8px; right: -8px; background: #e74c3c; color: white; border-radius: 50%; width: 20px; height: 20px; display: flex; align-items: center; justify-content: center; font-size: 0.75rem; font-weight: bold; }
        .container { max-width: 1200px; margin: 2rem auto; padding: 0 1rem; }
        .hero { text-align: center; margin-bottom: 3rem; padding: 2rem 0; background-color: white; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
        .hero h1 { font-size: 2.5rem; margin-bottom: 1rem; color: #1a365d; }
        .hero p { font-size: 1.1rem; max-width: 600px; margin: 0 auto; color: #666; }
        .categories { display: flex; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 2rem; justify-content: center; }
        .category-btn { padding: 0.5rem 1rem; background: white; border: 1px solid #ddd; border-radius: 4px; cursor: pointer; transition: all 0.2s ease; }
        .category-btn:hover, .category-btn.active { background: #1a365d; border-color: #1a365d; color: white; }
        .products-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1.5rem; margin-bottom: 3rem; }
        .product-card { background: white; border: 1px solid #ddd; border-radius: 8px; overflow: hidden; box-shadow: 0 2px 5px rgba(0,0,0,0.1); transition: all 0.2s ease; }
        .product-card:hover { transform: translateY(-5px); box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        .product-image { width: 100%; height: 200px; object-fit: cover; border-bottom: 1px solid #ddd; }
        .product-info { padding: 1rem; }
        .product-title { font-size: 1.1rem; font-weight: bold; margin-bottom: 0.5rem; color: #1a365d; }
        .product-price { font-size: 1.2rem; font-weight: bold; color: #e74c3c; margin-bottom: 1rem; }
        .product-description { color: #666; margin-bottom: 1rem; font-size: 0.9rem; }
        .add-to-cart { width: 100%; background-color: #1a365d; color: white; border: none; padding: 0.5rem; border-radius: 4px; cursor: pointer; font-weight: 600; transition: all 0.2s ease; }
        .add-to-cart:hover { background-color: #142a4a; }
        .modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, 0.5); z-index: 2000; }
        .modal-content { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); background: white; border-radius: 8px; padding: 2rem; max-width: 90%; width: 600px; max-height: 90%; overflow-y: auto; box-shadow: 0 5px 15px rgba(0,0,0,0.2); color: #333; }
        .close { position: absolute; top: 1rem; right: 1rem; font-size: 1.5rem; cursor: pointer; color: #666; }
        .close:hover { color: #333; }
        .cart-item { display: flex; align-items: center; padding: 1rem; border-bottom: 1px solid #ddd; gap: 1rem; }
        .cart-item img { width: 60px; height: 60px; object-fit: cover; border-radius: 4px; border: 1px solid #ddd; }
        .cart-item-info { flex-grow: 1; }
        .cart-item-title { font-weight: bold; margin-bottom: 0.25rem; color: #1a365d; }
        .quantity-controls { display: flex; align-items: center; gap: 0.5rem; margin: 0.5rem 0; }
        .quantity-btn { background: #1a365d; color: white; border: none; width: 25px; height: 25px; border-radius: 4px; cursor: pointer; display: flex; align-items: center; justify-content: center; }
        .quantity-btn:hover { background: #142a4a; }
        .remove-item { background: #e74c3c; color: white; border: none; padding: 0.25rem 0.5rem; border-radius: 4px; cursor: pointer; font-size: 0.8rem; }
        .remove-item:hover { background: #c0392b; }
        .cart-total { text-align: right; padding: 1rem 0; font-size: 1.3rem; font-weight: bold; color: #1a365d; border-top: 1px solid #ddd; margin-top: 1rem; }
        .admin-form { background: white; border: 1px solid #ddd; padding: 1.5rem; border-radius: 8px; margin-bottom: 2rem; }
        .form-group { margin-bottom: 1rem; }
        .form-group label { display: block; margin-bottom: 0.5rem; font-weight: 600; color: #1a365d; }
        .form-group label .required-star { color: #e74c3c; margin-left: 2px; }
        .form-group input, .form-group textarea, .form-group select { width: 100%; padding: 0.5rem; border: 1px solid #ddd; border-radius: 4px; font-size: 1rem; }
        .form-group input:focus, .form-group textarea:focus, .form-group select:focus { outline: none; border-color: #1a365d; }
        .hidden { display: none !important; }
        .checkout-form { max-width: 500px; margin: 0 auto; }
        .file-upload-area { border: 2px dashed #ddd; border-radius: 8px; padding: 1.5rem; text-align: center; cursor: pointer; margin-bottom: 1rem; }
        .file-upload-area:hover { border-color: #1a365d; }
        .image-preview { max-width: 200px; max-height: 200px; border-radius: 8px; margin-top: 1rem; border: 1px solid #ddd; }
        .payment-info { background: #f9f9f9; border: 1px solid #ddd; padding: 1rem; border-radius: 8px; margin-bottom: 1rem; }
        .payment-info h4 { color: #1a365d; margin-bottom: 0.5rem; }
        .payment-method { padding: 0.5rem; border: 1px solid #ddd; border-radius: 4px; margin-bottom: 0.5rem; }
        .toast { position: fixed; bottom: 20px; right: 20px; background: #1a365d; color: white; padding: 1rem; border-radius: 4px; box-shadow: 0 2px 10px rgba(0,0,0,0.2); z-index: 3000; opacity: 0; visibility: hidden; transition: opacity 0.3s, visibility 0.3s; }
        .toast.show { opacity: 1; visibility: visible; }
        .admin-logo { text-align: center; margin-bottom: 1.5rem; }
        .admin-logo img { max-width: 200px; height: auto; }
        .logo-upload-container { margin-bottom: 1.5rem; text-align: center; }
        .logo-preview { max-width: 200px; max-height: 100px; margin-top: 1rem; display: none; }
        .summary-line { display: flex; justify-content: space-between; font-size: 1rem; padding: 0.25rem 0; }
        .summary-line.total { font-weight: bold; font-size: 1.2rem; margin-top: 0.5rem; border-top: 1px solid #ccc; padding-top: 0.5rem; }
        @media (max-width: 768px) {
            .nav { flex-direction: column; gap: 1rem; }
            .hero h1 { font-size: 2rem; }
            .products-grid { grid-template-columns: 1fr; }
            .modal-content { width: 95%; }
        }
    </style>
</head>
<body>
    <header class="header">
        <nav class="nav">
            <div class="logo" id="logo">
                <img id="mainHeaderLogo" alt="Company Logo">
                <span id="logoText">
                    <i class="fas fa-crown"></i>
                    Lure Kings
                </span>
            </div>
            <div class="nav-buttons">
                <button class="btn btn-secondary" onclick="showView('store')">Store</button>
                <button class="btn btn-primary cart-icon" onclick="showCart()">
                    <i class="fas fa-shopping-cart"></i>
                    <span class="cart-count" id="cartCount">0</span>
                </button>
            </div>
        </nav>
    </header>

    <div class="toast" id="toast">Item added to cart!</div>

    <div class="container">
        <div id="storeView">
            </div>

        <div id="adminView" class="hidden">
             </div>
    </div>

    <div id="cartModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeCart()">&times;</span>
            <h2 style="margin-bottom: 1rem; color: #1a365d;">Shopping Cart</h2>
            <div id="cartItems"></div>
            <div class="cart-total">
                <div id="cartSummary">
                    <div class="summary-line">
                        <span>Subtotal:</span>
                        <span id="cartSubtotalValue">$0.00</span>
                    </div>
                </div>
            </div>
            <button class="btn btn-primary" onclick="showCheckout()" style="width: 100%; margin-top: 1rem;">
                Proceed to Checkout
            </button>
        </div>
    </div>

    <div id="checkoutModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeCheckout()">&times;</span>
            <h2 style="margin-bottom: 1rem; color: #1a365d;">Secure Checkout</h2>
            
            <form id="checkoutForm" method="POST">
                <input type="hidden" name="_subject" value="New Order from Lure Kings">
                <input type="hidden" name="_template" value="table">
                <input type="hidden" name="_next"> <input type="hidden" name="_cc" value="lure.kings.fishing.aus@gmail.com">
                <input type="hidden" name="_autoresponse" value="Thank you for your order! We'll process it shortly.">
                
                <div class="form-group">
                    <label for="customerName">Full Name<span class="required-star">*</span></label>
                    <input type="text" id="customerName" name="name" required>
                </div>
                <div class="form-group">
                    <label for="customerEmail">Email Address<span class="required-star">*</span></label>
                    <input type="email" id="customerEmail" name="email" required>
                </div>
                <div class="form-group">
                    <label for="customerPhone">Phone Number<span class="required-star">*</span></label>
                    <input type="tel" id="customerPhone" name="phone" pattern="[0-9]*" oninput="this.value = this.value.replace(/[^0-9]/g, '');" required>
                </div>
                <div class="form-group">
                    <label for="customerAddress">Delivery Address<span class="required-star">*</span></label>
                    <textarea id="customerAddress" name="address" rows="3" required></textarea>
                </div>
                
                <div class="form-group">
                    <button type="button" class="btn btn-secondary" style="width:100%; border-color:#1a365d; color:#1a365d;" onclick="calculateShipping()">Calculate Shipping</button>
                    <small style="display: block; text-align: center; margin-top: 5px;">Click to calculate shipping fee based on your address.</small>
                </div>
                
                <div class="form-group">
                    <label for="orderNotes">Order Notes (Optional)</label>
                    <textarea id="orderNotes" name="notes" rows="2" placeholder="Any special instructions..."></textarea>
                </div>

                <div class="form-group payment-info">
                    <h4>Payment Method<span class="required-star">*</span></h4>
                    <div class="payment-method">
                        <input type="radio" id="bankTransfer" name="payment_method" value="Bank Transfer" required>
                        <label for="bankTransfer">Direct Bank Transfer</label>
                        <div id="bankDetails" class="hidden" style="padding-left: 20px; font-size: 0.9em; opacity: 0.8;">
                            <p><strong>Bank:</strong> ANZ Bank | <strong>Account:</strong> Lure Kings Pty Ltd<br>
                               <strong>BSB:</strong> 012-345 | <strong>Acc No:</strong> 123456789<br>
                               Use your Order ID as reference.</p>
                        </div>
                    </div>
                    <div class="payment-method">
                        <input type="radio" id="stripe" name="payment_method" value="Stripe">
                        <label for="stripe">Stripe (Credit/Debit Card)</label>
                        <div id="stripe-element" class="hidden" style="padding: 10px;">
                            <p style="font-style:italic;">Stripe integration placeholder.</p>
                        </div>
                    </div>
                     <div class="payment-method">
                        <input type="radio" id="paypal" name="payment_method" value="PayPal">
                        <label for="paypal">PayPal</label>
                        <div id="paypal-button-container" class="hidden" style="padding: 10px;">
                            <p style="font-style:italic;">PayPal integration placeholder.</p>
                        </div>
                    </div>
                </div>

                <div class="form-group">
                    <label>Order Summary</label>
                    <div id="orderItemsDisplay" style="padding: 0.5rem; background: #f5f5f5; border-radius: 4px;"></div>
                </div>
                <div id="checkoutSummary" class="cart-total" style="padding: 1rem; background: #f9f9f9; border-radius: 4px; text-align:right;">
                     <div class="summary-line">
                        <span>Subtotal:</span>
                        <span id="checkoutSubtotal">$0.00</span>
                    </div>
                    <div class="summary-line">
                        <span>Shipping:</span>
                        <span id="checkoutShipping">$0.00</span>
                    </div>
                    <div class="summary-line total">
                        <span>Total:</span>
                        <span id="checkoutTotal">$0.00</span>
                    </div>
                </div>
                <input type="hidden" id="orderItems" name="order_items">
                <input type="hidden" id="orderTotal" name="order_total">
                <input type="hidden" id="shippingCost" name="shipping_cost">
                
                <button type="submit" class="btn btn-primary" style="width: 100%; margin-top: 1rem;">
                    Place Order
                </button>
            </form>
        </div>
    </div>
    
    <script>
    // --- GLOBAL STATE ---
    let isAdminLoggedIn = false;
    const ADMIN_PASSWORD = "Maxchingershambo08"; // As requested
    let clickCount = 0;
    let clickTimeout;
    let products = [];
    let cart = [];
    let currentFilter = 'all';
    let shippingCost = 0; // NEW: To hold shipping cost
    const FLAT_RATE_SHIPPING = 10.00; // NEW: Placeholder shipping fee

    // --- FALLBACK DATA ---
    const defaultProducts = [
        { id: 1, name: "Bass Pro Jig Head", category: "jigs", price: 12.99, description: "Premium jig head perfect for bass fishing with realistic action.", image: "https://images.unsplash.com/photo-1544551763-46a013bb70d5?w=400&h=300&fit=crop" },
        { id: 2, name: "Soft Plastic Worm", category: "soft-plastics", price: 8.49, description: "Lifelike soft plastic worm that attracts fish with its natural movement.", image: "https://images.unsplash.com/photo-1559827260-dc66d52bef19?w=400&h=300&fit=crop" },
        { id: 3, name: "Popper Topwater Lure", category: "topwaters", price: 15.99, description: "Creates explosive surface action that drives fish wild.", image: "https://images.unsplash.com/photo-1578662996442-48f60103fc96?w=400&h=300&fit=crop" },
        { id: 4, name: "Colorado Spinnerbait", category: "spinnerbaits", price: 11.79, description: "Classic spinnerbait with Colorado blade for maximum flash and vibration.", image: "https://images.unsplash.com/photo-1559827260-dc66d52bef19?w=400&h=300&fit=crop" }
    ];

    // --- APP INITIALIZATION ---
    document.addEventListener('DOMContentLoaded', init);

    function init() {
        // Load data from localStorage
        const storedProducts = localStorage.getItem('products');
        products = storedProducts ? JSON.parse(storedProducts) : defaultProducts;

        const storedCart = localStorage.getItem('cart');
        cart = storedCart ? JSON.parse(storedCart) : [];

        // UPDATED: Load logo and apply to main header
        const savedLogo = localStorage.getItem('companyLogo');
        if (savedLogo) {
            applyLogo(savedLogo);
        } else {
            // If no logo, show text
            document.getElementById('logoText').style.display = 'flex';
        }
        
        // Render initial views
        renderProducts();
        updateCartCount();
        renderAdminProducts();
        
        // Setup listeners
        setupEventListeners();
        setupImageUpload('imageUpload', 'imagePreview', 'productImageURL', '.admin-form .file-upload-area');
        setupImageUpload('logoUpload', 'logoPreview', null, '.logo-upload-container .file-upload-area', handleLogoUpload);

        // Handle order success message from redirect
        const urlParams = new URLSearchParams(window.location.search);
        if (urlParams.has('order') && urlParams.get('order') === 'success') {
            showToast("Thank you! Your order has been placed successfully.");
            // Optional: Clean up the URL
            window.history.replaceState({}, document.title, window.location.pathname);
        }
    }

    // --- EVENT LISTENERS ---
    function setupEventListeners() {
        document.getElementById('logo').addEventListener('click', handleCrownClick);
        
        document.getElementById('productForm').addEventListener('submit', function(e) {
            e.preventDefault();
            saveProduct();
        });

        const checkoutForm = document.getElementById('checkoutForm');
        checkoutForm.addEventListener('submit', function(e) {
            e.preventDefault(); // Prevent default submission
            const selectedPayment = document.querySelector('input[name="payment_method"]:checked');
            if (!selectedPayment) {
                alert("Please select a payment method.");
                return;
            }
            if (shippingCost === 0) {
                 alert("Please calculate shipping before placing the order.");
                 return;
            }
            prepareOrderForSubmission();
            checkoutForm.submit(); // Manually submit the form
        });
        
        // Payment method display logic
        document.querySelectorAll('input[name="payment_method"]').forEach(radio => {
            radio.addEventListener('change', (e) => {
                document.getElementById('bankDetails').classList.toggle('hidden', e.target.id !== 'bankTransfer');
                document.getElementById('stripe-element').classList.toggle('hidden', e.target.id !== 'stripe');
                document.getElementById('paypal-button-container').classList.toggle('hidden', e.target.id !== 'paypal');
            });
        });
    }

    // --- NEW: Shipping Calculation Placeholder ---
    function calculateShipping() {
        const address = document.getElementById('customerAddress').value;
        if (!address.trim()) {
            alert("Please enter a delivery address before calculating shipping.");
            return;
        }
        shippingCost = FLAT_RATE_SHIPPING;
        updateAllTotals();
        showToast(`Shipping cost calculated: $${shippingCost.toFixed(2)}`);
    }

    // --- CART & TOTALS ---
    function showCart() {
        updateAllTotals();
        document.getElementById('cartModal').style.display = 'block';
    }
    
    function showCheckout() {
        if (cart.length === 0) {
            alert("Your cart is empty. Please add items before checking out.");
            return;
        }
        shippingCost = 0; // Reset shipping cost when opening checkout
        updateAllTotals();
        closeCart();
        document.getElementById('checkoutModal').style.display = 'block';
    }
    
    function updateAllTotals() {
        const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
        const total = subtotal + shippingCost;
        
        // Update Cart Modal
        document.getElementById('cartItems').innerHTML = cart.length ? cart.map(item => `
            <div class="cart-item">
                <img src="${item.image}" alt="${item.name}">
                <div class="cart-item-info">
                    <div class="cart-item-title">${item.name}</div>
                    <div>$${item.price.toFixed(2)} each</div>
                    <div class="quantity-controls">
                        <button class="quantity-btn" onclick="updateCartItem(${item.id}, -1)">-</button>
                        <span>${item.quantity}</span>
                        <button class="quantity-btn" onclick="updateCartItem(${item.id}, 1)">+</button>
                    </div>
                </div>
                <div>
                   <div style="font-weight: bold; text-align: right;">$${(item.price * item.quantity).toFixed(2)}</div>
                   <button class="remove-item" style="margin-top: 5px;" onclick="removeFromCart(${item.id})">Remove</button>
                </div>
            </div>
        `).join('') : '<p>Your cart is empty.</p>';
        document.getElementById('cartSubtotalValue').textContent = `$${subtotal.toFixed(2)}`;

        // Update Checkout Modal
        document.getElementById('orderItemsDisplay').innerHTML = cart.map(item => `
            <div class="summary-line"><span>${item.name} (x${item.quantity})</span><span>$${(item.price * item.quantity).toFixed(2)}</span></div>
        `).join('');
        document.getElementById('checkoutSubtotal').textContent = `$${subtotal.toFixed(2)}`;
        document.getElementById('checkoutShipping').textContent = `$${shippingCost.toFixed(2)}`;
        document.getElementById('checkoutTotal').textContent = `$${total.toFixed(2)}`;
    }
    
    function updateCartItem(productId, change) {
        const item = cart.find(item => item.id === productId);
        if (!item) return;
        item.quantity += change;
        if (item.quantity <= 0) {
            cart = cart.filter(i => i.id !== productId);
        }
        saveCartToStorage();
        updateCartCount();
        updateAllTotals();
    }
    
    function removeFromCart(productId) {
        cart = cart.filter(item => item.id !== productId);
        saveCartToStorage();
        updateCartCount();
        updateAllTotals();
    }
    
    function prepareOrderForSubmission() {
        const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
        const total = subtotal + shippingCost;

        const orderSummary = cart.map(item => 
            `${item.name} (Qty: ${item.quantity})`
        ).join('\n');
        
        document.getElementById('orderItems').value = orderSummary;
        document.getElementById('shippingCost').value = `$${shippingCost.toFixed(2)}`;
        document.getElementById('orderTotal').value = `$${total.toFixed(2)}`;

        const checkoutForm = document.getElementById('checkoutForm');
        // UPDATED: Dynamically set action and redirect URL
        checkoutForm.action = "https://formsubmit.co/lure.kings.fishing.aus@gmail.com";
        // This will redirect back to the current page with a success flag
        checkoutForm.querySelector('[name="_next"]').value = `${window.location.origin}${window.location.pathname}?order=success`;

        // Clear cart after preparing for submission
        cart = [];
        shippingCost = 0;
        saveCartToStorage();
        updateCartCount();
    }

    // --- LOGO HANDLING ---
    function applyLogo(logoUrl) {
        const mainLogoImg = document.getElementById('mainHeaderLogo');
        const adminLogoImg = document.getElementById('companyLogo');
        const logoPreviewImg = document.getElementById('logoPreview');
        const logoText = document.getElementById('logoText');

        mainLogoImg.src = logoUrl;
        mainLogoImg.style.display = 'block';
        adminLogoImg.src = logoUrl;
        logoPreviewImg.src = logoUrl;
        logoPreviewImg.style.display = 'block';
        logoText.style.display = 'none'; // Hide text when logo is present
    }
    
    function handleLogoUpload(event) {
        const file = event.target.files[0];
        if (!file) return;
        
        const reader = new FileReader();
        reader.onload = function(e) {
            const logoUrl = e.target.result;
            applyLogo(logoUrl); // Apply to all logo elements
            localStorage.setItem('companyLogo', logoUrl); // Persist logo
        };
        reader.readAsDataURL(file);
    }
    
    // --- OTHER FUNCTIONS (Mostly Unchanged) ---
    // (addProduct, deleteProduct, showToast, setupImageUpload, etc.)
    // Note: The structure of these can remain largely the same as in the previous version,
    // as they correctly modify the `products` array. `saveProductsToStorage()` is called within them.
    // The following includes all remaining functions for completeness.
    function saveProductsToStorage() { localStorage.setItem('products', JSON.stringify(products)); }
    function saveCartToStorage() { localStorage.setItem('cart', JSON.stringify(cart)); }
    function showView(view) { if (view === 'admin' && !isAdminLoggedIn) { showAdminLogin(); return; } document.getElementById('storeView').classList.toggle('hidden', view !== 'store'); document.getElementById('adminView').classList.toggle('hidden', view !== 'admin'); }
    function renderProducts() { const grid = document.getElementById('productsGrid'); grid.innerHTML = ''; const filtered = currentFilter === 'all' ? products : products.filter(p => p.category === currentFilter); filtered.forEach(p => { const card = document.createElement('div'); card.className = 'product-card'; card.innerHTML = `<img src="${p.image}" alt="${p.name}" class="product-image"><div class="product-info"><h3 class="product-title">${p.name}</h3><div class="product-price">$${p.price.toFixed(2)}</div><p class="product-description">${p.description}</p><button class="add-to-cart" onclick="addToCart(${p.id})">Add to Cart</button></div>`; grid.appendChild(card); }); }
    function filterByCategory(category) { currentFilter = category; renderProducts(); document.querySelectorAll('.category-btn').forEach(btn => { btn.classList.remove('active'); if (btn.textContent.toLowerCase().includes(category)) btn.classList.add('active'); }); }
    function addToCart(productId) { const product = products.find(p => p.id === productId); if (!product) return; const item = cart.find(i => i.id === productId); if (item) { item.quantity++; } else { cart.push({...product, quantity: 1}); } saveCartToStorage(); updateCartCount(); showToast(`${product.name} added to cart`); }
    function updateCartCount() { document.getElementById('cartCount').textContent = cart.reduce((t, i) => t + i.quantity, 0); }
    function closeCart() { document.getElementById('cartModal').style.display = 'none'; }
    function closeCheckout() { document.getElementById('checkoutModal').style.display = 'none'; }
    function handleCrownClick() { clickCount++; clearTimeout(clickTimeout); clickTimeout = setTimeout(() => { clickCount = 0; }, 1000); if (clickCount >= 3) { clickCount = 0; showAdminLogin(); } }
    function showAdminLogin() { const pw = prompt("Enter admin password:"); if (pw === ADMIN_PASSWORD) { isAdminLoggedIn = true; showView('admin'); } else if (pw !== null) { alert('Incorrect password!'); } }
    function renderAdminProducts() { const cont = document.getElementById('adminProductsList'); cont.innerHTML = ''; if (!products.length) { cont.innerHTML = '<p>No products found</p>'; return; } products.slice().reverse().forEach(p => { const el = document.createElement('div'); el.className = 'product-card'; el.innerHTML = `<img src="${p.image}" alt="${p.name}" class="product-image"><div class="product-info"><h3 class="product-title">${p.name}</h3><p style="font-size:0.9em;color:#666">${p.category}</p><p style="font-weight:bold;color:#e74c3c">$${p.price.toFixed(2)}</p><div style="margin-top:1rem;"><button onclick="editProduct(${p.id})" class="btn btn-secondary">Edit</button><button onclick="deleteProduct(${p.id})" class="btn btn-secondary" style="background:#e74c3c;">Delete</button></div></div>`; cont.appendChild(el); }); }
    function saveProduct() { const id = document.getElementById('productId').value; const name = document.getElementById('productName').value; const cat = document.getElementById('productCategory').value; const price = parseFloat(document.getElementById('productPrice').value); const desc = document.getElementById('productDescription').value; const img = document.getElementById('productImageURL').value; if (!name || !cat || isNaN(price) || !desc || !img) { alert('Please fill all fields and provide an image.'); return; } if (id) { const i = products.findIndex(p => p.id == id); if (i > -1) products[i] = { ...products[i], name, category: cat, price, description: desc, image: img }; } else { products.push({ id: Date.now(), name, category: cat, price, description: desc, image: img }); } saveProductsToStorage(); renderProducts(); renderAdminProducts(); document.getElementById('productForm').reset(); document.getElementById('productId').value = ''; document.getElementById('imagePreview').style.display = 'none'; showToast(id ? 'Product updated!' : 'Product added!'); }
    function editProduct(id) { const p = products.find(prod => prod.id === id); if (!p) return; document.getElementById('productId').value = p.id; document.getElementById('productName').value = p.name; document.getElementById('productCategory').value = p.category; document.getElementById('productPrice').value = p.price; document.getElementById('productDescription').value = p.description; document.getElementById('productImageURL').value = p.image; const prev = document.getElementById('imagePreview'); prev.src = p.image; prev.style.display = 'block'; document.getElementById('productForm').scrollIntoView({ behavior: 'smooth' }); }
    function deleteProduct(id) { if (!confirm('Are you sure you want to delete this product?')) return; products = products.filter(p => p.id !== id); saveProductsToStorage(); renderProducts(); renderAdminProducts(); showToast('Product deleted.'); }
    function showToast(message) { const t = document.getElementById('toast'); t.textContent = message; t.classList.add('show'); setTimeout(() => { t.classList.remove('show'); }, 3000); }
    function setupImageUpload(inputId, previewId, urlInputId, areaSelector, customHandler) { const fileInput = document.getElementById(inputId); const uploadArea = document.querySelector(areaSelector); const handler = customHandler || function(event) { const file = event.target.files[0]; if (!file) return; const reader = new FileReader(); reader.onload = function(e) { document.getElementById(previewId).src = e.target.result; document.getElementById(previewId).style.display = 'block'; if (urlInputId) document.getElementById(urlInputId).value = e.target.result; }; reader.readAsDataURL(file); }; fileInput.addEventListener('change', handler); uploadArea.addEventListener('click', () => fileInput.click()); ['dragover', 'drop', 'dragleave'].forEach(evt => { uploadArea.addEventListener(evt, e => { e.preventDefault(); e.stopPropagation(); if (evt === 'dragover') uploadArea.style.borderColor = '#1a365d'; else uploadArea.style.borderColor = '#ddd'; if (evt === 'drop' && e.dataTransfer.files.length) { fileInput.files = e.dataTransfer.files; handler({ target: fileInput }); } }); }); }

    // [The rest of your script, including the closing </script> and </body></html> tags]
    </script>
</body>
</html>
