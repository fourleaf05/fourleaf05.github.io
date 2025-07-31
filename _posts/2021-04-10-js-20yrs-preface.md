---
layout:       post
title:        "英语四六级查分入口"
author:       ""
header-style: text
catalog:      true
tags:
    - Web
    - JavaScript
---

# 英语四六级查分入口

<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>英语四六级成绩查询系统</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Helvetica Neue', Arial, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1e5799, #207cca);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.25);
        }
        
        header {
            background: #0d47a1;
            color: white;
            padding: 25px 30px;
            text-align: center;
            position: relative;
        }
        
        .header-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        h1 {
            font-size: 2.4rem;
            margin-bottom: 15px;
            font-weight: 600;
            letter-spacing: 1px;
        }
        
        .subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        .content {
            display: flex;
            min-height: 500px;
        }
        
        .login-section {
            flex: 1;
            padding: 40px;
            background: white;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        
        .score-section {
            flex: 1;
            padding: 40px;
            background: #f9f9f9;
            display: flex;
            flex-direction: column;
            justify-content: center;
            display: none; /* 初始隐藏成绩区域 */
        }
        
        .login-form {
            max-width: 400px;
            margin: 0 auto;
            width: 100%;
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #444;
            font-size: 1rem;
        }
        
        input[type="text"],
        input[type="password"] {
            width: 100%;
            padding: 14px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: border 0.3s, box-shadow 0.3s;
        }
        
        input[type="text"]:focus,
        input[type="password"]:focus {
            border-color: #2196F3;
            box-shadow: 0 0 0 3px rgba(33, 150, 243, 0.2);
            outline: none;
        }
        
        .submit-btn {
            background: linear-gradient(to right, #2196F3, #21CBF3);
            color: white;
            border: none;
            padding: 15px;
            font-size: 1.1rem;
            font-weight: 500;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            margin-top: 10px;
            transition: transform 0.2s, box-shadow 0.3s;
        }
        
        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(33, 150, 243, 0.3);
        }
        
        .submit-btn:active {
            transform: translateY(0);
        }
        
        .score-container {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .score-title {
            font-size: 2.2rem;
            color: #0d47a1;
            margin-bottom: 30px;
            padding-bottom: 15px;
            border-bottom: 2px solid #e0e0e0;
        }
        
        .score-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .score-image {
            width: 100%;
            display: block;
            border-bottom: 1px solid #eee;
        }
        
        .footer {
            text-align: center;
            padding: 25px;
            background: #f5f5f5;
            color: #666;
            font-size: 0.9rem;
        }
        
        .note {
            background: #fff8e1;
            padding: 15px;
            border-radius: 8px;
            margin-top: 20px;
            color: #5d4037;
            font-size: 0.95rem;
            line-height: 1.5;
        }
        
        @media (max-width: 900px) {
            .content {
                flex-direction: column;
            }
            
            header, .login-section, .score-section {
                padding: 20px;
            }
            
            .score-section {
                min-height: 400px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="header-content">
                <h1>英语四六级成绩查询系统</h1>
                <p class="subtitle">教育部考试中心官方成绩查询平台</p >
            </div>
        </header>
        
        <div class="content">
            <div class="login-section">
                <form id="cet-login" class="login-form">
                    <div class="form-group">
                        <label for="username">准考证号/身份证号</label>
                        <input type="text" id="username" name="username" required 
                               placeholder="请输入您的准考证号或身份证号">
                    </div>
                    
                    <div class="form-group">
                        <label for="password">密码</label>
                        <input type="password" id="password" name="password" required 
                               placeholder="请输入您的密码">
                    </div>
                    
                    <button type="submit" class="submit-btn">查询成绩</button>
                    
                    <div class="note">
                        <strong>温馨提示：</strong> 
                        请确保您输入的证件号和密码与报名时使用的信息一致。
                        如忘记密码，请联系所在学校教务处。
                    </div>
                </form>
            </div>
            
            <div id="score-section" class="score-section">
                <div class="score-container">
                    <h2 class="score-title">成绩查询结果</h2>
                    
                    <div class="score-card">
                        < img id="cet-score-image" alt="英语四六级成绩单" class="score-image">
                    </div>
                    
                    <div class="note" style="margin-top: 25px;">
                        此成绩单仅供参考，正式成绩以学校教务处出具的纸质成绩单为准。
                    </div>
                </div>
            </div>
        </div>
        
        <div class="footer">
            <p>© 2023 中国教育考试院 版权所有 | 全国大学英语四、六级考试委员会</p >
        </div>
    </div>
    
    <script>
        document.getElementById('cet-login').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // 获取输入的值（不进行实际验证）
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            // 显示成绩区域
            document.getElementById('score-section').style.display = 'flex';
            
            // 设置成绩单图片路径（使用您指定的 img/cet_score.jpeg）
            const scoreImage = document.getElementById('cet-score-image');
            scoreImage.src = "img/cet_score.jpeg?t=" + Date.now(); // 添加时间戳防止缓存
            scoreImage.alt = username + "的英语四六级成绩单";
            
            // 滚动到成绩区域
            setTimeout(() => {
                document.getElementById('score-section').scrollIntoView({
                    behavior: 'smooth',
                    block: 'start'
                });
            }, 300);
        });
    </script>
</body>
</html>
