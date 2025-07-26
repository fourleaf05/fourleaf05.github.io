<!DOCTYPE html>
<html>
<head>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { 
            background: #f9f9f9; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            height: 100vh; 
        }
        .login-box {
            width: 310px; 
            padding: 20px; 
            background: white; 
            border: 1px solid #d8dee2; 
            border-radius: 5px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.05);
        }
        h2 { text-align: center; margin-bottom: 20px; color: #333; }
        .input-field { margin-bottom: 15px; }
        label { display: block; font-weight: bold; margin-bottom: 5px; }
        input { 
            width: 100%; 
            padding: 8px; 
            border: 1px solid #ddd; 
            border-radius: 3px; 
        }
        .btn { 
            background: #28a745; 
            color: white; 
            border: none; 
            padding: 10px; 
            width: 100%; 
            border-radius: 3px; 
            cursor: pointer; 
        }
        .btn:hover { background: #279f43; }
    </style>
</head>
<body>
    <div class="login-box">
        <h2>账号登录</h2>
        <form action="welcome.html">
            <div class="input-field">
                <label>用户名或邮箱</label>
                <input type="text" name="username">
            </div>
            <div class="input-field">
                <label>密码</label>
                <input type="password" name="password">
            </div>
            <input type="submit" class="btn" value="登录">
        </form>
    </div>
</body>
</html>
