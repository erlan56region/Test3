
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Аквалос - Автономная канализация</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            color: #333;
            line-height: 1.6;
            background-color: #f9f9f9;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header styles */
        header {
            background-color: #fff;
            box-shadow: 0 2px 15px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            font-size: 28px;
            font-weight: bold;
            color: #0a6c8c;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            font-size: 32px;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 25px;
            position: relative;
        }
        
        nav ul li a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
            padding: 5px 0;
        }
        
        nav ul li a:hover {
            color: #0a6c8c;
        }
        
        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: #0a6c8c;
            transition: width 0.3s ease;
        }
        
        nav ul li a:hover::after {
            width: 100%;
        }
        
        .phone {
            font-weight: bold;
            color: #0a6c8c;
            font-size: 18px;
            display: flex;
            align-items: center;
        }
        
        .phone i {
            margin-right: 8px;
        }
        
        /* Section styles */
        section {
            padding: 100px 0 80px;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 1s forwards 0.3s;
        }
        
        .section-title h2 {
            font-size: 36px;
            color: #0a6c8c;
            margin-bottom: 15px;
        }
        
        .section-title p {
            color: #666;
            max-width: 700px;
            margin: 0 auto;
            font-size: 18px;
        }
        
        /* Sewage systems section */
        .sewage-systems {
            background-color: #fff;
        }
        
        .filter-container {
            background-color: #f0f7fa;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 40px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 1s forwards 0.5s;
        }
        
        .filter-title {
            font-size: 20px;
            color: #0a6c8c;
            margin-bottom: 20px;
            text-align: center;
        }
        
        .filters {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }
        
        .filter-group {
            display: flex;
            flex-direction: column;
            min-width: 200px;
        }
        
        .filter-group label {
            margin-bottom: 8px;
            font-weight: 500;
            color: #555;
        }
        
        .filter-group select {
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background-color: white;
            font-size: 16px;
            transition: all 0.3s;
        }
        
        .filter-group select:focus {
            outline: none;
            border-color: #0a6c8c;
            box-shadow: 0 0 0 2px rgba(10, 108, 140, 0.2);
        }
        
        .systems-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }
        
        .system-card {
            background-color: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
            position: relative;
            border: 1px solid #eaeaea;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 1s forwards;
        }
        
        .system-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .system-name {
            font-size: 22px;
            font-weight: bold;
            color: #0a6c8c;
            margin-bottom: 15px;
            text-align: center;
        }
        
        .system-price {
            font-size: 28px;
            font-weight: bold;
            color: #ff7e00;
            margin-bottom: 25px;
            text-align: center;
        }
        
        .specs-list {
            list-style: none;
            margin-bottom: 30px;
        }
        
        .specs-list li {
            padding: 12px 0;
            border-bottom: 1px solid #f0f0f0;
            display: flex;
            justify-content: space-between;
            transition: background-color 0.3s;
        }
        
        .specs-list li:hover {
            background-color: #f9f9f9;
        }
        
        .spec-name {
            color: #666;
        }
        
        .spec-value {
            font-weight: bold;
            color: #333;
        }
        
        .order-btn {
            display: block;
            width: 100%;
            background-color: #ff7e00;
            color: white;
            padding: 15px;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
            text-decoration: none;
            position: relative;
            overflow: hidden;
        }
        
        .order-btn:hover {
            background-color: #e67100;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 126, 0, 0.4);
        }
        
        .order-btn:active {
            transform: translateY(0);
        }
        
        .popular-badge {
            position: absolute;
            top: -10px;
            right: 20px;
            background-color: #ff7e00;
            color: white;
            padding: 8px 20px;
            border-radius: 20px;
            font-size: 14px;
            font-weight: bold;
            box-shadow: 0 3px 10px rgba(255, 126, 0, 0.3);
            animation: pulse 2s infinite;
        }
        
        .comparison-btn {
            display: block;
            margin: 40px auto 0;
            background-color: #0a6c8c;
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 1s forwards 1s;
        }
        
        .comparison-btn:hover {
            background-color: #085a75;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(10, 108, 140, 0.4);
        }
        
        /* Footer */
        footer {
            background-color: #333;
            color: white;
            padding: 50px 0 20px;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            margin-bottom: 20px;
            color: #ff7e00;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
            display: flex;
            align-items: center;
        }
        
        .footer-column ul li i {
            margin-right: 10px;
            color: #ff7e00;
        }
        
        .footer-column ul li a {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column ul li a:hover {
            color: #ff7e00;
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid #444;
            color: #aaa;
            font-size: 14px;
        }
        
        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
            100% {
                transform: scale(1);
            }
        }
        
        .system-card:nth-child(1) {
            animation-delay: 0.3s;
        }
        
        .system-card:nth-child(2) {
            animation-delay: 0.5s;
        }
        
        .system-card:nth-child(3) {
            animation-delay: 0.7s;
        }
        
        .system-card:nth-child(4) {
            animation-delay: 0.9s;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            nav ul li {
                margin: 5px 10px;
            }
            
            section {
                padding: 80px 0 60px;
            }
            
            .section-title h2 {
                font-size: 30px;
            }
            
            .filters {
                flex-direction: column;
                align-items: center;
            }
            
            .filter-group {
                width: 100%;
                max-width: 300px;
            }
        }
        
        /* Comparison Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0,0,0,0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }
        
        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal {
            background-color: white;
            border-radius: 10px;
            width: 90%;
            max-width: 1000px;
            max-height: 90vh;
            overflow-y: auto;
            padding: 30px;
            position: relative;
            transform: translateY(50px);
            opacity: 0;
            transition: all 0.5s;
        }
        
        .modal-overlay.active .modal {
            transform: translateY(0);
            opacity: 1;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: #666;
            transition: color 0.3s;
        }
        
        .close-modal:hover {
            color: #ff7e00;
        }
        
        .comparison-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        
        .comparison-table th, .comparison-table td {
            padding: 15px;
            text-align: center;
            border-bottom: 1px solid #eee;
        }
        
        .comparison-table th {
            background-color: #f0f7fa;
            color: #0a6c8c;
            font-weight: bold;
        }
        
        .comparison-table tr:hover {
            background-color: #f9f9f9;
        }
        
        .highlight {
            background-color: #fff9e6 !important;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo"><i class="fas fa-tint"></i>АКВАЛОС</div>
            <nav>
                <ul>
                    <li><a href="#">Главная</a></li>
                    <li><a href="#">Автономная канализация</a></li>
                    <li><a href="#">Системы полива</a></li>
                    <li><a href="#">О компании</a></li>
                    <li><a href="#">Контакты</a></li>
                </ul>
            </nav>
            <div class="phone"><i class="fas fa-phone"></i>+7 (495) 123-45-67</div>
        </div>
    </header>

    <!-- Sewage Systems Section -->
    <section class="sewage-systems">
        <div class="container">
            <div class="section-title">
                <h2>Автономная канализация АКВАЛОС</h2>
                <p>Надежные и эффективные системы очистки сточных вод для загородных домов</p>
            </div>
            
            <div class="filter-container">
                <h3 class="filter-title">Подберите систему по вашим параметрам</h3>
                <div class="filters">
                    <div class="filter-group">
                        <label for="users">Количество пользователей</label>
                        <select id="users">
                            <option value="all">Все варианты</option>
                            <option value="3">До 3 человек</option>
                            <option value="5">До 5 человек</option>
                            <option value="10">До 10 человек</option>
                            <option value="15">До 15 человек</option>
                            <option value="20">До 20 человек</option>
                            <option value="30">До 30 человек</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <label for="water-outlet">Способ отведения воды</label>
                        <select id="water-outlet">
                            <option value="all">Все варианты</option>
                            <option value="self">Самотечный</option>
                            <option value="forced">Принудительный</option>
                            <option value="both">Самотечный/Принудительный</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <label for="performance">Производительность</label>
                        <select id="performance">
                            <option value="all">Все варианты</option>
                            <option value="0.6">До 0.6 м³/сутки</option>
                            <option value="1.0">До 1.0 м³/сутки</option>
                            <option value="2.0">До 2.0 м³/сутки</option>
                            <option value="3.0">До 3.0 м³/сутки</option>
                            <option value="4.0">До 4.0 м³/сутки</option>
                            <option value="6.0">До 6.0 м³/сутки</option>
                        </select>
                    </div>
                </div>
            </div>
            
            <div class="systems-grid" id="systems-container">
                <!-- System 1 -->
                <div class="system-card" data-users="3" data-water-outlet="self" data-performance="0.6">
                    <div class="system-name">АКВАЛОС 2 Un</div>
                    <div class="system-price">101 000 руб.</div>
                    <ul class="specs-list">
                        <li>
                            <span class="spec-name">Количество пользователей:</span>
                            <span class="spec-value">до 3 человек</span>
                        </li>
                        <li>
                            <span class="spec-name">Производительность:</span>
                            <span class="spec-value">0.6 м³/сутки</span>
                        </li>
                        <li>
                            <span class="spec-name">Залповый сброс:</span>
                            <span class="spec-value">180 л</span>
                        </li>
                        <li>
                            <span class="spec-name">Глубина подводящей трубы:</span>
                            <span class="spec-value">40-80 см</span>
                        </li>
                        <li>
                            <span class="spec-name">Габаритные размеры Д×Ш×В:</span>
                            <span class="spec-value">1.2×1.0×1.7 м</span>
                        </li>
                        <li>
                            <span class="spec-name">Способ отведения воды:</span>
                            <span class="spec-value">Самотечный</span>
                        </li>
                    </ul>
                    <a href="#" class="order-btn">ЗАКАЗАТЬ</a>
                </div>
                
                <!-- System 2 -->
                <div class="system-card" data-users="5" data-water-outlet="both" data-performance="1.0">
                    <div class="popular-badge">ПОПУЛЯРНАЯ</div>
                    <div class="system-name">АКВАЛОС 5 Un</div>
                    <div class="system-price">158 000 руб.</div>
                    <ul class="specs-list">
                        <li>
                            <span class="spec-name">Количество пользователей:</span>
                            <span class="spec-value">до 5 человек</span>
                        </li>
                        <li>
                            <span class="spec-name">Производительность:</span>
                            <span class="spec-value">1.0 м³/сутки</span>
                        </li>
                        <li>
                            <span class="spec-name">Залповый сброс:</span>
                            <span class="spec-value">250 л</span>
                        </li>
                        <li>
                            <span class="spec-name">Глубина подводящей трубы:</span>
                            <span class="spec-value">40-80 см</span>
                        </li>
                        <li>
                            <span class="spec-name">Габаритные размеры Д×Ш×В:</span>
                            <span class="spec-value">1.7×1.2×2.0 м</span>
                        </li>
                        <li>
                            <span class="spec-name">Способ отведения воды:</span>
                            <span class="spec-value">Самотечный/Принудительный</span>
                        </li>
                    </ul>
                    <a href="#" class="order-btn">ЗАКАЗАТЬ</a>
                </div>
                
                <!-- System 3 -->
                <div class="system-card" data-users="10" data-water-outlet="both" data-performance="2.0">
                    <div class="system-name">АКВАЛОС 10 Pro</div>
                    <div class="system-price">245 000 руб.</div>
                    <ul class="specs-list">
                        <li>
                            <span class="spec-name">Количество пользователей:</span>
                            <span class="spec-value">до 10 человек</span>
                        </li>
                        <li>
                            <span class="spec-name">Производительность:</span>
                            <span class="spec-value">2.0 м³/сутки</span>
                        </li>
                        <li>
                            <span class="spec-name">Залповый сброс:</span>
                            <span class="spec-value">550 л</span>
                        </li>
                        <li>
                            <span class="spec-name">Глубина подводящей трубы:</span>
                            <span class="spec-value">40-100 см</span>
                        </li>
                        <li>
                            <span class="spec-name">Габаритные размеры Д×Ш×В:</span>
                            <span class="spec-value">2.4×1.5×2.3 м</span>
                        </li>
                        <li>
                            <span class="spec-name">Способ отведения воды:</span>
                            <span class="spec-value">Самотечный/Принудительный</span>
                        </li>
                    </ul>
                    <a href="#" class="order-btn">ЗАКАЗАТЬ</a>
                </div>
            </div>
            
            <button class="comparison-btn" id="compare-btn">
                <i class="fas fa-chart-bar"></i> Сравнить модели
            </button>
        </div>
    </section>

    <!-- Additional Systems Section -->
    <section class="sewage-systems" style="background-color: #f5f9fa;">
        <div class="container">
            <div class="section-title">
                <h2>Системы для более 10 человек</h2>
                <p>Мощные решения для коттеджных поселков, гостиниц и ресторанов</p>
            </div>
            <div class="systems-grid">
                <!-- System 4 -->
                <div class="system-card" data-users="15" data-water-outlet="both" data-performance="3.0">
                    <div class="system-name">АКВАЛОС 15 Pro</div>
                    <div class="system-price">367 000 руб.</div>
                    <ul class="specs-list">
                        <li>
                            <span class="spec-name">Количество пользователей:</span>
                            <span class="spec-value">до 15 человек</span>
                        </li>
                        <li>
                            <span class="spec-name">Производительность:</span>
                            <span class="spec-value">3.0 м³/сутки</span>
                        </li>
                        <li>
                            <span class="spec-name">Залповый сброс:</span>
                            <span class="spec-value">800 л</span>
                        </li>
                        <li>
                            <span class="spec-name">Глубина подводящей трубы:</span>
                            <span class="spec-value">50-120 см</span>
                        </li>
                        <li>
                            <span class="spec-name">Габаритные размеры Д×Ш×В:</span>
                            <span class="spec-value">3.0×1.5×2.3 м</span>
                        </li>
                        <li>
                            <span class="spec-name">Способ отведения воды:</span>
                            <span class="spec-value">Самотечный/Принудительный</span>
                        </li>
                    </ul>
                    <a href="#" class="order-btn">ЗАКАЗАТЬ</a>
                </div>
                
                <!-- System 5 -->
                <div class="system-card" data-users="20" data-water-outlet="both" data-performance="4.0">
                    <div class="system-name">АКВАЛОС 20 Pro</div>
                    <div class="system-price">489 000 руб.</div>
                    <ul class="specs-list">
                        <li>
                            <span class="spec-name">Количество пользователей:</span>
                            <span class="spec-value">до 20 человек</span>
                        </li>
                        <li>
                            <span class="spec-name">Производительность:</span>
                            <span class="spec-value">4.0 м³/сутки</span>
                        </li>
                        <li>
                            <span class="spec-name">Залповый сброс:</span>
                            <span class="spec-value">1100 л</span>
                        </li>
                        <li>
                            <span class="spec-name">Глубина подводящей трубы:</span>
                            <span class="spec-value">50-120 см</span>
                        </li>
                        <li>
                            <span class="spec-name">Габаритные размеры Д×Ш×В:</span>
                            <span class="spec-value">3.6×1.8×2.3 м</span>
                        </li>
                        <li>
                            <span class="spec-name">Способ отведения воды:</span>
                            <span class="spec-value">Самотечный/Принудительный</span>
                        </li>
                    </ul>
                    <a href="#" class="order-btn">ЗАКАЗАТЬ</a>
                </div>
                
                <!-- System 6 -->
                <div class="system-card" data-users="30" data-water-outlet="forced" data-performance="6.0">
                    <div class="system-name">АКВАЛОС 30 Pro</div>
                    <div class="system-price">625 000 руб.</div>
                    <ul class="specs-list">
                        <li>
                            <span class="spec-name">Количество пользователей:</span>
                            <span class="spec-value">до 30 человек</span>
                        </li>
                        <li>
                            <span class="spec-name">Производительность:</span>
                            <span class="spec-value">6.0 м³/сутки</span>
                        </li>
                        <li>
                            <span class="spec-name">Залповый сброс:</span>
                            <span class="spec-value">1650 л</span>
                        </li>
                        <li>
                            <span class="spec-name">Глубина подводящей трубы:</span>
                            <span class="spec-value">50-150 см</span>
                        </li>
                        <li>
                            <span class="spec-name">Габаритные размеры Д×Ш×В:</span>
                            <span class="spec-value">4.2×2.0×2.5 м</span>
                        </li>
                        <li>
                            <span class="spec-name">Способ отведения воды:</span>
                            <span class="spec-value">Принудительный</span>
                        </li>
                    </ul>
                    <a href="#" class="order-btn">ЗАКАЗАТЬ</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Comparison Modal -->
    <div class="modal-overlay" id="comparison-modal">
        <div class="modal">
            <button class="close-modal" id="close-modal">&times;</button>
            <h2 style="color: #0a6c8c; text-align: center; margin-bottom: 20px;">Сравнение моделей АКВАЛОС</h2>
            <table class="comparison-table">
                <thead>
                    <tr>
                        <th>Характеристика</th>
                        <th>АКВАЛОС 2 Un</th>
                        <th>АКВАЛОС 5 Un</th>
                        <th>АКВАЛОС 10 Pro</th>
                        <th>АКВАЛОС 15 Pro</th>
                        <th>АКВАЛОС 20 Pro</th>
                        <th>АКВАЛОС 30 Pro</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Цена</td>
                        <td>101 000 руб.</td>
                        <td>158 000 руб.</td>
                        <td>245 000 руб.</td>
                        <td>367 000 руб.</td>
                        <td>489 000 руб.</td>
                        <td>625 000 руб.</td>
                    </tr>
                    <tr>
                        <td>Количество пользователей</td>
                        <td>до 3</td>
                        <td>до 5</td>
                        <td>до 10</td>
                        <td>до 15</td>
                        <td>до 20</td>
                        <td>до 30</td>
                    </tr>
                    <tr>
                        <td>Производительность</td>
                        <td>0.6 м³/сутки</td>
                        <td>1.0 м³/сутки</td>
                        <td>2.0 м³/сутки</td>
                        <td>3.0 м³/сутки</td>
                        <td>4.0 м³/сутки</td>
                        <td>6.0 м³/сутки</td>
                    </tr>
                    <tr>
                        <td>Залповый сброс</td>
                        <td>180 л</td>
                        <td>250 л</td>
                        <td>550 л</td>
                        <td>800 л</td>
                        <td>1100 л</td>
                        <td>1650 л</td>
                    </tr>
                    <tr>
                        <td>Способ отведения воды</td>
                        <td>Самотечный</td>
                        <td>Самотечный/Принудительный</td>
                        <td>Самотечный/Принудительный</td>
                        <td>Самотечный/Принудительный</td>
                        <td>Самотечный/Принудительный</td>
                        <td>Принудительный</td>
                    </tr>
                    <tr class="highlight">
                        <td>Рекомендуемое применение</td>
                        <td>Дача, небольшой дом</td>
                        <td>Загородный дом</td>
                        <td>Коттедж, гостевой дом</td>
                        <td>Большой коттедж, мини-отель</td>
                        <td>Коттеджный поселок, кафе</td>
                        <td>Гостиница, ресторан</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-column">
                    <h3>АКВАЛОС</h3>
                    <p>Проектирование и установка систем автономной канализации и полива с 2010 года</p>
                </div>
                <div class="footer-column">
                    <h3>Услуги</h3>
                    <ul>
                        <li><i class="fas fa-cog"></i><a href="#">Автономная канализация</a></li>
                        <li><i class="fas fa-tint"></i><a href="#">Системы полива</a></li>
                        <li><i class="fas fa-tools"></i><a href="#">Обслуживание</a></li>
                        <li><i class="fas fa-wrench"></i><a href="#">Ремонт</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Контакты</h3>
                    <ul>
                        <li><i class="fas fa-map-marker-alt"></i>г. Москва, ул. Примерная, д. 123</li>
                        <li><i class="fas fa-phone"></i>+7 (495) 123-45-67</li>
                        <li><i class="fas fa-envelope"></i>info@akvalos.ru</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                &copy; 2023 АКВАЛОС. Все права защищены.
            </div>
        </div>
    </footer>

    <script>
        // Фильтрация систем
        const userFilter = document.getElementById('users');
        const waterOutletFilter = document.getElementById('water-outlet');
        const performanceFilter = document.getElementById('performance');
        const systemCards = document.querySelectorAll('.system-card');
        
        function filterSystems() {
            const userValue = userFilter.value;
            const waterOutletValue = waterOutletFilter.value;
            const performanceValue = performanceFilter.value;
            
            systemCards.forEach(card => {
                const cardUsers = card.getAttribute('data-users');
                const cardWaterOutlet = card.getAttribute('data-water-outlet');
                const cardPerformance = card.getAttribute('data-performance');
                
                const userMatch = userValue === 'all' || cardUsers === userValue;
                const waterOutletMatch = waterOutletValue === 'all' || cardWaterOutlet === waterOutletValue;
                const performanceMatch = performanceValue === 'all' || cardPerformance === performanceValue;
                
                if (userMatch && waterOutletMatch && performanceMatch) {
                    card.style.display = 'block';
                    // Добавляем анимацию появления
                    card.style.animation = 'fadeInUp 0.5s forwards';
                } else {
                    card.style.display = 'none';
                }
            });
        }
        
        userFilter.addEventListener('change', filterSystems);
        waterOutletFilter.addEventListener('change', filterSystems);
        performanceFilter.addEventListener('change', filterSystems);
        
        // Модальное окно сравнения
        const compareBtn = document.getElementById('compare-btn');
        const comparisonModal = document.getElementById('comparison-modal');
        const closeModal = document.getElementById('close-modal');
        
        compareBtn.addEventListener('click', () => {
            comparisonModal.classList.add('active');
        });
        
        closeModal.addEventListener('click', () => {
            comparisonModal.classList.remove('active');
        });
        
        // Закрытие модального окна при клике вне его
        comparisonModal.addEventListener('click', (e) => {
            if (e.target === comparisonModal) {
                comparisonModal.classList.remove('active');
            }
        });
        
        // Анимация при прокрутке
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeInUp 1s forwards';
                }
            });
        }, observerOptions);
        
        // Наблюдаем за всеми карточками систем
        document.querySelectorAll('.system-card').forEach(card => {
            observer.observe(card);
        });
    </script>
</body>
</html>
