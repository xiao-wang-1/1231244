<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>圣诞快乐！</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(to bottom, #001122, #003344);
            color: #fff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            overflow-x: hidden;
            padding: 20px;
        }
        
        .container {
            text-align: center;
            max-width: 1000px;
            width: 100%;
        }
        
        header {
            margin-bottom: 30px;
        }
        
        h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            color: #4CAF50;
            text-shadow: 0 0 10px rgba(76, 175, 80, 0.5);
        }
        
        .subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
            margin-bottom: 30px;
        }
        
        .tree-container {
            display: flex;
            justify-content: center;
            margin: 30px 0;
            position: relative;
        }
        
        .tree {
            position: relative;
        }
        
        /* 树干 */
        .trunk {
            width: 40px;
            height: 80px;
            background: #8B4513;
            margin: 0 auto;
            border-radius: 5px;
        }
        
        /* 树叶层 */
        .layer {
            width: 0;
            height: 0;
            border-left: 100px solid transparent;
            border-right: 100px solid transparent;
            border-bottom: 100px solid #0a5c0a;
            margin-bottom: -50px;
            position: relative;
        }
        
        .layer:nth-child(2) {
            border-left-width: 120px;
            border-right-width: 120px;
            border-bottom-width: 120px;
            border-bottom-color: #0b6b0b;
            z-index: 3;
        }
        
        .layer:nth-child(3) {
            border-left-width: 140px;
            border-right-width: 140px;
            border-bottom-width: 140px;
            border-bottom-color: #0c7a0c;
            z-index: 2;
        }
        
        .layer:nth-child(4) {
            border-left-width: 160px;
            border-right-width: 160px;
            border-bottom-width: 160px;
            border-bottom-color: #0d890d;
            z-index: 1;
        }
        
        /* 装饰球 */
        .ornament {
            position: absolute;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            z-index: 10;
            cursor: pointer;
            transition: transform 0.3s;
        }
        
        .ornament:hover {
            transform: scale(1.2);
        }
        
        /* 树顶星星 */
        .star {
            position: absolute;
            top: -45px;
            left: 50%;
            transform: translateX(-50%);
            color: gold;
            font-size: 50px;
            text-shadow: 0 0 10px gold;
            z-index: 5;
            animation: twinkle 2s infinite alternate;
        }
        
        /* 礼物盒子 */
        .gifts {
            display: flex;
            justify-content: center;
            margin-top: 20px;
            gap: 30px;
        }
        
        .gift {
            width: 80px;
            height: 80px;
            position: relative;
            cursor: pointer;
            transition: transform 0.3s;
        }
        
        .gift:hover {
            transform: translateY(-10px);
        }
        
        .gift-box {
            width: 100%;
            height: 70%;
            position: absolute;
            bottom: 0;
        }
        
        .gift-lid {
            width: 110%;
            height: 30%;
            position: absolute;
            top: 0;
            left: -5%;
        }
        
        .gift-ribbon {
            width: 20px;
            height: 100%;
            background: rgba(255, 255, 255, 0.7);
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .gift-ribbon-horizontal {
            width: 100%;
            height: 20px;
            background: rgba(255, 255, 255, 0.7);
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
        }
        
        .gift-1 .gift-box { background: #FF5252; }
        .gift-1 .gift-lid { background: #FF8A80; }
        
        .gift-2 .gift-box { background: #4CAF50; }
        .gift-2 .gift-lid { background: #81C784; }
        
        .gift-3 .gift-box { background: #2196F3; }
        .gift-3 .gift-lid { background: #64B5F6; }
        
        /* 雪花 */
        .snowflakes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }
        
        .snowflake {
            position: absolute;
            background: white;
            border-radius: 50%;
            opacity: 0.8;
        }
        
        /* 控制面板 */
        .controls {
            background: rgba(0, 30, 50, 0.7);
            border-radius: 15px;
            padding: 20px;
            margin-top: 30px;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .control-group {
            display: flex;
            flex-direction: column;
            align-items: center;
            min-width: 120px;
        }
        
        .control-label {
            margin-bottom: 8px;
            font-size: 0.9rem;
        }
        
        button {
            background: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            transition: background 0.3s;
        }
        
        button:hover {
            background: #3d8b40;
        }
        
        .toggle-btn {
            background: #2196F3;
        }
        
        .toggle-btn:hover {
            background: #0b7dda;
        }
        
        /* 动画 */
        @keyframes twinkle {
            0% { opacity: 0.7; transform: translateX(-50%) rotate(0deg); }
            100% { opacity: 1; transform: translateX(-50%) rotate(20deg); }
        }
        
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }
        
        /* 响应式设计 */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.2rem;
            }
            
            .layer {
                border-left-width: 70px;
                border-right-width: 70px;
                border-bottom-width: 70px;
                margin-bottom: -35px;
            }
            
            .layer:nth-child(2) {
                border-left-width: 90px;
                border-right-width: 90px;
                border-bottom-width: 90px;
            }
            
            .layer:nth-child(3) {
                border-left-width: 110px;
                border-right-width: 110px;
                border-bottom-width: 110px;
            }
            
            .layer:nth-child(4) {
                border-left-width: 130px;
                border-right-width: 130px;
                border-bottom-width: 130px;
            }
            
            .gifts {
                gap: 15px;
            }
            
            .gift {
                width: 60px;
                height: 60px;
            }
        }
        
        footer {
            margin-top: 30px;
            font-size: 0.9rem;
            opacity: 0.8;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="snowflakes" id="snowflakes"></div>
    
    <div class="container">
        <header>
            <h1><i class="fas fa-tree"></i> 圣诞快乐！</h1>
            <p class="subtitle">点击装饰球和礼物，看看会发生什么！</p>
        </header>
        
        <div class="tree-container">
            <div class="tree">
                <div class="star" id="star">★</div>
                <div class="layer" id="layer4"></div>
                <div class="layer" id="layer3"></div>
                <div class="layer" id="layer2"></div>
                <div class="layer" id="layer1"></div>
                <div class="trunk"></div>
            </div>
        </div>
        
        <div class="gifts">
            <div class="gift gift-1" id="gift1">
                <div class="gift-lid"></div>
                <div class="gift-box"></div>
                <div class="gift-ribbon"></div>
                <div class="gift-ribbon-horizontal"></div>
            </div>
            
            <div class="gift gift-2" id="gift2">
                <div class="gift-lid"></div>
                <div class="gift-box"></div>
                <div class="gift-ribbon"></div>
                <div class="gift-ribbon-horizontal"></div>
            </div>
            
            <div class="gift gift-3" id="gift3">
                <div class="gift-lid"></div>
                <div class="gift-box"></div>
                <div class="gift-ribbon"></div>
                <div class="gift-ribbon-horizontal"></div>
            </div>
        </div>
        
        <div class="controls">
            <div class="control-group">
                <div class="control-label">灯光效果</div>
                <button class="toggle-btn" id="toggleLights">
                    <i class="fas fa-lightbulb"></i> 开关彩灯
                </button>
            </div>
            
            <div class="control-group">
                <div class="control-label">下雪效果</div>
                <button class="toggle-btn" id="toggleSnow">
                    <i class="fas fa-snowflake"></i> 开关雪花
                </button>
            </div>
            
            <div class="control-group">
                <div class="control-label">重置装饰</div>
                <button id="resetOrnaments">
                    <i class="fas fa-redo"></i> 重置
                </button>
            </div>
        </div>
        
        <footer>
            <p>祝您和您的家人圣诞快乐，新年幸福！</p>
            <p>使用HTML、CSS和JavaScript创建</p>
        </footer>
    </div>
    
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const tree = document.querySelector('.tree');
            const star = document.getElementById('star');
            const layers = [
                document.getElementById('layer1'),
                document.getElementById('layer2'),
                document.getElementById('layer3'),
                document.getElementById('layer4')
            ];
            const gifts = [
                document.getElementById('gift1'),
                document.getElementById('gift2'),
                document.getElementById('gift3')
            ];
            const toggleLightsBtn = document.getElementById('toggleLights');
            const toggleSnowBtn = document.getElementById('toggleSnow');
            const resetOrnamentsBtn = document.getElementById('resetOrnaments');
            const snowflakesContainer = document.getElementById('snowflakes');
            
            let ornaments = [];
            let lightsOn = false;
            let snowOn = true;
            let snowflakes = [];
            
            // 创建装饰球
            function createOrnaments() {
                // 清除现有装饰
                ornaments.forEach(ornament => {
                    if (ornament.element && ornament.element.parentNode) {
                        ornament.element.parentNode.removeChild(ornament.element);
                    }
                });
                
                ornaments = [];
                
                // 定义装饰球颜色
                const colors = ['#FF5252', '#FF9800', '#4CAF50', '#2196F3', '#9C27B0', '#FFEB3B'];
                
                // 为每层树添加装饰球
                layers.forEach((layer, layerIndex) => {
                    const layerRect = layer.getBoundingClientRect();
                    const treeRect = tree.getBoundingClientRect();
                    
                    // 每层添加不同数量的装饰球
                    const ornamentsCount = 5 + layerIndex * 2;
                    
                    for (let i = 0; i < ornamentsCount; i++) {
                        const ornament = document.createElement('div');
                        ornament.className = 'ornament';
                        
                        // 随机位置
                        const left = Math.random() * (layerRect.width - 20) + (layerRect.left - treeRect.left);
                        const top = layerRect.top - treeRect.top + Math.random() * (layerRect.height - 20);
                        
                        ornament.style.left = `${left}px`;
                        ornament.style.top = `${top}px`;
                        
                        // 随机颜色
                        const colorIndex = Math.floor(Math.random() * colors.length);
                        ornament.style.backgroundColor = colors[colorIndex];
                        ornament.style.boxShadow = `0 0 5px ${colors[colorIndex]}`;
                        
                        tree.appendChild(ornament);
                        
                        // 存储装饰球信息
                        ornaments.push({
                            element: ornament,
                            color: colors[colorIndex],
                            originalColor: colors[colorIndex],
                            layer: layerIndex,
                            blinking: false
                        });
                        
                        // 添加点击事件
                        ornament.addEventListener('click', function() {
                            toggleOrnamentBlink(this);
                        });
                    }
                });
            }
            
            // 切换装饰球闪烁
            function toggleOrnamentBlink(ornamentElement) {
                const ornament = ornaments.find(o => o.element === ornamentElement);
                if (!ornament) return;
                
                ornament.blinking = !ornament.blinking;
                
                if (ornament.blinking) {
                    ornament.element.style.animation = 'blink 0.8s infinite';
                    ornament.element.style.boxShadow = `0 0 15px ${ornament.color}`;
                } else {
                    ornament.element.style.animation = '';
                    ornament.element.style.boxShadow = `0 0 5px ${ornament.color}`;
                }
            }
            
            // 切换彩灯效果
            function toggleLights() {
                lightsOn = !lightsOn;
                
                if (lightsOn) {
                    // 打开彩灯
                    layers.forEach(layer => {
                        layer.style.boxShadow = '0 0 20px rgba(76, 175, 80, 0.7)';
                    });
                    
                    // 让一些装饰球闪烁
                    ornaments.forEach((ornament, index) => {
                        if (index % 3 === 0) {
                            setTimeout(() => {
                                ornament.element.style.boxShadow = `0 0 15px ${ornament.color}`;
                                ornament.element.style.animation = 'blink 0.8s infinite';
                                ornament.blinking = true;
                            }, index * 100);
                        }
                    });
                    
                    toggleLightsBtn.innerHTML = '<i class="fas fa-lightbulb"></i> 关闭彩灯';
                } else {
                    // 关闭彩灯
                    layers.forEach(layer => {
                        layer.style.boxShadow = '';
                    });
                    
                    // 停止所有装饰球闪烁
                    ornaments.forEach(ornament => {
                        ornament.element.style.boxShadow = `0 0 5px ${ornament.color}`;
                        ornament.element.style.animation = '';
                        ornament.blinking = false;
                    });
                    
                    toggleLightsBtn.innerHTML = '<i class="fas fa-lightbulb"></i> 开关彩灯';
                }
            }
            
            // 创建雪花
            function createSnowflakes() {
                // 清除现有雪花
                snowflakes.forEach(snowflake => {
                    if (snowflake.element && snowflake.element.parentNode) {
                        snowflake.element.parentNode.removeChild(snowflake.element);
                    }
                });
                
                snowflakes = [];
                
                // 创建新雪花
                const snowflakeCount = 80;
                
                for (let i = 0; i < snowflakeCount; i++) {
                    const snowflake = document.createElement('div');
                    snowflake.className = 'snowflake';
                    
                    // 随机大小
                    const size = Math.random() * 8 + 2;
                    snowflake.style.width = `${size}px`;
                    snowflake.style.height = `${size}px`;
                    
                    // 随机位置
                    snowflake.style.left = `${Math.random() * 100}vw`;
                    
                    // 随机透明度
                    snowflake.style.opacity = Math.random() * 0.8 + 0.2;
                    
                    // 随机下落速度
                    const duration = Math.random() * 5 + 5;
                    snowflake.style.animation = `fall ${duration}s linear infinite`;
                    
                    // 添加到页面
                    snowflakesContainer.appendChild(snowflake);
                    
                    // 存储雪花信息
                    snowflakes.push({
                        element: snowflake,
                        size: size,
                        speed: duration,
                        position: parseFloat(snowflake.style.left)
                    });
                }
                
                // 添加雪花下落动画
                const style = document.createElement('style');
                style.innerHTML = `
                    @keyframes fall {
                        0% {
                            top: -10px;
                            transform: translateX(0) rotate(0deg);
                        }
                        100% {
                            top: 100vh;
                            transform: translateX(${Math.random() * 100 - 50}px) rotate(${Math.random() * 360}deg);
                        }
                    }
                `;
                document.head.appendChild(style);
            }
            
            // 切换雪花效果
            function toggleSnow() {
                snowOn = !snowOn;
                
                if (snowOn) {
                    snowflakesContainer.style.display = 'block';
                    createSnowflakes();
                    toggleSnowBtn.innerHTML = '<i class="fas fa-snowflake"></i> 关闭雪花';
                } else {
                    snowflakesContainer.style.display = 'none';
                    toggleSnowBtn.innerHTML = '<i class="fas fa-snowflake"></i> 开关雪花';
                }
            }
            
            // 礼物点击事件
            gifts.forEach((gift, index) => {
                gift.addEventListener('click', function() {
                    // 创建爆炸效果
                    createExplosion(this, index);
                    
                    // 改变礼物颜色
                    const giftBox = this.querySelector('.gift-box');
                    const colors = ['#FF5252', '#FF9800', '#4CAF50', '#2196F3', '#9C27B0', '#FFEB3B'];
                    const newColor = colors[Math.floor(Math.random() * colors.length)];
                    
                    giftBox.style.backgroundColor = newColor;
                    
                    // 显示消息
                    const messages = [
                        "里面是温暖的围巾！",
                        "你得到了一个新玩具！",
                        "这是一本好书！",
                        "美味的巧克力！",
                        "惊喜！是圣诞袜！",
                        "哇！是你一直想要的礼物！"
                    ];
                    
                    showMessage(messages[Math.floor(Math.random() * messages.length)]);
                });
            });
            
            // 创建爆炸效果
            function createExplosion(element, colorIndex) {
                const colors = ['#FF5252', '#FF9800', '#4CAF50'];
                const explosionColor = colors[colorIndex] || '#FF5252';
                
                for (let i = 0; i < 15; i++) {
                    const particle = document.createElement('div');
                    particle.style.position = 'absolute';
                    particle.style.width = '10px';
                    particle.style.height = '10px';
                    particle.style.backgroundColor = explosionColor;
                    particle.style.borderRadius = '50%';
                    particle.style.left = '50%';
                    particle.style.top = '50%';
                    particle.style.zIndex = '100';
                    
                    document.body.appendChild(particle);
                    
                    // 随机方向
                    const angle = Math.random() * Math.PI * 2;
                    const velocity = 2 + Math.random() * 2;
                    const vx = Math.cos(angle) * velocity;
                    const vy = Math.sin(angle) * velocity;
                    
                    let x = 0;
                    let y = 0;
                    let opacity = 1;
                    
                    const animate = () => {
                        x += vx;
                        y += vy;
                        opacity -= 0.03;
                        
                        particle.style.transform = `translate(${x * 20}px, ${y * 20}px)`;
                        particle.style.opacity = opacity;
                        
                        if (opacity > 0) {
                            requestAnimationFrame(animate);
                        } else {
                            document.body.removeChild(particle);
                        }
                    };
                    
                    animate();
                }
            }
            
            // 显示消息
            function showMessage(text) {
                // 移除现有消息
                const existingMessage = document.querySelector('.message');
                if (existingMessage) {
                    existingMessage.remove();
                }
                
                // 创建新消息
                const message = document.createElement('div');
                message.className = 'message';
                message.textContent = text;
                message.style.position = 'fixed';
                message.style.top = '20px';
                message.style.left = '50%';
                message.style.transform = 'translateX(-50%)';
                message.style.background = 'rgba(0, 0, 0, 0.8)';
                message.style.color = 'white';
                message.style.padding = '15px 25px';
                message.style.borderRadius = '10px';
                message.style.zIndex = '1000';
                message.style.fontSize = '1.2rem';
                message.style.boxShadow = '0 0 20px rgba(255, 255, 255, 0.5)';
                
                document.body.appendChild(message);
                
                // 3秒后移除消息
                setTimeout(() => {
                    if (message.parentNode) {
                        message.style.opacity = '0';
                        message.style.transition = 'opacity 0.5s';
                        setTimeout(() => {
                            if (message.parentNode) {
                                message.parentNode.removeChild(message);
                            }
                        }, 500);
                    }
                }, 3000);
            }
            
            // 星星点击事件
            star.addEventListener('click', function() {
                this.style.color = this.style.color === 'gold' ? '#FFD700' : 'gold';
                this.style.textShadow = this.style.textShadow.includes('0 0 20px gold') 
                    ? '0 0 20px #FFD700' 
                    : '0 0 20px gold';
                
                showMessage("许个愿吧！圣诞愿望会实现的！");
            });
            
            // 按钮事件监听
            toggleLightsBtn.addEventListener('click', toggleLights);
            toggleSnowBtn.addEventListener('click', toggleSnow);
            
            resetOrnamentsBtn.addEventListener('click', function() {
                createOrnaments();
                showMessage("装饰已重置！");
            });
            
            // 初始化
            createOrnaments();
            createSnowflakes();
            
            // 显示初始提示
            setTimeout(() => {
                showMessage("点击装饰球可以让它们闪烁！");
            }, 1000);
        });
    </script>
</body>
</html>
