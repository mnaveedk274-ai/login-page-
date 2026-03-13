<!DOCTYPE html>
<html lang="en" data-theme="dark">   <!-- default dark -->
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>MET-1 Login</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/> <!-- optional for icons -->
  <style>
    :root {
      --bg: #0f172a;
      --text: #e2e8f0;
      --card: #1e293b;
      --primary: #3b82f6;
      --gradient: linear-gradient(90deg, #3b82f6, #8b5cf6);
    }
    [data-theme="light"] {
      --bg: #f1f5f9;
      --text: #0f172a;
      --card: #ffffff;
      --primary: #2563eb;
      --gradient: linear-gradient(90deg, #2563eb, #7c3aed);
    }
    body {
      margin: 0;
      font-family: system-ui, sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 20px;
      box-sizing: border-box;
    }
    .logo {
      font-size: 120px;
      margin-bottom: 30px;
    }
    .theme-buttons {
      display: flex;
      gap: 15px;
      margin-bottom: 40px;
    }
    .theme-btn {
      padding: 12px 24px;
      border: none;
      border-radius: 50px;
      font-weight: bold;
      cursor: pointer;
      font-size: 16px;
      transition: all 0.3s;
    }
    .theme-btn.active {
      box-shadow: 0 0 15px rgba(0,0,0,0.3);
      transform: scale(1.05);
    }
    .login-card {
      background: var(--card);
      padding: 40px 30px;
      border-radius: 16px;
      width: 100%;
      max-width: 380px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.4);
      text-align: center;
    }
    h1 {
      margin: 0 0 30px;
      font-size: 28px;
    }
    input {
      width: 100%;
      padding: 14px;
      margin: 12px 0;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      background: rgba(255,255,255,0.1);
      color: var(--text);
    }
    input::placeholder {
      color: rgba(255,255,255,0.5);
    }
    [data-theme="light"] input {
      background: #f1f5f9;
      color: #0f172a;
    }
    [data-theme="light"] input::placeholder {
      color: #64748b;
    }
    .login-btn {
      width: 100%;
      padding: 14px;
      margin: 20px 0 10px;
      border: none;
      border-radius: 50px;
      background: var(--gradient);
      color: white;
      font-size: 18px;
      font-weight: bold;
      cursor: pointer;
      transition: all 0.3s;
    }
    .login-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(59,130,246,0.4);
    }
    .contact-btn {
      margin-top: 30px;
      padding: 12px 30px;
      border-radius: 50px;
      background: #25D366;
      color: white;
      font-weight: bold;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      box-shadow: 0 5px 15px rgba(37,211,102,0.3);
    }
  </style>
</head>
<body>

  <div class="logo">🏫</div>   <!-- school building emoji, screenshot mein flag wala building tha -->

  <div class="theme-buttons">
    <button class="theme-btn active" onclick="setTheme('dark')">Dark Theme</button>
    <button class="theme-btn" onclick="setTheme('light')">Light Theme</button>
  </div>

  <div class="login-card">
    <h1>Login</h1>
    
    <input type="text" placeholder="MET-1" value="MET-1" readonly />   <!-- maybe fixed or just example -->
    <input type="password" placeholder="......" />
    
    <button class="login-btn">Login</button>
  </div>

  <a href="https://wa.me/92300xxxxxxx" class="contact-btn">   <!-- number change kar dena -->
    <i class="fab fa-whatsapp"></i> Contact Admin
  </a>

  <script>
    function setTheme(theme) {
      document.documentElement.setAttribute('data-theme', theme);
      document.querySelectorAll('.theme-btn').forEach(btn => {
        btn.classList.toggle('active', btn.textContent.includes(theme.charAt(0).toUpperCase() + theme.slice(1)));
      });
      localStorage.setItem('theme', theme);
    }

    // Load saved theme
    const savedTheme = localStorage.getItem('theme') || 'dark';
    setTheme(savedTheme);

    // Login button dummy (real mein backend call hoga)
    document.querySelector('.login-btn').addEventListener('click', () => {
      alert('Login attempt... (ye sirf demo hai, asal mein check hota hoga server pe)');
    });
  </script>

</body>
</html>
