# my-webpage
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>我的第一个互动网页</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: Arial, "Microsoft YaHei", sans-serif;
      background: linear-gradient(135deg, #667eea, #764ba2);
      display: flex;
      justify-content: center;
      align-items: center;
      color: #222;
      padding: 20px;
    }

    .card {
      width: 100%;
      max-width: 520px;
      background: white;
      border-radius: 24px;
      padding: 32px;
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.2);
      text-align: center;
    }

    h1 {
      margin-top: 0;
      color: #4f46e5;
    }

    p {
      line-height: 1.7;
    }

    input {
      width: 100%;
      padding: 14px;
      margin: 12px 0;
      border: 2px solid #ddd;
      border-radius: 12px;
      font-size: 16px;
    }

    button {
      border: none;
      padding: 12px 18px;
      margin: 8px 4px;
      border-radius: 999px;
      background: #4f46e5;
      color: white;
      font-size: 15px;
      cursor: pointer;
      transition: transform 0.2s, background 0.2s;
    }

    button:hover {
      transform: translateY(-2px);
      background: #3730a3;
    }

    .output {
      margin-top: 20px;
      padding: 18px;
      border-radius: 16px;
      background: #f3f4f6;
      min-height: 60px;
      font-weight: bold;
    }

    .counter {
      font-size: 42px;
      color: #4f46e5;
      margin: 12px 0;
    }

    .small {
      font-size: 13px;
      color: #666;
      margin-top: 22px;
    }
  </style>
</head>
<body>
  <main class="card">
    <h1>你好，GitHub Pages！</h1>
    <p>这是我的第一个互动网页。输入你的名字，点击按钮试试看。</p>

    <input id="nameInput" type="text" placeholder="请输入你的名字" />
    <button onclick="sayHello()">打招呼</button>
    <button onclick="changeTheme()">换背景颜色</button>

    <div class="output" id="message">这里会显示互动结果。</div>

    <h2>点击计数器</h2>
    <div class="counter" id="count">0</div>
    <button onclick="increaseCount()">+1</button>
    <button onclick="resetCount()">清零</button>

    <p class="small">Made with HTML + CSS + JavaScript</p>
  </main>

  <script>
    let count = 0;

    function sayHello() {
      const name = document.getElementById("nameInput").value.trim();
      const message = document.getElementById("message");

      if (name === "") {
        message.textContent = "请先输入你的名字 🙂";
      } else {
        message.textContent = `你好，${name}！欢迎来到我的网页 🎉`;
      }
    }

    function increaseCount() {
      count = count + 1;
      document.getElementById("count").textContent = count;
    }

    function resetCount() {
      count = 0;
      document.getElementById("count").textContent = count;
    }

    function changeTheme() {
      const themes = [
        "linear-gradient(135deg, #667eea, #764ba2)",
        "linear-gradient(135deg, #f093fb, #f5576c)",
        "linear-gradient(135deg, #4facfe, #00f2fe)",
        "linear-gradient(135deg, #43e97b, #38f9d7)",
        "linear-gradient(135deg, #fa709a, #fee140)"
      ];

      const randomIndex = Math.floor(Math.random() * themes.length);
      document.body.style.background = themes[randomIndex];
    }
  </script>
</body>
</html>
