<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
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

    /* === Header Controls (เหมือนหน้านามปากกา) === */
    .header-controls {
      display: flex;
      justify-content: flex-end; /* จัดให้ชิดขวา */
      align-items: center;
      margin-bottom: 30px; /* ลด margin-bottom จากเดิม 30px ให้เป็น 20px */
      flex-wrap: wrap;
      gap: 15px;
    }

    /* ลบ .site-button ออกจาก header controls */
    /* .site-button ที่เป็นลิงก์ไปยังหน้าหลักจะไม่ถูกแสดงใน header อีกต่อไป */

    .user-info { /* สำหรับรวม coin และ language */
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
    
    h1 { /* ชื่อหัวข้อหลักของหน้าแรก */
      color: #7b4ca0;
      font-size: 2.2rem;
      margin-top: 20px; /* เพิ่ม margin-top เพื่อให้มีช่องว่างจาก header */
      margin-bottom: 10px;
      animation: pulse 3s ease-in-out infinite;
    }

    .intro-text { /* ข้อความอธิบายใต้นามปากกา */
      color: #5e437f;
      font-size: 1.1rem;
      margin-bottom: 40px;
      line-height: 1.6;
      max-width: 700px;
      margin-left: auto;
      margin-right: auto;
      white-space: pre-wrap; /* เพื่อให้รองรับ \n ใน data-i18n และสร้างย่อหน้า */
      text-align: justify; /* จัด justify เหมือนเนื้อนิยาย */
    }
    .intro-text p { /* สำหรับย่อหน้าแรกอัตโนมัติ */
        text-indent: 2.5em; /* เยื้องบรรทัดแรก */
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
      font-size: 1.5rem; /* ขนาดชื่อนามปากกาในรายการ */
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

    .desc { /* คำโปรยของแต่ละนามปากกา */
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
      font-size: 1.25rem; /* ขนาดเท่าหน้านามปากกา */
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

    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.03); }
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-6px); }
    }

    /* Media query สำหรับหน้าจอขนาดเล็ก (เหมือนหน้านามปากกา) */
    @media screen and (max-width: 600px) {
      .header-controls {
        flex-direction: column;
        align-items: flex-start;
      }
      .user-info {
        width: 100%;
        justify-content: flex-start;
      }
      .site-button { /* หากนำ site-button กลับมาใช้ */
        width: 100%;
        box-sizing: border-box;
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
    }
  </style>
</head>
<body>

  <div class="header-controls">
    <div class="user-info">
      <div class="coin-display" data-i18n="coinLabel">
        💰 เหรียญของคุณ: <span id="coin-count">0</span> เหรียญ
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
    data-content-kr="Arn-niyay-khan의 세계에 오신 것을 환영합니다. 이곳에서는 다양한 필명과 독특한 장르의 컬렉션이 여러분을 기다립니다.
    
    로맨틱하고 강렬한 드라마, 초현실적인 판타지, 또는 매운 에로티카를 좋아하든, 우리는 여러분이 탐험하고 무한한 상상력에 몰입할 수 있는 모든 취향을 제공합니다."
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

  <div class="footer" data-i18n="footerText">
    © 2025 Arn-niyay-khan | พอร์ตนามปากกาหลากรส นักเขียนหลากแนว ✨
  </div>

  <div style="margin-top: 60px; text-align: center;">
    <h2 style="color: #7b4ca0; font-size: 1.8rem; margin-bottom: 25px;" data-i18n="buyCoinsTitle">✨ เติมเหรียญเพื่ออ่านนิยาย ✨</h2>
    <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px; max-width: 600px; margin: 0 auto 40px auto;">
      <button class="buy-coin-button" data-coins="10" data-price="5" data-i18n="buyCoin10">10 เหรียญ (5 บาท)</button>
      <button class="buy-coin-button" data-coins="20" data-price="10" data-i18n="buyCoin20">20 เหรียญ (10 บาท)</button>
      <button class="buy-coin-button" data-coins="30" data-price="15" data-i18n="buyCoin30">30 เหรียญ (15 บาท)</button>
      <button class="buy-coin-button" data-coins="40" data-price="20" data-i18n="buyCoin40">40 เหรียญ (20 บาท)</button>
      <button class="buy-coin-button" data-coins="50" data-price="25" data-i18n="buyCoin50">50 เหรียญ (25 บาท)</button>
      <button class="buy-coin-button" data-coins="60" data-price="30" data-i18n="buyCoin60">60 เหรียญ (30 บาท)</button>
      <button class="buy-coin-button" data-coins="70" data-price="35" data-i18n="buyCoin70">70 เหรียญ (35 บาท)</button>
      <button class="buy-coin-button" data-coins="80" data-price="40" data-i18n="buyCoin80">80 เหรียญ (40 บาท)</button>
      <button class="buy-coin-button" data-coins="90" data-price="45" data-i18n="buyCoin90">90 เหรียญ (45 บาท)</button>
      <button class="buy-coin-button" data-coins="100" data-price="50" data-i18n="buyCoin100">100 เหรียญ (50 บาท)</button>
    </div>
    <p style="font-size: 1rem; color: #5e437f;" data-i18n="exchangeRate">อัตรา: 1 บาท = 2 เหรียญ</p>
  </div>


  <div id="paymentModal" style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background-color:rgba(0,0,0,0.4); z-index:9999;">
    <div style="background:#fff; max-width:500px; margin:5% auto; padding:30px; border-radius:12px; text-align:center; box-shadow:0 4px 12px rgba(0,0,0,0.2); font-family:'Mitr', sans-serif;">
      <h3 style="color:#6e3cab; margin-bottom: 20px;" data-i18n="paymentTitle"></h3>
      <p style="font-size:1.1rem; color:#5e437f; margin-bottom:15px;" data-i18n="paymentInstructions"></p>
      
      <div id="countdown" style="font-size: 1.2rem; font-weight: bold; color: #d9534f; margin-bottom: 20px;"></div>
      
      <img id="qrCodeImage" src="placeholder_qr.png" alt="QR Code" style="width: 200px; height: 200px; border: 1px solid #eee; border-radius: 8px; margin-bottom: 20px;">
      <p style="font-size: 0.9rem; color: #888; margin-bottom: 20px;" data-i18n="qrDownloadPrompt"></p>

      <button id="downloadQrButton" style="padding: 10px 20px; background-color: #5cb85c; color: white; border: none; border-radius: 30px; font-weight: bold; cursor: pointer; margin-bottom: 15px;" data-i18n="downloadQr">
        ⬇️ ดาวน์โหลด QR Code
      </button>
      
      <p style="font-size: 1rem; color: #6e3cab;" data-i18n="internationalPaymentInfo">สำหรับลูกค้าต่างชาติ: ติดต่อสอบถามช่องทางชำระเงินที่สะดวก</p>

      <button onclick="showPaymentForm()" style="padding: 10px 20px; background-color: #0275d8; color: white; border: none; border-radius: 30px; font-weight: bold; cursor: pointer; margin-top: 20px;" data-i18n="iPaidButton">
        ✅ ฉันสแกน/โอนแล้ว
      </button>
      <button onclick="cancelPayment()" style="margin-left:10px; padding:10px 20px; border:none; border-radius:30px; background:#ccc; color:#333; font-weight:bold;" data-i18n="cancel">ยกเลิก</button>
    </div>
  </div>

  <div id="paymentFormModal" style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background-color:rgba(0,0,0,0.4); z-index:9999;">
    <div style="background:#fff; max-width:500px; margin:5% auto; padding:30px; border-radius:12px; text-align:left; box-shadow:0 4px 12px rgba(0,0,0,0.2); font-family:'Mitr', sans-serif;">
      <h3 style="color:#6e3cab; text-align:center; margin-bottom: 20px;" data-i18n="confirmPaymentFormTitle">แจ้งโอนเหรียญ</h3>
      <form id="submitPaymentForm" onsubmit="submitPaymentData(event)">
        <div style="margin-bottom: 15px;">
          <label for="transferName" style="display: block; margin-bottom: 5px; color:#5e437f;" data-i18n="transferNameLabel">ชื่อผู้โอน:</label>
          <input type="text" id="transferName" name="transferName" required style="width: calc(100% - 22px); padding: 10px; border: 1px solid #ccc; border-radius: 8px; font-family: 'Mitr', sans-serif;">
        </div>
        <div style="margin-bottom: 15px;">
          <label for="transferDateTime" style="display: block; margin-bottom: 5px; color:#5e437f;" data-i18n="transferDateTimeLabel">วัน-เวลาที่โอน:</label>
          <input type="datetime-local" id="transferDateTime" name="transferDateTime" required style="width: calc(100% - 22px); padding: 10px; border: 1px solid #ccc; border-radius: 8px; font-family: 'Mitr', sans-serif;">
        </div>
        <div style="margin-bottom: 20px;">
          <label for="transferSlip" style="display: block; margin-bottom: 5px; color:#5e437f;" data-i18n="transferSlipLabel">แนบสลิป/หลักฐานการโอน:</label>
          <input type="file" id="transferSlip" name="transferSlip" accept="image/*,.pdf" style="width: 100%;" required>
        </div>
        <div style="text-align: center; margin-top: 20px;">
          <button type="submit" style="padding: 10px 20px; background-color: #a87ce6; color: white; border: none; border-radius: 30px; font-weight: bold; cursor: pointer;" data-i18n="submitPaymentButton">ส่งข้อมูล</button>
          <button type="button" onclick="cancelPaymentForm()" style="margin-left:10px; padding:10px 20px; border:none; border-radius:30px; background:#ccc; color:#333; font-weight:bold;" data-i18n="cancel">ยกเลิก</button>
        </div>
      </form>
    </div>
  </div>


  <script>
    let pendingCoinsToBuy = 0;
    let pendingPriceToPay = 0;
    let countdownInterval;
    const PAYMENT_TIMEOUT_SECONDS = 60; // 1 นาที

    // URL ของ Google Apps Script Web App (เมื่อคุณ Deploy แล้ว)
    // *** สำคัญ: ต้องเปลี่ยน URL นี้เป็นของคุณเองหลังจาก Deploy Google Apps Script ***
    const GOOGLE_APPS_SCRIPT_URL = 'YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL_HERE'; 

    // ฟังก์ชันสำหรับจัดการเหรียญ
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
    }

    // Object สำหรับคำแปล
    const translations = {
      th: {
        pageTitle: "รวมนามปากกา | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
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
        buyCoinsTitle: "✨ เติมเหรียญเพื่ออ่านนิยาย ✨",
        buyCoin10: "10 เหรียญ (5 บาท)",
        buyCoin20: "20 เหรียญ (10 บาท)",
        buyCoin30: "30 เหรียญ (15 บาท)",
        buyCoin40: "40 เหรียญ (20 บาท)",
        buyCoin50: "50 เหรียญ (25 บาท)",
        buyCoin60: "60 เหรียญ (30 บาท)",
        buyCoin70: "70 เหรียญ (35 บาท)",
        buyCoin80: "80 เหรียญ (40 บาท)",
        buyCoin90: "90 เหรียญ (45 บาท)",
        buyCoin100: "100 เหรียญ (50 บาท)",
        exchangeRate: "อัตรา: 1 บาท = 2 เหรียญ",
        paymentTitle: "ชำระเงินเพื่อซื้อ {{coins}} เหรียญ",
        paymentInstructions: "กรุณาสแกน QR Code หรือโอนเงินจำนวน {{price}} บาท ภายใน 1 นาที",
        qrDownloadPrompt: "กดปุ่มเพื่อดาวน์โหลด QR Code สำหรับการสแกนจ่าย",
        downloadQr: "⬇️ ดาวน์โหลด QR Code",
        internationalPaymentInfo: "สำหรับลูกค้าต่างชาติ: ติดต่อสอบถามช่องทางชำระเงินที่สะดวก",
        iPaidButton: "✅ ฉันสแกน/โอนแล้ว",
        confirmPaymentFormTitle: "แจ้งโอนเหรียญ",
        transferNameLabel: "ชื่อผู้โอน:",
        transferDateTimeLabel: "วัน-เวลาที่โอน:",
        transferSlipLabel: "แนบสลิป/หลักฐานการโอน:",
        submitPaymentButton: "ส่งข้อมูล",
        cancel: "ยกเลิก",
        paymentSuccessAlert: "การแจ้งโอนของคุณถูกส่งแล้วค่ะ! กรุณารอทีมงานตรวจสอบสักครู่ แล้วเหรียญจะถูกเพิ่มให้โดยเร็วค่ะ",
        paymentFailedAlert: "เกิดข้อผิดพลาดในการส่งข้อมูลการโอนเงิน กรุณาลองใหม่อีกครั้ง หรือติดต่อทีมงานค่ะ"
      },
      en: {
        pageTitle: "Pen Name Collection | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
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
        buyCoinsTitle: "✨ Top Up Coins to Read Novels ✨",
        buyCoin10: "10 Coins (5 THB)",
        buyCoin20: "20 Coins (10 THB)",
        buyCoin30: "30 Coins (15 THB)",
        buyCoin40: "40 Coins (20 THB)",
        buyCoin50: "50 Coins (25 THB)",
        buyCoin60: "60 Coins (30 THB)",
        buyCoin70: "70 Coins (35 THB)",
        buyCoin80: "80 Coins (40 THB)",
        buyCoin90: "90 Coins (45 THB)",
        buyCoin100: "100 Coins (50 THB)",
        exchangeRate: "Rate: 1 THB = 2 Coins",
        paymentTitle: "Pay for {{coins}} Coins",
        paymentInstructions: "Please scan the QR Code or transfer {{price}} THB within 1 minute.",
        qrDownloadPrompt: "Click the button to download the QR Code for scanning.",
        downloadQr: "⬇️ Download QR Code",
        internationalPaymentInfo: "For international customers: Please contact us for convenient payment methods.",
        iPaidButton: "✅ I have scanned/transferred",
        confirmPaymentFormTitle: "Notify Transfer",
        transferNameLabel: "Transfer Name:",
        transferDateTimeLabel: "Date-Time of Transfer:",
        transferSlipLabel: "Attach Slip/Proof of Transfer:",
        submitPaymentButton: "Submit Data",
        cancel: "Cancel",
        paymentSuccessAlert: "Your transfer notification has been sent! Please wait for our team to verify, and coins will be added shortly.",
        paymentFailedAlert: "An error occurred while sending transfer data. Please try again or contact support."
      },
      ch: {
        pageTitle: "笔名合集 | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 您的金币：",
        languageLabel: "🌐 语言切换：",
        mainTitle: "🌟 Arn-niyay-khan 笔名合集 🌟",
        mainIntro: "欢迎来到 Arn-niyay-khan 的世界，这里汇集了各种独特的笔名和风格迥异的故事。\n\n无论您喜欢浪漫、扣人心弦的戏剧、超现实的奇幻，还是火辣的色情文学，我们都能满足您的所有品味，让您沉浸在无限的想象中。",
        coderakTitle: "📘 โค้ดรัก (Codrak)",
        coderakDesc: "耽美小说：浪漫、狗血、揪心💔",
        coderakTag: "耽美戏剧",
        lippoTitle: "🔥 LIPPO",
        lippoDesc: "重口味耽美情色小说，炽热的爱 NC++ 🔥🛏",
        lippoTag: "耽美情色",
        welawadeeTitle: "🌙 เวฬาวดี (Welawadee)",
        welawadeeDesc: "耽美 omegaverse，可怀孕，超自然 ✨🌌",
        welawadeeTag: "耽美超自然",
        wealthyTitle: "💄 WEALTHY",
        wealthyDesc: "浓烈情色男女小说，火辣的爱 NC++ 🍷",
        wealthyTag: "成人情色",
        bellwarinTitle: "🌼 เบลวรินท์ (Bellwarin)",
        bellwarinDesc: "男女清新浪漫小说，治愈系暖心 ☀️🧁",
        bellwarinTag: "男女治愈系",
        nichchabenTitle: "🌈 ณิชชาเบญ (Nichchaben)",
        nichchabenDesc: "百合小说：多样女性向题材 💕👭",
        nichchabenTag: "百合",
        footerText: "© 2025 Arn-niyay-khan | 多样笔名，多样作者 ✨",
        buyCoinsTitle: "✨ 充值金币阅读小说 ✨",
        buyCoin10: "10 金币 (5 泰铢)",
        buyCoin20: "20 金币 (10 泰铢)",
        buyCoin30: "30 金币 (15 泰铢)",
        buyCoin40: "40 金币 (20 泰铢)",
        buyCoin50: "50 金币 (25 泰铢)",
        buyCoin60: "60 金币 (30 泰铢)",
        buyCoin70: "70 金币 (35 泰铢)",
        buyCoin80: "80 金币 (40 泰铢)",
        buyCoin90: "90 金币 (45 泰铢)",
        buyCoin100: "100 金币 (50 泰铢)",
        exchangeRate: "汇率：1 泰铢 = 2 金币",
        paymentTitle: "支付购买 {{coins}} 金币",
        paymentInstructions: "请在 1 分钟内扫描二维码或转账 {{price}} 泰铢。",
        qrDownloadPrompt: "点击按钮下载二维码进行扫描。",
        downloadQr: "⬇️ 下载二维码",
        internationalPaymentInfo: "国际客户：请联系我们获取便捷的支付方式。",
        iPaidButton: "✅ 我已扫描/转账",
        confirmPaymentFormTitle: "转账通知",
        transferNameLabel: "转账人姓名：",
        transferDateTimeLabel: "转账日期时间：",
        transferSlipLabel: "附上转账凭证：",
        submitPaymentButton: "提交数据",
        cancel: "取消",
        paymentSuccessAlert: "您的转账通知已发送！请等待我们团队验证，金币将尽快添加。",
        paymentFailedAlert: "发送转账数据时发生错误。请重试或联系客服。"
      },
      ru: {
        pageTitle: "Коллекция псевдонимов | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 Ваши монеты:",
        languageLabel: "🌐 Выбрать язык:",
        mainTitle: "🌟 Коллекция псевдонимов Arn-niyay-khan 🌟",
        mainIntro: "Добро пожаловать в мир Arn-niyay-khan, где собрана разнообразная коллекция псевдонимов и уникальных жанров.\n\nЛюбите ли вы романтику, напряженную драму, сюрреалистическое фэнтези или пикантную эротику, у нас есть всё, чтобы вы могли исследовать и погрузиться в безграничное воображение.",
        coderakTitle: "📘 Кодрак",
        coderakDesc: "BL романы: романтические, драматические, душераздирающие 💔",
        coderakTag: "BL Драма",
        lippoTitle: "🔥 ЛИППО",
        lippoDesc: "Жаркие эротические BL романы, страстная любовь NC++ 🔥🛏",
        lippoTag: "BL Эротика",
        welawadeeTitle: "🌙 Велавади",
        welawadeeDesc: "BL омегаверс, беременность, сверхъестественное ✨🌌",
        welawadeeTag: "BL Сверхъестественное",
        wealthyTitle: "💄 БОГАТЫЙ",
        wealthyDesc: "Интенсивные эротические романы М/Ж, горячая любовь NC++ 🍷",
        wealthyTag: "Взрослая Эротика",
        bellwarinTitle: "🌼 Беллаварин",
        bellwarinDesc: "Яркие, приятные романы М/Ж, нежные и сердечные ☀️🧁",
        bellwarinTag: "М/Ж Приятный",
        nichchabenTitle: "🌈 Ниччабен",
        nichchabenDesc: "Юри романы: разнообразные Ж/Ж жанры 💕👭",
        nichchabenTag: "Юри",
        footerText: "© 2025 Arn-niyay-khan | Разнообразные псевдонимы, разнообразные авторы ✨",
        buyCoinsTitle: "✨ Пополнить монеты для чтения романов ✨",
        buyCoin10: "10 Монет (5 бат)",
        buyCoin20: "20 Монет (10 бат)",
        buyCoin30: "30 Монет (15 бат)",
        buyCoin40: "40 Монет (20 бат)",
        buyCoin50: "50 Монет (25 бат)",
        buyCoin60: "60 Монет (30 бат)",
        buyCoin70: "70 Монет (35 бат)",
        buyCoin80: "80 Монет (40 бат)",
        buyCoin90: "90 Монет (45 бат)",
        buyCoin100: "100 Монет (50 бат)",
        exchangeRate: "Курс: 1 бат = 2 монеты",
        paymentTitle: "Оплатите {{coins}} монет",
        paymentInstructions: "Пожалуйста, отсканируйте QR-код или переведите {{price}} бат в течение 1 минуты.",
        qrDownloadPrompt: "Нажмите кнопку, чтобы скачать QR-код для сканирования.",
        downloadQr: "⬇️ Скачать QR-код",
        internationalPaymentInfo: "Для международных клиентов: пожалуйста, свяжитесь с нами для удобных способов оплаты.",
        iPaidButton: "✅ Я отсканировал/перевел",
        confirmPaymentFormTitle: "Уведомление о переводе",
        transferNameLabel: "Имя отправителя:",
        transferDateTimeLabel: "Дата-время перевода:",
        transferSlipLabel: "Прикрепите квитанцию/подтверждение перевода:",
        submitPaymentButton: "Отправить данные",
        cancel: "Отмена",
        paymentSuccessAlert: "Ваше уведомление о переводе отправлено! Пожалуйста, подождите, пока наша команда проверит, и монеты будут добавлены в ближайшее время.",
        paymentFailedAlert: "Произошла ошибка при отправке данных перевода. Пожалуйста, попробуйте еще раз или свяжитесь со службой поддержки."
      },
      jp: {
        pageTitle: "ペンネームコレクション | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 あなたのコイン：",
        languageLabel: "🌐 言語を選択：",
        mainTitle: "🌟 Arn-niyay-khan ペンネームコレクション 🌟",
        mainIntro: "Arn-niyay-khan の世界へようこそ。ここでは、多様なペンネームとユニークなジャンルのコレクションがあなたを待っています。\n\nロマンチックな物語、激しいドラマ、超現実的なファンタジー、またはスパイシーなエロチカがお好みでも、私たちはあらゆる好みを提供し、無限の想像力に浸ることができます。",
        coderakTitle: "📘 コードラック",
        coderakDesc: "BL小説：ロマンチック、ドラマチック、胸が締め付けられるような物語 💔",
        coderakTag: "BLドラマ",
        lippoTitle: "🔥 リッポ",
        lippoDesc: "濃厚エロティックBL小説、情熱的な愛 NC++ 🔥🛏",
        lippoTag: "BLエロティカ",
        welawadeeTitle: "🌙 ウェラワディー",
        welawadeeDesc: "BLオメガバース、妊娠、超自然 ✨🌌",
        welawadeeTag: "BL超自然",
        wealthyTitle: "💄 ウェルシー",
        wealthyDesc: "濃厚エロティック男女小説、スパイシーな愛 NC++ 🍷",
        wealthyTag: "成人向けエロティカ",
        bellwarinTitle: "🌼 ベラリン",
        bellwarinDesc: "明るく心温まる男女ロマンス、優しい気持ち ☀️🧁",
        bellwarinTag: "男女心温まる",
        nichchabenTitle: "🌈 ニチャベン",
        nichchabenDesc: "百合小説：多様なF/Fジャンル 💕👭",
        nichchabenTag: "百合",
        footerText: "© 2025 Arn-niyay-khan | 多様なペンネーム、多様な作家 ✨",
        buyCoinsTitle: "✨ 小説を読むためのコインをチャージ ✨",
        buyCoin10: "10 コイン (5 バーツ)",
        buyCoin20: "20 コイン (10 バーツ)",
        buyCoin30: "30 コイン (15 バーツ)",
        buyCoin40: "40 コイン (20 バーツ)",
        buyCoin50: "50 コイン (25 バーツ)",
        buyCoin60: "60 コイン (30 バーツ)",
        buyCoin70: "70 コイン (35 バーツ)",
        buyCoin80: "80 コイン (40 バーツ)",
        buyCoin90: "90 コイン (45 バーツ)",
        buyCoin100: "100 コイン (50 バーツ)",
        exchangeRate: "レート：1 バーツ = 2 コイン",
        paymentTitle: "{{coins}} コインの支払い",
        paymentInstructions: "1分以内にQRコードをスキャンするか、{{price}} バーツを送金してください。",
        qrDownloadPrompt: "ボタンをクリックしてQRコードをダウンロードし、スキャンしてください。",
        downloadQr: "⬇️ QRコードをダウンロード",
        internationalPaymentInfo: "海外のお客様：お支払い方法についてはお問い合わせください。",
        iPaidButton: "✅ スキャン/送金しました",
        confirmPaymentFormTitle: "送金通知",
        transferNameLabel: "送金者名：",
        transferDateTimeLabel: "送金日時：",
        transferSlipLabel: "送金証拠を添付：",
        submitPaymentButton: "データを送信",
        cancel: "キャンセル",
        paymentSuccessAlert: "送金通知が送信されました！チームが確認するまでしばらくお待ちください。コインはすぐにチャージされます。",
        paymentFailedAlert: "送金データの送信中にエラーが発生しました。もう一度お試しいただくか、サポートにお問い合わせください。"
      },
      kr: {
        pageTitle: "필명 컬렉션 | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 보유 코인:",
        languageLabel: "🌐 언어 변경:",
        mainTitle: "🌟 Arn-niyay-khan 필명 컬렉션 🌟",
        mainIntro: "Arn-niyay-khan의 세계에 오신 것을 환영합니다. 이곳에서는 다양한 필명과 독특한 장르의 컬렉션이 여러분을 기다립니다.\n\n로맨틱하고 강렬한 드라마, 초현실적인 판타지, 또는 매운 에로티카를 좋아하든, 우리는 여러분이 탐험하고 무한한 상상력에 몰입할 수 있는 모든 취향을 제공합니다.",
        coderakTitle: "📘 코드락",
        coderakDesc: "BL 소설: 로맨틱, 드라마틱, 가슴 저미는 이야기 💔",
        coderakTag: "BL 드라마",
        lippoTitle: "🔥 리포",
        lippoDesc: "강렬한 에로틱 BL 소설, 뜨거운 사랑 NC++ 🔥🛏",
        lippoTag: "BL 에로티카",
        welawadeeTitle: "🌙 웰라와디",
        welawadeeDesc: "BL 오메가버스, 임신 가능, 초자연 ✨🌌",
        welawadeeTag: "BL 초자연",
        wealthyTitle: "💄 웨시",
        wealthyDesc: "강렬한 에로틱 남녀 소설, 매운 사랑 NC++ 🍷",
        wealthyTag: "성인 에로티카",
        bellwarinTitle: "🌼 벨라린",
        bellwarinDesc: "밝고 기분 좋은 남녀 로맨스, 부드러운 마음 ☀️🧁",
        bellwarinTag: "남녀 로맨스",
        nichchabenTitle: "🌈 니차벤",
        nichchabenDesc: "유리 소설: 다양한 F/F 장르 💕👭",
        nichchabenTag: "유리",
        footerText: "© 2025 Arn-niyay-khan | 다양한 필명, 다양한 작가 ✨",
        buyCoinsTitle: "✨ 소설을 읽기 위한 코인 충전 ✨",
        buyCoin10: "10 코인 (5 바트)",
        buyCoin20: "20 코인 (10 바트)",
        buyCoin30: "30 코인 (15 바트)",
        buyCoin40: "40 코인 (20 바트)",
        buyCoin50: "50 코인 (25 바트)",
        buyCoin60: "60 코인 (30 바트)",
        buyCoin70: "70 코인 (35 바트)",
        buyCoin80: "80 코인 (40 바트)",
        buyCoin90: "90 코인 (45 바트)",
        buyCoin100: "100 코인 (50 바트)",
        exchangeRate: "환율: 1 바트 = 2 코인",
        paymentTitle: "{{coins}} 코인 결제",
        paymentInstructions: "1분 이내에 QR 코드를 스캔하거나 {{price}} 바트를 이체해주세요.",
        qrDownloadPrompt: "스캔을 위해 QR 코드를 다운로드하려면 버튼을 클릭하세요.",
        downloadQr: "⬇️ QR 코드 다운로드",
        internationalPaymentInfo: "해외 고객: 편리한 결제 방법에 대해 문의해주세요.",
        iPaidButton: "✅ 스캔/이체 완료",
        confirmPaymentFormTitle: "이체 알림",
        transferNameLabel: "이체자 이름:",
        transferDateTimeLabel: "이체 날짜-시간:",
        transferSlipLabel: "이체 영수증/증명서 첨부:",
        submitPaymentButton: "데이터 제출",
        cancel: "취소",
        paymentSuccessAlert: "이체 알림이 전송되었습니다! 팀 확인 후 코인이 곧 추가됩니다.",
        paymentFailedAlert: "이체 데이터 전송 중 오류가 발생했습니다. 다시 시도하거나 고객 지원에 문의하세요."
      },
      vn: {
        pageTitle: "Bộ sưu tập bút danh | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 Xu của bạn:",
        languageLabel: "🌐 Chọn ngôn ngữ:",
        mainTitle: "🌟 Bộ sưu tập bút danh Arn-niyay-khan 🌟",
        mainIntro: "Chào mừng đến với thế giới của Arn-niyay-khan, nơi tập hợp một bộ sưu tập đa dạng các bút danh và thể loại độc đáo.\n\nDù bạn yêu thích những câu chuyện lãng mạn, kịch tính, giả tưởng siêu thực, hay erotic nóng bỏng, chúng tôi đều có mọi hương vị để bạn khám phá và đắm chìm trong trí tưởng tượng vô hạn.",
        coderakTitle: "📘 Codrak",
        coderakDesc: "Tiểu thuyết BL: lãng mạn, kịch tính, cảm động 💔",
        coderakTag: "BL Drama",
        lippoTitle: "🔥 LIPPO",
        lippoDesc: "Tiểu thuyết BL erotic nặng đô, tình yêu cuồng nhiệt NC++ 🔥🛏",
        lippoTag: "BL Erotica",
        welawadeeTitle: "🌙 Welawadee",
        welawadeeDesc: "Tiểu thuyết BL omegaverse, có thể mang thai, siêu nhiên ✨🌌",
        welawadeeTag: "BL Siêu nhiên",
        wealthyTitle: "💄 WEALTHY",
        wealthyDesc: "Tiểu thuyết erotic nam nữ gay cấn, tình yêu nóng bỏng NC++ 🍷",
        wealthyTag: "Erotic người lớn",
        bellwarinTitle: "🌼 Bellwarin",
        bellwarinDesc: "Tình yêu nam nữ tươi sáng, chữa lành, dịu dàng ☀️🧁",
        bellwarinTag: "Nam nữ chữa lành",
        nichchabenTitle: "🌈 Nichchaben",
        nichchabenDesc: "Tiểu thuyết Yuri: đa dạng thể loại nữ-nữ 💕👭",
        nichchabenTag: "Yuri",
        footerText: "© 2025 Arn-niyay-khan | Bút danh đa dạng, tác giả đa dạng ✨",
        buyCoinsTitle: "✨ Nạp xu để đọc tiểu thuyết ✨",
        buyCoin10: "10 Xu (5 Baht)",
        buyCoin20: "20 Xu (10 Baht)",
        buyCoin30: "30 Xu (15 Baht)",
        buyCoin40: "40 Xu (20 Baht)",
        buyCoin50: "50 Xu (25 Baht)",
        buyCoin60: "60 Xu (30 Baht)",
        buyCoin70: "70 Xu (35 Baht)",
        buyCoin80: "80 Xu (40 Baht)",
        buyCoin90: "90 Xu (45 Baht)",
        buyCoin100: "100 Xu (50 Baht)",
        exchangeRate: "Tỷ giá: 1 Baht = 2 Xu",
        paymentTitle: "Thanh toán để mua {{coins}} Xu",
        paymentInstructions: "Vui lòng quét mã QR hoặc chuyển khoản {{price}} Baht trong vòng 1 phút.",
        qrDownloadPrompt: "Nhấp nút để tải mã QR về và quét thanh toán.",
        downloadQr: "⬇️ Tải mã QR",
        internationalPaymentInfo: "Đối với khách hàng quốc tế: Vui lòng liên hệ với chúng tôi để biết các phương thức thanh toán tiện lợi.",
        iPaidButton: "✅ Tôi đã quét/chuyển khoản",
        confirmPaymentFormTitle: "Thông báo chuyển khoản",
        transferNameLabel: "Tên người chuyển khoản:",
        transferDateTimeLabel: "Ngày-giờ chuyển khoản:",
        transferSlipLabel: "Đính kèm biên lai/bằng chứng chuyển khoản:",
        submitPaymentButton: "Gửi dữ liệu",
        cancel: "Hủy",
        paymentSuccessAlert: "Thông báo chuyển khoản của bạn đã được gửi! Vui lòng chờ đội ngũ của chúng tôi xác minh, xu sẽ được thêm vào sớm nhất.",
        paymentFailedAlert: "Đã xảy ra lỗi khi gửi dữ liệu chuyển khoản. Vui lòng thử lại hoặc liên hệ hỗ trợ."
      }
    };
    
    // ฟังก์ชันสำหรับเปลี่ยนภาษา
    function switchLang(lang) {
      const langPack = translations[lang];
      if (!langPack) return;

      // อัปเดตข้อความสำหรับองค์ประกอบที่มี data-i18n
      document.querySelectorAll("[data-i18n]").forEach(el => {
        const key = el.getAttribute("data-i18n");
        if (langPack[key]) {
          // ส่วนพิเศษสำหรับ coinLabel เพื่อรักษา span ของจำนวนเหรียญ
          if (key === "coinLabel") {
            el.innerHTML = langPack[key] + `<span id="coin-count">${getCoins()}</span>` + (lang === 'th' ? ' เหรียญ' : '');
          } else if (el.tagName === 'TITLE') { // จัดการ title tag
            document.title = langPack[key];
          } 
          else {
            el.textContent = langPack[key];
          }
        }
      });

      // ส่วนสำหรับข้อความ intro-text ที่ต้องมีการ Render ย่อหน้า
      const introTextEl = document.getElementById("introText");
      if (introTextEl && langPack.mainIntro) {
          const content = langPack.mainIntro;
          const paragraphs = content.trim().split(/\n\s*\n|\n+/);
          introTextEl.innerHTML = paragraphs.map(p => `<p>${p.trim()}</p>`).join("");
      }

      // Update the selected language in the dropdown
      const langSelect = document.getElementById("language-select");
      if (langSelect) {
        langSelect.value = lang;
      }
      
      localStorage.setItem("lang", lang);
      updateCoinDisplay(); // อัปเดตการแสดงผลเหรียญหลังจากเปลี่ยนภาษา
    }

    // ฟังก์ชันเริ่มกระบวนการซื้อเหรียญ
    function startBuyCoins(coins, price) {
        pendingCoinsToBuy = coins;
        pendingPriceToPay = price;

        const lang = localStorage.getItem("lang") || "th";
        const paymentTitleEl = document.getElementById("paymentTitle");
        const paymentInstructionsEl = document.getElementById("paymentInstructions");
        const qrCodeImageEl = document.getElementById("qrCodeImage");

        // อัปเดตข้อความ Pop-up
        paymentTitleEl.textContent = translations[lang].paymentTitle.replace('{{coins}}', coins);
        paymentInstructionsEl.innerHTML = (translations[lang].paymentInstructions || '')
            .replace('{{price}}', price)
            .replace(/\n/g, "<br>");

        // *** สำคัญ: สร้าง QR Code จริงที่นี่ ***
        // นี่คือตัวอย่าง URL QR Code ที่คุณสามารถสร้างได้จาก PromptPay API (ถ้ามี)
        // หรือสร้างเป็น QR Code แบบคงที่สำหรับบัญชีของคุณ
        // ถ้าเป็น PromptPay: 'https://promptpay.io/' + รหัสพร้อมเพย์ + '/' + price
        // ถ้าเป็นบัญชีธนาคาร: ต้องสร้าง QR Code จากแอปธนาคารของคุณเอง แล้วใช้รูปนั้น
        // สำหรับการสาธิต ผมจะใช้ placeholder image
        // หากต้องการสร้าง QR Code สำหรับ PromptPay/Standard Thai QR ให้ใช้ API หรือเครื่องมือภายนอก
        const qrData = `PAYMENT_INFO_FOR_${price}_THB`; // ข้อมูลที่จะเข้ารหัสใน QR
        // ตัวอย่างการสร้าง QR code URL จาก API บางตัว (ต้องติดตั้งไลบรารี่/API จริง)
        // qrCodeImageEl.src = `https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=${encodeURIComponent(qrData)}`;
        
        // สำหรับตอนนี้ ใช้ placeholder image ไปก่อน
        qrCodeImageEl.src = `https://via.placeholder.com/200x200?text=Scan+to+Pay+${price}+THB`; 
        qrCodeImageEl.alt = `QR Code for ${price} THB`;

        // ตั้งค่า URL สำหรับดาวน์โหลด QR Code
        document.getElementById("downloadQrButton").onclick = () => {
            const a = document.createElement('a');
            a.href = qrCodeImageEl.src;
            a.download = `QR_Code_${price}THB_${coins}Coins.png`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
        };

        document.getElementById("paymentModal").style.display = "block";
        startCountdown();
    }

    // ฟังก์ชันเริ่มนับถอยหลัง
    function startCountdown() {
        let timeLeft = PAYMENT_TIMEOUT_SECONDS;
        const countdownEl = document.getElementById("countdown");
        countdownEl.textContent = `${timeLeft} ${translations[localStorage.getItem("lang") || "th"].secondsLeft}`; // แปล "secondsLeft"

        countdownInterval = setInterval(() => {
            timeLeft--;
            countdownEl.textContent = `${timeLeft} ${translations[localStorage.getItem("lang") || "th"].secondsLeft}`;

            if (timeLeft <= 0) {
                clearInterval(countdownInterval);
                countdownEl.textContent = translations[localStorage.getItem("lang") || "th"].timeExpired;
                // อาจจะปิด Pop-up หรือเปลี่ยนสถานะ
            }
        }, 1000);
    }

    // ฟังก์ชันยกเลิก Pop-up การชำระเงิน
    function cancelPayment() {
        clearInterval(countdownInterval);
        document.getElementById("paymentModal").style.display = "none";
        pendingCoinsToBuy = 0;
        pendingPriceToPay = 0;
    }

    // ฟังก์ชันแสดงฟอร์มแจ้งโอน
    function showPaymentForm() {
        clearInterval(countdownInterval); // หยุดนับถอยหลัง
        document.getElementById("paymentModal").style.display = "none"; // ซ่อน Pop-up ชำระเงิน
        document.getElementById("paymentFormModal").style.display = "block"; // แสดง Pop-up ฟอร์มแจ้งโอน

        // กำหนดวันเวลาปัจจุบันในฟอร์ม (ตามเขตเวลาของผู้ใช้)
        const now = new Date();
        const year = now.getFullYear();
        const month = (now.getMonth() + 1).toString().padStart(2, '0');
        const day = now.getDate().toString().padStart(2, '0');
        const hours = now.getHours().toString().padStart(2, '0');
        const minutes = now.getMinutes().toString().padStart(2, '0');
        document.getElementById("transferDateTime").value = `${year}-${month}-${day}T${hours}:${minutes}`;
    }

    // ฟังก์ชันยกเลิกฟอร์มแจ้งโอน
    function cancelPaymentForm() {
        document.getElementById("paymentFormModal").style.display = "none";
        pendingCoinsToBuy = 0;
        pendingPriceToPay = 0;
    }

    // ฟังก์ชันส่งข้อมูลฟอร์มไปยัง Google Sheet
    async function submitPaymentData(event) {
        event.preventDefault(); // ป้องกันการโหลดหน้าใหม่

        const form = event.target;
        const formData = new FormData(form);
        
        const transferName = formData.get('transferName');
        const transferDateTime = formData.get('transferDateTime');
        const transferSlip = formData.get('transferSlip'); // File object

        // อ่านไฟล์เป็น Base64 (สำหรับการส่งไป Apps Script)
        let slipBase64 = '';
        if (transferSlip && transferSlip.size > 0) {
            const reader = new FileReader();
            reader.readAsDataURL(transferSlip);
            await new Promise(resolve => {
                reader.onload = () => {
                    slipBase64 = reader.result;
                    resolve();
                };
            });
        }

        const dataToSend = {
            action: "addPayment",
            coins: pendingCoinsToBuy,
            price: pendingPriceToPay,
            transferName: transferName,
            transferDateTime: transferDateTime,
            slipData: slipBase64, // Base64 string of the file
            slipFileName: transferSlip ? transferSlip.name : ''
        };

        try {
            const response = await fetch(GOOGLE_APPS_SCRIPT_URL, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/x-www-form-urlencoded',
                },
                body: new URLSearchParams(dataToSend),
            });

            const result = await response.json();
            
            if (result.status === 'success') {
                alert(translations[localStorage.getItem("lang") || "th"].paymentSuccessAlert);
                cancelPaymentForm(); // ปิดฟอร์มหลังจากส่งสำเร็จ
            } else {
                alert(`${translations[localStorage.getItem("lang") || "th"].paymentFailedAlert}: ${result.message || ''}`);
            }
        } catch (error) {
            console.error('Error submitting payment:', error);
            alert(translations[localStorage.getItem("lang") || "th"].paymentFailedAlert);
        }
    }


    // ฟังก์ชันสำหรับเปลี่ยนภาษา (เหมือนหน้านามปากกา)
    function switchLang(lang) {
      const langPack = translations[lang];
      if (!langPack) return;

      // อัปเดตข้อความสำหรับองค์ประกอบที่มี data-i18n
      document.querySelectorAll("[data-i18n]").forEach(el => {
        const key = el.getAttribute("data-i18n");
        if (langPack[key]) {
          // ส่วนพิเศษสำหรับ coinLabel เพื่อรักษา span ของจำนวนเหรียญ
          if (key === "coinLabel") {
            el.innerHTML = langPack[key] + `<span id="coin-count">${getCoins()}</span>` + (lang === 'th' ? ' เหรียญ' : '');
          } else if (el.tagName === 'TITLE') { // จัดการ title tag
            document.title = langPack[key];
          } 
          else {
            el.textContent = langPack[key];
          }
        }
      });

      // ส่วนสำหรับข้อความ intro-text ที่ต้องมีการ Render ย่อหน้า
      const introTextEl = document.getElementById("introText");
      if (introTextEl && langPack.mainIntro) {
          const content = langPack.mainIntro;
          const paragraphs = content.trim().split(/\n\s*\n|\n+/);
          introTextEl.innerHTML = paragraphs.map(p => `<p>${p.trim()}</p>`).join("");
      }

      // อัปเดตข้อความใน Pop-up การชำระเงิน (กรณีเปิดอยู่)
      const paymentTitleEl = document.getElementById("paymentTitle");
      if (paymentTitleEl && pendingCoinsToBuy > 0) {
        paymentTitleEl.textContent = translations[lang].paymentTitle.replace('{{coins}}', pendingCoinsToBuy);
      }
      const paymentInstructionsEl = document.getElementById("paymentInstructions");
      if (paymentInstructionsEl && pendingPriceToPay > 0) {
        paymentInstructionsEl.innerHTML = (translations[lang].paymentInstructions || '')
            .replace('{{price}}', pendingPriceToPay)
            .replace(/\n/g, "<br>");
      }


      // Update the selected language in the dropdown
      const langSelect = document.getElementById("language-select");
      if (langSelect) {
        langSelect.value = lang;
      }
      
      localStorage.setItem("lang", lang);
      updateCoinDisplay(); // อัปเดตการแสดงผลเหรียญหลังจากเปลี่ยนภาษา
    }

    // เมื่อ DOM โหลดเสร็จ
    document.addEventListener("DOMContentLoaded", function () {
      // ตรวจสอบและกำหนดเหรียญเริ่มต้นถ้ายังไม่มี
      if (!localStorage.getItem("user_coins")) {
        setCoins(100); // กำหนดเหรียญเริ่มต้น 100
      }

      const savedLang = localStorage.getItem("lang") || "th";
      switchLang(savedLang); // Apply the saved language on load

      // เพิ่ม Event Listeners ให้กับปุ่มซื้อเหรียญ
      document.querySelectorAll(".buy-coin-button").forEach(button => {
        button.addEventListener("click", () => {
          const coins = parseInt(button.dataset.coins);
          const price = parseInt(button.dataset.price);
          startBuyCoins(coins, price);
        });
      });
    });
  </script>
</body>
</html>
