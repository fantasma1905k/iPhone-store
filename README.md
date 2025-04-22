#iphone store
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>IPhone Store</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body class="welcome">
  <div class="splash">
    <h1>IPhone Store</h1>
    <p>Bem-vindo à sua loja de iPhones!</p>
  </div>
  <script>
    setTimeout(() => {
      window.location.href = "login.html";
    }, 3000);
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Login - IPhone Store</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body class="login-page">
  <div class="container">
    <div class="form-container">
      <form id="auth-form">
        <h2 id="form-title">Entrar</h2>
        <input type="text" id="name" placeholder="Nome completo" style="display: none;" />
        <input type="email" id="email" placeholder="E-mail" required />
        <input type="password" id="password" placeholder="Senha" required />
        <input type="password" id="confirm-password" placeholder="Confirmar senha" style="display: none;" />
        <button type="submit" id="submit-btn">Entrar</button>
        <p id="toggle-form">Não tem uma conta? <a href="#">Cadastre-se</a></p>
        <p id="error-message" class="error"></p>
      </form>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(to right, #1e3c72, #2a5298);
  color: #fff;
}

.welcome .splash {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  animation: fadeIn 2s ease-in-out;
}

.login-page .container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.form-container {
  background-color: rgba(255, 255, 255, 0.1);
  padding: 2rem;
  border-radius: 10px;
  backdrop-filter: blur(10px);
}

form {
  display: flex;
  flex-direction: column;
}

input {
  margin-bottom: 1rem;
  padding: 0.5rem;
  border: none;
  border-radius: 5px;
}

button {
  padding: 0.5rem;
  border: none;
  border-radius: 5px;
  background-color: #fff;
  color: #1e3c72;
  font-weight: bold;
  cursor: pointer;
}

button:hover {
  background-color: #f0f0f0;
}

.error {
  color: #ff6b6b;
  margin-top: 0.5rem;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
document.addEventListener('DOMContentLoaded', () => {
  const form = document.getElementById('auth-form');
  const toggleForm = document.getElementById('toggle-form');
  const formTitle = document.getElementById('form-title');
  const nameInput = document.getElementById('name');
  const confirmPasswordInput = document.getElementById('confirm-password');
  const submitBtn = document.getElementById('submit-btn');
  const errorMessage = document.getElementById('error-message');

  let isLogin = true;

  toggleForm.addEventListener('click', (e) => {
    e.preventDefault();
    isLogin = !isLogin;
    if (isLogin) {
      formTitle.textContent = 'Entrar';
      nameInput.style.display = 'none';
      confirmPasswordInput.style.display = 'none';
      submitBtn.textContent = 'Entrar';
      toggleForm.innerHTML = 'Não tem uma conta? <a href="#">Cadastre-se</a>';
    } else {
      formTitle.textContent = 'Cadastrar';
      nameInput.style.display = 'block';
      confirmPasswordInput.style.display = 'block';
      submitBtn.textContent = 'Cadastrar';
      toggleForm.innerHTML = 'Já tem uma conta? <a href="#">Entrar</a>';
    }
    errorMessage.textContent = '';
  });

  form.addEventListener('submit', (e) => {
    e.preventDefault();
    errorMessage.textContent = '';

    const email = document.getElementById('email').value.trim();
    const password = document.getElementById('password').value;
    const confirmPassword = confirmPasswordInput.value;
    const name = nameInput.value.trim();

    if (!email || !password || (!isLogin && (!name || !confirmPassword))) {
      errorMessage.textContent = 'Por favor, preencha todos os campos.';
      return;
    }

    if (!validateEmail(email)) {
      errorMessage.textContent = 'E-mail inválido.';
      return;
    }

    if (!isLogin && password !== confirmPassword) {
      errorMessage.textContent = 'As senhas não coincidem.';
      return;
    }

    // Aqui você pode adicionar a lógica para autenticar ou registrar o usuário
    alert(isLogin ? 'Login realizado com sucesso!' : 'Cadastro realizado com sucesso!');
    form.reset();
  });

  function validateEmail(email) {
    const re = /\S+@\S+\.\S+/;

::contentReference[oaicite:1]{index=1}
 
