<!DOCTYPE html>
<html lang="th" class="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ShopOnline - ร้านค้าออนไลน์</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        :root {
            --primary: #3b82f6;
            --primary-dark: #1d4ed8;
            --secondary: #10b981;
            --dark: #1f2937;
            --light: #f9fafb;
        }
        
        .theme-dark {
            --bg-primary: #111827;
            --bg-secondary: #1f2937;
            --text-primary: #f9fafb;
            --text-secondary: #d1d5db;
        }
        
        .theme-light {
            --bg-primary: #ffffff;
            --bg-secondary: #f9fafb;
            --text-primary: #111827;
            --text-secondary: #6b7280;
        }
        
        .cart-badge {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: #ef4444;
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            font-size: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .product-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1);
        }
        
        .discount-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background-color: #ef4444;
            color: white;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 12px;
            font-weight: bold;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800 transition-colors duration-300">
    <!-- Navigation Bar -->
    <nav class="bg-white shadow-lg sticky top-0 z-50">
        <div class="container mx-auto px-4">
            <div class="flex justify-between items-center h-16">
                <!-- Logo -->
                <div class="flex items-center space-x-3">
                    <div class="w-10 h-10 bg-blue-500 rounded-lg flex items-center justify-center">
                        <span class="text-white font-bold text-xl">S</span>
                    </div>
                    <span class="text-xl font-bold text-gray-800">ShopOnline</span>
                </div>

                <!-- Desktop Menu -->
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#home" class="text-gray-700 hover:text-blue-500 transition">
                        <i class="fas fa-home mr-2"></i>หน้าแรก
                    </a>
                    <a href="#products" class="text-gray-700 hover:text-blue-500 transition">
                        <i class="fas fa-box mr-2"></i>สินค้าทั้งหมด
                    </a>
                    <div class="relative group">
                        <button class="text-gray-700 hover:text-blue-500 transition">
                            <i class="fas fa-list mr-2"></i>หมวดหมู่
                        </button>
                        <div class="absolute hidden group-hover:block bg-white shadow-lg rounded-lg mt-2 w-48">
                            <a href="#" class="block px-4 py-2 hover:bg-gray-100">อิเล็กทรอนิกส์</a>
                            <a href="#" class="block px-4 py-2 hover:bg-gray-100">เสื้อผ้า</a>
                            <a href="#" class="block px-4 py-2 hover:bg-gray-100">เครื่องสำอาง</a>
                            <a href="#" class="block px-4 py-2 hover:bg-gray-100">ของใช้ในบ้าน</a>
                        </div>
                    </div>
                    <a href="#topup" class="text-gray-700 hover:text-blue-500 transition">
                        <i class="fas fa-wallet mr-2"></i>เติมเงิน
                    </a>
                </div>

                <!-- Right Side Icons -->
                <div class="flex items-center space-x-6">
                    <!-- Theme Toggle -->
                    <button id="themeToggle" class="text-gray-700">
                        <i class="fas fa-moon"></i>
                    </button>
                    
                    <!-- Cart -->
                    <div class="relative">
                        <a href="#cart" class="text-gray-700 hover:text-blue-500">
                            <i class="fas fa-shopping-cart text-xl"></i>
                            <span class="cart-badge">3</span>
                        </a>
                    </div>
                    
                    <!-- User -->
                    <div class="relative group">
                        <button class="flex items-center space-x-2 text-gray-700">
                            <div class="w-8 h-8 bg-blue-100 rounded-full flex items-center justify-center">
                                <i class="fas fa-user text-blue-500"></i>
                            </div>
                            <span>สมาชิก</span>
                        </button>
                        <div class="absolute right-0 hidden group-hover:block bg-white shadow-lg rounded-lg mt-2 w-48">
                            <a href="#login" class="block px-4 py-2 hover:bg-gray-100">
                                <i class="fas fa-sign-in-alt mr-2"></i>เข้าสู่ระบบ
                            </a>
                            <a href="#register" class="block px-4 py-2 hover:bg-gray-100">
                                <i class="fas fa-user-plus mr-2"></i>สมัครสมาชิก
                            </a>
                            <a href="#profile" class="block px-4 py-2 hover:bg-gray-100">
                                <i class="fas fa-user-circle mr-2"></i>โปรไฟล์
                            </a>
                            <a href="#discord" class="block px-4 py-2 hover:bg-gray-100">
                                <i class="fab fa-discord mr-2"></i>Login with Discord
                            </a>
                        </div>
                    </div>
                    
                    <!-- Mobile Menu Button -->
                    <button id="mobileMenuButton" class="md:hidden text-gray-700">
                        <i class="fas fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Mobile Menu -->
    <div id="mobileMenu" class="md:hidden hidden bg-white shadow-lg">
        <div class="container mx-auto px-4 py-4">
            <a href="#home" class="block py-2 text-gray-700">
                <i class="fas fa-home mr-2"></i>หน้าแรก
            </a>
            <a href="#products" class="block py-2 text-gray-700">
                <i class="fas fa-box mr-2"></i>สินค้าทั้งหมด
            </a>
            <a href="#categories" class="block py-2 text-gray-700">
                <i class="fas fa-list mr-2"></i>หมวดหมู่
            </a>
            <a href="#topup" class="block py-2 text-gray-700">
                <i class="fas fa-wallet mr-2"></i>เติมเงิน
            </a>
        </div>
    </div>

    <!-- Hero Carousel -->
    <section id="home" class="py-8">
        <div class="container mx-auto px-4">
            <div class="bg-gradient-to-r from-blue-500 to-purple-600 rounded-2xl p-8 text-white">
                <div class="max-w-2xl">
                    <h1 class="text-4xl md:text-5xl font-bold mb-4">ยินดีต้อนรับสู่ ShopOnline</h1>
                    <p class="text-xl mb-6">ร้านค้าออนไลน์ที่ครบวงจรที่สุด พร้อมระบบเติมเงินอัตโนมัติและสินค้าหลากหลายประเภท</p>
                    <div class="flex flex-wrap gap-4">
                        <a href="#products" class="bg-white text-blue-600 px-6 py-3 rounded-lg font-bold hover:bg-gray-100 transition">
                            ช็อปปิ้งตอนนี้
                        </a>
                        <a href="#register" class="bg-transparent border-2 border-white px-6 py-3 rounded-lg font-bold hover:bg-white/10 transition">
                            สมัครสมาชิกฟรี
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Categories -->
    <section class="py-12">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl font-bold mb-8 text-center">หมวดหมู่แนะนำ</h2>
            <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
                <!-- Category 1 -->
                <div class="bg-white rounded-xl shadow-md overflow-hidden product-card">
                    <div class="h-40 bg-gradient-to-r from-blue-400 to-blue-300"></div>
                    <div class="p-4">
                        <h3 class="font-bold text-lg mb-2">อิเล็กทรอนิกส์</h3>
                        <p class="text-gray-600 text-sm">สินค้าไอทีและอุปกรณ์อิเล็กทรอนิกส์</p>
                        <a href="#" class="text-blue-500 font-medium mt-3 inline-block">ดูสินค้า <i class="fas fa-arrow-right ml-1"></i></a>
                    </div>
                </div>
                
                <!-- Category 2 -->
                <div class="bg-white rounded-xl shadow-md overflow-hidden product-card">
                    <div class="h-40 bg-gradient-to-r from-green-400 to-green-300"></div>
                    <div class="p-4">
                        <h3 class="font-bold text-lg mb-2">เสื้อผ้าแฟชั่น</h3>
                        <p class="text-gray-600 text-sm">เสื้อผ้าทันสมัยสำหรับทุกโอกาส</p>
                        <a href="#" class="text-blue-500 font-medium mt-3 inline-block">ดูสินค้า <i class="fas fa-arrow-right ml-1"></i></a>
                    </div>
                </div>
                
                <!-- Category 3 -->
                <div class="bg-white rounded-xl shadow-md overflow-hidden product-card">
                    <div class="h-40 bg-gradient-to-r from-pink-400 to-pink-300"></div>
                    <div class="p-4">
                        <h3 class="font-bold text-lg mb-2">เครื่องสำอาง</h3>
                        <p class="text-gray-600 text-sm">ความสวยงามและบำรุงผิวพรรณ</p>
                        <a href="#" class="text-blue-500 font-medium mt-3 inline-block">ดูสินค้า <i class="fas fa-arrow-right ml-1"></i></a>
                    </div>
                </div>
                
                <!-- Category 4 -->
                <div class="bg-white rounded-xl shadow-md overflow-hidden product-card">
                    <div class="h-40 bg-gradient-to-r from-yellow-400 to-yellow-300"></div>
                    <div class="p-4">
                        <h3 class="font-bold text-lg mb-2">ของใช้ในบ้าน</h3>
                        <p class="text-gray-600 text-sm">อุปกรณ์และเฟอร์นิเจอร์สำหรับบ้าน</p>
                        <a href="#" class="text-blue-500 font-medium mt-3 inline-block">ดูสินค้า <i class="fas fa-arrow-right ml-1"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Products -->
    <section id="products" class="py-12 bg-gray-50">
        <div class="container mx-auto px-4">
            <div class="flex justify-between items-center mb-8">
                <h2 class="text-3xl font-bold">สินค้าแนะนำ</h2>
                <a href="#" class="text-blue-500 font-medium">ดูทั้งหมด <i class="fas fa-arrow-right ml-1"></i></a>
            </div>
            
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                <!-- Product 1 -->
                <div class="bg-white rounded-xl shadow-md overflow-hidden product-card">
                    <div class="relative">
                        <div class="h-48 bg-gradient-to-r from-blue-100 to-blue-50"></div>
                        <div class="discount-badge">-20%</div>
                        <button class="absolute top-3 right-3 w-10 h-10 bg-white/80 rounded-full flex items-center justify-center">
                            <i class="fas fa-heart text-red-500"></i>
                        </button>
                    </div>
                    <div class="p-4">
                        <h3 class="font-bold text-lg mb-2">สมาร์ทโฟนรุ่นใหม่</h3>
                        <p class="text-gray-600 text-sm mb-3">สมาร์ทโฟนประสิทธิภาพสูง กล้องระดับโปร</p>
                        <div class="flex items-center justify-between">
                            <div>
                                <span class="text-2xl font-bold text-gray-800">฿9,999</span>
                                <span class="text-sm text-gray-500 line-through ml-2">฿12,500</span>
                            </div>
                            <button class="bg-blue-500 text-white w-10 h-10 rounded-full flex items-center justify-center hover:bg-blue-600 transition">
                                <i class="fas fa-cart-plus"></i>
                            </button>
                        </div>
                        <div class="mt-3 flex items-center text-sm text-gray-500">
                            <i class="fas fa-box mr-1"></i>
                            <span>มีสต็อก 15 ชิ้น</span>
                        </div>
                    </div>
                </div>
                
                <!-- Product 2 -->
                <div class="bg-white rounded-xl shadow-md overflow-hidden product-card">
                    <div class="relative">
                        <div class="h-48 bg-gradient-to-r from-green-100 to-green-50"></div>
                        <button class="absolute top-3 right-3 w-10 h-10 bg-white/80 rounded-full flex items-center justify-center">
                            <i class="far fa-heart text-gray-500"></i>
                        </button>
                    </div>
                    <div class="p-4">
                        <h3 class="font-bold text-lg mb-2">เสื้อฮูดีแฟชั่น</h3>
                        <p class="text-gray-600 text-sm mb-3">เสื้อฮูดีผ้าคอตตอน ใส่สบาย</p>
                        <div class="flex items-center justify-between">
                            <div>
                                <span class="text-2xl font-bold text-gray-800">฿599</span>
                            </div>
                            <button class="bg-blue-500 text-white w-10 h-10 rounded-full flex items-center justify-center hover:bg-blue-600 transition">
                                <i class="fas fa-cart-plus"></i>
                            </button>
                        </div>
                        <div class="mt-3 flex items-center text-sm text-gray-500">
                            <i class="fas fa-box mr-1"></i>
                            <span>มีสต็อก 42 ชิ้น</span>
                        </div>
                    </div>
                </div>
                
                <!-- Product 3 -->
                <div class="bg-white rounded-xl shadow-md overflow-hidden product-card">
                    <div class="relative">
                        <div class="h-48 bg-gradient-to-r from-pink-100 to-pink-50"></div>
                        <div class="discount-badge">-15%</div>
                        <button class="absolute top-3 right-3 w-10 h-10 bg-white/80 rounded-full flex items-center justify-center">
                            <i class="far fa-heart text-gray-500"></i>
                        </button>
                    </div>
                    <div class="p-4">
                        <h3 class="font-bold text-lg mb-2">เครื่องสำอางเซ็ต</h3>
                        <p class="text-gray-600 text-sm mb-3">เซ็ตเครื่องสำอางครบชุดสำหรับทุกวัน</p>
                        <div class="flex items-center justify-between">
                            <div>
                                <span class="text-2xl font-bold text-gray-800">฿1,299</span>
                                <span class="text-sm text-gray-500 line-through ml-2">฿1,550</span>
                            </div>
                            <button class="bg-blue-500 text-white w-10 h-10 rounded-full flex items-center justify-center hover:bg-blue-600 transition">
                                <i class="fas fa-cart-plus"></i>
                            </button>
                        </div>
                        <div class="mt-3 flex items-center text-sm text-gray-500">
                            <i class="fas fa-clock mr-1"></i>
                            <span>สั่งทำ (3-5 วัน)</span>
                        </div>
                    </div>
                </div>
                
                <!-- Product 4 -->
                <div class="bg-white rounded-xl shadow-md overflow-hidden product-card">
                    <div class="relative">
                        <div class="h-48 bg-gradient-to-r from-yellow-100 to-yellow-50"></div>
                        <button class="absolute top-3 right-3 w-10 h-10 bg-white/80 rounded-full flex items-center justify-center">
                            <i class="fas fa-heart text-red-500"></i>
                        </button>
                    </div>
                    <div class="p-4">
                        <h3 class="font-bold text-lg mb-2">โคมไฟตั้งโต๊ะ</h3>
                        <p class="text-gray-600 text-sm mb-3">โคมไฟดีไซน์โมเดิร์น ปรับความสว่างได้</p>
                        <div class="flex items-center justify-between">
                            <div>
                                <span class="text-2xl font-bold text-gray-800">฿1,850</span>
                            </div>
                            <button class="bg-blue-500 text-white w-10 h-10 rounded-full flex items-center justify-center hover:bg-blue-600 transition">
                                <i class="fas fa-cart-plus"></i>
                            </button>
                        </div>
                        <div class="mt-3 flex items-center text-sm text-gray-500">
                            <i class="fas fa-box mr-1"></i>
                            <span>มีสต็อก 8 ชิ้น</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Top-up System -->
    <section id="topup" class="py-12">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl font-bold mb-8 text-center">ระบบเติมเงิน</h2>
            <div class="grid md:grid-cols-3 gap-8">
                <!-- TrueWallet -->
                <div class="bg-white rounded-xl shadow-lg p-6 text-center">
                    <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
                        <i class="fas fa-wallet text-green-600 text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">TrueWallet</h3>
                    <p class="text-gray-600 mb-4">เติมเงินผ่านซองอั่งเปา TrueWallet ระบบอัตโนมัติทันที</p>
                    <button class="bg-green-500 text-white px-6 py-2 rounded-lg font-medium hover:bg-green-600 transition">
                        เติมเงิน
                    </button>
                </div>
                
                <!-- PromptPay -->
                <div class="bg-white rounded-xl shadow-lg p-6 text-center">
                    <div class="w-16 h-16 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-4">
                        <i class="fas fa-qrcode text-blue-600 text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">PromptPay QR</h3>
                    <p class="text-gray-600 mb-4">สแกน QR Code เพื่อชำระเงิน ตรวจสอบอัตโนมัติ</p>
                    <button class="bg-blue-500 text-white px-6 py-2 rounded-lg font-medium hover:bg-blue-600 transition">
                        สร้าง QR
                    </button>
                </div>
                
                <!-- Manual Top-up -->
                <d
