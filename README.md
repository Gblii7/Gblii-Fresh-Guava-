<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🦖 Godzilla Juice Fruitful</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #f0f9f0 0%, #fff5e6 100%);
            color: #2d4a2d;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            margin-bottom: 30px;
            border: 3px solid #a8d8a8;
        }

        .logo {
            font-size: 2.5rem;
            font-weight: bold;
            color: #2d4a2d;
            margin-bottom: 10px;
        }

        .tagline {
            color: #ff8c42;
            font-size: 1.1rem;
            margin-bottom: 20px;
        }

        .tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
            gap: 10px;
        }

        .tab-button {
            background: #a8d8a8;
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .tab-button.active {
            background: #ff8c42;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255,140,66,0.3);
        }

        .tab-content {
            display: none;
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            border: 2px solid #a8d8a8;
        }

        .tab-content.active {
            display: block;
        }

        .customer-form {
            display: grid;
            gap: 25px;
        }

        .form-section {
            background: #f8fff8;
            padding: 25px;
            border-radius: 15px;
            border: 2px solid #e8f5e8;
        }

        .section-title {
            font-size: 1.4rem;
            color: #2d4a2d;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #2d4a2d;
        }

        .form-group input, 
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e8f5e8;
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #a8d8a8;
            box-shadow: 0 0 0 3px rgba(168,216,168,0.2);
        }

        .juice-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            background: white;
            border-radius: 15px;
            border: 2px solid #e8f5e8;
            margin-bottom: 15px;
            transition: all 0.3s ease;
        }

        .juice-item:hover {
            border-color: #a8d8a8;
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(168,216,168,0.2);
        }

        .juice-info {
            flex: 1;
        }

        .juice-name {
            font-size: 1.2rem;
            font-weight: 600;
            color: #2d4a2d;
        }

        .juice-price {
            font-size: 1.1rem;
            color: #ff8c42;
            font-weight: bold;
        }

        .quantity-control {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .qty-btn {
            background: #a8d8a8;
            color: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .qty-btn:hover {
            background: #ff8c42;
            transform: scale(1.1);
        }

        .qty-display {
            font-size: 1.2rem;
            font-weight: bold;
            color: #2d4a2d;
            min-width: 30px;
            text-align: center;
        }

        .payment-options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .payment-option {
            background: white;
            padding: 20px;
            border-radius: 15px;
            border: 2px solid #e8f5e8;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .payment-option:hover,
        .payment-option.selected {
            border-color: #a8d8a8;
            background: #f8fff8;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(168,216,168,0.2);
        }

        .delivery-notes {
            background: #fff5e6;
            padding: 25px;
            border-radius: 15px;
            border: 2px solid #ffd4a8;
        }

        .delivery-notes ul {
            list-style: none;
            padding-left: 0;
        }

        .delivery-notes li {
            margin-bottom: 10px;
            padding-left: 5px;
        }

        .order-summary {
            background: #f8fff8;
            padding: 25px;
            border-radius: 15px;
            border: 2px solid #a8d8a8;
            margin-top: 20px;
        }

        .summary-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }

        .total {
            font-size: 1.3rem;
            font-weight: bold;
            color: #ff8c42;
            border-top: 2px solid #e8f5e8;
            padding-top: 15px;
            margin-top: 15px;
        }

        .submit-btn {
            background: linear-gradient(45deg, #a8d8a8, #ff8c42);
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 1.2rem;
            font-weight: bold;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
            margin-top: 20px;
        }

        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255,140,66,0.3);
        }

        .submit-btn:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
        }

        .admin-dashboard {
            display: grid;
            gap: 20px;
        }

        .order-card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            border: 2px solid #e8f5e8;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .order-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .order-id {
            font-size: 1.2rem;
            font-weight: bold;
            color: #2d4a2d;
        }

        .order-status {
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: bold;
        }

        .status-pending {
            background: #fff5e6;
            color: #ff8c42;
            border: 2px solid #ffd4a8;
        }

        .status-delivered {
            background: #f8fff8;
            color: #2d4a2d;
            border: 2px solid #a8d8a8;
        }

        .customer-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin-bottom: 20px;
        }

        .info-item {
            background: #f8fff8;
            padding: 15px;
            border-radius: 10px;
            border: 1px solid #e8f5e8;
        }

        .info-label {
            font-weight: bold;
            color: #2d4a2d;
            margin-bottom: 5px;
        }

        .order-items {
            margin-bottom: 20px;
        }

        .order-actions {
            display: flex;
            gap: 10px;
        }

        .action-btn {
            padding: 10px 20px;
            border: none;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .btn-deliver {
            background: #a8d8a8;
            color: white;
        }

        .btn-deliver:hover {
            background: #2d4a2d;
            transform: translateY(-2px);
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
            animation: fadeIn 0.3s ease;
        }

        .modal-content {
            background-color: white;
            margin: 10% auto;
            padding: 40px;
            border-radius: 20px;
            width: 90%;
            max-width: 500px;
            text-align: center;
            border: 3px solid #a8d8a8;
            animation: slideIn 0.3s ease;
        }

        .modal-emoji {
            font-size: 4rem;
            margin-bottom: 20px;
        }

        .modal-title {
            font-size: 1.8rem;
            color: #2d4a2d;
            margin-bottom: 15px;
        }

        .modal-message {
            font-size: 1.1rem;
            color: #666;
            line-height: 1.6;
            margin-bottom: 30px;
        }

        .close-btn {
            background: #ff8c42;
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .close-btn:hover {
            background: #e67934;
            transform: translateY(-2px);
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideIn {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }
            
            .payment-options {
                grid-template-columns: 1fr;
            }
            
            .customer-info {
                grid-template-columns: 1fr;
            }
            
            .tabs {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="logo">🦖 Godzilla Juice Fruitful</div>
            <div class="tagline">Fresh • Natural • Delivered Daily</div>
        </div>

        <div class="tabs">
            <button class="tab-button active" onclick="showTab('customer')">Place Order</button>
            <button class="tab-button" onclick="showTab('admin')">Admin Dashboard</button>
        </div>

        <!-- Customer Tab -->
        <div id="customerTab" class="tab-content active">
            <form class="customer-form" id="orderForm">
                <div class="form-section">
                    <div class="section-title">👤 Customer Information</div>
                    <div class="form-group">
                        <label for="customerName">Name *</label>
                        <input type="text" id="customerName" name="customerName" required>
                    </div>
                    <div class="form-group">
                        <label for="customerAddress">Full Address *</label>
                        <textarea id="customerAddress" name="customerAddress" rows="3" required></textarea>
                    </div>
                    <div class="form-group">
                        <label for="customerPhone">Contact Number *</label>
                        <input type="tel" id="customerPhone" name="customerPhone" required>
                    </div>
                </div>

                <div class="form-section">
                    <div class="section-title">🥤 Godzilla Juice Selection</div>
                    
                    <div class="juice-item">
                        <div class="juice-info">
                            <div class="juice-name">Rose Guava Juice</div>
                            <div class="juice-price">RM7 /set</div>
                        </div>
                        <div class="quantity-control">
                            <button type="button" class="qty-btn" onclick="changeQuantity('roseGuava', -1)">−</button>
                            <span class="qty-display" id="roseGuavaQty">0</span>
                            <button type="button" class="qty-btn" onclick="changeQuantity('roseGuava', 1)">+</button>
                        </div>
                    </div>

                    <div class="juice-item">
                        <div class="juice-info">
                            <div class="juice-name">Dragon Mango Juice</div>
                            <div class="juice-price">RM7 /set</div>
                        </div>
                        <div class="quantity-control">
                            <button type="button" class="qty-btn" onclick="changeQuantity('dragonMango', -1)">−</button>
                            <span class="qty-display" id="dragonMangoQty">0</span>
                            <button type="button" class="qty-btn" onclick="changeQuantity('dragonMango', 1)">+</button>
                        </div>
                    </div>

                    <div class="juice-item">
                        <div class="juice-info">
                            <div class="juice-name">Blast Pineapple</div>
                            <div class="juice-price">RM7 /set</div>
                        </div>
                        <div class="quantity-control">
                            <button type="button" class="qty-btn" onclick="changeQuantity('blastPineapple', -1)">−</button>
                            <span class="qty-display" id="blastPineappleQty">0</span>
                            <button type="button" class="qty-btn" onclick="changeQuantity('blastPineapple', 1)">+</button>
                        </div>
                    </div>

                    <div class="juice-item">
                        <div class="juice-info">
                            <div class="juice-name">Storm Berry</div>
                            <div class="juice-price">RM7 /set</div>
                        </div>
                        <div class="quantity-control">
                            <button type="button" class="qty-btn" onclick="changeQuantity('stormBerry', -1)">−</button>
                            <span class="qty-display" id="stormBerryQty">0</span>
                            <button type="button" class="qty-btn" onclick="changeQuantity('stormBerry', 1)">+</button>
                        </div>
                    </div>

                    <div class="juice-item">
                        <div class="juice-info">
                            <div class="juice-name">Smart Citrus</div>
                            <div class="juice-price">RM7 /set</div>
                        </div>
                        <div class="quantity-control">
                            <button type="button" class="qty-btn" onclick="changeQuantity('smartCitrus', -1)">−</button>
                            <span class="qty-display" id="smartCitrusQty">0</span>
                            <button type="button" class="qty-btn" onclick="changeQuantity('smartCitrus', 1)">+</button>
                        </div>
                    </div>

                    <div class="juice-item">
                        <div class="juice-info">
                            <div class="juice-name">Tropical Whip</div>
                            <div class="juice-price">RM7 /set</div>
                        </div>
                        <div class="quantity-control">
                            <button type="button" class="qty-btn" onclick="changeQuantity('tropicalWhip', -1)">−</button>
                            <span class="qty-display" id="tropicalWhipQty">0</span>
                            <button type="button" class="qty-btn" onclick="changeQuantity('tropicalWhip', 1)">+</button>
                        </div>
                    </div>

                    <div class="juice-item">
                        <div class="juice-info">
                            <div class="juice-name">Melt Melon</div>
                            <div class="juice-price">RM7 /set</div>
                        </div>
                        <div class="quantity-control">
                            <button type="button" class="qty-btn" onclick="changeQuantity('meltMelon', -1)">−</button>
                            <span class="qty-display" id="meltMelonQty">0</span>
                            <button type="button" class="qty-btn" onclick="changeQuantity('meltMelon', 1)">+</button>
                        </div>
                    </div>
                </div>

                <div class="form-section">
                    <div class="section-title">💳 Payment Method</div>
                    <div class="payment-options">
                        <div class="payment-option" onclick="selectPayment('cod')">
                            <div style="font-size: 2rem; margin-bottom: 10px;">💵</div>
                            <div><strong>COD</strong></div>
                            <div>(Cash On Delivery)</div>
                        </div>
                        <div class="payment-option" onclick="selectPayment('qr')">
                            <div style="font-size: 2rem; margin-bottom: 10px;">📱</div>
                            <div><strong>QR</strong></div>
                            <div>(QR On Delivery)</div>
                        </div>
                    </div>
                </div>

                <div class="delivery-notes">
                    <div class="section-title">📝 Delivery Notes</div>
                    <ul>
                        <li>✅ Membership RM29 / Year cancelled anytime. (RM 0.07 / day)</li>
                        <li>✅ 1 year Fruit Slice for FREE. Memberships ONLY start claim on 11.77am - 1.77pm EVERYDAY. 360 DAY A YEAR.</li>
                        <li>✅ Make order before 11am.</li>
                        <li>✅ Delivery starts at 1pm - 5pm. (Same day delivery).</li>
                        <li>✅ Stand by Call time via WhatsApp 📱</li>
                    </ul>
                </div>

                <div class="order-summary">
                    <div class="section-title">📋 Order Summary</div>
                    <div id="orderSummaryItems"></div>
                    <div class="total">
                        <div class="summary-item">
                            <span>Total:</span>
                            <span id="orderTotal">RM0</span>
                        </div>
                    </div>
                </div>

                <button type="submit" class="submit-btn" id="submitBtn" disabled>
                    🦖 Place Order - Godzilla Juice Delivery!
                </butt
