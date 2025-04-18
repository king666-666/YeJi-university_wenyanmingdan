<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>東方文理大學 (ELAU)</title>
    <style>
        /* 始頁樣式 - 玄青為底配素文 */
        #start-page {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #1a5276, #0e3a5e);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            transition: opacity 1s ease-out;
        }
        
        #start-page.hidden {
            opacity: 0;
            pointer-events: none;
        }
        
        #start-page h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            color: #ffffff;
            text-shadow: 0 2px 8px rgba(0,0,0,0.6);
            font-weight: 700;
            letter-spacing: 2px;
            animation: fadeIn 1.5s ease-in-out;
        }
        
        #start-page .subtitle {
            font-size: 1.5rem;
            margin-bottom: 40px;
            max-width: 800px;
            text-align: center;
            line-height: 1.6;
            color: #f1c40f;
            text-shadow: 0 1px 3px rgba(0,0,0,0.5);
            animation: slideUp 1s ease-in-out;
        }
        
        #enter-btn {
            padding: 15px 40px;
            background-color: #f1c40f;
            color: #1a5276;
            border: none;
            border-radius: 50px;
            font-size: 1.3rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            animation: pulse 2s infinite;
        }
        
        #enter-btn:hover {
            background-color: #f39c12;
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.4);
        }

        /* 正文樣式 - 素底玄文 */
        body {
            font-family: 'Microsoft YaHei', sans-serif;
            line-height: 1.6;
            color: #333333;
            background-color: #f5f7fa;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            background-color: #ffffff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .logo {
            max-width: 200px;
            margin: 20px auto;
        }
        
        .logo img {
            max-width: 100%;
            height: auto;
            display: block;
            margin: 0 auto;
        }
        
        h1, h2, h3, h4 {
            color: #1a5276;
        }
        
        h2 {
            border-bottom: 2px solid #1a5276;
            padding-bottom: 8px;
            margin-top: 40px;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            background-color: #ffffff;
        }
        
        th, td {
            border: 1px solid #e0e0e0;
            padding: 12px;
            text-align: left;
        }
        
        th {
            background-color: #1a5276;
            color: #ffffff;
        }
        
        .nav {
            background-color: #ffffff;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 30px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        
        .nav a {
            margin-right: 20px;
            text-decoration: none;
            color: #1a5276;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav a:hover {
            color: #f39c12;
            text-decoration: none;
        }
        
        .back-to-top {
            display: inline-block;
            background-color: #1a5276;
            color: white;
            padding: 8px 15px;
            border-radius: 4px;
            text-decoration: none;
            font-size: 0.9em;
            margin-top: 20px;
            transition: background-color 0.3s;
        }
        
        .back-to-top:hover {
            background-color: #f39c12;
        }
        
        footer {
            text-align: center;
            margin-top: 50px;
            padding: 30px 0;
            border-top: 1px solid #e0e0e0;
            font-size: 0.9em;
            color: #666666;
            background-color: #ffffff;
            border-radius: 8px;
        }
        
        .highlight {
            background-color: #ffffff;
            padding: 25px;
            border-radius: 8px;
            margin: 25px 0;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            border-left: 4px solid #f1c40f;
        }
        
        /* 動畫效果 */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes slideUp {
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
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        /* 響應式設計 */
        @media (max-width: 768px) {
            #start-page h1 {
                font-size: 2.5rem;
            }
            
            #start-page .subtitle {
                font-size: 1.2rem;
            }
            
            .nav a {
                display: block;
                margin: 10px 0;
            }
            
            table {
                font-size: 0.9em;
            }
        }
    </style>
</head>
<body>
    <!-- 始頁 -->
    <div id="start-page">
        <h1>東方文理大學</h1>
        <p class="subtitle">校董會及校領導名單</p>
        <button id="enter-btn">進入名單</button>
    </div>

    <!-- 正文 -->
    <div id="main-content" style="display:none;">
        <header>
            <div class="logo">
                <img src="images/logo.png" alt="東方文理大學徽記" 
                     onerror="this.onerror=null;this.src='images/logo.jpg';">
            </div>
            <h1>東方文理大學 (ELAU)</h1>
            <p><em>明德至善 博學創新</em></p>
        </header>

        <div class="nav">
            <h2>速覽</h2>
            <a href="#leadership">校董會及校領導名單</a>
        </div>

        <section id="leadership">
            <h2>校董會及校領導</h2>
            
            <div class="highlight">
                <h3>校董會</h3>
                <table>
                    <tr>
                        <th>職位</th>
                        <th>姓名</th>
                        <th>簡介</th>
                    </tr>
                    <tr>
                        <td>校董會主席</td>
                        <td>轩辕明德</td>
                        <td>前礼部尚书，现任寰宇教育基金会理事长</td>
                    </tr>
                    <tr>
                        <td>常務校董</td>
                        <td>南宫文渊</td>
                        <td>火星開發總設計師</td>
                    </tr>
                    <tr>
                        <td>校董</td>
                        <td>诸葛思齐</td>
                        <td>量子计算专家</td>
                    </tr>
                </table>
            </div>
            
            <div class="highlight">
                <h3>校領導班子</h3>
                <table>
                    <tr>
                        <th>職務</th>
                        <th>姓名</th>
                        <th>簡介</th>
                    </tr>
                    <tr>
                        <td>校长</td>
                        <td>皇甫守正</td>
                        <td>理论物理学家</td>
                    </tr>
                    <tr>
                        <td>常務副校长</td>
                        <td>长孙弘文</td>
                        <td>古典文献学专家</td>
                    </tr>
                </table>
            </div>
        </section>

        <footer>
            <p>© 民國一百一十四年 東方文理大學</p>
        </footer>
    </div>

    <script>
        document.getElementById('enter-btn').addEventListener('click', function() {
            document.getElementById('start-page').classList.add('hidden');
            document.getElementById('main-content').style.display = 'block';
            window.scrollTo(0, 0);
        });
    </script>
</body>
</html># YeJi-university_wenyanmingdan
