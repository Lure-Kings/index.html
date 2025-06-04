<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lure Kings - Premium Fishing Lures</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }

        .header {
            background-color: #1a365d;
            padding: 1rem 2rem;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: white;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            cursor: pointer;
        }

        .logo i {
            font-size: 1.8rem;
            color: #f8d56b;
        }

        .nav-buttons {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .btn {
            padding: 0.5rem 1rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s ease;
        }

        .btn-primary {
            background-color: #1a365d;
            color: white;
        }

        .btn-secondary {
            background-color: transparent;
            color: white;
            border: 1px solid white;
        }

        .btn:hover {
            opacity: 0.9;
        }

        .cart-icon {
            position: relative;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #e74c3c;
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.75rem;
            font-weight: bold;
        }

        .container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        .hero {
            text-align: center;
            margin-bottom: 3rem;
            padding: 2rem 0;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #1a365d;
        }

        .hero p {
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
            color: #666;
        }

        .categories {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 2rem;
            justify-content: center;
        }

        .category-btn {
            padding: 0.5rem 1rem;
            background: white;
            border: 1px solid #ddd;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .category-btn:hover, .category-btn.active {
            background: #1a365d;
            border-color: #1a365d;
            color: white;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
            margin-bottom: 3rem;
        }

        .product-card {
            background: white;
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transition: all 0.2s ease;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .product-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-bottom: 1px solid #ddd;
        }

        .product-info {
            padding: 1rem;
        }

        .product-title {
            font-size: 1.1rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            color: #1a365d;
        }

        .product-price {
            font-size: 1.2rem;
            font-weight: bold;
            color: #e74c3c;
            margin-bottom: 1rem;
        }

        .product-description {
            color: #666;
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }

        .add-to-cart {
            width: 100%;
            background-color: #1a365d;
            color: white;
            border: none;
            padding: 0.5rem;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s ease;
        }

        .add-to-cart:hover {
            background-color: #142a4a;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 2000;
        }

        .modal-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            border-radius: 8px;
            padding: 2rem;
            max-width: 90%;
            max-height: 90%;
            overflow-y: auto;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            color: #333;
        }

        .close {
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 1.5rem;
            cursor: pointer;
            color: #666;
        }

        .close:hover {
            color: #333;
        }

        .cart-item {
            display: flex;
            align-items: center;
            padding: 1rem;
            border-bottom: 1px solid #ddd;
            gap: 1rem;
        }

        .cart-item img {
            width: 60px;
            height: 60px;
            object-fit: cover;
            border-radius: 4px;
            border: 1px solid #ddd;
        }

        .cart-item-info {
            flex-grow: 1;
        }

        .cart-item-title {
            font-weight: bold;
            margin-bottom: 0.25rem;
            color: #1a365d;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin: 0.5rem 0;
        }

        .quantity-btn {
            background: #1a365d;
            color: white;
            border: none;
            width: 25px;
            height: 25px;
            border-radius: 4px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .quantity-btn:hover {
            background: #142a4a;
        }

        .remove-item {
            background: #e74c3c;
            color: white;
            border: none;
            padding: 0.25rem 0.5rem;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.8rem;
        }

        .remove-item:hover {
            background: #c0392b;
        }

        .cart-total {
            text-align: center;
            padding: 1rem;
            font-size: 1.3rem;
            font-weight: bold;
            color: #1a365d;
            border-top: 1px solid #ddd;
            margin-top: 1rem;
        }

        .admin-form {
            background: white;
            border: 1px solid #ddd;
            padding: 1.5rem;
            border-radius: 8px;
            margin-bottom: 2rem;
        }

        .form-group {
            margin-bottom: 1rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #1a365d;
        }

        .form-group input, .form-group textarea, .form-group select {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }

        .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
            outline: none;
            border-color: #1a365d;
        }

        .hidden {
            display: none !important;
        }

        .checkout-form {
            max-width: 500px;
            margin: 0 auto;
        }

        .file-upload-area {
            border: 2px dashed #ddd;
            border-radius: 8px;
            padding: 1.5rem;
            text-align: center;
            cursor: pointer;
            margin-bottom: 1rem;
        }

        .file-upload-area:hover {
            border-color: #1a365d;
        }

        .image-preview {
            max-width: 200px;
            max-height: 200px;
            border-radius: 8px;
            margin-top: 1rem;
            border: 1px solid #ddd;
        }

        .payment-info {
            background: #f9f9f9;
            border: 1px solid #ddd;
            padding: 1rem;
            border-radius: 8px;
            margin-bottom: 1rem;
        }

        .payment-info h4 {
            color: #1a365d;
            margin-bottom: 0.5rem;
        }

        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #1a365d;
            color: white;
            padding: 1rem;
            border-radius: 4px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
            z-index: 3000;
            display: none;
        }

        .admin-logo {
            text-align: center;
            margin-bottom: 1.5rem;
        }

        .admin-logo img {
            max-width: 200px;
            height: auto;
        }

        @media (max-width: 768px) {
            .nav {
                flex-direction: column;
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .products-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <nav class="nav">
            <div class="logo" id="logo">
                <i class="fas fa-crown"></i>
                Lure Kings
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
        <!-- Store View -->
        <div id="storeView">
            <div class="hero">
                <h1>Premium Fishing Lures</h1>
                <p>High-quality fishing lures for the serious angler</p>
            </div>

            <div class="categories">
                <button class="category-btn active" onclick="filterByCategory('all')">All Lures</button>
                <button class="category-btn" onclick="filterByCategory('jigs')">Jigs</button>
                <button class="category-btn" onclick="filterByCategory('soft-plastics')">Soft Plastics</button>
                <button class="category-btn" onclick="filterByCategory('topwaters')">Topwaters</button>
                <button class="category-btn" onclick="filterByCategory('spinnerbaits')">Spinnerbaits</button>
            </div>

            <div class="products-grid" id="productsGrid"></div>
        </div>

        <!-- Admin View -->
        <div id="adminView" class="hidden">
            <div class="hero">
                <div class="admin-logo">
                    <img src="https://via.placeholder.com/200x100?text=Lure+Kings+Logo" alt="Lure Kings Logo">
                </div>
                <h1>Admin Dashboard</h1>
                <p>Manage your Lure Kings inventory</p>
            </div>

            <div class="admin-form">
                <h2 style="margin-bottom: 1rem; color: #1a365d;">Add New Product</h2>
                <form id="productForm">
                    <div class="form-group">
                        <label for="productName">Product Name</label>
                        <input type="text" id="productName" required>
                    </div>
                    <div class="form-group">
                        <label for="productCategory">Category</label>
                        <select id="productCategory" required>
                            <option value="">Select Category</option>
                            <option value="jigs">Jigs</option>
                            <option value="soft-plastics">Soft Plastics</option>
                            <option value="topwaters">Topwaters</option>
                            <option value="spinnerbaits">Spinnerbaits</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="productPrice">Price ($)</label>
                        <input type="number" id="productPrice" step="0.01" min="0" required>
                    </div>
                    <div class="form-group">
                        <label for="productDescription">Description</label>
                        <textarea id="productDescription" rows="3" required></textarea>
                    </div>
                    <div class="form-group">
                        <label for="productImage">Product Image</label>
                        <div class="file-upload-area" onclick="document.getElementById('imageUpload').click()">
                            <i class="fas fa-cloud-upload-alt" style="font-size: 2rem; color: #1a365d; margin-bottom: 0.5rem;"></i>
                            <p>Click to upload image or drag & drop</p>
                            <p style="font-size: 0.9rem; opacity: 0.7;">Supports JPG, PNG, GIF</p>
                        </div>
                        <input type="file" id="imageUpload" accept="image/*" style="display: none;">
                        <input type="url" id="productImage" placeholder="Or enter image URL">
                        <img id="imagePreview" class="image-preview" style="display: none;">
                    </div>
                    <button type="submit" class="btn btn-primary" style="width: 100%;">
                        Add Product
                    </button>
                </form>
            </div>

            <div class="admin-form">
                <h2 style="margin-bottom: 1rem; color: #1a365d;">Manage Existing Products</h2>
                <div id="adminProductsList"></div>
            </div>
        </div>
    </div>

    <!-- Cart Modal -->
    <div id="cartModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeCart()">&times;</span>
            <h2 style="margin-bottom: 1rem; color: #1a365d;">
                Shopping Cart
            </h2>
            <div id="cartItems"></div>
            <div class="cart-total" id="cartTotal">Total: $0.00</div>
            <button class="btn btn-primary" onclick="showCheckout()" style="width: 100%; margin-top: 1rem;">
                Proceed to Checkout
            </button>
        </div>
    </div>

    <!-- Checkout Modal -->
    <div id="checkoutModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeCheckout()">&times;</span>
            <h2 style="margin-bottom: 1rem; color: #1a365d;">
                Secure Checkout
            </h2>
            
            <div class="payment-info">
                <h4>Payment Information</h4>
                <p><strong>Bank Details:</strong> ANZ Bank</p>
                <p><strong>Account Name:</strong> Lure Kings Pty Ltd</p>
                <p><strong>BSB:</strong> 012-345</p>
                <p><strong>Account Number:</strong> 123456789</p>
                <p style="margin-top: 0.5rem; font-size: 0.9rem; opacity: 0.8;">
                    Use your order number as the payment reference
                </p>
            </div>

            <div class="checkout-form">
                <form id="checkoutForm">
                    <div class="form-group">
                        <label for="customerName">Full Name</label>
                        <input type="text" id="customerName" required>
                    </div>
                    <div class="form-group">
                        <label for="customerEmail">Email Address</label>
                        <input type="email" id="customerEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="customerPhone">Phone Number</label>
                        <input type="tel" id="customerPhone" required>
                    </div>
                    <div class="form-group">
                        <label for="customerAddress">Delivery Address</label>
                        <textarea id="customerAddress" rows="3" required></textarea>
                    </div>
                    <div class="form-group">
                        <label for="orderNotes">Order Notes (Optional)</label>
                        <textarea id="orderNotes" rows="2" placeholder="Any special instructions..."></textarea>
                    </div>
                    <div class="cart-total" id="checkoutTotal">Total: $0.00</div>
                    <button type="submit" class="btn btn-primary" style="width: 100%; margin-top: 1rem;">
                        Place Order
                    </button>
                </form>
            </div>
        </div>
    </div>

    <script>
        // Global variables
        let isAdminLoggedIn = false;
        const ADMIN_PASSWORD = "lureking2024";
        let clickCount = 0;
        let clickTimeout;
        
        let products = [
            {
                id: 1,
                name: "Bass Pro Jig Head",
                category: "jigs",
                price: 12.99,
                description: "Premium jig head perfect for bass fishing with realistic action.",
                image: "https://images.unsplash.com/photo-1544551763-46a013bb70d5?w=400&h=300&fit=crop"
            },
            {
                id: 2,
                name: "Soft Plastic Worm",
                category: "soft-plastics",
                price: 8.49,
                description: "Lifelike soft plastic worm that attracts fish with its natural movement.",
                image: "https://images.unsplash.com/photo-1559827260-dc66d52bef19?w=400&h=300&fit=crop"
            },
            {
                id: 3,
                name: "Popper Topwater Lure",
                category: "topwaters",
                price: 15.99,
                description: "Creates explosive surface action that drives fish wild.",
                image: "https://images.unsplash.com/photo-1578662996442-48f60103fc96?w=400&h=300&fit=crop"
            },
            {
                id: 4,
                name: "Colorado Spinnerbait",
                category: "spinnerbaits",
                price: 11.79,
                description: "Classic spinnerbait with Colorado blade for maximum flash and vibration.",
                image: "https://images.unsplash.com/photo-1559827260-dc66d52bef19?w=400&h=300&fit=crop"
            }
        ];

        let cart = [];
        let currentFilter = 'all';

        // Initialize the app when page loads
        document.addEventListener('DOMContentLoaded', function() {
            init();
        });

        function init() {
            renderProducts();
            updateCartCount();
            renderAdminProducts();
            setupEventListeners();
            setupImageUpload();
            
            // Add crown click listener
            document.getElementById('logo').addEventListener('click', handleCrownClick);
        }

        function handleCrownClick() {
            clickCount++;
            
            // Reset counter after 1 second
            clearTimeout(clickTimeout);
            clickTimeout = setTimeout(() => {
                clickCount = 0;
            }, 1000);
            
            // If clicked 3 times, show admin login
            if (clickCount >= 3) {
                clickCount = 0;
                showAdminLogin();
            }
        }

        function setupEventListeners() {
            // Admin form submission
            document.getElementById('productForm').addEventListener('submit', function(e) {
                e.preventDefault();
                addProduct();
            });

            // Checkout form submission
            document.getElementById('checkoutForm').addEventListener('submit', function(e) {
                e.preventDefault();
                processCheckout();
            });

            // Admin login form submission
            document.getElementById('adminLoginForm')?.addEventListener('submit', function(e) {
                e.preventDefault();
                const password = document.getElementById('adminPassword').value;
                if (password === ADMIN_PASSWORD) {
                    isAdminLoggedIn = true;
                    closeAdminLogin();
                    showView('admin');
                    document.getElementById('adminPassword').value = '';
                } else {
                    alert('Incorrect password!');
                }
            });

            // Image upload handling
            document.getElementById('imageUpload').addEventListener('change', function(e) {
                handleImageUpload(e);
            });
        }

        // View management
        function showView(view) {
            if (view === 'admin' && !isAdminLoggedIn) {
                showAdminLogin();
                return;
            }
            
            document.getElementById('storeView').classList.toggle('hidden', view !== 'store');
            document.getElementById('adminView').classList.toggle('hidden', view !== 'admin');
        }

        // Product rendering
        function renderProducts() {
            const grid = document.getElementById('productsGrid');
            grid.innerHTML = '';
            
            const filteredProducts = currentFilter === 'all' 
                ? products 
                : products.filter(p => p.category === currentFilter);
            
            filteredProducts.forEach(product => {
                const card = document.createElement('div');
                card.className = 'product-card';
                card.innerHTML = `
                    <img src="${product.image}" alt="${product.name}" class="product-image">
                    <div class="product-info">
                        <h3 class="product-title">${product.name}</h3>
                        <div class="product-price">$${product.price.toFixed(2)}</div>
                        <p class="product-description">${product.description}</p>
                        <button class="add-to-cart" onclick="addToCart(${product.id})">Add to Cart</button>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        function filterByCategory(category) {
            currentFilter = category;
            renderProducts();
            
            // Update active state of category buttons
            document.querySelectorAll('.category-btn').forEach(btn => {
                btn.classList.toggle('active', btn.textContent.toLowerCase().includes(category));
            });
        }

        // Cart functionality
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;
            
            const existingItem = cart.find(item => item.id === productId);
            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({...product, quantity: 1});
            }
            
            updateCartCount();
            showToast(`${product.name} added to cart`);
        }

        function updateCartCount() {
            const count = cart.reduce((total, item) => total + item.quantity, 0);
            document.getElementById('cartCount').textContent = count;
        }

        function showToast(message) {
            const toast = document.getElementById('toast');
            toast.textContent = message;
            toast.style.display = 'block';
            
            setTimeout(() => {
                toast.style.display = 'none';
            }, 3000);
        }

        function showCart() {
            const modal = document.getElementById('cartModal');
            const cartItems = document.getElementById('cartItems');
            const cartTotal = document.getElementById('cartTotal');
            
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                cartItems.innerHTML = '<p>Your cart is empty</p>';
                cartTotal.textContent = 'Total: $0.00';
            } else {
                let total = 0;
                
                cart.forEach(item => {
                    const itemTotal = item.price * item.quantity;
                    total += itemTotal;
                    
                    const cartItem = document.createElement('div');
                    cartItem.className = 'cart-item';
                    cartItem.innerHTML = `
                        <img src="${item.image}" alt="${item.name}">
                        <div class="cart-item-info">
                            <div class="cart-item-title">${item.name}</div>
                            <div>$${item.price.toFixed(2)} each</div>
                            <div class="quantity-controls">
                                <button class="quantity-btn" onclick="updateCartItem(${item.id}, -1)">-</button>
                                <span>${item.quantity}</span>
                                <button class="quantity-btn" onclick="updateCartItem(${item.id}, 1)">+</button>
                            </div>
                            <div>$${itemTotal.toFixed(2)}</div>
                        </div>
                        <button class="remove-item" onclick="removeFromCart(${item.id})">Remove</button>
                    `;
                    cartItems.appendChild(cartItem);
                });
                
                cartTotal.textContent = `Total: $${total.toFixed(2)}`;
                document.getElementById('checkoutTotal').textContent = `Total: $${total.toFixed(2)}`;
            }
            
            modal.style.display = 'block';
        }

        function closeCart() {
            document.getElementById('cartModal').style.display = 'none';
        }

        function updateCartItem(productId, change) {
            const item = cart.find(item => item.id === productId);
            if (!item) return;
            
            item.quantity += change;
            
            if (item.quantity <= 0) {
                removeFromCart(productId);
            } else {
                updateCartCount();
                showCart(); // Refresh cart display
            }
        }

        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCartCount();
            showCart(); // Refresh cart display
        }

        // Checkout functionality
        function showCheckout() {
            closeCart();
            document.getElementById('checkoutModal').style.display = 'block';
        }

        function closeCheckout() {
            document.getElementById('checkoutModal').style.display = 'none';
        }

        function processCheckout() {
            const name = document.getElementById('customerName').value;
            const email = document.getElementById('customerEmail').value;
            
            if (cart.length === 0) {
                alert('Your cart is empty!');
                return;
            }
            
            // Generate order number
            const orderNumber = 'LK-' + Date.now().toString().slice(-6);
            
            // Prepare order details
            const order = {
                orderNumber,
                customer: { name, email },
                items: cart,
                total: cart.reduce((sum, item) => sum + (item.price * item.quantity), 0),
                date: new Date().toISOString()
            };
            
            // In a real app, you would send this data to your server
            console.log('Order placed:', order);
            
            // Send email (simulated - in a real app you would use a backend service)
            sendOrderEmail(order);
            
            alert(`Order #${orderNumber} placed successfully!\nA confirmation has been sent to ${email}`);
            
            // Reset cart and close modals
            cart = [];
            updateCartCount();
            closeCheckout();
            document.getElementById('checkoutForm').reset();
        }

        function sendOrderEmail(order) {
            // This is a simulation - in a real app you would use a backend service
            // to send emails to both the customer and your business email
            
            const emailContent = `
                Order #${order.orderNumber}
                Date: ${new Date(order.date).toLocaleString()}
                Customer: ${order.customer.name}
                Email: ${order.customer.email}
                
                Items:
                ${order.items.map(item => `
                - ${item.name} (${item.quantity} x $${item.price.toFixed(2)}) = $${(item.quantity * item.price).toFixed(2)}
                `).join('')}
                
                Total: $${order.total.toFixed(2)}
                
                Thank you for your order!
                Lure Kings Team
            `;
            
            console.log('Email sent to customer:', order.customer.email);
            console.log('Email sent to business:', 'lure.kings.fishing.aus@gmail.com');
            console.log('Email content:', emailContent);
        }

        // Admin functionality
        function showAdminLogin() {
            // Create a simple password prompt
            const password = prompt("Enter admin password:");
            if (password === ADMIN_PASSWORD) {
                isAdminLoggedIn = true;
                showView('admin');
            } else if (password !== null) {
                alert('Incorrect password!');
            }
        }

        function renderAdminProducts() {
            const container = document.getElementById('adminProductsList');
            container.innerHTML = '';
            
            if (products.length === 0) {
                container.innerHTML = '<p>No products found</p>';
                return;
            }
            
            products.forEach(product => {
                const productElement = document.createElement('div');
                productElement.className = 'product-card';
                productElement.innerHTML = `
                    <div class="product-info">
                        <h3 class="product-title">${product.name}</h3>
                        <p>Category: ${product.category}</p>
                        <p>Price: $${product.price.toFixed(2)}</p>
                        <p>${product.description}</p>
                        <button onclick="editProduct(${product.id})" class="btn btn-secondary">Edit</button>
                        <button onclick="deleteProduct(${product.id})" class="btn btn-secondary" style="background: #e74c3c;">Delete</button>
                    </div>
                `;
                container.appendChild(productElement);
            });
        }

        function addProduct() {
            const name = document.getElementById('productName').value;
            const category = document.getElementById('productCategory').value;
            const price = parseFloat(document.getElementById('productPrice').value);
            const description = document.getElementById('productDescription').value;
            let image = document.getElementById('productImage').value;
            
            // Use uploaded image if available
            const uploadedImage = document.getElementById('imagePreview').src;
            if (uploadedImage && !uploadedImage.includes('data:')) {
                image = uploadedImage;
            }
            
            if (!name || !category || isNaN(price) || !description || !image) {
                alert('Please fill all fields');
                return;
            }
            
            const newProduct = {
                id: products.length > 0 ? Math.max(...products.map(p => p.id)) + 1 : 1,
                name,
                category,
                price,
                description,
                image
            };
            
            products.push(newProduct);
            renderProducts();
            renderAdminProducts();
            
            // Reset form
            document.getElementById('productForm').reset();
            document.getElementById('imagePreview').style.display = 'none';
            alert('Product added successfully!');
        }

        function editProduct(id) {
            const product = products.find(p => p.id === id);
            if (!product) return;
            
            // Fill the form with product data
            document.getElementById('productName').value = product.name;
            document.getElementById('productCategory').value = product.category;
            document.getElementById('productPrice').value = product.price;
            document.getElementById('productDescription').value = product.description;
            document.getElementById('productImage').value = product.image;
            
            // Show image preview if exists
            if (product.image) {
                const preview = document.getElementById('imagePreview');
                preview.src = product.image;
                preview.style.display = 'block';
            }
            
            // Remove the product (will be re-added when form is submitted)
            products = products.filter(p => p.id !== id);
            
            // Scroll to form
            document.getElementById('productForm').scrollIntoView();
        }

        function deleteProduct(id) {
            if (!confirm('Are you sure you want to delete this product?')) return;
            
            products = products.filter(p => p.id !== id);
            renderProducts();
            renderAdminProducts();
        }

        // Image upload handling
        function setupImageUpload() {
            const uploadArea = document.querySelector('.file-upload-area');
            const fileInput = document.getElementById('imageUpload');
            const preview = document.getElementById('imagePreview');
            
            uploadArea.addEventListener('dragover', (e) => {
                e.preventDefault();
                uploadArea.style.borderColor = '#1a365d';
            });
            
            uploadArea.addEventListener('dragleave', () => {
                uploadArea.style.borderColor = '#ddd';
            });
            
            uploadArea.addEventListener('drop', (e) => {
                e.preventDefault();
                uploadArea.style.borderColor = '#ddd';
                
                if (e.dataTransfer.files.length) {
                    fileInput.files = e.dataTransfer.files;
                    handleImageUpload({ target: fileInput });
                }
            });
        }

        function handleImageUpload(event) {
            const file = event.target.files[0];
            if (!file) return;
            
            if (!file.type.match('image.*')) {
                alert('Please select an image file');
                return;
            }
            
            const reader = new FileReader();
            reader.onload = function(e) {
                const preview = document.getElementById('imagePreview');
                preview.src = e.target.result;
                preview.style.display = 'block';
                
                // Also set the image URL field
                document.getElementById('productImage').value = e.target.result;
            };
            reader.readAsDataURL(file);
        }
    </script>
</body>
</html>
