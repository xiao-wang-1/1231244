<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>冬至快乐 | 温暖祝福</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Ma+Shan+Zheng&family=Noto+Serif+SC:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Noto Serif SC', serif;
            background: linear-gradient(135deg, #1a2a3a 0%, #0c151f 100%);
            color: #f5f5f5;
            min-height: 100vh;
            overflow-x: hidden;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            text-align: center;
            margin-bottom: 40px;
            padding: 20px;
            position: relative;
        }
        
        .title {
            font-family: 'Ma Shan Zheng', cursive;
            font-size: 3.5rem;
            color: #FF9900;
            margin-bottom: 10px;
            text-shadow: 0 0 15px rgba(255, 153, 0, 0.5);
            animation: glow 3s infinite alternate;
        }
        
        @keyframes glow {
            from { text-shadow: 0 0 10px rgba(255, 153, 0, 0.5); }
            to { text-shadow: 0 0 25px rgba(255, 153, 0, 0.8), 0 0 35px rgba(255, 153, 0, 0.4); }
        }
        
        .subtitle {
            font-size: 1.2rem;
            color: #b0c4de;
            margin-bottom: 30px;
        }
        
        .main-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 40px;
            margin-bottom: 50px;
        }
        
        .card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            flex: 1;
            min-width: 300px;
            max-width: 500px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-10px);
        }
        
        .card-title {
            color: #FFCC00;
            font-size: 1.8rem;
            margin-bottom: 20px;
            text-align: center;
            border-bottom: 2px dashed rgba(255, 204, 0, 0.3);
            padding-bottom: 10px;
        }
        
        .greeting-text {
            font-size: 1.2rem;
            line-height: 1.8;
            margin-bottom: 20px;
            text-align: justify;
        }
        
        .dumpling-container {
            text-align: center;
            margin: 30px 0;
        }
        
        .dumpling {
            display: inline-block;
            width: 120px;
            height: 80px;
            background: linear-gradient(to bottom, #f8f3e6 0%, #f0e5c9 100%);
            border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
            position: relative;
            margin: 0 15px;
            cursor: pointer;
            transition: transform 0.3s;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .dumpling:hover {
            transform: scale(1.1) rotate(5deg);
        }
        
        .dumpling:before {
            content: '';
            position: absolute;
            top: 15px;
            left: 20px;
            width: 80px;
            height: 40px;
            background: #e6b23a;
            border-radius: 50%;
            opacity: 0.7;
        }
        
        .dumpling-count {
            margin-top: 10px;
            font-size: 1.2rem;
            color: #FFCC00;
        }
        
        .interactive-section {
            text-align: center;
            margin-top: 30px;
        }
        
        .btn {
            background: linear-gradient(to right, #FF9900, #FF6600);
            color: white;
            border: none;
            padding: 12px 30px;
            font-size: 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            margin: 10px;
            transition: all 0.3s ease;
            font-family: 'Noto Serif SC', serif;
            box-shadow: 0 5px 15px rgba(255, 102, 0, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 102, 0, 0.4);
        }
        
        .btn:active {
            transform: translateY(1px);
        }
        
        .btn-share {
            background: linear-gradient(to right, #4CAF50, #2E7D32);
        }
        
        .message-display {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            margin-top: 20px;
            min-height: 80px;
            font-size: 1.3rem;
            color: #FFCC00;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            border-left: 5px solid #FF9900;
        }
        
        .snowflake {
            position: absolute;
            background: white;
            border-radius: 50%;
            opacity: 0.8;
            pointer-events: none;
        }
        
        .lantern {
            position: absolute;
            font-size: 2rem;
            color: #FF3333;
            animation: swing 4s infinite ease-in-out;
        }
        
        @keyframes swing {
            0%, 100% { transform: translateY(0) rotate(-5deg); }
            50% { transform: translateY(-20px) rotate(5deg); }
        }
        
        .footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #b0c4de;
            font-size: 0.9rem;
        }
        
        .festival-info {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            margin-top: 30px;
            gap: 20px;
        }
        
        .info-item {
            text-align: center;
            padding: 15px;
            flex: 1;
            min-width: 200px;
        }
        
        .info-item i {
            font-size: 2rem;
            color: #FF9900;
            margin-bottom: 10px;
        }
        
        .info-title {
            font-size: 1.2rem;
            color: #FFCC00;
            margin-bottom: 10px;
        }
        
        .share-link {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 15px;
            margin-top: 20px;
            word-break: break-all;
            font-family: monospace;
            color: #4CAF50;
            display: none;
        }
        
        .share-link.show {
            display: block;
            animation: fadeIn 0.5s;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @media (max-width: 768px) {
            .title {
                font-size: 2.5rem;
            }
            
            .main-content {
                flex-direction: column;
                align-items: center;
            }
            
            .card {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1 class="title">冬至快乐</h1>
            <p class="subtitle">阴极之至，阳气始生，日南至，日短之至，日影长之至，故曰"冬至"</p>
        </header>
        
        <div class="main-content">
            <div class="card">
                <h2 class="card-title">冬至祝福</h2>
                <div class="greeting-text">
                    <p>亲爱的朋友：</p>
                    <p>冬至到来，白昼最短，思念最长。愿我的祝福，像这冬至的阳光，驱散你所有的寒冷；愿我的问候，像冬至的饺子，包裹你所有的温暖。</p>
                    <p>在这寒冷的季节里，愿你的生活热气腾腾，愿你的心中暖意融融。冬至快乐，阖家安康！</p>
                </div>
                
                <div class="dumpling-container">
                    <div class="dumpling" id="dumpling1"></div>
                    <div class="dumpling" id="dumpling2"></div>
                    <div class="dumpling" id="dumpling3"></div>
                    <p class="dumpling-count">点击饺子，收获温暖！</p>
                </div>
                
                <div class="interactive-section">
                    <button class="btn" id="wishBtn">发送冬至祝福</button>
                    <button class="btn btn-share" id="shareBtn">分享祝福链接</button>
                    
                    <div class="message-display" id="messageDisplay">
                        点击按钮，获取专属冬至祝福
                    </div>
                    
                    <div class="share-link" id="shareLink">
                        <!-- 分享链接将在这里显示 -->
                    </div>
                </div>
            </div>
            
            <div class="card">
                <h2 class="card-title">冬至习俗</h2>
                <div class="festival-info">
                    <div class="info-item">
                        <i class="fas fa-utensils"></i>
                        <div class="info-title">吃饺子</div>
                        <p>北方冬至有吃饺子的习俗，寓意驱寒保暖，防止冻耳。</p>
                    </div>
                    <div class="info-item">
                        <i class="fas fa-moon"></i>
                        <div class="info-title">祭祖</div>
                        <p>冬至是祭祖的重要日子，许多地方会举行祭祀活动。</p>
                    </div>
                    <div class="info-item">
                        <i class="fas fa-calendar-alt"></i>
                        <div class="info-title">数九寒天</div>
                        <p>从冬至开始"数九"，每九天为一个"九"，冬至是"一九"第一天。</p>
                    </div>
                </div>
                
                <div class="greeting-text" style="margin-top: 30px;">
                    <h3>冬至养生小贴士：</h3>
                    <ul style="padding-left: 20px; margin-top: 10px;">
                        <li>注意保暖，尤其是头部、脚部和腰部</li>
                        <li>适当进补，多吃温性食物</li>
                        <li>早睡晚起，保证充足睡眠</li>
                        <li>适度锻炼，增强抵抗力</li>
                    </ul>
                </div>
            </div>
        </div>
        
        <div class="footer">
            <p>© 2023 冬至祝福 | 设计灵感来源于中国传统文化</p>
            <p>今日冬至：2023年12月22日 农历冬月初十</p>
        </div>
    </div>

    <script>
        // 冬至祝福语数组
        const winterSolsticeWishes = [
            "冬至到，吃水饺，吉祥安康双耳好；养生道，要记牢，汤圆羊肉可别少；亲人聚，真热闹，幸福快乐跑不了！",
            "冬至饺子个个香，祝你圣诞冬至温暖幸福都不散！",
            "冬至到，夜最长，愿你的生活美荡漾；冬至来，送关怀，愿你的身体健康在；冬至节，传递爱，祝你整个冬季温暖舒适好运来。",
            "冬至到，数九起。一九二九手藏袖；三九四九冰上走；五九六九河开柳；七九雁来；八九耕牛遍地走；九九加一九，幸福生活天天有！",
            "冬至到，送一碗羊肉汤，愿你能温暖心房；送一盘幸福饺，愿你能快乐逍遥；送一个好运饼，愿你能财源滚滚。",
            "吃了冬至饭，一天长一线。今日冬至，太阳开始回来了，春天也越来越近，愿我的祝福能像这冬至的阳光，为您驱走严寒，送去温暖。",
            "冬至这天，北半球昼最短，夜最长；这天之后，白天渐长，夜晚渐短。愿你的好运随着阳光一同增长，冬至快乐！",
            "冬至节气到，饺子快递到：平安是皮儿，幸福是馅儿，真情煮熟了，吃了乐淘淘，喝了饺子汤，全家都健康。祝冬日吉祥！"
        ];
        
        // 冬至诗词数组
        const winterSolsticePoems = [
            "冬至至后日初长，远在剑南思洛阳。青袍白马有何意，金谷铜驼非故乡。",
            "年年至日长为客，忽忽穷愁泥杀人。江上形容吾独老，天边风俗自相亲。",
            "邯郸驿里逢冬至，抱膝灯前影伴身。想得家中夜深坐，还应说着远行人。",
            "天时人事日相催，冬至阳生春又来。刺绣五纹添弱线，吹葭六琯动浮灰。"
        ];
        
        // 获取DOM元素
        const wishBtn = document.getElementById('wishBtn');
        const shareBtn = document.getElementById('shareBtn');
        const messageDisplay = document.getElementById('messageDisplay');
        const shareLink = document.getElementById('shareLink');
        const dumplings = document.querySelectorAll('.dumpling');
        
        // 点击发送祝福按钮
        wishBtn.addEventListener('click', function() {
            // 随机选择祝福语或诗词
            const isPoem = Math.random() > 0.6;
            const messages = isPoem ? winterSolsticePoems : winterSolsticeWishes;
            const randomIndex = Math.floor(Math.random() * messages.length);
            const randomMessage = messages[randomIndex];
            
            // 显示消息
            messageDisplay.textContent = randomMessage;
            
            // 添加动画效果
            messageDisplay.style.animation = 'none';
            setTimeout(() => {
                messageDisplay.style.animation = 'fadeIn 0.5s';
            }, 10);
            
            // 创建飘落效果
            createSnowflakes(15);
        });
        
        // 点击分享按钮
        shareBtn.addEventListener('click', function() {
            const currentURL = window.location.href;
            shareLink.innerHTML = `冬至快乐祝福链接：<br><strong>${currentURL}</strong><br><br>复制链接分享给朋友，传递冬至温暖！`;
            shareLink.classList.add('show');
            
            // 复制到剪贴板
            navigator.clipboard.writeText(currentURL).then(() => {
                // 显示复制成功提示
                const originalText = shareBtn.textContent;
                shareBtn.innerHTML = '<i class="fas fa-check"></i> 链接已复制';
                shareBtn.style.background = 'linear-gradient(to right, #2E7D32, #1B5E20)';
                
                setTimeout(() => {
                    shareBtn.innerHTML = originalText;
                    shareBtn.style.background = 'linear-gradient(to right, #4CAF50, #2E7D32)';
                }, 2000);
            });
        });
        
        // 点击饺子
        dumplings.forEach((dumpling, index) => {
            dumpling.addEventListener('click', function() {
                // 饺子动画
                this.style.transform = 'scale(1.3) rotate(15deg)';
                this.style.transition = 'transform 0.2s';
                
                // 显示小祝福
                const miniWishes = [
                    "温暖相伴",
                    "阖家欢乐",
                    "幸福安康",
                    "吉祥如意"
                ];
                const randomMiniWish = miniWishes[Math.floor(Math.random() * miniWishes.length)];
                
                // 创建祝福气泡
                const bubble = document.createElement('div');
                bubble.textContent = randomMiniWish;
                bubble.style.position = 'absolute';
                bubble.style.backgroundColor = '#FF9900';
                bubble.style.color = 'white';
                bubble.style.padding = '5px 10px';
                bubble.style.borderRadius = '15px';
                bubble.style.fontSize = '0.9rem';
                bubble.style.zIndex = '1000';
                bubble.style.top = (dumpling.getBoundingClientRect().top - 30) + 'px';
                bubble.style.left = (dumpling.getBoundingClientRect().left + dumpling.offsetWidth/2 - 40) + 'px';
                bubble.style.animation = 'fadeIn 0.3s, floatUp 1.5s forwards';
                
                // 添加浮起动画
                const style = document.createElement('style');
                style.textContent = `
                    @keyframes floatUp {
                        0% { opacity: 1; transform: translateY(0); }
                        100% { opacity: 0; transform: translateY(-50px); }
                    }
                `;
                document.head.appendChild(style);
                
                document.body.appendChild(bubble);
                
                // 移除气泡
                setTimeout(() => {
                    bubble.remove();
                    style.remove();
                }, 1500);
                
                // 恢复饺子原始状态
                setTimeout(() => {
                    this.style.transform = 'scale(1.1) rotate(5deg)';
                }, 300);
            });
        });
        
        // 创建雪花效果
        function createSnowflakes(count) {
            for (let i = 0; i < count; i++) {
                const snowflake = document.createElement('div');
                snowflake.className = 'snowflake';
                
                // 随机大小
                const size = Math.random() * 10 + 5;
                snowflake.style.width = `${size}px`;
                snowflake.style.height = `${size}px`;
                
                // 随机位置
                snowflake.style.left = `${Math.random() * 100}vw`;
                snowflake.style.top = '-20px';
                
                // 随机透明度
                snowflake.style.opacity = Math.random() * 0.6 + 0.3;
                
                // 随机动画时长
                const duration = Math.random() * 5 + 5;
                snowflake.style.animation = `fall ${duration}s linear forwards`;
                
                // 添加动画
                const style = document.createElement('style');
                style.textContent = `
                    @keyframes fall {
                        to {
                            transform: translateY(100vh) rotate(360deg);
                            opacity: 0;
                        }
                    }
                `;
                document.head.appendChild(style);
                
                document.body.appendChild(snowflake);
                
                // 移除雪花
                setTimeout(() => {
                    snowflake.remove();
                    style.remove();
                }, duration * 1000);
            }
        }
        
        // 创建灯笼
        function createLanterns() {
            const lanternContainer = document.createElement('div');
            lanternContainer.style.position = 'fixed';
            lanternContainer.style.top = '0';
            lanternContainer.style.width = '100%';
            lanternContainer.style.pointerEvents = 'none';
            lanternContainer.style.zIndex = '100';
            
            for (let i = 0; i < 6; i++) {
                const lantern = document.createElement('div');
                lantern.className = 'lantern';
                lantern.innerHTML = '<i class="fas fa-star"></i>';
                lantern.style.left = `${(i+1) * 15}%`;
                lantern.style.animationDelay = `${i * 0.5}s`;
                
                lanternContainer.appendChild(lantern);
            }
            
            document.body.appendChild(lanternContainer);
        }
        
        // 页面加载完成后执行
        window.addEventListener('load', function() {
            // 创建初始雪花
            createSnowflakes(20);
            
            // 创建灯笼
            createLanterns();
            
            // 显示初始祝福
            messageDisplay.textContent = winterSolsticeWishes[0];
        });
    </script>
</body>
</html>
