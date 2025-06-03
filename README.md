# index.html
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
            background: linear-gradient(135deg, #1a1a1a 0%, #2d3748 50%, #1a365d 100%);
            min-height: 100vh;
            color: #ffffff;
        }

        .header {
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(15px);
            padding: 1rem 2rem;
            box-shadow: 0 4px 20px rgba(59, 130, 246, 0.3);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 2px solid #3b82f6;
        }

        .nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 2.5rem;
            font-weight: bold;
            color: #3b82f6;
            text-shadow: 0 0 20px rgba(59, 130, 246, 0.5);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo i {
            font-size: 2rem;
            color: #60a5fa;
        }

        .nav-buttons {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .btn {
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            font-size: 0.9rem;
        }

        .btn-primary {
            background: linear-gradient(45deg, #3b82f6, #1d4ed8);
            color: white;
            box-shadow: 0 4px 15px rgba(59, 130, 246, 0.4);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: #ffffff;
            border: 2px solid rgba(255, 255, 255, 0.2);
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 25px rgba(59, 130, 246, 0.6);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.2);
            border-color: #3b82f6;
        }

        .cart-icon {
            position: relative;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #ef4444;
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
            margin: 0 auto;
            padding: 2rem;
        }

        .hero {
            text-align: center;
            color: white;
            margin-bottom: 3rem;
            padding: 2rem 0;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            text-shadow: 0 0 30px rgba(59, 130, 246, 0.5);
            background: linear-gradient(45deg, #3b82f6, #60a5fa, #93c5fd);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.2rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto;
            color: #e2e8f0;
        }

        .categories {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin-bottom: 3rem;
        }

        .category-btn {
            padding: 1rem;
            background: rgba(0, 0, 0, 0.7);
            border: 2px solid rgba(59, 130, 246, 0.3);
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            color: #ffffff;
            backdrop-filter: blur(10px);
        }

        .category-btn:hover, .category-btn.active {
            background: linear-gradient(45deg, #3b82f6, #1d4ed8);
            border-color: #60a5fa;
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(59, 130, 246, 0.4);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .product-card {
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid rgba(59, 130, 246, 0.3);
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.5);
            transition: all 0.3s ease;
            backdrop-filter: blur(15px);
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 35px rgba(59, 130, 246, 0.3);
            border-color: #3b82f6;
        }

        .product-image {
            width: 100%;
            height: 250px;
            object-fit: cover;
            border-bottom: 1px solid rgba(59, 130, 246, 0.3);
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-title {
            font-size: 1.25rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            color: #3b82f6;
        }

        .product-price {
            font-size: 1.5rem;
            font-weight: bold;
            color: #60a5fa;
            margin-bottom: 1rem;
        }

        .product-description {
            color: #e2e8f0;
            margin-bottom: 1rem;
            line-height: 1.4;
        }

        .add-to-cart {
            width: 100%;
            background: linear-gradient(45deg, #3b82f6, #1d4ed8);
            color: white;
            border: none;
            padding: 0.75rem;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .add-to-cart:hover {
            transform: translateY(-1px);
            box-shadow: 0 4px 15px rgba(59, 130, 246, 0.6);
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            z-index: 2000;
            backdrop-filter: blur(5px);
        }

        .modal-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: linear-gradient(135deg, #1a1a1a, #2d3748);
            border: 2px solid #3b82f6;
            border-radius: 16px;
            padding: 2rem;
            max-width: 90%;
            max-height: 90%;
            overflow-y: auto;
            box-shadow: 0 20px 60px rgba(59, 130, 246, 0.3);
            color: #ffffff;
        }

        .close {
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 2rem;
            cursor: pointer;
            color: #e2e8f0;
            transition: color 0.3s;
        }

        .close:hover {
            color: #3b82f6;
        }

        .cart-item {
            display: flex;
            align-items: center;
            padding: 1rem;
            border-bottom: 1px solid rgba(59, 130, 246, 0.3);
            gap: 1rem;
            background: rgba(0, 0, 0, 0.3);
            margin-bottom: 0.5rem;
            border-radius: 8px;
        }

        .cart-item img {
            width: 60px;
            height: 60px;
            object-fit: cover;
            border-radius: 8px;
            border: 1px solid rgba(59, 130, 246, 0.3);
        }

        .cart-item-info {
            flex-grow: 1;
        }

        .cart-item-title {
            font-weight: bold;
            margin-bottom: 0.25rem;
            color: #3b82f6;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin: 0.5rem 0;
        }

        .quantity-btn {
            background: #3b82f6;
            color: white;
            border: none;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .quantity-btn:hover {
            background: #1d4ed8;
            transform: scale(1.1);
        }

        .remove-item {
            background: #ef4444;
            color: white;
            border: none;
            padding: 0.25rem 0.5rem;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.8rem;
            transition: all 0.3s ease;
        }

        .remove-item:hover {
            background: #dc2626;
            transform: scale(1.05);
        }

        .cart-total {
            text-align: center;
            padding: 1rem;
            font-size: 1.5rem;
            font-weight: bold;
            color: #3b82f6;
            border-top: 2px solid rgba(59, 130, 246, 0.3);
            margin-top: 1rem;
        }

        .admin-form {
            background: rgba(0, 0, 0, 0.7);
            border: 1px solid rgba(59, 130, 246, 0.3);
            padding: 2rem;
            border-radius: 16px;
            margin-bottom: 2rem;
            backdrop-filter: blur(15px);
        }

        .form-group {
            margin-bottom: 1rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #3b82f6;
        }

        .form-group input, .form-group textarea, .form-group select {
            width: 100%;
            padding: 0.75rem;
            border: 2px solid rgba(59, 130, 246, 0.3);
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s;
            background: rgba(0, 0, 0, 0.5);
            color: #ffffff;
        }

        .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
            outline: none;
            border-color: #3b82f6;
            box-shadow: 0 0 10px rgba(59, 130, 246, 0.3);
        }

        .hidden {
            display: none !important;
        }

        .checkout-form {
            max-width: 500px;
            margin: 0 auto;
        }

        .admin-access-info {
            background: rgba(59, 130, 246, 0.1);
            border: 1px solid rgba(59, 130, 246, 0.3);
            padding: 1rem;
            border-radius: 8px;
            margin-bottom: 2rem;
            color: #e2e8f0;
        }

        .admin-access-info h3 {
            color: #3b82f6;
            margin-bottom: 0.5rem;
        }

        .file-upload-area {
            border: 2px dashed rgba(59, 130, 246, 0.5);
            border-radius: 8px;
            padding: 2rem;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            background: rgba(59, 130, 246, 0.1);
        }

        .file-upload-area:hover {
            border-color: #3b82f6;
            background: rgba(59, 130, 246, 0.2);
        }

        .file-upload-area.dragover {
            border-color: #60a5fa;
            background: rgba(59, 130, 246, 0.3);
        }

        .image-preview {
            max-width: 200px;
            max-height: 200px;
            border-radius: 8px;
            margin-top: 1rem;
            border: 1px solid rgba(59, 130, 246, 0.3);
        }

        .payment-info {
            background: rgba(59, 130, 246, 0.1);
            border: 1px solid rgba(59, 130, 246, 0.3);
            padding: 1rem;
            border-radius: 8px;
            margin-bottom: 1rem;
        }

        .payment-info h4 {
            color: #3b82f6;
            margin-bottom: 0.5rem;
        }

        @media (max-width: 768px) {
            .nav {
                flex-direction: column;
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .categories {
                grid-template-columns: repeat(2, 1fr);
            }

            .products-grid {
                grid-template-columns: 1fr;
            }

            .logo {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <nav class="nav">
            <div class="logo">
                <i class="fas fa-crown"></i>
                Lure Kings
            </div>
            <div class="nav-buttons">
                <button class="btn btn-secondary" onclick="showView('store')">Store</button>
                <button class="btn btn-secondary" onclick="showAdminLogin()">Admin</button>
                <button class="btn btn-primary cart-icon" onclick="showCart()">
                    <i class="fas fa-shopping-cart"></i>
                    <span class="cart-count" id="cartCount">0</span>
                </button>
            </div>
        </nav>
    </header>

    <div class="container">
        <!-- Store View -->
        <div id="storeView">
            <div class="hero">
                <h1>Premium Fishing Lures</h1>
                <p>Rule the waters with our expertly crafted collection of fishing lures designed to help you land the catch of a lifetime</p>
            </div>

            <div class="categories">
                <button class="category-btn active" onclick="filterByCategory('all')">All Lures</button>
                <button class="category-btn" onclick="filterByCategory('jigs')">Jigs</button>
                <button class="category-btn" onclick="filterByCategory('soft-plastics')">Soft Plastics</button>
                <button class="category-btn" onclick="filterByCategory('topwaters')">Topwaters</button>
                <button class="category-btn" onclick="filterByCategory('spinnerbaits')">Spinnerbaits</button>
                <button class="category-btn" onclick="filterByCategory('vibrating-bladed-jigs')">Vibrating/Bladed Jigs</button>
                <button class="category-btn" onclick="filterByCategory('crankbaits')">Crankbaits</button>
                <button class="category-btn" onclick="filterByCategory('jerkbaits')">Jerkbaits</button>
                <button class="category-btn" onclick="filterByCategory('swimbaits')">Swimbaits</button>
                <button class="category-btn" onclick="filterByCategory('flies')">Flies</button>
            </div>

            <div class="products-grid" id="productsGrid"></div>
        </div>

        <!-- Admin View -->
        <div id="adminView" class="hidden">
            <div class="hero">
                <h1><i class="fas fa-crown"></i> Admin Dashboard</h1>
                <p>Manage your Lure Kings inventory and settings</p>
            </div>

            <div class="admin-access-info">
                <h3><i class="fas fa-info-circle"></i> Admin Access Instructions</h3>
                <p><strong>Easy Access Method:</strong> Add <code>#admin</code> to your website URL (e.g., yourwebsite.com#admin)</p>
                <p><strong>Current Password:</strong> <code>lureking2024</code></p>
                <p><strong>To change password:</strong> Edit the ADMIN_PASSWORD variable in the JavaScript code</p>
            </div>

            <div class="admin-form">
                <h2 style="margin-bottom: 1rem; color: #3b82f6;"><i class="fas fa-plus-circle"></i> Add New Product</h2>
                <form id="productForm">
                    <div class="form-group">
                        <label for="productName"><i class="fas fa-tag"></i> Product Name</label>
                        <input type="text" id="productName" required>
                    </div>
                    <div class="form-group">
                        <label for="productCategory"><i class="fas fa-list"></i> Category</label>
                        <select id="productCategory" required>
                            <option value="">Select Category</option>
                            <option value="jigs">Jigs</option>
                            <option value="soft-plastics">Soft Plastics</option>
                            <option value="topwaters">Topwaters</option>
                            <option value="spinnerbaits">Spinnerbaits</option>
                            <option value="vibrating-bladed-jigs">Vibrating/Bladed Jigs</option>
                            <option value="crankbaits">Crankbaits</option>
                            <option value="jerkbaits">Jerkbaits</option>
                            <option value="swimbaits">Swimbaits</option>
                            <option value="flies">Flies</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="productPrice"><i class="fas fa-dollar-sign"></i> Price ($)</label>
                        <input type="number" id="productPrice" step="0.01" min="0" required>
                    </div>
                    <div class="form-group">
                        <label for="productDescription"><i class="fas fa-align-left"></i> Description</label>
                        <textarea id="productDescription" rows="3" required></textarea>
                    </div>
                    <div class="form-group">
                        <label for="productImage"><i class="fas fa-image"></i> Product Image</label>
                        <div class="file-upload-area" onclick="document.getElementById('imageUpload').click()">
                            <i class="fas fa-cloud-upload-alt" style="font-size: 2rem; color: #3b82f6; margin-bottom: 0.5rem;"></i>
                            <p>Click to upload image or drag & drop</p>
                            <p style="font-size: 0.9rem; opacity: 0.7;">Supports JPG, PNG, GIF</p>
                        </div>
                        <input type="file" id="imageUpload" accept="image/*" style="display: none;">
                        <input type="url" id="productImage" placeholder="Or enter image URL" style="margin-top: 0.5rem;">
                        <img id="imagePreview" class="image-preview" style="display: none;">
                    </div>
                    <button type="submit" class="btn btn-primary" style="width: 100%;">
                        <i class="fas fa-plus"></i> Add Product
                    </button>
                </form>
            </div>

            <div class="admin-form">
                <h2 style="margin-bottom: 1rem; color: #3b82f6;"><i class="fas fa-cog"></i> Manage Existing Products</h2>
                <div id="adminProductsList"></div>
            </div>
        </div>
    </div>

    <!-- Admin Login Modal -->
    <div id="adminLoginModal" class="modal">
        <div class="modal-content" style="max-width: 400px;">
            <span class="close" onclick="closeAdminLogin()">&times;</span>
            <h2 style="margin-bottom: 1rem; color: #3b82f6; text-align: center;">
                <i class="fas fa-crown"></i> Admin Login
            </h2>
            <form id="adminLoginForm" class="checkout-form">
                <div class="form-group">
                    <label for="adminPassword"><i class="fas fa-lock"></i> Password</label>
                    <input type="password" id="adminPassword" required placeholder="Enter admin password">
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">
                    <i class="fas fa-sign-in-alt"></i> Login
                </button>
            </form>
            <div style="text-align: center; margin-top: 1rem; padding: 1rem; background: rgba(59, 130, 246, 0.1); border-radius: 8px;">
                <p style="font-size: 0.9rem; color: #e2e8f0; margin-bottom: 0.5rem;">
                    <i class="fas fa-info-circle"></i> Quick Access Tip
                </p>
                <p style="font-size: 0.85rem; color: #94a3b8;">
                    Add <code>#admin</code> to your URL for direct access
                </p>
            </div>
        </div>
    </div>

    <!-- Cart Modal -->
    <div id="cartModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeCart()">&times;</span>
            <h2 style="margin-bottom: 1rem; color: #3b82f6;">
                <i class="fas fa-shopping-cart"></i> Shopping Cart
            </h2>
            <div id="cartItems"></div>
            <div class="cart-total" id="cartTotal">Total: $0.00</div>
            <button class="btn btn-primary" onclick="showCheckout()" style="width: 100%; margin-top: 1rem;">
                <i class="fas fa-credit-card"></i> Proceed to Checkout
            </button>
        </div>
    </div>

    <!-- Checkout Modal -->
    <div id="checkoutModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeCheckout()">&times;</span>
            <h2 style="margin-bottom: 1rem; color: #3b82f6;">
                <i class="fas fa-credit-card"></i> Secure Checkout
            </h2>
            
            <div class="payment-info">
                <h4><i class="fas fa-university"></i> Payment Information</h4>
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
                        <label for="customerName"><i class="fas fa-user"></i> Full Name</label>
                        <input type="text" id="customerName" required>
                    </div>
                    <div class="form-group">
                        <label for="customerEmail"><i class="fas fa-envelope"></i> Email Address</label>
                        <input type="email" id="customerEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="customerPhone"><i class="fas fa-phone"></i> Phone Number</label>
                        <input type="tel" id="customerPhone" required>
                    </div>
                    <div class="form-group">
                        <label for="customerAddress"><i class="fas fa-map-marker-alt"></i> Delivery Address</label>
                        <textarea id="customerAddress" rows="3" required></textarea>
                    </div>
                    <div class="form-group">
                        <label for="orderNotes"><i class="fas fa-sticky-note"></i> Order Notes (Optional)</label>
                        <textarea id="orderNotes" rows="2" placeholder="Any special instructions..."></textarea>
                    </div>
                    <div class="cart-total" id="checkoutTotal">Total: $0.00</div>
                    <button type="submit" class="btn btn-primary" style="width: 100%; margin-top: 1rem;">
                        <i class="fas fa-check-circle"></i> Place Order
                    </button>
                </form>
            </div>
        </div>
    </div>

    <script>
        // Global variables
        let isAdminLoggedIn = false;
        const ADMIN_PASSWORD = "lureking2024";
        
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
            },
            {
                id: 5,
                name: "Chatterbait Bladed Jig",
                category: "vibrating-bladed-jigs",
                price: 13.99,
                description: "Vibrating bladed jig that creates unique sound and action underwater.",
                image: "https://images.unsplash.com/photo-1544551763-46a013bb70d5?w=400&h=300&fit=crop"
            },
            {
                id: 6,
                name: "Deep Diving Crankbait",
                category: "crankbaits",
                price: 16.49,
                description: "Reaches deep water where big fish hide, with realistic swimming action.",
                image: "https://images.unsplash.com/photo-1578662996442-48f60103fc96?w=400&h=300&fit=crop"
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
            checkAdminAccess();
            setupImageUpload();
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
            document.getElementById('adminLoginForm').addEventListener('submit', function(e) {
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
            showCartNotification(product.name);
        }

        function updateCartCount() {
            const count = cart.reduce((total, item) => total + item.quantity, 0);
            document.getElementById('cartCount').textContent = count;
        }

        function showCartNotification(productName) {
            // Could implement a toast notification here
            console.log(`${productName} added to cart`);
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
            
            // In a real app, you would send this data to your server
            const order = {
                orderNumber,
                customer: { name, email },
                items: cart,
                total: cart.reduce((sum, item) => sum + (item.price * item.quantity), 0),
                date: new Date().toISOString()
            };
            
            console.log('Order placed:', order);
            alert(`Order #${orderNumber} placed successfully!\nA confirmation has been sent to ${email}`);
            
            // Reset cart and close modals
            cart = [];
            updateCartCount();
            closeCheckout();
            document.getElementById('checkoutForm').reset();
        }

        // Admin functionality
        function showAdminLogin() {
            document.getElementById('adminLoginModal').style.display = 'block';
        }

        function closeAdminLogin() {
            document.getElementById('adminLoginModal').style.display = 'none';
        }

        function checkAdminAccess() {
            if (window.location.hash === '#admin') {
                showAdminLogin();
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
                        <button onclick="deleteProduct(${product.id})" class="btn btn-secondary" style="background: #ef4444;">Delete</button>
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
                uploadArea.classList.add('dragover');
            });
            
            uploadArea.addEventListener('dragleave', () => {
                uploadArea.classList.remove('dragover');
            });
            
            uploadArea.addEventListener('drop', (e) => {
                e.preventDefault();
                uploadArea.classList.remove('dragover');
                
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
