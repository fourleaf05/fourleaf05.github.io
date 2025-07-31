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

<form id="cet-login" class="login-form">
  <div class="form-group">
    <label for="username">准考证号/身份证号：</label>
    <input type="text" id="username" name="username" required placeholder="请输入您的准考证号或身份证号">
  </div>
  <div class="form-group">
    <label for="password">密码：</label>
    <input type="password" id="password" name="password" required placeholder="请输入您的密码">
  </div>
  <button type="submit" class="submit-btn">查询成绩</button>
</form>

<div id="score-result" style="display: none;">
  <h2>成绩查询结果</h2>
  < img id="cet-score-image" alt="四六级成绩单" style="max-width: 100%;">
</div>

<script>
document.getElementById('cet-login').addEventListener('submit', function(e) {
  e.preventDefault();
  
  // 获取输入的值（不进行验证）
  const username = document.getElementById('username').value;
  const password = document.getElementById('password').value;
  
  // 模拟成绩单展示（实际应用中应替换为真实成绩单URL）
  const scoreImage = document.getElementById('cet-score-image');
  scoreImage.src = "img/cet_score.jpeg?t=" + Date.now(); // 缓存刷新
  scoreImage.alt = `${username}的英语四六级成绩单`;
  
  // 显示结果区域
  document.getElementById('score-result').style.display = 'block';
  
  // 平滑滚动到结果区域
  document.getElementById('score-result').scrollIntoView({behavior: 'smooth'});
});
</script>

<style>
.login-form {
  max-width: 500px;
  margin: 20px auto;
  padding: 25px;
  background: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 8px;
  font-weight: bold;
  color: #333;
}

input[type="text"],
input[type="password"] {
  width: 100%;
  padding: 12px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 16px;
  box-sizing: border-box;
}

.submit-btn {
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 12px 20px;
  font-size: 16px;
  border-radius: 4px;
  cursor: pointer;
  width: 100%;
  transition: background-color 0.3s;
}

.submit-btn:hover {
  background-color: #45a049;
}
</style>
