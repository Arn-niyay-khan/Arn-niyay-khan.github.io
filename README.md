<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title data-i18n="pageTitle">รวมนามปากกา | Arn-niyay-khan</title>
  <link href="https://fonts.googleapis.com/css2?family=Mitr&display=swap" rel="stylesheet">
  <style>
    body {
      background: linear-gradient(145deg, #fdf5ff, #f0f8ff);
      font-family: 'Mitr', sans-serif;
      color: #432d5d;
      padding: 40px;
      max-width: 1024px;
      margin: auto;
      text-align: center;
      user-select: none;
    }

    /* === Header Controls === */
    .header-controls {
      display: flex;
      justify-content: flex-end;
      align-items: center;
      margin-bottom: 30px; 
      flex-wrap: wrap;
      gap: 15px;
    }

    .user-info {
      display: flex;
      align-items: center;
      gap: 15px;
      flex-wrap: wrap;
      justify-content: flex-end;
    }

    .coin-display {
      font-size: 0.99rem;
      color: #6e3cab;
    }

    /* เพิ่ม CSS สำหรับส่วนแสดงอีเมลผู้ใช้ */
    #userEmailDisplay {
      display: flex;
      align-items: center;
      gap: 5px;
    }

    #logoutButton {
        background: none;
        border: none;
        color: #8a63bb;
        text-decoration: underline;
        cursor: pointer;
        font-size: 0.9rem;
        margin-left: 5px;
        padding: 0;
    }
    #logoutButton:hover {
        color: #6e3cab;
    }

    .language-selector {
      font-size: 0.99rem;
      color: #6e3cab;
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .language-selector select {
      font-size: 0.8rem;
      padding: 4px 8px;
      border-radius: 6px;
      margin-left: 5px;
    }
    /* === End Header Controls === */

    /* === Login Section Styles === */
    #loginSection {
        margin-top: 20px;
        padding: 20px;
        background-color: #fff;
        border-radius: 10px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        max-width: 500px;
        margin: 30px auto;
        text-align: center;
    }

    #loginSection h2 {
        color: #7b4ca0;
        font-size: 1.8rem;
        margin-bottom: 15px;
    }
    #loginSection p {
        color: #5e437f;
        font-size: 0.95rem;
        margin-bottom: 20px;
    }
    #loginSection input[type="email"] {
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 8px;
        font-family: 'Mitr', sans-serif;
        flex-grow: 1;
        max-width: 250px;
    }
    #loginSection button {
        padding: 10px 15px;
        background-color: #a87ce6;
        color: white;
        border: none;
        border-radius: 30px;
        font-weight: bold;
        cursor: pointer;
        transition: background 0.3s ease;
    }
    #loginSection button:hover {
        background-color: #8f63d2;
    }
    #magicLinkMessage {
        margin-top: 15px;
        font-size: 0.9rem;
        color: #5e437f;
    }
    /* === End Login Section Styles === */
    
    h1 {
      color: #7b4ca0;
      font-size: 2.2rem;
      margin-top: 20px;
      margin-bottom: 10px;
      animation: pulse 3s ease-in-out infinite;
    }

    .intro-text {
      color: #5e437f;
      font-size: 1.1rem;
      margin-bottom: 40px;
      line-height: 1.6;
      max-width: 700px;
      margin-left: auto;
      margin-right: auto;
      white-space: pre-wrap;
      text-align: justify;
    }
    .intro-text p {
        text-indent: 2.5em;
        margin-bottom: 1em;
    }


    ul {
      list-style: none;
      padding-left: 0;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 25px;
    }

    li {
      background-color: #ffffffd0;
      border-left: 8px solid #b084f7;
      border-radius: 14px;
      padding: 20px;
      transition: all 0.3s ease;
      box-shadow: 0 4px 12px rgba(0,0,0,0.06);
      position: relative;
      width: 280px;
      text-align: left;
    }

    li:hover {
      transform: translateY(-5px) scale(1.02);
      box-shadow: 0 6px 18px rgba(0,0,0,0.1);
    }

    a {
      color: #6639b6;
      font-size: 1.5rem;
      font-weight: bold;
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    a::before {
      font-size: 1.5rem;
      transition: transform 0.3s ease;
    }

    li:hover a::before {
      transform: rotate(-8deg) scale(1.1);
    }

    .desc {
      color: #5e437f;
      font-size: 1rem;
      margin-top: 8px;
      line-height: 1.5;
    }

    .tag {
      position: absolute;
      top: -10px;
      right: -10px;
      background: #ff77d6;
      color: white;
      font-size: 0.8rem;
      padding: 4px 10px;
      border-radius: 999px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.15);
      animation: float 4s ease-in-out infinite;
    }

    .footer {
      margin-top: 60px;
      font-size: 1.25rem;
      color: #9a7fb5;
      text-align: center;
    }
    
    /* ปุ่มล้าง LocalStorage (คงไว้เพื่อการทดสอบ) */
    .clear-localstorage-button {
      position: fixed;
      bottom: 20px;
      right: 20px;
      z-index: 9999;
      background: red;
      color: white;
      padding: 10px;
      border-radius: 8px;
      cursor: pointer;
    }

    /* === Buy Coins Section Styles (Local) === */
    .buy-coin-section {
        margin-top: 60px;
        text-align: center;
        padding-bottom: 30px;
        border-bottom: 1px solid #e0c8ff;
    }
    .buy-coin-section h2 {
        color: #7b4ca0;
        font-size: 1.8rem;
        margin-bottom: 25px;
    }
    /* เพิ่มสำหรับข้อความแนะนำการชำระเงิน */
    .payment-info-desc {
        font-size: 1.1rem;
        color: #5e437f;
        margin-bottom: 20px;
        line-height: 1.6;
    }
    .buy-coin-buttons-grid {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 15px;
        max-width: 600px;
        margin: 0 auto 20px auto;
    }
    .buy-coin-button {
        padding: 12px 25px;
        background-color: #a87ce6;
        color: #fff;
        border: none;
        border-radius: 30px;
        font-size: 1.1rem;
        font-weight: bold;
        cursor: pointer;
        transition: background 0.3s ease, transform 0.3s ease;
        flex: 1 1 auto;
        min-width: 120px;
        box-sizing: border-box;
    }
    .buy-coin-button:hover {
        background-color: #8f63d2;
        transform: scale(1.03);
    }
    .custom-amount {
        margin-top: 20px;
        font-size: 1rem;
        color: #5e437f;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
        gap: 10px;
    }
    .custom-amount label {
        flex-shrink: 0;
    }
    .custom-amount input[type="number"] {
        padding: 8px 12px;
        border: 1px solid #ccc;
        border-radius: 8px;
        font-family: 'Mitr', sans-serif;
        font-size: 1rem;
        width: 100px;
        text-align: center;
    }
    .custom-amount button {
        /* ซ่อนปุ่ม custom buy ถ้าไม่อยากให้ผู้ใช้ระบุเอง */
        display: none; 
        padding: 8px 15px;
        background-color: #5cb85c;
        color: white;
        border: none;
        border-radius: 30px;
        font-weight: bold;
        cursor: pointer;
        transition: background 0.3s ease;
    }
    .custom-amount button:hover {
        background-color: #4cae4c;
    }
    #coinPreview {
        margin-top: 10px;
        font-weight: bold;
        color: #7b4ca0;
        width: 100%;
    }
    /* === End Buy Coins Section Styles (Local) === */

    /* === Interfan Coin Section Styles (ใหม่) === */
    .interfan-coin-section {
        margin-top: 60px;
        text-align: center;
        padding-top: 30px;
        border-top: 1px solid #e0c8ff;
        background: #fdf5ff;
        border-radius: 16px;
        box-shadow: 0 4px 15px rgba(0,0,0,0.08);
        max-width: 800px;
        margin-left: auto;
        margin-right: auto;
        padding: 40px;
    }
    .interfan-coin-section h2 {
        color: #7b4ca0;
        font-size: 1.8rem;
        margin-bottom: 25px;
    }
    .interfan-payment-info {
        font-size: 1.1rem;
        color: #5e437f;
        margin-bottom: 20px;
        line-height: 1.6;
    }
    .interfan-button-grid {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 15px;
        margin-top: 20px;
    }
    .interfan-buy-btn {
        background-color: #e6a87c;
        color: white;
        padding: 12px 25px;
        border: none;
        border-radius: 30px;
        font-size: 1.1rem;
        font-weight: bold;
        cursor: pointer;
        transition: background 0.3s ease, transform 0.3s ease;
        flex: 1 1 auto;
        min-width: 140px;
        box-sizing: border-box;
    }
    .interfan-buy-btn:hover {
        background-color: #cc916d;
        transform: scale(1.03);
    }
    .interfan-redeem-section {
        margin-top: 40px;
        padding-top: 30px;
        border-top: 1px dashed #d89fe5;
    }
    .interfan-redeem-section h3 {
        color: #7b4ca0;
        font-size: 1.5rem;
        margin-bottom: 20px;
    }
    .interfan-redeem-input-group {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 10px;
        margin-bottom: 15px;
        flex-wrap: wrap;
    }
    input#redeemCode {
        padding: 10px 15px;
        border: 1px solid #ccc;
        border-radius: 8px;
        font-family: 'Mitr', sans-serif;
        font-size: 1rem;
        width: 200px;
        max-width: 70%;
        box-sizing: border-box;
    }
    button#redeemButton {
        background-color: #22c55e;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        font-weight: bold;
        font-size: 1rem;
        transition: background 0.3s ease, transform 0.3s ease;
    }
    button#redeemButton:hover {
        background-color: #16a34a;
        transform: scale(1.03);
    }
    #redeemMessage {
        margin-top: 10px;
        font-size: 1rem;
        font-weight: bold;
        color: #6b21a8;
    }
    /* === End Interfan Coin Section Styles === */


    /* === Contact Admin Section Styles === */
    .contact-admin-section {
        text-align: center;
        margin-top: 60px;
        padding-top: 20px;
        border-top: 1px solid #e0c8ff;
    }

    #contactAdminBtn {
        background-color: #7b4ca0;
        color: white;
        padding: 15px 25px;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        font-size: 1.15rem;
        font-weight: bold;
        transition: background-color 0.3s ease, transform 0.3s ease;
        display: block;
        margin: 0 auto 10px auto;
        box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }

    #contactAdminBtn:hover {
        background-color: #613b82;
        transform: scale(1.03);
    }

    .response-time-message {
        font-size: 1rem;
        color: #5e437f;
        margin-top: 5px;
    }
    /* === End Contact Admin Section Styles === */


    /* === Modal Styles === */
    .modal-overlay {
        display: none;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0,0,0,0.6);
        z-index: 9998;
    }
    .modal-content {
        background:#fff;
        max-width:500px;
        margin:5% auto;
        padding:30px;
        border-radius:12px;
        text-align:center;
        box-shadow:0 6px 20px rgba(0,0,0,0.3);
        font-family:'Mitr', sans-serif;
        position: relative;
        z-index: 9999;
    }
    .modal-content h3 {
        color:#6e3cab;
        margin-bottom: 20px;
        font-size: 1.5rem;
    }
    .modal-content p {
        font-size:1.1rem;
        color:#5e437f;
        margin-bottom:15px;
        line-height: 1.5;
    }
    .modal-content button {
        padding: 10px 20px;
        border: none;
        border-radius: 30px;
        font-weight: bold;
        cursor: pointer;
        transition: background 0.3s ease, transform 0.2s ease;
        font-size: 1rem;
    }
    .modal-content button:hover {
        transform: scale(1.05);
    }
    .modal-content .btn-cancel {
        background:#ccc;
        color:#333;
    }
    .modal-content .btn-confirm {
        background:#a87ce6;
        color:#fff;
    }
    .modal-content #downloadQrButton {
        background-color: #5cb85c;
        color: white;
    }
    .modal-content #downloadQrButton:hover {
        background-color: #4cae4c;
    }
    .modal-content #iPaidButton {
        background-color: #0275d8;
        color: white;
    }
    .modal-content #iPaidButton:hover {
        background-color: #0264b3;
    }
    .modal-content #countdown {
        display: none; /* เราจะไม่ใช้นับถอยหลังในระบบ Manual */
    }
    .modal-content #qrCodeImage {
        width: 200px;
        height: 200px;
        border: 1px solid #eee;
        border-radius: 8px;
        margin-bottom: 20px;
    }
    /* ปรับขนาด internationalPaymentInfo ใน Modal */
    .modal-content #internationalPaymentInfo {
        font-size: 0.9rem; 
        color: #d9534f;
        margin-top: 20px;
    }

    /* === End Modal Styles === */

    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.03); }
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-6px); }
    }

    /* Media query สำหรับหน้าจอขนาดเล็ก */
    @media screen and (max-width: 600px) {
      .header-controls {
        flex-direction: column;
        align-items: flex-start;
      }
      .user-info {
        width: 100%;
        justify-content: flex-start;
      }
      h1 {
          font-size: 1.8rem;
      }
      .intro-text {
          font-size: 1rem;
      }
      a {
          font-size: 1.3rem;
      }
      .desc {
          font-size: 0.9rem;
      }
      li {
          width: 100%;
          box-sizing: border-box;
      }
      /* Buy Coin Section on mobile */
      .buy-coin-buttons-grid button,
      .custom-amount input[type="number"],
      .custom-amount button {
          width: 100%;
          box-sizing: border-box;
          margin-bottom: 10px;
      }
      .custom-amount {
          flex-direction: column;
          align-items: center;
      }
      .custom-amount label {
          margin-bottom: 5px;
      }
      .modal-content {
          margin: 10% auto;
          padding: 20px;
      }
      .modal-content h3 {
          font-size: 1.3rem;
      }
      .modal-content p {
          font-size: 1rem;
      }
      /* Interfan Coin Section on mobile */
      .interfan-buy-btn,
      .interfan-redeem-input-group button,
      input#redeemCode {
          width: 100%;
          box-sizing: border-box;
          margin-bottom: 10px;
      }
      .interfan-redeem-input-group {
        flex-direction: column;
        align-items: center;
      }
      #redeemMessage {
        text-align: center;
      }
    }
  </style>
</head>
<body>

  <div class="header-controls">
    <div class="user-info">
      <div class="coin-display" data-i18n="coinLabel">
        💰 เหรียญของคุณ: <span id="coin-count">0</span> เหรียญ
      </div>
      <div id="userEmailDisplay" style="font-size: 0.99rem; color: #6e3cab; margin-left: 15px; display: none;">
        สวัสดี, <span id="loggedInEmail"></span>!
        <button id="logoutButton">(ออกจากระบบ)</button>
      </div>

      <div class="language-selector">
        <label for="language-select" data-i18n="languageLabel">🌐 เปลี่ยนภาษา:</label>
        <select id="language-select" onchange="switchLang(this.value)">
          <option value="th">ไทย</option>
          <option value="en">English</option>
          <option value="ch">中国人</option>
          <option value="ru">русский язык</option>
          <option value="jp">日本語</option>
          <option value="kr">한국어</option>
          <option value="vn">Tiếng Việt</option>
        </select>
      </div>
    </div>
  </div>

  <div id="loginSection">
    <h2 data-i18n="loginTitle">เข้าสู่ระบบ / ลงทะเบียน (ไม่ใช้รหัสผ่าน)</h2>
    <p data-i18n="loginInstruction">กรอกอีเมลของคุณเพื่อรับ Magic Link สำหรับการเข้าสู่ระบบ</p>
    <div style="display: flex; justify-content: center; align-items: center; gap: 10px; margin-top: 20px;">
      <input type="email" id="userEmailLogin" placeholder="youremail@example.com" required>
      <button id="requestMagicLinkBtn" data-i18n="requestMagicLinkButton">รับลิงก์เข้าสู่ระบบ</button>
    </div>
    <p id="magicLinkMessage"></p>
  </div>


  <h1 data-i18n="mainTitle">🌟 รวมนามปากกาในเครือ Arn-niyay-khan 🌟</h1>
  <div class="intro-text" id="introText" data-i18n-content-type="intro"
    data-content-th="ยินดีต้อนรับสู่โลกของ Arn-niyay-khan ที่รวบรวมหลากหลายนามปากกาและแนวเรื่องไม่ซ้ำใคร
    
    ไม่ว่าคุณจะชื่นชอบเรื่องราวรักโรแมนติก ดราม่าเข้มข้น แฟนตาซีเหนือจริง หรืออีโรติกจัดจ้าน เรามีทุกรสชาติให้คุณได้ค้นหาและดื่มด่ำไปกับจินตนาการที่ไร้ขีดจำกัด"
    data-content-en="Welcome to the world of Arn-niyay-khan, where a diverse collection of pen names and unique genres awaits.
    
    Whether you love romantic, intense drama, surreal fantasy, or spicy erotica, we have every flavor for you to explore and immerse yourself in boundless imagination."
    data-content-ch="欢迎来到 Arn-niyay-khan 的世界，这里汇集了各种独特的笔名和风格迥异的故事。
    
    无论您喜欢浪漫、扣人心弦的戏剧、超现实的奇幻，还是火辣的色情文学，我们都能满足您的所有品味，让您沉浸在无限的想象中。"
    data-content-ru="Добро пожаловать в мир Arn-niyay-khan, где собрана разнообразная коллекция псевдонимов и уникальных жанров.
    
    Любите ли вы романтику, напряженную драму, сюрреалистическое фэнтези или пикантную эротику, у нас есть всё, чтобы вы могли исследовать и погрузиться в безграничное воображение."
    data-content-jp="Arn-niyay-khan の世界へようこそ。ここでは、多様なペンネームとユニークなジャンルのコレクションがあなたを待っています。
    
    ロマンチックな物語、激しいドラマ、超現実的なファンタジー、またはスパイシーなエロチカがお好みでも、私たちはあらゆる好みを提供し、無限の想像力に浸ることができます。"
    data-content-kr="Arn-niyay-khan의 세계에 오신 것을 환영합니다. 이곳에서는 다양한 필명과 독특한 장르의 컬렉션이 여러분을 기다립니다。
    
    로맨틱하고 강렬한 드라마, 초현실적인 판타지, 또는 매운 에로티카를 좋아하든, 우리는 여러분이 탐험하고 무한한 상상력에 몰입할 수 있는 모든 취향을 제공합니다。"
    data-content-vn="Chào mừng đến với thế giới của Arn-niyay-khan, nơi tập hợp một bộ sưu tập đa dạng các bút danh và thể loại độc đáo.
    
    Dù bạn yêu thích những câu chuyện lãng mạn, kịch tính, giả tưởng siêu thực, hay erotic nóng bỏng, chúng tôi đều có mọi hương vị để bạn khám phá và đắm chìm trong trí tưởng tượng vô hạn."
  ></div>

  <button onclick="localStorage.clear(); alert('เคลียร์ localStorage แล้วค่ะ'); location.reload();" class="clear-localstorage-button">🧹 ล้าง localStorage</button>

  <ul>
    <li data-i18n-genre="drama_bl">
      <a href="coderak/" data-i18n="coderakTitle">📘 โค้ดรัก</a>
      <div class="desc" data-i18n="coderakDesc">นิยายวายแนวโรแมนติก ดราม่า บีบหัวใจ 💔</div>
      <div class="tag" data-i18n="coderakTag">วายดราม่า</div>
    </li>
    <li data-i18n-genre="erotic_bl">
      <a href="lippo/" data-i18n="lippoTitle">🔥 LIPPO</a>
      <div class="desc" data-i18n="lippoDesc">นิยายวายแนวอีโรติกจัดหนัก รักเร่าร้อน NC++ 🔥🛏</div>
      <div class="tag" data-i18n="lippoTag">วาย NC จัดเต็ม</div>
    </li>
    <li data-i18n-genre="welawadee_bl">
      <a href="welawadee/" data-i18n="welawadeeTitle">🌙 เวฬาวดี</a>
      <div class="desc" data-i18n="welawadeeDesc">วาย omegaverse, ท้องได้, เหนือธรรมชาติ ✨🌌</div>
      <div class="tag" data-i18n="welawadeeTag">วายเหนือธรรมชาติ</div>
    </li>
    <li data-i18n-genre="erotic_mf">
      <a href="wealthy/" data-i18n="wealthyTitle">💄 WEALTHY</a>
      <div class="desc" data-i18n="wealthyDesc">นิยายชายหญิงอีโรติกเข้มข้น รักรสแซ่บ NC++ 🍷</div>
      <div class="tag" data-i18n="wealthyTag">อีโรติกผู้ใหญ่</div>
    </li>
    <li data-i18n-genre="feelgood_mf">
      <a href="bellwarin/" data-i18n="bellwarinTitle">🌼 เบลวรินท์</a>
      <div class="desc" data-i18n="bellwarinDesc">ชายหญิงรักสดใส ฟีลกู๊ด นุ่มนวลหัวใจ ☀️🧁</div>
      <div class="tag" data-i18n="bellwarinTag">ฟีลกู๊ดชายหญิง</div>
    </li>
    <li data-i18n-genre="yuri">
      <a href="nichchaben/" data-i18n="nichchabenTitle">🌈 ณิชชาเบญ</a>
      <div class="desc" data-i18n="nichchabenDesc">นิยายยูริ หญิงรักหญิง หลากหลายแนว 💕👭</div>
      <div class="tag" data-i18n="nichchabenTag">ยูริ</div>
    </li>
  </ul>


  <div class="buy-coin-section">
    <h2 data-i18n="buyCoinsTitle">✨ เติมเหรียญเพื่ออ่านนิยาย ✨</h2>
    <p class="payment-info-desc" data-i18n="thaiPaymentMethod">💵 ชำระผ่าน QR Code PromptPay หรือ Mobile Banking</p>
    <p class="payment-info-desc" data-i18n="thaiExchangeRate">⭐ 1 บาท = 100 เหรียญ</p>
    <div class="buy-coin-buttons-grid">
      <button class="buy-coin-button" data-price="5" data-coins="500" data-i18n="buyPrice5">5 บาท (500 เหรียญ)</button>
      <button class="buy-coin-button" data-price="10" data-coins="1000" data-i18n="buyPrice10">10 บาท (1,000 เหรียญ)</button>
      <button class="buy-coin-button" data-price="20" data-coins="2000" data-i18n="buyPrice20">20 บาท (2,000 เหรียญ)</button>
      <button class="buy-coin-button" data-price="50" data-coins="5000" data-i18n="buyPrice50">50 บาท (5,000 เหรียญ)</button>
      <button class="buy-coin-button" data-price="100" data-coins="10000" data-i18n="buyPrice100">100 บาท (10,000 เหรียญ)</button>
      <button class="buy-coin-button" data-price="200" data-coins="20000" data-i18n="buyPrice200">200 บาท (20,000 เหรียญ)</button>
      <button class="buy-coin-button" data-price="500" data-coins="50000" data-i18n="buyPrice500">500 บาท (50,000 เหรียญ)</button>
      <button class="buy-coin-button" data-price="1000" data-coins="100000" data-i18n="buyPrice1000">1,000 บาท (100,000 เหรียญ)</button>
    </div>
    <div class="custom-amount">
    

  <div class="interfan-coin-section">
    <h2 data-i18n="interfanBuyCoinsTitle">✨ เติมเหรียญสำหรับแฟนต่างชาติ (Interfan) ✨</h2>
    <p class="interfan-payment-info" data-i18n="interfanPaymentMethod">💵 ชำระผ่านบัตรเครดิตหรือ PayPal บน Gumroad</p>
    <p class="interfan-payment-info" data-i18n="interfanExchangeRate">⭐ 1 USD ≈ 3,400 เหรียญ</p>
    
    <div class="interfan-button-grid">
      <button class="interfan-buy-btn" data-product-key="usd_0_99" data-coins="1000" data-i18n="buyUSD1000Coins">ซื้อ 1,000 เหรียญ - $0.99</button>
      <button class="interfan-buy-btn" data-product-key="usd_1_99" data-coins="5000" data-i18n="buyUSD5000Coins">ซื้อ 5,000 เหรียญ - $1.99</button>
      <button class="interfan-buy-btn" data-product-key="usd_2_99" data-coins="10000" data-i18n="buyUSD10000Coins">ซื้อ 10,000 เหรียญ - $2.99</button>
      <button class="interfan-buy-btn" data-product-key="usd_9_99" data-coins="50000" data-i18n="buyUSD50000Coins">ซื้อ 50,000 เหรียญ - $9.99</button>
      <button class="interfan-buy-btn" data-product-key="usd_19_99" data-coins="100000" data-i18n="buyUSD100000Coins">ซื้อ 100,000 เหรียญ - $19.99</button>
    </div>

    <div class="interfan-redeem-section">
      <h3 data-i18n="redeemTitle">✨ ใส่รหัสยืนยันที่ได้รับจาก Gumroad เพื่อรับเหรียญ ✨</h3>
      <p style="font-size: 0.9rem; color: #8a63bb;" data-i18n="redeemInstruction">โปรดตรวจสอบอีเมลของคุณเพื่อหารหัสยืนยันหลังจากชำระเงินสำเร็จ</p>
      <div class="interfan-redeem-input-group">
        <input type="text" id="redeemCode" data-i18n-placeholder="redeemCodePlaceholder">
        <button id="redeemButton" data-i18n="redeemButton">ยืนยันรับเหรียญ</button>
      </div>
      <p id="redeemMessage" data-i18n="redeemMessageText"></p>
      <p id="loggedInUserForRedeem" style="font-size: 0.9rem; color: #d9534f; display: none;" data-i18n="loggedInUserForRedeem">กรุณาเข้าสู่ระบบก่อนทำการแลกเหรียญ</p>
    </div>
  </div>


<div class="footer" data-i18n="footerText">
    © 2025 Arn-niyay-khan | พอร์ตนามปากกาหลากรส นักเขียนหลากแนว ✨
  </div>

  
  <div class="contact-admin-section">
    <button id="contactAdminBtn" data-i18n="contactAdminButton">ติดต่อแอดมิน</button>
    <p class="response-time-message" data-i18n="responseTimeMessage">จะติดต่อกลับภายใน 24 ชั่วโมงหรือเร็วที่สุด</p>
  </div>


  <div id="paymentModal" class="modal-overlay">
    <div class="modal-content">
      <h3 id="paymentTitle" data-i18n="paymentTitle"></h3>
      <p id="paymentInstructions" data-i18n="paymentInstructions"></p>
      
      <img id="qrCodeImage" src="placeholder_qr.png" alt="QR Code" style="width: 200px; height: 200px; border: 1px solid #eee; border-radius: 8px; margin-bottom: 20px;">
      <p style="font-size: 0.9rem; color: #888; margin-bottom: 20px;" data-i18n="qrDownloadPrompt"></p>

      <button id="downloadQrButton" class="btn-confirm" data-i18n="downloadQr">
        ⬇️ ดาวน์โหลด QR Code
      </button>
      
      <p id="internationalPaymentInfo" style="font-size: 1rem; color: #6e3cab; margin-top: 20px;" data-i18n="internationalPaymentInfo">สำหรับลูกค้าต่างชาติ: โปรดใช้ระบบ Gumroad เพื่อชำระเงิน</p>

      <button id="iPaidButton" class="btn-confirm" data-i18n="iPaidButton">
        ✅ ฉันสแกน/โอนแล้ว
      </button>
      <button onclick="cancelPaymentModal()" class="btn-cancel" data-i18n="cancel">ยกเลิก</button>
    </div>
  </div>

  <script>
    // URL ของ Google Apps Script Web App ที่ Deploy แล้ว
    // *** สำคัญ: ต้องเปลี่ยน URL นี้เป็นของคุณเองหลังจาก Deploy Google Apps Script ***
    const GAS_WEB_APP_URL = 'YOUR_DEPLOYED_WEB_APP_URL_HERE'; 

    // ***** สำคัญมาก: เปลี่ยนลิงก์เหล่านี้เป็นลิงก์ Gumroad จริงๆ ของสินค้าแต่ละตัวของคุณ *****
    const gumroadProductLinks = {
        // สำหรับราคา USD (ต่างชาติ) - Link to your Gumroad products selling coins in USD
        'usd_0_99': { link: 'https://yourname.gumroad.com/l/usd099coins', coins: 1000 },
        'usd_1_99': { link: 'https://yourname.gumroad.com/l/usd199coins', coins: 5000 },
        'usd_2_99': { link: 'https://yourname.gumroad.com/l/usd299coins', coins: 10000 },
        'usd_9_99': { link: 'https://yourname.gumroad.com/l/usd999coins', coins: 50000 },
        'usd_19_99': { link: 'https://yourname.gumroad.com/l/usd1999coins', coins: 100000 }
    };

    // URL ของรูปภาพ QR Code สำหรับคนไทย (คุณต้องอัปโหลดรูปเหล่านี้ไปที่โฮสติ้งของคุณเอง)
    // ตัวอย่าง: https://yourdomain.com/qrcodes/qr_50thb.png
    // *** สำคัญ: ต้องเปลี่ยน URL Placeholder เหล่านี้เป็น URL รูปภาพ QR Code จริงๆ ของคุณ ***
    const thaiQrCodeLinks = {
        5: 'https://via.placeholder.com/200?text=QR+5+THB',
        10: 'https://via.placeholder.com/200?text=QR+10+THB',
        20: 'https://via.placeholder.com/200?text=QR+20+THB',
        50: 'https://via.placeholder.com/200?text=QR+50+THB',
        100: 'https://via.placeholder.com/200?text=QR+100+THB',
        200: 'https://via.placeholder.com/200?text=QR+200+THB',
        500: 'https://via.placeholder.com/200?text=QR+500+THB',
        1000: 'https://via.placeholder.com/200?text=QR+1000+THB'
    };

    const EXCHANGE_RATE = 100; // 1 บาท = 100 เหรียญ
    const MAX_BUY_AMOUNT_THB = 1000; // ซื้อได้สูงสุด 1,000 บาท

    // ฟังก์ชันสำหรับจัดการเหรียญ (เก็บใน LocalStorage แต่ข้อมูลหลักอยู่ที่ GAS/Google Sheet)
    function getCoins() {
      return parseInt(localStorage.getItem("user_coins") || "0");
    }

    function setCoins(value) {
      localStorage.setItem("user_coins", value);
      updateCoinDisplay();
    }

    function updateCoinDisplay() {
      const coinEl = document.getElementById("coin-count");
      if (coinEl) coinEl.textContent = getCoins();
      
      const loggedInEmail = localStorage.getItem('user_email');
      const userEmailDisplay = document.getElementById('userEmailDisplay');
      const loginSection = document.getElementById('loginSection');
      const loggedInEmailSpan = document.getElementById('loggedInEmail');
      const redeemLoggedInMessage = document.getElementById('loggedInUserForRedeem');

      if (loggedInEmail) {
          userEmailDisplay.style.display = 'flex';
          loggedInEmailSpan.textContent = loggedInEmail;
          loginSection.style.display = 'none'; // ซ่อนส่วนล็อกอินถ้าล็อกอินแล้ว
          // แสดงส่วนเติมเหรียญและแลกรหัสเมื่อล็อกอินแล้ว
          document.querySelector('.buy-coin-section').style.display = 'block';
          document.querySelector('.interfan-coin-section').style.display = 'block';
          redeemLoggedInMessage.style.display = 'none'; // ซ่อนข้อความแจ้งให้ล็อกอินในส่วน redeem
      } else {
          userEmailDisplay.style.display = 'none';
          loginSection.style.display = 'block'; // แสดงส่วนล็อกอินถ้ายังไม่ล็อกอิน
          // ซ่อนส่วนเติมเหรียญและแลกรหัสถ้ายังไม่ล็อกอิน
          document.querySelector('.buy-coin-section').style.display = 'none';
          document.querySelector('.interfan-coin-section').style.display = 'none';
          redeemLoggedInMessage.style.display = 'block'; // แสดงข้อความแจ้งให้ล็อกอินในส่วน redeem
      }
    }

    // Object สำหรับคำแปล
    const translations = {
      th: {
        pageTitle: "รวมนามปากกา | Arn-niyay-khan",
        coinLabel: "💰 เหรียญของคุณ: ",
        languageLabel: "🌐 เปลี่ยนภาษา:",
        mainTitle: "🌟 รวมนามปากกาในเครือ Arn-niyay-khan 🌟",
        mainIntro: "ยินดีต้อนรับสู่โลกของ Arn-niyay-khan ที่รวบรวมหลากหลายนามปากกาและแนวเรื่องไม่ซ้ำใคร\n\nไม่ว่าคุณจะชื่นชอบเรื่องราวรักโรแมนติก ดราม่าเข้มข้น แฟนตาซีเหนือจริง หรืออีโรติกจัดจ้าน เรามีทุกรสชาติให้คุณได้ค้นหาและดื่มด่ำไปกับจินตนาการที่ไร้ขีดจำกัด",
        coderakTitle: "📘 โค้ดรัก",
        coderakDesc: "นิยายวายแนวโรแมนติก ดราม่า บีบหัวใจ 💔",
        coderakTag: "วายดราม่า",
        lippoTitle: "🔥 LIPPO",
        lippoDesc: "นิยายวายแนวอีโรติกจัดหนัก รักเร่าร้อน NC++ 🔥🛏",
        lippoTag: "วาย NC จัดเต็ม",
        welawadeeTitle: "🌙 เวฬาวดี",
        welawadeeDesc: "วาย omegaverse, ท้องได้, เหนือธรรมชาติ ✨🌌",
        welawadeeTag: "วายเหนือธรรมชาติ",
        wealthyTitle: "💄 WEALTHY",
        wealthyDesc: "นิยายชายหญิงอีโรติกเข้มข้น รักรสแซ่บ NC++ 🍷",
        wealthyTag: "อีโรติกผู้ใหญ่",
        bellwarinTitle: "🌼 เบลวรินท์",
        bellwarinDesc: "ชายหญิงรักสดใส ฟีลกู๊ด นุ่มนวลหัวใจ ☀️🧁",
        bellwarinTag: "ฟีลกู๊ดชายหญิง",
        nichchabenTitle: "🌈 ณิชชาเบญ",
        nichchabenDesc: "นิยายยูริ หญิงรักหญิง หลากหลายแนว 💕👭",
        nichchabenTag: "ยูริ",
        footerText: "© 2025 Arn-niyay-khan | พอร์ตนามปากกาหลากรส นักเขียนหลากแนว ✨",
        
        // Translations for Login (Magic Link)
        loginTitle: "เข้าสู่ระบบ / ลงทะเบียน (ไม่ใช้รหัสผ่าน)",
        loginInstruction: "กรอกอีเมลของคุณเพื่อรับ Magic Link สำหรับการเข้าสู่ระบบ",
        requestMagicLinkButton: "รับลิงก์เข้าสู่ระบบ", // New
        requestMagicLinkSuccess: "ส่งลิงก์เข้าสู่ระบบไปยัง {{email}} แล้วค่ะ กรุณาตรวจสอบกล่องจดหมายของคุณ (อาจอยู่ใน Spam/Junk)",
        requestMagicLinkError: "ไม่สามารถส่งลิงก์เข้าสู่ระบบได้ กรุณาลองใหม่อีกครั้ง หรือติดต่อแอดมิน",
        logoutConfirm: "คุณต้องการออกจากระบบใช่หรือไม่?",
        logoutSuccess: "ออกจากระบบแล้วค่ะ",

        // Translations for Thai Coin Purchase (QR Code Manual)
        buyCoinsTitle: "✨ เติมเหรียญเพื่ออ่านนิยาย ✨",
        thaiPaymentMethod: "💵 ชำระผ่าน QR Code PromptPay หรือ Mobile Banking",
        thaiExchangeRate: `⭐ 1 บาท = ${EXCHANGE_RATE} เหรียญ`,
        buyPrice5: "5 บาท (500 เหรียญ)",
        buyPrice10: "10 บาท (1,000 เหรียญ)",
        buyPrice20: "20 บาท (2,000 เหรียญ)",
        buyPrice50: "50 บาท (5,000 เหรียญ)",
        buyPrice100: "100 บาท (10,000 เหรียญ)",
        buyPrice200: "200 บาท (20,000 เหรียญ)",
        buyPrice500: "500 บาท (50,000 เหรียญ)",
        buyPrice1000: "1,000 บาท (100,000 เหรียญ)",
        customAmountLabel: "หรือระบุจำนวนเงินเอง:", 
        customAmountPlaceholder: "ใส่จำนวนเงิน (บาท)", 
        customBuyButton: "ซื้อเหรียญ", 
        coinPreviewText: "คุณจะได้รับ 0 เหรียญ", 
        paymentTitle: "ชำระเงินเพื่อซื้อ {{coins}} เหรียญ", // For QR Code modal
        paymentInstructions: "กรุณาสแกน QR Code เพื่อชำระเงิน {{price}} บาท\nหลังจากชำระเงินแล้ว กรุณาแคปเจอร์สลิปและติดต่อแอดมินเพื่อรับเหรียญ", // Instructions for QR Code manual
        qrDownloadPrompt: "กดปุ่มเพื่อดาวน์โหลด QR Code สำหรับการสแกนจ่าย",
        downloadQr: "⬇️ ดาวน์โหลด QR Code",
        internationalPaymentInfo: "สำหรับลูกค้าต่างชาติ: โปรดใช้ระบบ Gumroad เพื่อชำระเงิน", // Updated text
        iPaidButton: "✅ ฉันสแกน/โอนแล้ว",
        paymentConfirmationManual: "การชำระเงินของคุณเสร็จสมบูรณ์แล้ว! กรุณาติดต่อแอดมินพร้อมสลิปการโอนและอีเมล/ชื่อผู้ใช้ของคุณทันที เพื่อให้แอดมินทำการเติมเหรียญให้ค่ะ",
        
        // Translations for Interfan (Gumroad + Redeem Code)
        interfanBuyCoinsTitle: "✨ เติมเหรียญสำหรับแฟนต่างชาติ (Interfan) ✨",
        interfanPaymentMethod: "💵 ชำระผ่านบัตรเครดิตหรือ PayPal บน Gumroad",
        interfanExchangeRate: `⭐ 1 USD ≈ ${USD_TO_COINS_RATE} เหรียญ`,
        buyUSD1000Coins: "ซื้อ 1,000 เหรียญ - $0.99",
        buyUSD5000Coins: "ซื้อ 5,000 เหรียญ - $1.99",
        buyUSD10000Coins: "ซื้อ 10,000 เหรียญ - $2.99",
        buyUSD50000Coins: "ซื้อ 50,000 เหรียญ - $9.99",
        buyUSD100000Coins: "ซื้อ 100,000 เหรียญ - $19.99",
        redeemTitle: "✨ ใส่รหัสยืนยันที่ได้รับจาก Gumroad เพื่อรับเหรียญ ✨",
        redeemInstruction: "โปรดตรวจสอบอีเมลของคุณเพื่อหารหัสยืนยันหลังจากชำระเงินสำเร็จ",
        redeemCodePlaceholder: "กรอกรหัสที่นี่...",
        redeemButton: "ยืนยันรับเหรียญ",
        redeemMessageText: "กรุณากรอกรหัสก่อนค่ะ", 
        redeemSuccess: "✅ ยืนยันสำเร็จ! คุณได้รับ {{coins}} เหรียญ",
        redeemInvalid: "❌ รหัสไม่ถูกต้อง หรือใช้ไปแล้วค่ะ",
        alreadyRedeemed: "❌ รหัสนี้ถูกใช้ไปแล้วค่ะ",
        loadingText: "กำลังตรวจสอบรหัส...",
        loggedInUserForRedeem: "กรุณาเข้าสู่ระบบก่อนทำการแลกเหรียญ", // New translation

        // General & Admin Contact
        contactAdminButton: "ติดต่อแอดมิน",
        responseTimeMessage: "จะติดต่อกลับภายใน 24 ชั่วโมงหรือเร็วที่สุด",
        adminEmailSubject: "สอบถามข้อมูลจากเว็บไซต์",
        adminEmailBody: "สวัสดีครับ/ค่ะ,\n\nฉันต้องการสอบถามเกี่ยวกับ...",
        paymentFailedAlert: "เกิดข้อผิดพลาด กรุณาลองใหม่อีกครั้ง หรือติดต่อทีมงานค่ะ", 
        cancel: "ยกเลิก",
      },
      en: {
        pageTitle: "Pen Name Collection | Arn-niyay-khan",
        coinLabel: "💰 Your coins: ",
        languageLabel: "🌐 Language:",
        mainTitle: "🌟 Pen Name Collection by Arn-niyay-khan 🌟",
        mainIntro: "Welcome to the world of Arn-niyay-khan, where a diverse collection of pen names and unique genres awaits.\n\nWhether you love romantic, intense drama, surreal fantasy, or spicy erotica, we have every flavor for you to explore and immerse yourself in boundless imagination.",
        coderakTitle: "📘 Codrak",
        coderakDesc: "BL novels: romantic, dramatic, heartwarming 💔",
        coderakTag: "BL Drama",
        lippoTitle: "🔥 LIPPO",
        lippoDesc: "Heavy erotic BL novels, passionate love NC++ 🔥🛏",
        lippoTag: "BL Erotica",
        welawadeeTitle: "🌙 Welawadee",
        welawadeeDesc: "BL omegaverse, mpreg, supernatural ✨🌌",
        welawadeeTag: "BL Supernatural",
        wealthyTitle: "💄 WEALTHY",
        wealthyDesc: "Intense erotic M/F novels, spicy love NC++ 🍷",
        wealthyTag: "Adult Erotica",
        bellwarinTitle: "🌼 Bellwarin",
        bellwarinDesc: "Bright, feel-good M/F romance, soft-hearted ☀️🧁",
        bellwarinTag: "M/F Feel-Good",
        nichchabenTitle: "🌈 Nichchaben",
        nichchabenDesc: "Yuri novels: diverse F/F genres 💕👭",
        nichchabenTag: "Yuri",
        footerText: "© 2025 Arn-niyay-khan | Diverse Pen Names, Diverse Authors ✨",

        // Translations for Login (Magic Link)
        loginTitle: "Login / Register (No Password)",
        loginInstruction: "Enter your email to receive a Magic Link for login.",
        requestMagicLinkButton: "Get Login Link", // New
        requestMagicLinkSuccess: "Magic link sent to {{email}}. Please check your inbox (including Spam/Junk).",
        requestMagicLinkError: "Failed to send magic link. Please try again or contact admin.",
        logoutConfirm: "Are you sure you want to log out?",
        logoutSuccess: "Logged out successfully.",

        // Translations for Thai Coin Purchase (QR Code Manual)
        buyCoinsTitle: "✨ Top Up Coins to Read Novels ✨",
        thaiPaymentMethod: "💵 Pay via QR Code PromptPay or Mobile Banking",
        thaiExchangeRate: `⭐ 1 THB = ${EXCHANGE_RATE} Coins`,
        buyPrice5: "5 THB (500 Coins)",
        buyPrice10: "10 THB (1,000 Coins)",
        buyPrice20: "20 THB (2,000 Coins)",
        buyPrice50: "50 THB (5,000 Coins)",
        buyPrice100: "100 THB (10,000 Coins)",
        buyPrice200: "200 THB (20,000 Coins)",
        buyPrice500: "500 THB (50,000 Coins)",
        buyPrice1000: "1,000 THB (100,000 Coins)",
        customAmountLabel: "Or enter custom amount:",
        customAmountPlaceholder: "Enter amount (THB)",
        customBuyButton: "Buy Coins",
        coinPreviewText: "You will get 0 Coins",
        paymentTitle: "Pay for {{coins}} Coins",
        paymentInstructions: "Please scan the QR Code to pay {{price}} THB.\nAfter payment, please capture the slip and contact admin to receive coins.",
        qrDownloadPrompt: "Click the button to download the QR Code for scanning.",
        downloadQr: "⬇️ Download QR Code",
        internationalPaymentInfo: "For international customers: Please use Gumroad system for payment.", // Updated text
        iPaidButton: "✅ I have scanned/transferred",
        paymentConfirmationManual: "Your payment is complete! Please contact the admin with your transfer slip and email/username immediately for coin top-up.",

        // Translations for Interfan (Gumroad + Redeem Code)
        interfanBuyCoinsTitle: "✨ Top Up Coins for Interfans ✨",
        interfanPaymentMethod: "💵 Pay via Credit Card or PayPal on Gumroad",
        interfanExchangeRate: `⭐ 1 USD ≈ ${USD_TO_COINS_RATE} Coins`,
        buyUSD1000Coins: "Buy 1,000 Coins - $0.99",
        buyUSD5000Coins: "Buy 5,000 Coins - $1.99",
        buyUSD10000Coins: "Buy 10,000 Coins - $2.99",
        buyUSD50000Coins: "Buy 50,000 Coins - $9.99",
        buyUSD100000Coins: "Buy 100,000 Coins - $19.99",
        redeemTitle: "✨ Enter the confirmation code from Gumroad to receive coins ✨",
        redeemInstruction: "Please check your email for the confirmation code after successful payment.",
        redeemCodePlaceholder: "Enter code here...",
        redeemButton: "Confirm Redemption",
        redeemMessageText: "Please enter the code.",
        redeemSuccess: "✅ Redemption successful! You received {{coins}} coins",
        redeemInvalid: "❌ Invalid code or already used.",
        alreadyRedeemed: "❌ This code has already been used.",
        loadingText: "Checking code...",
        loggedInUserForRedeem: "Please log in before redeeming coins.",

        // General & Admin Contact
        contactAdminButton: "Contact Admin",
        responseTimeMessage: "Will reply within 24 hours or as soon as possible",
        adminEmailSubject: "Inquiry from Website",
        adminEmailBody: "Hello,\n\nI would like to inquire about...",
        paymentFailedAlert: "An error occurred. Please try again or contact support.",
        cancel: "Cancel",
      },
      // ... (ภาษาอื่นๆ ที่คุณมี) ...
    };
    
    // ฟังก์ชันสำหรับเปลี่ยนภาษา
    function switchLang(lang) {
      const langPack = translations[lang];
      if (!langPack) return;

      localStorage.setItem("lang", lang); // Save selected language

      document.querySelectorAll("[data-i18n]").forEach(el => {
        const key = el.getAttribute("data-i18n");
        if (langPack[key]) {
          if (key === "coinLabel") {
            el.innerHTML = langPack[key] + `<span id="coin-count">${getCoins()}</span>`;
          } else if (el.tagName === 'TITLE') {
            document.title = langPack[key];
          } else if (key.startsWith('buyPrice')) {
            el.textContent = langPack[key];
          } else if (key.startsWith('buyUSD')) {
            el.textContent = langPack[key];
          } else if (key === 'thaiExchangeRate') {
            el.textContent = langPack[key].replace(`${EXCHANGE_RATE}`, EXCHANGE_RATE);
          } else if (key === 'interfanExchangeRate') {
            el.textContent = langPack[key].replace(`${USD_TO_COINS_RATE}`, USD_TO_COINS_RATE);
          } else if (el.hasAttribute('data-i18n-placeholder')) {
            el.placeholder = langPack[key];
          } else if (key === 'paymentInstructions') {
            // For QR Code Modal, assuming it's the only one using this key with {{price}}
            const price = el.dataset.originalPrice || ''; // Fetch price from dataset if needed, or rely on update in showPaymentModal
            el.innerHTML = langPack[key].replace('{{price}}', price).replace(/\n/g, "<br>");
          }
          else {
            el.textContent = langPack[key];
          }
        }
      });

      // Update placeholder for customAmountInput (if still used)
      const customAmountInput = document.getElementById('customAmount');
      if (customAmountInput && langPack.customAmountPlaceholder) {
          customAmountInput.placeholder = langPack.customAmountPlaceholder;
      }
      
      // Update placeholder for redeemCode
      const redeemCodeInput = document.getElementById('redeemCode');
      if (redeemCodeInput && langPack.redeemCodePlaceholder) {
          redeemCodeInput.placeholder = langPack.redeemCodePlaceholder;
      }

      // Special handling for intro-text with paragraphs
      const introTextEl = document.getElementById("introText");
      if (introTextEl && langPack.mainIntro) {
          const content = langPack.mainIntro;
          const paragraphs = content.trim().split(/\n\s*\n|\n+/);
          introTextEl.innerHTML = paragraphs.map(p => `<p>${p.trim()}</p>`).join("");
      }

      // Update text for magicLinkMessage
      const magicLinkMessageEl = document.getElementById('magicLinkMessage');
      if (magicLinkMessageEl) {
        magicLinkMessageEl.textContent = ''; // Clear default message on language change
      }
      // Update text for redeemMessage
      const redeemMessageEl = document.getElementById('redeemMessage');
      if (redeemMessageEl) {
        redeemMessageEl.textContent = langPack.redeemMessageText;
      }

      updateCoinDisplay(); // Ensure coin display updates with new language
    }

    // --- Magic Link Functions ---
    async function requestMagicLink() {
        const emailInput = document.getElementById('userEmailLogin');
        const email = emailInput.value.toLowerCase().trim();
        const messageEl = document.getElementById('magicLinkMessage');
        const lang = localStorage.getItem("lang") || "th";

        if (!email || !email.includes('@')) {
            messageEl.style.color = 'red';
            messageEl.textContent = 'กรุณากรอกอีเมลที่ถูกต้องค่ะ';
            return;
        }

        messageEl.style.color = '#5e437f';
        messageEl.textContent = 'กำลังส่งลิงก์...';

        try {
            const response = await fetch(`${GAS_WEB_APP_URL}?action=requestMagicLink&email=${encodeURIComponent(email)}`, {
                method: 'POST', 
                headers: {
                    'Content-Type': 'application/x-www-form-urlencoded',
                },
            });
            const result = await response.json();

            if (result.status === 'success') {
                messageEl.style.color = 'green';
                messageEl.textContent = translations[lang].requestMagicLinkSuccess.replace('{{email}}', email);
            } else {
                messageEl.style.color = 'red';
                messageEl.textContent = `${translations[lang].requestMagicLinkError}: ${result.message || ''}`;
            }
        } catch (error) {
            console.error('Error requesting magic link:', error);
            messageEl.style.color = 'red';
            messageEl.textContent = translations[lang].requestMagicLinkError;
        }
    }

    function logout() {
        const lang = localStorage.getItem("lang") || "th";
        if (confirm(translations[lang].logoutConfirm)) {
            localStorage.removeItem('user_email');
            localStorage.removeItem('user_coins');
            // redeemed_codes ควรจะยังคงอยู่ เพื่อป้องกันการใช้รหัสซ้ำ ถึงแม้จะ logout แล้ว
            updateCoinDisplay(); // Update UI to show login section
            alert(translations[lang].logoutSuccess);
        }
    }

    // Listen for messages from the Magic Link redirect page
    window.addEventListener('message', (event) => {
        // Ensure the message is from a trusted origin (your own domain or GAS domain)
        if (event.data && event.data.type === 'LOGIN_SUCCESS') {
            localStorage.setItem('user_email', event.data.email);
            localStorage.setItem('user_coins', event.data.coinBalance);
            updateCoinDisplay();
        }
    });

    // --- Thai Coin Purchase (QR Code Manual) Function ---
    function showPaymentModal(priceInBaht, coinsAmount) {
        const lang = localStorage.getItem("lang") || "th";
        const paymentModal = document.getElementById("paymentModal");
        const paymentTitleEl = document.getElementById("paymentTitle");
        const paymentInstructionsEl = document.getElementById("paymentInstructions");
        const qrCodeImageEl = document.getElementById("qrCodeImage");
        const downloadQrButton = document.getElementById("downloadQrButton");
        const iPaidButton = document.getElementById("iPaidButton");

        const qrImageUrl = thaiQrCodeLinks[priceInBaht];
        if (!qrImageUrl || qrImageUrl.includes('placeholder.com')) {
            alert(translations[lang].paymentFailedAlert + ": กรุณาตั้งค่าลิงก์ QR Code สำหรับยอด " + priceInBaht + " บาทในโค้ด JavaScript ก่อนใช้งาน");
            return;
        }

        paymentTitleEl.textContent = translations[lang].paymentTitle.replace('{{coins}}', coinsAmount);
        paymentInstructionsEl.innerHTML = translations[lang].paymentInstructions
            .replace('{{price}}', priceInBaht)
            .replace(/\n/g, "<br>");

        document.getElementById('internationalPaymentInfo').style.display = 'none'; // Hide this text for Thai QR code payment

        qrCodeImageEl.src = qrImageUrl;
        qrCodeImageEl.alt = `QR Code for ${priceInBaht} THB`;

        downloadQrButton.style.display = 'inline-block';
        downloadQrButton.onclick = () => {
            const a = document.createElement('a');
            a.href = qrCodeImageEl.src;
            a.download = `QR_Code_${priceInBaht}THB_${coinsAmount}Coins.png`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
        };
        
        iPaidButton.onclick = () => {
            const contactMessage = translations[lang].paymentConfirmationManual;
            alert(contactMessage);
            const adminContactLink = "https://line.me/ti/p/@your_line_id"; // *** เปลี่ยนเป็น LINE ID ของคุณ ***
            window.open(adminContactLink, '_blank');
            cancelPaymentModal(); 
        };

        paymentModal.style.display = "block";
    }

    function cancelPaymentModal() {
        document.getElementById("paymentModal").style.display = "none";
        // Reset modal state if needed
        document.getElementById('internationalPaymentInfo').style.display = 'block'; // Show it again for next use
    }

    // --- Redeem Code (Gumroad) Function ---
    async function redeemCode() {
        const codeInput = document.getElementById("redeemCode");
        const code = codeInput.value.trim();
        const messageEl = document.getElementById("redeemMessage");
        const lang = localStorage.getItem("lang") || "th";
        const userEmail = localStorage.getItem('user_email');

        if (!userEmail) {
            messageEl.style.color = 'red';
            messageEl.textContent = translations[lang].loggedInUserForRedeem;
            return;
        }

        messageEl.style.color = '#5e437f';
        messageEl.textContent = translations[lang].loadingText;

        if (!code) {
            messageEl.style.color = 'red';
            messageEl.textContent = translations[lang].redeemMessageText;
            return;
        }
        
        try {
            const response = await fetch(`${GAS_WEB_APP_URL}?action=redeemCode`, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/x-www-form-urlencoded',
                },
                body: new URLSearchParams({ 
                    code: code,
                    email: userEmail 
                }),
            });

            const result = await response.json();

            if (result.status === 'success') {
                const coinsToAdd = result.coins;
                setCoins(getCoins() + coinsToAdd); 
                messageEl.style.color = 'green';
                messageEl.textContent = translations[lang].redeemSuccess.replace('{{coins}}', coinsToAdd);
                codeInput.value = ''; // Clear code input
            } else {
                messageEl.style.color = 'red';
                if (result.message === 'already_redeemed') {
                    messageEl.textContent = translations[lang].alreadyRedeemed;
                } else if (result.message === 'invalid_code') {
                    messageEl.textContent = translations[lang].redeemInvalid;
                } else {
                    messageEl.textContent = translations[lang].paymentFailedAlert;
                }
            }
        } catch (error) {
            console.error("Error redeeming code:", error);
            messageEl.style.color = 'red';
            messageEl.textContent = translations[lang].paymentFailedAlert;
        }
    }


    // เมื่อ DOM โหลดเสร็จ
    document.addEventListener("DOMContentLoaded", function () {
      // Set initial user_coins and display based on login status
      updateCoinDisplay(); // This will check localStorage and show/hide login/coin sections

      const savedLang = localStorage.getItem("lang") || "th";
      switchLang(savedLang); // Apply the saved language on load

      // Event Listener สำหรับปุ่มขอ Magic Link
      document.getElementById('requestMagicLinkBtn').addEventListener('click', requestMagicLink);
      // Event Listener สำหรับปุ่ม Logout
      document.getElementById('logoutButton').addEventListener('click', logout);
      // Event Listener สำหรับปุ่ม Redeem (Gumroad)
      document.getElementById('redeemButton').addEventListener('click', redeemCode);

      // --- Buy Coin Buttons (Thai - QR Code Manual) ---
      document.querySelectorAll(".buy-coin-button").forEach(button => {
        button.addEventListener("click", () => {
          const price = parseInt(button.dataset.price);
          const coins = parseInt(button.dataset.coins);
          const userEmail = localStorage.getItem('user_email');
          if (!userEmail) { // Check if user is logged in
            alert(translations[localStorage.getItem("lang") || "th"].loggedInUserForRedeem);
            return;
          }
          showPaymentModal(price, coins); // Call the QR Code payment modal
        });
      });

      // --- Interfan Buy Buttons (Gumroad) ---
      document.querySelectorAll(".interfan-buy-btn").forEach(button => {
        button.addEventListener("click", () => {
          const productKey = button.dataset.productKey;
          const productInfo = gumroadProductLinks[productKey];
          const userEmail = localStorage.getItem('user_email');

          if (!userEmail) { // Check if user is logged in
            alert(translations[localStorage.getItem("lang") || "th"].loggedInUserForRedeem);
            return;
          }

          if (productInfo && productInfo.link) {
            window.open(productInfo.link, '_blank'); // Open Gumroad link in a new tab
            const lang = localStorage.getItem("lang") || "th";
            alert(translations[lang].redeemInstruction); // Guide user to use the code
          } else {
            alert(translations[localStorage.getItem("lang") || "th"].paymentFailedAlert + ": Missing Gumroad product link.");
          }
        });
      });

      // --- Custom Amount (Optional) ---
      // Hiding the button as it requires specific Gumroad product setup or manual process
      // If you decide to support custom amounts, you'll need a way to generate dynamic QR codes or Gumroad products.
      const btnCustomBuy = document.getElementById('btnCustomBuy');
      if (btnCustomBuy) btnCustomBuy.style.display = 'none';

      const customAmountInput = document.getElementById('customAmount');
      const coinPreview = document.getElementById('coinPreview');
      if (customAmountInput && coinPreview) {
          customAmountInput.addEventListener('input', function() {
              let amountInBaht = parseInt(this.value);
              if (isNaN(amountInBaht) || amountInBaht < 1) {
                  amountInBaht = 0;
              }
              if (amountInBaht > MAX_BUY_AMOUNT_THB) {
                  amountInBaht = MAX_BUY_AMOUNT_THB;
                  this.value = MAX_BUY_AMOUNT_THB;
              }
              const coins = amountInBaht * EXCHANGE_RATE;
              const lang = localStorage.getItem("lang") || "th";
              const langPack = translations[lang];
              coinPreview.textContent = langPack.coinPreviewText.replace('0', coins);
          });
          // Initial update for preview
          const initialAmount = parseInt(customAmountInput.value) || 0;
          coinPreview.textContent = translations[savedLang].coinPreviewText.replace('0', initialAmount * EXCHANGE_RATE);
      }

      // Event Listener สำหรับปุ่มติดต่อแอดมิน
      document.getElementById('contactAdminBtn').addEventListener('click', function() {
          const lang = localStorage.getItem("lang") || "th";
          const adminEmail = 'cherry.writer62@gmail.com';
          const subject = translations[lang].adminEmailSubject;
          const body = translations[lang].adminEmailBody;

          const mailtoLink = `mailto:${adminEmail}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
          window.location.href = mailtoLink;
      });
    });
  </script>
</body>
</html>
