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
      color: #432d5d; /* ปรับสีให้เข้ากับนามปากกา */
      padding: 40px;
      max-width: 1024px;
      margin: auto;
      text-align: center;
      user-select: none; /* เพิ่ม user-select เพื่อป้องกันการเลือกข้อความ */
    }

    /* === Header Controls (เหมือนหน้านามปากกา) === */
    .header-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 30px;
      flex-wrap: wrap;
      gap: 15px;
    }

    .site-button {
      display: inline-block;
      padding: 12px 28px;
      background-color: #f6d8ff;
      color: #6d3fb0;
      font-size: 1.35rem; /* ขนาดเท่าหน้านามปากกาและนิยาย */
      font-weight: bold;
      border-radius: 999px;
      box-shadow: 0 3px 10px rgba(0,0,0,0.1);
      text-decoration: none;
      transition: transform 0.3s ease, background-color 0.3s ease;
      flex-shrink: 0;
    }

    .site-button:hover {
      background-color: #e8c2ff;
      transform: scale(1.05);
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
      color: #7b4ca0; /* ปรับสีให้เข้ากัน */
      font-size: 2.2rem; /* ขนาดใหญ่ขึ้น เพื่อให้เป็นหัวข้อหลัก */
      margin-bottom: 10px;
      animation: pulse 3s ease-in-out infinite;
    }

    .intro-text { /* ข้อความอธิบายใต้นามปากกา */
      color: #5e437f; /* ปรับสีให้เข้ากัน */
      font-size: 1.1rem; /* ขนาดกำลังดี */
      margin-bottom: 40px;
      line-height: 1.6;
      max-width: 700px;
      margin-left: auto;
      margin-right: auto;
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
      color: #5e437f; /* ปรับสีให้เข้ากัน */
      font-size: 1rem; /* ขนาดกำลังดี */
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
      color: #9a7fb5; /* ปรับสีให้เข้ากัน */
      text-align: center;
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
      .site-button {
        width: 100%;
        box-sizing: border-box;
      }
      h1 { /* ปรับขนาดหัวข้อหลักบนมือถือ */
          font-size: 1.8rem;
      }
      .intro-text { /* ปรับขนาดคำโปรยใต้นามปากกาบนมือถือ */
          font-size: 1rem;
      }
      a { /* ขนาดชื่อนามปากกาในรายการบนมือถือ */
          font-size: 1.3rem;
      }
      .desc { /* คำโปรยของแต่ละนามปากกาบนมือถือ */
          font-size: 0.9rem;
      }
      li {
          width: 100%; /* ให้รายการเต็มความกว้างบนมือถือ */
          box-sizing: border-box;
      }
    }
  </style>
</head>
<body>

  <div class="header-controls">
    <a href="/" class="site-button" data-i18n="siteButton">✨ Arn-niyay-khan ✨</a>
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
  <p class="intro-text" data-i18n="mainIntro">
    ยินดีต้อนรับสู่โลกของ Arn-niyay-khan ที่รวบรวมหลากหลายนามปากกาและแนวเรื่องไม่ซ้ำใคร 
    ไม่ว่าคุณจะชื่นชอบเรื่องราวรักโรแมนติก ดราม่าเข้มข้น แฟนตาซีเหนือจริง หรืออีโรติกจัดจ้าน 
    เรามีทุกรสชาติให้คุณได้ค้นหาและดื่มด่ำไปกับจินตนาการที่ไร้ขีดจำกัด
  </p>

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
    <li data-i18n-genre="supernatural_bl">
      <a href="welawadee/" data-i18n="welawadeeTitle">🌙 เวฬาวดี</a>
      <div class="desc" data-i18n="welawadeeDesc">วาย omegaverse, ท้องได้, เหนือธรรมชาติ ✨🌌</div>
      <div class="tag" data-i18n="welawadeeTag">วายเหนือธรรมชาติ</div>
    </li>
    <li data-i18n-genre="erotic_straight">
      <a href="wealthy/" data-i18n="wealthyTitle">💄 WEALTHY</a>
      <div class="desc" data-i18n="wealthyDesc">นิยายชายหญิงอีโรติกเข้มข้น รักรสแซ่บ NC++ 🍷</div>
      <div class="tag" data-i18n="wealthyTag">อีโรติกผู้ใหญ่</div>
    </li>
    <li data-i18n-genre="feelgood_straight">
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

  <script>
    // ฟังก์ชันสำหรับจัดการเหรียญ (เหมือนหน้านามปากกา)
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

    // Object สำหรับคำแปล (เหมือนหน้านามปากกา)
    const translations = {
      th: {
        pageTitle: "รวมนามปากกา | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 เหรียญของคุณ: ",
        languageLabel: "🌐 เปลี่ยนภาษา:",
        mainTitle: "🌟 รวมนามปากกาในเครือ Arn-niyay-khan 🌟",
        mainIntro: "ยินดีต้อนรับสู่โลกของ Arn-niyay-khan ที่รวบรวมหลากหลายนามปากกาและแนวเรื่องไม่ซ้ำใคร ไม่ว่าคุณจะชื่นชอบเรื่องราวรักโรแมนติก ดราม่าเข้มข้น แฟนตาซีเหนือจริง หรืออีโรติกจัดจ้าน เรามีทุกรสชาติให้คุณได้ค้นหาและดื่มด่ำไปกับจินตนาการที่ไร้ขีดจำกัด",
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
        footerText: "© 2025 Arn-niyay-khan | พอร์ตนามปากกาหลากรส นักเขียนหลากแนว ✨"
      },
      en: {
        pageTitle: "Pen Name Collection | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 Your coins: ",
        languageLabel: "🌐 Language:",
        mainTitle: "🌟 Pen Name Collection by Arn-niyay-khan 🌟",
        mainIntro: "Welcome to the world of Arn-niyay-khan, where a diverse collection of pen names and unique genres awaits. Whether you love romantic, intense drama, surreal fantasy, or spicy erotica, we have every flavor for you to explore and immerse yourself in boundless imagination.",
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
        footerText: "© 2025 Arn-niyay-khan | Diverse Pen Names, Diverse Authors ✨"
      },
      ch: {
        pageTitle: "笔名合集 | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 您的金币：",
        languageLabel: "🌐 语言切换：",
        mainTitle: "🌟 Arn-niyay-khan 笔名合集 🌟",
        mainIntro: "欢迎来到 Arn-niyay-khan 的世界，这里汇集了各种独特的笔名和风格迥异的故事。无论您喜欢浪漫、扣人心弦的戏剧、超现实的奇幻，还是火辣的色情文学，我们都能满足您的所有品味，让您沉浸在无限的想象中。",
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
        footerText: "© 2025 Arn-niyay-khan | 多样笔名，多样作者 ✨"
      },
      ru: {
        pageTitle: "Коллекция псевдонимов | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 Ваши монеты:",
        languageLabel: "🌐 Выбрать язык:",
        mainTitle: "🌟 Коллекция псевдонимов Arn-niyay-khan 🌟",
        mainIntro: "Добро пожаловать в мир Arn-niyay-khan, где собрана разнообразная коллекция псевдонимов и уникальных жанров. Любите ли вы романтику, напряженную драму, сюрреалистическое фэнтези или пикантную эротику, у нас есть всё, чтобы вы могли исследовать и погрузиться в безграничное воображение.",
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
        footerText: "© 2025 Arn-niyay-khan | Разнообразные псевдонимы, разнообразные авторы ✨"
      },
      jp: {
        pageTitle: "ペンネームコレクション | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 あなたのコイン：",
        languageLabel: "🌐 言語を選択：",
        mainTitle: "🌟 Arn-niyay-khan ペンネームコレクション 🌟",
        mainIntro: "Arn-niyay-khan の世界へようこそ。ここでは、多様なペンネームとユニークなジャンルのコレクションがあなたを待っています。ロマンチックな物語、激しいドラマ、超現実的なファンタジー、またはスパイシーなエロチカがお好みでも、私たちはあらゆる好みを提供し、無限の想像力に浸ることができます。",
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
        footerText: "© 2025 Arn-niyay-khan | 多様なペンネーム、多様な作家 ✨"
      },
      kr: {
        pageTitle: "필명 컬렉션 | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 보유 코인:",
        languageLabel: "🌐 언어 변경:",
        mainTitle: "🌟 Arn-niyay-khan 필명 컬렉션 🌟",
        mainIntro: "Arn-niyay-khan의 세계에 오신 것을 환영합니다. 이곳에서는 다양한 필명과 독특한 장르의 컬렉션이 여러분을 기다립니다. 로맨틱하고 강렬한 드라마, 초현실적인 판타지, 또는 매운 에로티카를 좋아하든, 우리는 여러분이 탐험하고 무한한 상상력에 몰입할 수 있는 모든 취향을 제공합니다.",
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
        footerText: "© 2025 Arn-niyay-khan | 다양한 필명, 다양한 작가 ✨"
      },
      vn: {
        pageTitle: "Bộ sưu tập bút danh | Arn-niyay-khan",
        siteButton: "✨ Arn-niyay-khan ✨",
        coinLabel: "💰 Xu của bạn:",
        languageLabel: "🌐 Chọn ngôn ngữ:",
        mainTitle: "🌟 Bộ sưu tập bút danh Arn-niyay-khan 🌟",
        mainIntro: "Chào mừng đến với thế giới của Arn-niyay-khan, nơi tập hợp một bộ sưu tập đa dạng các bút danh và thể loại độc đáo. Dù bạn yêu thích những câu chuyện lãng mạn, kịch tính, giả tưởng siêu thực, hay erotic nóng bỏng, chúng tôi đều có mọi hương vị để bạn khám phá và đắm chìm trong trí tưởng tượng vô hạn.",
        coderakTitle: "📘 Codrak",
        coderakDesc: "Tiểu thuyết BL: lãng mạn, kịch tính, cảm động 💔",
        coderakTag: "BL Drama",
        lippoTitle: "🔥 LIPPO",
        lippoDesc: "Tiểu thuyết BL erotic nặng đô, tình yêu cuồng nhiệt NC++ 🔥🛏",
        lippoTag: "BL Erotica",
        welawadeeTitle: "🌙 Welawadee",
        welawadeeDesc: "BL omegaverse, có thể mang thai, siêu nhiên ✨🌌",
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
        footerText: "© 2025 Arn-niyay-khan | Bút danh đa dạng, tác giả đa dạng ✨"
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
        setCoins(100);
      }

      const savedLang = localStorage.getItem("lang") || "th";
      switchLang(savedLang); // Apply the saved language on load
    });
  </script>
</body>
</html>
