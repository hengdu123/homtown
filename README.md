<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <style>
                * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Microsoft YaHei', sans-serif;
            min-height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.6)), 
                        url('./背景.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            max-width: 800px;
            background: rgba(0, 30, 60, 0.7);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(5px);
        }
        
        h1 {
            text-align: center;
            margin-bottom: 20px;
            font-size: 2.5rem;
            text-shadow: 0 2px 4px rgba(0,0,0,0.5);
            color: #FFD700;
        }
        
        .intro {
            line-height: 1.8;
            font-size: 1.1rem;
            margin-bottom: 20px;
        }
        
        .highlights {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 30px;
        }
        
        .card {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            padding: 20px;
            flex: 1 1 calc(33.333% - 20px);
            min-width: 250px;
            display: flex;
            flex-direction: column;
        }
        
        .card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 8px;
            border: 2px solid #FFD700;
            margin-bottom: 15px;
        }
        
        .card h3 {
            color: #FFD700;
            margin-bottom: 10px;
            border-bottom: 2px solid #FFD700;
            padding-bottom: 5px;
        }
        
        .card-content {
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .card {
                flex: 1 1 100%;
            }
        }
    </style>
    <!-- 原有样式保持不变 -->
</head>
<body>
    <div class="container">
        <div class="container">
        <h1>我的家乡——桂林山水</h1>
        
        <div class="intro">
            <p>我的家乡位于中国广西壮族自治区，素有“山水甲天下”的美誉。这里山清水秀、风景如画，四季分明，春夏秋冬各有千秋。春天，桃花盛开，山间小溪潺潺；夏天，绿树成荫，清凉宜人；秋天，层林尽染，五彩斑斓；冬天，白雪皑皑，宛如人间仙境。</p>
        </div>
        <div class="highlights">
            <div class="card">
                <!-- 添加data-hover-src属性 -->
                <img src="./美食1.jpg" 
                     data-hover-src="./美食2.jpg" 
                     alt="特色美食">
                <div class="card-content">
                    <h3>特色美食</h3>
                    <p>家乡的特色美食有：桂林米粉的柔韧、螺蛳粉的爽滑、猪脚粉的软糯，均源于此...</p>
                </div>
            </div>
            
            <div class="card">
                <!-- 添加data-hover-src属性 -->
                <img src="./风景1.jpg" 
                     data-hover-src="./风景2.jpg" 
                     alt="人文景观">
                <div class="card-content">
                    <h3>人文景观</h3>
                    <p>靖江王府、独秀峰铭刻明代王气，象鼻山、灵渠承载秦汉遗风...</p>
                </div>
            </div>
        </div>
    </div>

    <!-- 添加JavaScript代码 -->
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // 获取所有卡片中的图片
            const cardImages = document.querySelectorAll('.card img');
            
            // 为每张图片添加事件监听
            cardImages.forEach(img => {
                // 保存原始图片路径
                const originalSrc = img.src;
                const hoverSrc = img.getAttribute('data-hover-src');
                
                // 鼠标悬停时切换图片
                img.addEventListener('mouseover', function() {
                    if (hoverSrc) {
                        this.src = hoverSrc;
                    }
                });
                
                // 鼠标移出时恢复原始图片
                img.addEventListener('mouseout', function() {
                    this.src = originalSrc;
                });
            });
        });
    </script>
</body>
</html>
