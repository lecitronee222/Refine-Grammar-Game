<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Grammar Quest: F.6 HKDSE Master Edition</title>
  <style>
    :root {
      --sponge-yellow: #FBC02D;
      --deep-ocean: #004D40;
      --ocean-blue: #00838F;
      --coral-pink: #E64A19;
      --dark-brown: #3E2723;
      --choice-bg: #EFEBE9;
      --choice-border: #6D4C41;
      --success-green: #2E7D32;
      --error-red: #C62828;
    }

    * { box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; margin: 0; padding: 0; }
    body { background: linear-gradient(180deg, #E0F7FA 0%, #FFF9C4 100%); color: #212121; min-height: 100vh; padding: 15px; }
    .container { max-width: 960px; margin: 0 auto; background: #FFFFFF; border-radius: 20px; box-shadow: 0 10px 25px rgba(0,0,0,0.12); padding: 25px; border: 4px solid var(--sponge-yellow); }
    h1, h2, h3 { color: var(--deep-ocean); text-align: center; margin-bottom: 15px; }
    .screen { display: none; }
    .active { display: block; }

    /* Top Utility Bar */
    .top-bar { display: flex; justify-content: space-between; align-items: center; border-bottom: 2px dashed #B2DFDB; padding-bottom: 12px; margin-bottom: 18px; }
    .top-user-pill { display: flex; align-items: center; gap: 8px; font-weight: bold; color: var(--deep-ocean); background: #E0F2F1; padding: 6px 14px; border-radius: 20px; font-size: 0.9rem; }
    .top-nav-btns { display: flex; gap: 8px; }

    /* Buttons */
    .btn { padding: 10px 18px; border-radius: 10px; border: none; font-weight: bold; cursor: pointer; transition: 0.2s; font-size: 0.95rem; display: inline-flex; align-items: center; justify-content: center; gap: 6px; }
    .btn-primary { background: var(--coral-pink); color: #fff; }
    .btn-primary:hover { background: #D84315; transform: translateY(-1px); }
    .btn-ocean { background: var(--ocean-blue); color: #fff; }
    .btn-ocean:hover { background: #006064; }
    .btn-outline { background: transparent; border: 2px solid var(--ocean-blue); color: var(--ocean-blue); }
    .btn-outline:hover { background: #E0F7FA; }
    .btn-danger { background: var(--error-red); color: #fff; }
    .btn-danger:hover { background: #B71C1C; }

    /* 🎭 Character Avatar Doll (Interactive Attachment Engine) */
    .avatar-companion-panel { background: #FFFDE7; border: 2px solid #FFE082; border-radius: 16px; padding: 15px; display: flex; align-items: center; justify-content: space-between; margin-bottom: 20px; gap: 15px; flex-wrap: wrap; }
    .char-pedestal { position: relative; width: 140px; height: 180px; background: radial-gradient(circle, #FFFFFF 55%, #FFF8E1 100%); border: 3px solid #FFA000; border-radius: 18px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; box-shadow: 0 4px 12px rgba(255, 160, 0, 0.25); }
    .doll-body { position: relative; width: 100px; height: 150px; display: flex; flex-direction: column; align-items: center; justify-content: center; }
    
    /* Wearable slots */
    .wear-slot { position: absolute; pointer-events: none; z-index: 10; font-size: 1.8rem; filter: drop-shadow(0 2px 4px rgba(0,0,0,0.3)); }
    .slot-head { top: -14px; left: 50%; transform: translateX(-50%); }
    .slot-torso { top: 48px; left: 50%; transform: translateX(-50%); font-size: 1.5rem; }
    .slot-hand-left { bottom: 30px; left: -14px; font-size: 1.4rem; }
    .slot-hand-right { bottom: 30px; right: -14px; font-size: 1.4rem; }

    /* Character Skins */
    .avatar-sprite { width: 85px; height: 110px; border-radius: 16px; border: 3px solid #212121; display: flex; flex-direction: column; align-items: center; justify-content: center; position: relative; transition: 0.3s; }
    .skin-sponge { background: #FFEE58; box-shadow: inset 0 0 10px #FDD835; }
    .skin-squid { background: #80CBC4; box-shadow: inset 0 0 10px #4DB6AC; }
    .skin-squirrel { background: #D7CCC8; box-shadow: inset 0 0 10px #BCAAA4; }
    .skin-star { background: #FFAB91; box-shadow: inset 0 0 10px #FF8A65; }
    .char-face { font-size: 1.8rem; user-select: none; }
    .char-label { font-size: 0.75rem; font-weight: bold; background: rgba(0,0,0,0.6); color: #fff; padding: 2px 6px; border-radius: 8px; margin-top: 4px; }

    /* Avatar Selector Cards */
    .avatar-picker { display: flex; justify-content: center; gap: 12px; margin: 15px 0; flex-wrap: wrap; }
    .avatar-card { border: 3px solid #CFD8DC; border-radius: 14px; padding: 10px; text-align: center; cursor: pointer; transition: 0.2s; width: 130px; background: #FAFAFA; font-weight: bold; }
    .avatar-card:hover { transform: translateY(-2px); border-color: var(--ocean-blue); }
    .avatar-card.selected { border-color: var(--coral-pink); background: #FBE9E7; transform: scale(1.04); }

    /* Wardrobe Display */
    .wardrobe-box { flex: 1; min-width: 250px; }
    .wardrobe-tags { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 6px; }
    .item-tag { background: #FFF; border: 1.5px solid #FFCA28; border-radius: 12px; padding: 4px 10px; font-size: 0.8rem; font-weight: bold; display: inline-flex; align-items: center; gap: 4px; box-shadow: 0 1px 3px rgba(0,0,0,0.06); }

    /* Topics Matrix */
    .topic-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(290px, 1fr)); gap: 16px; margin-top: 15px; }
    .topic-card { background: #FAFAFA; border: 2px solid #B2DFDB; border-radius: 14px; padding: 16px; transition: 0.2s; }
    .topic-card:hover { border-color: var(--ocean-blue); box-shadow: 0 4px 12px rgba(0, 131, 143, 0.15); }
    .topic-card h4 { color: var(--deep-ocean); margin-bottom: 8px; display: flex; justify-content: space-between; align-items: center; }
    
    .stages-bar { display: grid; grid-template-columns: repeat(5, 1fr); gap: 4px; margin-top: 10px; }
    .stage-btn { padding: 8px 2px; text-align: center; border-radius: 8px; border: 1.5px solid #CFD8DC; font-size: 0.72rem; font-weight: bold; cursor: pointer; background: #ECEFF1; transition: 0.2s; display: flex; flex-direction: column; gap: 2px; }
    .stage-btn.cleared { background: #C8E6C9; border-color: #81C784; color: var(--success-green); }
    .stage-btn.current { background: #FFF9C4; border-color: #FBC02D; color: #E65100; animation: pulse 1.8s infinite; }
    .stage-btn.locked { opacity: 0.45; cursor: not-allowed; }
    .stage-sub { font-size: 0.6rem; font-weight: normal; }

    @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.03); } 100% { transform: scale(1); } }

    /* Question Screen */
    .quiz-container { background: #FFFFFF; border: 2px solid var(--ocean-blue); border-radius: 16px; padding: 22px; margin-top: 10px; }
    .quiz-meta { display: flex; justify-content: space-between; align-items: center; margin-bottom: 16px; border-bottom: 2px solid #E0F2F1; padding-bottom: 10px; }
    .prompt-box { background: #E0F7FA; border-left: 6px solid var(--ocean-blue); padding: 16px; border-radius: 8px; font-size: 1.15rem; font-weight: bold; line-height: 1.6; color: #006064; margin-bottom: 20px; }
    .choices-grid { display: grid; grid-template-columns: 1fr; gap: 10px; margin-bottom: 20px; }
    .choice-btn { background: var(--choice-bg); border: 2px solid var(--choice-border); color: var(--dark-brown); font-size: 1.05rem; font-weight: bold; padding: 14px 18px; border-radius: 12px; cursor: pointer; text-align: left; transition: 0.15s; }
    .choice-btn:hover { background: #D7CCC8; border-color: #3E2723; }
    .choice-btn.selected { background: #BCAAA4; border-color: #271410; color: #000; }

    /* Tables & Modals */
    .table-wrapper { width: 100%; overflow-x: auto; margin-top: 15px; }
    table { width: 100%; border-collapse: collapse; background: #fff; border-radius: 8px; overflow: hidden; font-size: 0.88rem; }
    th, td { padding: 10px 12px; border: 1px solid #E0E0E0; text-align: left; }
    th { background: #004D40; color: #fff; }
    tr:nth-child(even) { background: #F9F9F9; }
    .cell-correct { color: var(--success-green); font-weight: bold; }
    .cell-wrong { color: var(--error-red); font-weight: bold; }

    /* Modal Backdrop */
    .modal-backdrop { position: fixed; inset: 0; background: rgba(0,0,0,0.65); display: flex; align-items: center; justify-content: center; z-index: 999; backdrop-filter: blur(2px); }
    .modal-card { background: #fff; width: 92%; max-width: 720px; max-height: 85vh; border-radius: 18px; padding: 25px; overflow-y: auto; border: 4px solid var(--sponge-yellow); box-shadow: 0 10px 30px rgba(0,0,0,0.3); }
  </style>
</head>
<body>

<div class="container">
  <!-- Top Utility Bar -->
  <div class="top-bar">
    <div class="top-user-pill">
      <span id="topAvatarIcon">👀</span>
      <span id="topUsername">Guest Cadet</span>
    </div>
    <div class="top-nav-btns">
      <button class="btn btn-outline" onclick="showScreen('screen-leaderboard')">🏆 Leaderboard</button>
      <button class="btn btn-outline" onclick="openTeacherModal()">🔒 Instructor Portal</button>
    </div>
  </div>

  <!-- Screen 1: Registration / Avatar Setup -->
  <div id="screen-register" class="screen active">
    <h1>⚓ F.6 HKDSE Grammar Quest</h1>
    <p style="text-align: center; color: #555; margin-bottom: 20px;">
      Master 6 Critical DSE Paper 1 & 2 Focus Categories from Primary 1 Basics to Form 6 Mastery!
    </p>

    <div style="max-width: 440px; margin: 0 auto 20px auto;">
      <label style="font-weight: bold; color: var(--deep-ocean);">Enter Candidate Name or Class Number:</label>
      <input type="text" id="inputUsername" placeholder="e.g., 6A_AlexChan" style="width: 100%; padding: 12px; border-radius: 10px; border: 2px solid #80CBC4; margin-top: 6px; font-size: 1rem;">
    </div>

    <h3 style="margin-top: 15px;">Choose Your Living Companion Doll</h3>
    <div class="avatar-picker">
      <div class="avatar-card selected" onclick="pickAvatar('Sponge-Lad', 'skin-sponge', '👀', this)">
        <div style="font-size: 2.2rem;">🧽</div>
        <div>Sponge-Lad</div>
      </div>
      <div class="avatar-card" onclick="pickAvatar('Tentacle-Prof', 'skin-squid', '👓', this)">
        <div style="font-size: 2.2rem;">🦑</div>
        <div>Tentacle-Prof</div>
      </div>
      <div class="avatar-card" onclick="pickAvatar('Sandy-Squirrel', 'skin-squirrel', '🥜', this)">
        <div style="font-size: 2.2rem;">🐿️</div>
        <div>Sandy-Squirrel</div>
      </div>
      <div class="avatar-card" onclick="pickAvatar('Star-Buddy', 'skin-star', '🌟', this)">
        <div style="font-size: 2.2rem;">⭐</div>
        <div>Star-Buddy</div>
      </div>
    </div>

    <div style="text-align: center; margin-top: 25px;">
      <button class="btn btn-primary" style="font-size: 1.1rem; padding: 12px 30px;" onclick="registerUser()">Start Grammar Adventure ➔</button>
    </div>
  </div>

  <!-- Screen 2: Dashboard & Category Matrix -->
  <div id="screen-dashboard" class="screen">
    <!-- Companion Doll Stage Panel -->
    <div class="avatar-companion-panel">
      <div class="char-pedestal">
        <div class="doll-body">
          <div class="wear-slot slot-head" id="pedestalHead"></div>
          <div class="wear-slot slot-torso" id="pedestalTorso"></div>
          <div class="wear-slot slot-hand-left" id="pedestalHandL"></div>
          <div class="wear-slot slot-hand-right" id="pedestalHandR"></div>

          <div class="avatar-sprite skin-sponge" id="pedestalSprite">
            <div class="char-face" id="pedestalFace">👀</div>
            <div class="char-label" id="pedestalName">Sponge-Lad</div>
          </div>
        </div>
      </div>

      <div class="wardrobe-box">
        <h3 style="text-align: left; margin-bottom: 4px;">Companion Equipment Rig</h3>
        <p style="font-size: 0.85rem; color: #666;">Score <strong>16/20 or above</strong> on any stage to unlock wearable relics!</p>
        <div class="wardrobe-tags" id="wardrobeTags">
          <span style="font-size: 0.82rem; color: #888;">No accessories equipped yet.</span>
        </div>
      </div>
    </div>

    <h2>Select Grammar Focus Category</h2>
    <div class="topic-grid" id="topicsContainer"></div>
  </div>

  <!-- Screen 3: Quiz Screen -->
  <div id="screen-quiz" class="screen">
    <div class="quiz-container">
      <div class="quiz-meta">
        <div>
          <span id="quizTopicTitle" style="font-weight: bold; color: var(--ocean-blue); font-size: 1.1rem;">Topic</span>
          <div id="quizStageSubtitle" style="font-size: 0.82rem; color: #555;">Stage 1</div>
        </div>
        <div style="font-weight: bold; font-size: 1.1rem; color: var(--coral-pink);" id="quizProgressCount">Q: 1 / 20</div>
      </div>

      <div class="prompt-box" id="quizPrompt">Question text will load here...</div>
      <div class="choices-grid" id="choicesGrid"></div>

      <div style="display: flex; justify-content: space-between; align-items: center;">
        <button class="btn btn-outline" onclick="abandonQuiz()">✕ Exit Stage</button>
        <button class="btn btn-primary" id="btnNext" onclick="submitCurrentQuestion()">Confirm Answer ➔</button>
      </div>
    </div>
  </div>

  <!-- Screen 4: Stage Results & Answer Key -->
  <div id="screen-result" class="screen">
    <div style="text-align: center; margin-bottom: 20px;">
      <h1 id="resultTitle">Stage Evaluation</h1>
      <p id="resultFeedback" style="font-size: 1.15rem; color: #333; margin-top: 8px;"></p>
    </div>

    <div id="relicAlert" style="display: none; background: #E8F5E9; border: 2px solid #66BB6A; border-radius: 12px; padding: 14px; margin-bottom: 18px; text-align: center;"></div>

    <h3>Complete Stage Answer Review</h3>
    <p style="font-size: 0.85rem; color: #666; margin-bottom: 10px;">Candidates scoring 16 or above advance to subsequent stages.</p>

    <div class="table-wrapper">
      <table>
        <thead>
          <tr>
            <th>#</th>
            <th>Question Prompt</th>
            <th>Your Submission</th>
            <th>Official Key</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody id="resultReviewBody"></tbody>
      </table>
    </div>

    <div style="margin-top: 25px; display: flex; justify-content: center; gap: 12px;">
      <button class="btn btn-ocean" onclick="showScreen('screen-dashboard')">Return to Dashboard</button>
      <button class="btn btn-primary" id="btnNextLevel" style="display: none;" onclick="advanceNextStage()">Proceed to Next Stage ➔</button>
    </div>
  </div>

  <!-- Screen 5: Leaderboard -->
  <div id="screen-leaderboard" class="screen">
    <h2>🏆 Student Performance Leaderboard</h2>
    <div class="table-wrapper">
      <table>
        <thead>
          <tr>
            <th>Rank</th>
            <th>Candidate</th>
            <th>Avatar</th>
            <th>Cleared Stages</th>
            <th>Aggregate Score</th>
          </tr>
        </thead>
        <tbody id="leaderboardTbody"></tbody>
      </table>
    </div>
    <div style="text-align: center; margin-top: 20px;">
      <button class="btn btn-ocean" onclick="showScreen('screen-dashboard')">Back to Dashboard</button>
    </div>
  </div>
</div>

<!-- Modal: Hidden Teacher Portal (No PIN shown) -->
<div class="modal-backdrop" id="teacherModal" style="display: none;">
  <div class="modal-card">
    <div style="display: flex; justify-content: space-between; align-items: center; border-bottom: 2px solid #E0E0E0; padding-bottom: 10px; margin-bottom: 15px;">
      <h2 style="margin: 0; color: var(--deep-ocean);">🔒 Instructor Administrative Portal</h2>
      <button class="btn btn-outline" style="padding: 4px 10px;" onclick="closeTeacherModal()">✕</button>
    </div>

    <div id="teacherAuthArea">
      <p style="font-size: 0.9rem; color: #555; margin-bottom: 12px;">
        Enter master verification credentials to access student logs and administrative actions:
      </p>
      <div style="display: flex; gap: 8px;">
        <input 
          type="password" 
          id="teacherSecretInput" 
          placeholder="••••••••" 
          autocomplete="off" 
          style="flex: 1; padding: 10px; border-radius: 8px; border: 2px solid #B2DFDB;"
          onkeydown="if(event.key==='Enter') verifyTeacherPin()"
        >
        <button class="btn btn-primary" onclick="verifyTeacherPin()">Authenticate</button>
      </div>
    </div>

    <div id="teacherDashboardArea" style="display: none;">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 12px; flex-wrap: wrap; gap: 8px;">
        <h3 style="margin: 0;">Candidate Tracking Manifest</h3>
        <div style="display: flex; gap: 8px;">
          <button class="btn btn-ocean" onclick="exportToExcel()">📥 Export Excel (.xls)</button>
          <button class="btn btn-danger" onclick="clearAllData()">Reset Leaderboard</button>
        </div>
      </div>

      <div class="table-wrapper">
        <table>
          <thead>
            <tr>
              <th>Candidate</th>
              <th>Avatar</th>
              <th>Cleared</th>
              <th>High Score</th>
              <th>Total Attempts</th>
            </tr>
          </thead>
          <tbody id="teacherTableBody"></tbody>
        </table>
      </div>
    </div>
  </div>
</div>

<script>
  // Persistence Utilities
  const storage = {
    get: (k, d) => { try { const v = localStorage.getItem(k); return v ? JSON.parse(v) : d; } catch(e) { return d; } },
    set: (k, v) => { try { localStorage.setItem(k, JSON.stringify(v)); } catch(e) {} }
  };

  // Precomputed SHA-256 hash of instructor PIN
  const AUTH_HASH = "8c0a87a6d8beecb2bfba2725e6ffc6cf91054ee5b565012e848df87a327fcfa8";
  const PASS_CRITERIA = 16;
  const STAGE_QUESTIONS_NUM = 20;

  const STAGE_TITLES = {
    1: "Stage 1: Primary 1–3 Foundation",
    2: "Stage 2: Primary 4–6 Intermediate",
    3: "Stage 3: Secondary 1–3 Junior",
    4: "Stage 4: Secondary 4 Senior",
    5: "Stage 5: Secondary 4–6 / HKDSE Level 5**"
  };

  // Avatar Wearable Slot Mapping
  const REWARD_MAP = {
    "Prepositions": [
      { name: "Scholar Cap", slot: "slot-head", icon: "🧢" },
      { name: "Scout Vest", slot: "slot-torso", icon: "🦺" },
      { name: "Anchor Brooch", slot: "slot-torso", icon: "⚓" },
      { name: "Admiral Epaulettes", slot: "slot-hand-left", icon: "🎖️" },
      { name: "Pearl Tricorne", slot: "slot-head", icon: "👑" }
    ],
    "Word Formation": [
      { name: "Silver Quill", slot: "slot-hand-right", icon: "🪶" },
      { name: "Grammar Monocle", slot: "slot-head", icon: "🧐" },
      { name: "Sage Robe", slot: "slot-torso", icon: "🥋" },
      { name: "Lexicon Gem", slot: "slot-hand-left", icon: "💎" },
      { name: "Crown of Syntax", slot: "slot-head", icon: "👑" }
    ],
    "Tenses": [
      { name: "Chrono Pocketwatch", slot: "slot-hand-left", icon: "⏱️" },
      { name: "Hourglass Pendant", slot: "slot-torso", icon: "⏳" },
      { name: "Epoch Cape", slot: "slot-torso", icon: "🥋" },
      { name: "Temporal Ring", slot: "slot-hand-right", icon: "💍" },
      { name: "Sovereign Diadem", slot: "slot-head", icon: "👑" }
    ],
    "Articles": [
      { name: "Parchment Sash", slot: "slot-torso", icon: "📜" },
      { name: "Definite Sigil", slot: "slot-torso", icon: "🏷️" },
      { name: "Determinative Lens", slot: "slot-head", icon: "🔍" },
      { name: "Guardian Crest", slot: "slot-hand-left", icon: "🛡️" },
      { name: "Crown of Precision", slot: "slot-head", icon: "👑" }
    ],
    "Plurals": [
      { name: "Dual Wristbands", slot: "slot-hand-left", icon: "🧤" },
      { name: "Concordance Key", slot: "slot-hand-right", icon: "🗝️" },
      { name: "Multiplier Ribbon", slot: "slot-torso", icon: "🎗️" },
      { name: "Harmonic Bracer", slot: "slot-hand-left", icon: "🔮" },
      { name: "Infinity Coronet", slot: "slot-head", icon: "👑" }
    ],
    "Synonyms": [
      { name: "Pocket Glossary", slot: "slot-hand-right", icon: "📖" },
      { name: "Word Pouch", slot: "slot-hand-left", icon: "👛" },
      { name: "Chameleon Cloak", slot: "slot-torso", icon: "🧣" },
      { name: "Polyglot Tunic", slot: "slot-torso", icon: "🎽" },
      { name: "Wings of Eloquence", slot: "slot-torso", icon: "🪽" }
    ]
  };

  // Full 600 Question Master Bank (6 Categories × 5 Stages × 20 Non-Repeating Questions)
  const questionBank = {
    "Prepositions": {
      1: [
        { q: "The apple is sitting _____ the wooden desk.", a: "on", dist: ["at", "to", "into"] },
        { q: "My sleepy cat likes to rest _____ the dining table.", a: "under", dist: ["of", "to", "off"] },
        { q: "Primary school begins promptly _____ 8 o'clock.", a: "at", dist: ["on", "in", "to"] },
        { q: "All the colorful toys are kept _____ the big basket.", a: "in", dist: ["on", "at", "to"] },
        { q: "My brother's birthday party is celebrated _____ May.", a: "in", dist: ["on", "at", "of"] },
        { q: "Our family goes hiking _____ Sunday morning.", a: "on", dist: ["in", "at", "to"] },
        { q: "He sits happily _____ his best friend in class.", a: "next to", dist: ["at", "on", "into"] },
        { q: "Look closely _____ the pictures in the storybook.", a: "at", dist: ["in", "on", "to"] },
        { q: "The small sparrow flew _____ the open kitchen window.", a: "through", dist: ["at", "on", "of"] },
        { q: "Put your blue pen _____ your school bag now.", a: "into", dist: ["on", "at", "to"] },
        { q: "We live together in a cozy flat _____ Hong Kong.", a: "in", dist: ["at", "on", "to"] },
        { q: "I wake up cheerfully _____ 7:00 a.m. on weekdays.", a: "at", dist: ["on", "in", "by"] },
        { q: "The brown puppy is hiding _____ the bedroom door.", a: "behind", dist: ["on", "at", "into"] },
        { q: "Children must brush their teeth _____ night.", a: "at", dist: ["in", "on", "to"] },
        { q: "There is an art drawing _____ the living room wall.", a: "on", dist: ["in", "at", "to"] },
        { q: "The little girl walked hand in hand _____ her grandmother.", a: "with", dist: ["at", "on", "in"] },
        { q: "The recreation park is located very close _____ our home.", a: "to", dist: ["with", "for", "at"] },
        { q: "We open our holiday presents _____ Christmas Day.", a: "on", dist: ["in", "at", "of"] },
        { q: "The energetic frog jumped right _____ the shallow puddle.", a: "over", dist: ["at", "in", "on"] },
        { q: "Two yellow ducks are swimming _____ the garden pond.", a: "in", dist: ["on", "at", "to"] }
      ],
      2: [
        { q: "She has always been exceptionally good _____ playing the cello.", a: "at", dist: ["in", "on", "with"] },
        { q: "The tourists crossed the channel _____ high-speed ferry.", a: "by", dist: ["on", "in", "with"] },
        { q: "He admitted that he was terrified _____ creepy spiders.", a: "of", dist: ["from", "with", "about"] },
        { q: "Are you genuinely interested _____ wildlife conservation?", a: "in", dist: ["at", "on", "about"] },
        { q: "Our flight passengers arrived safely _____ the terminal.", a: "at", dist: ["to", "in", "on"] },
        { q: "The proud father was beaming _____ his son's graduation.", a: "with", dist: ["for", "about", "of"] },
        { q: "Please pay close attention and listen _____ the instructions.", a: "to", dist: ["at", "with", "for"] },
        { q: "The picnic was postponed because _____ torrential rain.", a: "of", dist: ["from", "with", "by"] },
        { q: "She thanked her classmates warmly _____ their thoughtful card.", a: "for", dist: ["of", "to", "with"] },
        { q: "Hong Kong is internationally famous _____ its vibrant night markets.", a: "for", dist: ["with", "about", "of"] },
        { q: "He borrowed a reference dictionary _____ the community library.", a: "from", dist: ["to", "at", "by"] },
        { q: "You should never shout angrily _____ your teammates.", a: "at", dist: ["to", "with", "on"] },
        { q: "The birthday boy was thrilled _____ the surprise celebration.", a: "by", dist: ["with", "on", "to"] },
        { q: "I concur and agree completely _____ your constructive suggestions.", a: "with", dist: ["to", "on", "for"] },
        { q: "Commuters have stood waiting at the station _____ forty minutes.", a: "for", dist: ["since", "during", "at"] },
        { q: "Our family has resided in Kowloon _____ 2014.", a: "since", dist: ["for", "in", "from"] },
        { q: "The school playground was bustling and full _____ eager children.", a: "of", dist: ["with", "by", "in"] },
        { q: "The boy apologized sincerely _____ shattering the glass beaker.", a: "for", dist: ["to", "about", "with"] },
        { q: "Please take good care _____ your younger sibling today.", a: "of", dist: ["to", "with", "about"] },
        { q: "The coach separated the squad _____ four training groups.", a: "into", dist: ["to", "in", "for"] }
      ],
      3: [
        { q: "The debate team succeeded _____ securing the championship trophy.", a: "in", dist: ["at", "to", "for"] },
        { q: "He has long suffered _____ severe allergic reactions during spring.", a: "from", dist: ["of", "with", "by"] },
        { q: "The host firmly insisted _____ settling the entire banquet bill.", a: "on", dist: ["in", "at", "to"] },
        { q: "Every laboratory assistant must conform _____ strict safety protocols.", a: "to", dist: ["with", "by", "for"] },
        { q: "The captain delivered the speech _____ behalf of the entire squad.", a: "on", dist: ["in", "at", "for"] },
        { q: "She warmly congratulated her peer _____ earning the scholarship.", a: "on", dist: ["for", "in", "at"] },
        { q: "The hikers were completely unaware _____ the sudden temperature plunge.", a: "of", dist: ["about", "with", "to"] },
        { q: "The modern cafeteria strives to cater _____ diverse dietary preferences.", a: "to", dist: ["for", "with", "at"] },
        { q: "Commercial advertising is strictly forbidden _____ school premises.", a: "on", dist: ["at", "over", "with"] },
        { q: "The young calligrapher prides herself _____ her meticulous brushwork.", a: "on", dist: ["in", "with", "for"] },
        { q: "He has grown accustomed _____ rigorous physical drills every dawn.", a: "to", dist: ["with", "for", "in"] },
        { q: "The dedicated scientist contributed extensively _____ renewable fuel research.", a: "to", dist: ["for", "in", "with"] },
        { q: "Timely maintenance prevented hazardous chemical leaks _____ occurring.", a: "from", dist: ["to", "by", "of"] },
        { q: "The historical drama is founded _____ documented accounts of the rebellion.", a: "on", dist: ["in", "at", "from"] },
        { q: "Project dossiers must be submitted _____ midday tomorrow at the latest.", a: "by", dist: ["until", "for", "during"] },
        { q: "The athlete withdrew from the tournament _____ account of an injury.", a: "on", dist: ["in", "by", "for"] },
        { q: "The school counselor expressed deep sympathy _____ the bereaved family.", a: "for", dist: ["with", "to", "towards"] },
        { q: "Young adolescents remain heavily dependent _____ parental financial backing.", a: "on", dist: ["with", "to", "of"] },
        { q: "The embarrassed speaker apologized _____ mispronouncing the guest's surname.", a: "for", dist: ["with", "to", "about"] },
        { q: "Detectives searched tirelessly _____ forensic evidence in the building.", a: "for", dist: ["to", "after", "with"] }
      ],
      4: [
        { q: "The statutory code was revised in full accordance _____ the updated ordinance.", a: "with", dist: ["to", "by", "for"] },
        { q: "Novice sprinters are notoriously prone _____ hamstring strains in cold weather.", a: "to", dist: ["for", "with", "at"] },
        { q: "The witness statements were not entirely compatible _____ forensic ballistics.", a: "with", dist: ["to", "for", "against"] },
        { q: "The finance minister seemed strangely oblivious _____ public outrage over fuel hikes.", a: "to", dist: ["of", "with", "about"] },
        { q: "New anti-smoking legislation was introduced with a view _____ protecting youth.", a: "to", dist: ["for", "at", "in"] },
        { q: "Civil servants are expected to refrain _____ engaging in partisan campaigns.", a: "from", dist: ["to", "by", "with"] },
        { q: "A quiet, well-lit study environment is highly conducive _____ deep academic focus.", a: "to", dist: ["for", "with", "in"] },
        { q: "Conservation groups vehemently objected _____ the massive coastal land reclamation.", a: "to", dist: ["for", "against", "with"] },
        { q: "The board ratified the restructuring program irrespective _____ labor union protests.", a: "of", dist: ["from", "with", "to"] },
        { q: "She proved to possess an uncanny flair _____ negotiating bilateral trade contracts.", a: "for", dist: ["in", "at", "with"] },
        { q: "Economists attributed the slump _____ fluctuating global interest benchmarks.", a: "to", dist: ["for", "with", "by"] },
        { q: "The claimant's speculative argument was entirely devoid _____ factual documentation.", a: "of", dist: ["from", "with", "by"] },
        { q: "The former executive was formally charged _____ embezzlement by prosecutors.", a: "with", dist: ["for", "of", "in"] },
        { q: "The judicial council displayed steadfast adherence _____ established legal precedents.", a: "to", dist: ["with", "for", "in"] },
        { q: "She harbored intense antipathy _____ unethical corporate monopolies.", a: "towards", dist: ["for", "with", "at"] },
        { q: "The senior legal advisor was exceptionally well-versed _____ cross-border taxation.", a: "in", dist: ["with", "at", "about"] },
        { q: "Strict quota limits were imposed in direct response _____ mounting import deficits.", a: "to", dist: ["for", "with", "towards"] },
        { q: "The novice applicant compensated _____ her lack of tenure through sheer diligence.", a: "for", dist: ["to", "with", "of"] },
        { q: "Tenured judges must remain completely immune _____ partisan political pressure.", a: "to", dist: ["from", "against", "with"] },
        { q: "The expedition leaders remained calm and resolute _____ the face of unexpected hazards.", a: "in", dist: ["at", "on", "with"] }
      ],
      5: [
        { q: "The veteran statesman proved fiercely averse _____ populist media sensationalism.", a: "to", dist: ["from", "against", "with"] },
        { q: "Only three senior cabinet members were privy _____ the classified diplomatic cable.", a: "to", dist: ["with", "in", "for"] },
        { q: "The executive compensation package was hardly commensurate _____ company losses.", a: "with", dist: ["to", "by", "against"] },
        { q: "The disgraced official was convicted _____ three counts of statutory bribery.", a: "of", dist: ["with", "for", "by"] },
        { q: "Her relentless quest for administrative control borders _____ authoritarianism.", a: "on", dist: ["at", "to", "with"] },
        { q: "The newly adopted doctrine was diametrically opposed _____ historical treaty terms.", a: "to", dist: ["with", "against", "from"] },
        { q: "Critics argued the surveillance bill impinged unduly _____ civil press freedoms.", a: "on", dist: ["at", "to", "into"] },
        { q: "The foreign minister took immense umbrage _____ the ambassador's derogatory remark.", a: "at", dist: ["to", "with", "for"] },
        { q: "The consortium acted in covert collusion _____ foreign tax haven intermediaries.", a: "with", dist: ["to", "by", "for"] },
        { q: "The collegiate governing constitution was modeled _____ ancient Oxford statutes.", a: "on", dist: ["after", "from", "with"] },
        { q: "His tactical intervention was deemed instrumental _____ averting an economic crisis.", a: "in", dist: ["to", "for", "with"] },
        { q: "The sharp currency devaluation is symptomatic _____ deep-seated fiscal vulnerability.", a: "of", dist: ["for", "with", "to"] },
        { q: "The courtroom was cleared because the matter remained sub _____ pending appeal.", a: "judice", dist: ["poena", "rosa", "silentio"] },
        { q: "The emergency audit was convened at the explicit behest _____ the governor.", a: "of", dist: ["to", "by", "from"] },
        { q: "The academic monograph expresses unmasked disdain _____ intellectual complacency.", a: "for", dist: ["to", "with", "at"] },
        { q: "Her rigorous experimental protocol proved entirely impervious _____ external critique.", a: "to", dist: ["from", "against", "with"] },
        { q: "The diplomat was censured for conniving _____ insurgent paramilitary factions.", a: "with", dist: ["at", "to", "for"] },
        { q: "The experimental compound must only be administered _____ direct clinical oversight.", a: "under", dist: ["with", "at", "in"] },
        { q: "Such brazen commercial exploitation is anathema _____ the institution's core ethos.", a: "to", dist: ["for", "with", "against"] },
        { q: "The military annexation proceeded under the false guise _____ peacekeeping relief.", a: "of", dist: ["for", "with", "in"] }
      ]
    },

    "Word Formation": {
      1: [
        { q: "Our English _____ (teach) is remarkably kind and patient with everyone.", a: "teacher", dist: ["teaching", "teached", "teachor"] },
        { q: "He was deeply _____ (happy) when he accidentally dropped his ice cream cone.", a: "unhappy", dist: ["dishappy", "imhappy", "happiless"] },
        { q: "The morning sun was shining _____ (bright) through our bedroom curtains.", a: "brightly", dist: ["brightness", "brightful", "brighty"] },
        { q: "That tall athlete is known as the fastest _____ (run) in the school.", a: "runner", dist: ["running", "runor", "runned"] },
        { q: "You must be extraordinarily _____ (care) when handling boiling water.", a: "careful", dist: ["careless", "caring", "carely"] },
        { q: "The sleepy infant was resting _____ (quiet) in her wooden cradle.", a: "quietly", dist: ["quietness", "quietful", "quiety"] },
        { q: "It is completely _____ (possible) to breathe underwater without special gear.", a: "impossible", dist: ["unpossible", "dispossible", "inpossible"] },
        { q: "The family adopted a _____ (love) golden retriever puppy yesterday.", a: "lovely", dist: ["lovingly", "loveless", "loveful"] },
        { q: "His uncle works as an experienced double-decker bus _____ (drive).", a: "driver", dist: ["driving", "drivor", "drived"] },
        { q: "It looks very _____ (rain) outside, so remember to take your raincoat.", a: "rainy", dist: ["raining", "rainful", "rainly"] },
        { q: "The thrilling fairy tale had a delightful and heartwarming _____ (end).", a: "ending", dist: ["ender", "endful", "endly"] },
        { q: "She gazed at the wilted flowers with profound _____ (sad).", a: "sadness", dist: ["sadly", "saddy", "unsad"] },
        { q: "The colorful picture dictionary is immensely _____ (help) for beginners.", a: "helpful", dist: ["helpless", "helply", "helping"] },
        { q: "A talented person who performs musical tracks is called a _____ (sing).", a: "singer", dist: ["songer", "singing", "singor"] },
        { q: "It is extremely _____ (safe) for toddlers to run near slippery swimming pools.", a: "unsafe", dist: ["disafe", "insafe", "safeless"] },
        { q: "The excited schoolchildren cheered _____ (happy) as the holidays arrived.", a: "happily", dist: ["happiness", "happyful", "unhappily"] },
        { q: "The freezing December breeze felt bitterly _____ (chill) this morning.", a: "chilly", dist: ["chillful", "chillness", "chillly"] },
        { q: "She welcomed the lost traveler with genuine _____ (warm).", a: "warmth", dist: ["warmly", "warmful", "warmness"] },
        { q: "Charles Dickens was a prolific and celebrated English _____ (write).", a: "writer", dist: ["writing", "writor", "written"] },
        { q: "Please remember to _____ (lock) the side gate before the guests arrive.", a: "unlock", dist: ["dislock", "mislock", "inlock"] }
      ],
      2: [
        { q: "The city council held a lengthy _____ (discuss) regarding green parks.", a: "discussion", dist: ["discussment", "discussing", "discusser"] },
        { q: "The captain made an executive _____ (decide) to alter the sailing route.", a: "decision", dist: ["decidement", "decidance", "decisiveness"] },
        { q: "The stranded passengers felt completely _____ (help) when their bus stalled.", a: "helpless", dist: ["unhelpful", "unhelping", "dishelp"] },
        { q: "Regular cardiovascular fitness is of paramount _____ (important) for longevity.", a: "importance", dist: ["importancy", "importantness", "importation"] },
        { q: "The illusionist made the silver coin suddenly _____ (appear) into thin air.", a: "disappear", dist: ["unappear", "misappear", "nonappear"] },
        { q: "The hotel receptionist greeted all incoming guests with great _____ (polite).", a: "politeness", dist: ["polity", "politely", "politery"] },
        { q: "Students require official parental _____ (permit) to attend the overnight camp.", a: "permission", dist: ["permittance", "permitment", "permitation"] },
        { q: "The instructor asked him to _____ (write) his messy homework assignment.", a: "rewrite", dist: ["diswrite", "miswrite", "unwrite"] },
        { q: "The unexpected _____ (arrive) of the delegation caused sudden commotion.", a: "arrival", dist: ["arrivement", "arriving", "arrivation"] },
        { q: "Unchecked coastal dredging caused widespread _____ (destroy) to fragile reefs.", a: "destruction", dist: ["destroyment", "destructance", "destroyal"] },
        { q: "Training a playful rescue puppy demands endless _____ (patient) and empathy.", a: "patience", dist: ["patientness", "patiency", "patiently"] },
        { q: "Inhaling industrial fumes over extended durations is highly _____ (harm).", a: "harmful", dist: ["harmless", "harming", "harmable"] },
        { q: "The polite shopkeeper bowed to _____ (apology) for the unexpected delay.", a: "apologize", dist: ["apologetic", "apologiseful", "apologement"] },
        { q: "Securing the championship brought overwhelming _____ (proud) to our hall.", a: "pride", dist: ["proudness", "proudful", "proudity"] },
        { q: "Consuming excessive refined sugars daily leads to an _____ (health) lifestyle.", a: "unhealthy", dist: ["dishealthy", "inhealthy", "healthless"] },
        { q: "A bout of unexpected seasonal _____ (ill) prevented her from taking the test.", a: "illness", dist: ["illful", "ility", "illement"] },
        { q: "Can you provide a comprehensive _____ (describe) of the missing vehicle?", a: "description", dist: ["describement", "describal", "descriptive"] },
        { q: "An eerie and unbroken _____ (silent) descended over the abandoned castle.", a: "silence", dist: ["silentness", "silency", "silently"] },
        { q: "The technician handled the delicate microscope lenses very _____ (care).", a: "carefully", dist: ["carefulness", "caringly", "careless"] },
        { q: "Their enduring bond of childhood _____ (friend) remained intact for fifty years.", a: "friendship", dist: ["friendness", "friendhood", "friendment"] }
      ],
      3: [
        { q: "Municipal authorities voted to _____ (modern) aging rail infrastructure.", a: "modernize", dist: ["modernate", "modernify", "modernism"] },
        { q: "Could you please _____ (clear) what your earlier contradictory remark implied?", a: "clarify", dist: ["clearize", "clearness", "clarificate"] },
        { q: "The abrupt shift in flight timetables created immense _____ (confuse) at the gate.", a: "confusion", dist: ["confusement", "confusity", "confuseness"] },
        { q: "Earning her medical doctorate was her greatest personal _____ (achieve).", a: "achievement", dist: ["achievance", "achievity", "achieving"] },
        { q: "Investigators could locate no tangible _____ (prove) tying the firm to fraud.", a: "proof", dist: ["proving", "provement", "proveness"] },
        { q: "Reckless toxic dumping presents an ongoing _____ (threaten) to river ecosystems.", a: "threat", dist: ["threatful", "threatening", "threatence"] },
        { q: "The rigid manager was faulted for demonstrating a complete lack of _____ (flexible).", a: "flexibility", dist: ["flexibleness", "flexiblance", "flexibilism"] },
        { q: "Embarking on a steep alpine climb without emergency equipment is _____ (advise).", a: "inadvisable", dist: ["unadvisable", "disadvisable", "nonadvisable"] },
        { q: "The contagious influenza strain spread across the province with alarming _____ (rapid).", a: "rapidity", dist: ["rapidness", "rapidment", "rapidance"] },
        { q: "The commander admitted he had completely _____ (judge) the opponent's resolve.", a: "misjudged", dist: ["disjudged", "unjudged", "maljudged"] },
        { q: "The disaster relief foundation depends solely upon public _____ (generous).", a: "generosity", dist: ["generousness", "generousity", "generoushood"] },
        { q: "The bilateral treaty contains legally _____ (bind) terms for all signatories.", a: "binding", dist: ["bindable", "bindful", "bounden"] },
        { q: "She voiced heartfelt _____ (grateful) toward the surgical team who saved her life.", a: "gratitude", dist: ["gratefulness", "gratefullity", "gratitution"] },
        { q: "The tech multinational announced the territorial _____ (expand) of its cloud centers.", a: "expansion", dist: ["expandment", "expansity", "expandance"] },
        { q: "His far-fetched alibi sounded completely _____ (convince) to the jury.", a: "unconvincing", dist: ["disconvincing", "inconvincing", "nonconvincing"] },
        { q: "The two prominent commercial hubs maintained an intense maritime _____ (rival).", a: "rivalry", dist: ["rivalship", "rivalness", "rivalment"] },
        { q: "Specialized reverse-osmosis filtration is utilized to _____ (pure) wastewater.", a: "purify", dist: ["purize", "pureness", "purificate"] },
        { q: "Targeted educational subsidies will _____ (able) low-income youth to attend college.", a: "enable", dist: ["inable", "disable", "emable"] },
        { q: "His resignation from the cabinet came as a totally _____ (expect) shock.", a: "unexpected", dist: ["disexpected", "inexpected", "misexpected"] },
        { q: "Severe drought conditions resulted in acute food and water _____ (scarce).", a: "scarcity", dist: ["scarceness", "scarcement", "scarcitude"] }
      ],
      4: [
        { q: "The corporate sustainability audit examined the long-term _____ (viable) of clean power.", a: "viability", dist: ["viableness", "viablement", "viabilism"] },
        { q: "The author's polemical editorial generated fierce national _____ (controversy).", a: "controversy", dist: ["controversity", "controversal", "controversion"] },
        { q: "The government invoked _____ (precedent) statutory powers during the emergency.", a: "unprecedented", dist: ["nonprecedented", "imprecedented", "disprecedented"] },
        { q: "Academics challenged the implicit epistemological _____ (presume) of the paper.", a: "presumptions", dist: ["presumings", "presumabilities", "presumptionals"] },
        { q: "The private wealth advisor acted with commendable _____ (discreet) during audits.", a: "discretion", dist: ["discreetness", "discreteness", "discretude"] },
        { q: "Technological displacement has resulted in a marked _____ (diminish) of artisan roles.", a: "diminution", dist: ["diminishment", "diminishing", "diminishance"] },
        { q: "Chemical buffers were dispersed into the lake to _____ (neutral) industrial acids.", a: "neutralize", dist: ["neutralate", "neutralify", "neutralism"] },
        { q: "The candidate displayed exceptional natural _____ (apt) for computational analysis.", a: "aptitude", dist: ["aptness", "aptity", "apticism"] },
        { q: "The DNA evidence provided _____ (refute) documentation of the suspect's innocence.", a: "irrefutable", dist: ["unrefutable", "disrefutable", "nonrefutable"] },
        { q: "The university provost emphasized the moral _____ (imperative) of truth in research.", a: "imperative", dist: ["imperativeness", "imperativity", "imperation"] },
        { q: "Runoff from excessive agrochemical spraying caused severe soil _____ (degrade).", a: "degradation", dist: ["degradement", "degradance", "degradity"] },
        { q: "The student struggled with feelings of intellectual _____ (adequacy) around peers.", a: "inadequacy", dist: ["unadequacy", "disadequacy", "nonadequacy"] },
        { q: "The counterfeit luxury items were virtually _____ (distinguish) from originals.", a: "indistinguishable", dist: ["undistinguishable", "disdistinguishable", "distinguishless"] },
        { q: "The regulatory commission penalized the firm for gross operational _____ (manage).", a: "mismanagement", dist: ["dismanagement", "unmanagement", "malmanagement"] },
        { q: "Cumbersome administrative red tape led to chronic institutional _____ (efficient).", a: "inefficiency", dist: ["unefficiency", "disefficiency", "nonefficiency"] },
        { q: "Her sudden, unprompted resignation was a source of endless _____ (perplex).", a: "perplexity", dist: ["perplexment", "perplexness", "perplexion"] },
        { q: "Epidemiologists warned of the potential seasonal _____ (recur) of the pathogen.", a: "recurrence", dist: ["recurrency", "recurrment", "recurration"] },
        { q: "The young activist faced daunting bureaucratic barriers with unwavering _____ (resolute).", a: "resolution", dist: ["resoluteness", "resolvance", "resolvity"] },
        { q: "Her theoretical essays are universally prized for their remarkable prose _____ (lucid).", a: "lucidity", dist: ["lucidness", "lucidance", "lucidation"] },
        { q: "The ombudsman investigated claims of systemic judicial _____ (partial).", a: "partiality", dist: ["partialness", "partiation", "partiment"] }
      ],
      5: [
        { q: "Excessive bureaucratic hyper-specialization breeds profound existential _____ (alien).", a: "alienation", dist: ["alienment", "alienage", "alienism"] },
        { q: "Engineers commended the astonishing thermal _____ (pliable) of the graphene alloy.", a: "pliability", dist: ["pliableness", "pliancy", "pliation"] },
        { q: "The senator's speech was undermined by cynical political _____ (disingenuous).", a: "disingenuousness", dist: ["disingenuity", "disingenuation", "disingenuism"] },
        { q: "Negotiations collapsed due to the rigid diplomatic _____ (transigent) of both factions.", a: "intransigence", dist: ["intransigency", "untransigence", "intransigentness"] },
        { q: "The monograph deconstructs the underlying _____ (epistemology) premises of modern science.", a: "epistemological", dist: ["epistemic", "epistemologian", "epistemologic"] },
        { q: "Satirical street cartoons sought to _____ (legitimate) the ruling junta's authority.", a: "delegitimize", dist: ["unlegitimate", "dislegitimate", "mislegitimate"] },
        { q: "The legal treaty was drafted in hopelessly _____ (labyrinth) syntactic clauses.", a: "labyrinthine", dist: ["labyrinthian", "labyrinthic", "labyrinthous"] },
        { q: "Sociologists noted the startling sociological _____ (incongruous) between policy and practice.", a: "incongruity", dist: ["incongruousness", "incongruence", "incongruation"] },
        { q: "The sudden devaluation of sovereign debt provoked massive macroeconomic _____ (dislocate).", a: "dislocation", dist: ["dislocatement", "dislocance", "dislocity"] },
        { q: "The visionary was haunted by the _____ (phantom) memory of his abandoned invention.", a: "phantasmal", dist: ["phantomic", "phantomness", "phantasm"] },
        { q: "The international tribunal affirmed the legal _____ (null) of the forged treaty.", a: "nullity", dist: ["nullness", "nullification", "nullitance"] },
        { q: "Ethicists debated the persistent moral _____ (equivocal) of autonomous weapons.", a: "equivocality", dist: ["equivocation", "equivocalness", "equivocance"] },
        { q: "The spokesperson engaged in calculated verbal _____ (obfuscate) to baffle reporters.", a: "obfuscation", dist: ["obfuscatement", "obfuscance", "obfuscative"] },
        { q: "The monk sustained philosophical _____ (equable) amidst intense worldly upheaval.", a: "equanimity", dist: ["equableness", "equability", "equamination"] },
        { q: "The agonizing legal dispute led to complete psychological _____ (enervate) for the victim.", a: "enervation", dist: ["enervatement", "enervance", "enervative"] },
        { q: "The antiquity's authentic Mediterranean _____ (provenance) was verified by historians.", a: "provenance", dist: ["provenience", "provent", "provenancy"] },
        { q: "Literary reviewers criticized the mystery novel for uninspired plot _____ (contrive).", a: "contrivance", dist: ["contrivement", "contrivity", "contrivation"] },
        { q: "The tyrannical decrees provoked universal _____ (affect) among former loyalists.", a: "disaffection", dist: ["unaffection", "inaffection", "misaffection"] },
        { q: "The professor warned against intellectual _____ (parochial) in an interconnected era.", a: "parochialism", dist: ["parochiality", "parochialness", "parochiacy"] },
        { q: "Trade pacts depend fundamentally upon the principle of mutual diplomatic _____ (reciprocate).", a: "reciprocity", dist: ["reciprocation", "reciprocalness", "reciprocity"] }
      ]
    },

    "Tenses": {
      1: [
        { q: "My father _____ (work) in a Central bank every Monday to Friday.", a: "works", dist: ["work", "working", "is work"] },
        { q: "Yesterday afternoon, I _____ (visit) my grandparents in Sha Tin.", a: "visited", dist: ["visit", "am visiting", "visits"] },
        { q: "Hark! The little infant _____ (cry) inside the nursery right now.", a: "is crying", dist: ["cries", "cried", "cry"] },
        { q: "Wild swallows usually _____ (build) mud nests high under our eaves.", a: "build", dist: ["builds", "are building", "built"] },
        { q: "Last weekend, my whole class _____ (go) to the Hong Kong Space Museum.", a: "went", dist: ["go", "goes", "are going"] },
        { q: "Look out of the window! It _____ (rain) heavily at this moment.", a: "is raining", dist: ["rains", "rained", "rain"] },
        { q: "A responsible child always _____ (brush) their teeth before bed.", a: "brushes", dist: ["brush", "is brushing", "brushed"] },
        { q: "The neighborhood boys _____ (play) football in the courtyard yesterday.", a: "played", dist: ["plays", "play", "are playing"] },
        { q: "I _____ (be) nine years old this coming September.", a: "am", dist: ["is", "are", "was"] },
        { q: "Our pet cat _____ (catch) a fat grey mouse an hour ago.", a: "caught", dist: ["catches", "catch", "is catching"] },
        { q: "We usually _____ (have) toasted bread and warm milk for breakfast.", a: "have", dist: ["has", "having", "had"] },
        { q: "Little Tommy _____ (not like) eating bitter melon or mustard greens.", a: "does not like", dist: ["do not like", "is not liking", "did not liked"] },
        { q: "Where _____ (do) you put my green ruler yesterday afternoon?", a: "did", dist: ["do", "does", "are"] },
        { q: "The choir pupils _____ (sing) the school hymn on stage right now.", a: "are singing", dist: ["sing", "sings", "sang"] },
        { q: "He quickly _____ (drink) a chilled glass of lemon juice this morning.", a: "drank", dist: ["drinks", "drink", "is drinking"] },
        { q: "As scientists know, planet Earth _____ (move) continuously around the Sun.", a: "moves", dist: ["move", "is moving", "moved"] },
        { q: "My elder sister _____ (bake) a delicious batch of cookies last night.", a: "baked", dist: ["bakes", "bake", "is baking"] },
        { q: "Quiet, please! The headmaster _____ (speak) into the microphone.", a: "is speaking", dist: ["speaks", "spoke", "speak"] },
        { q: "Children in our district _____ (not go) to primary school on Saturdays.", a: "do not go", dist: ["does not go", "are not going", "did not went"] },
        { q: "She _____ (write) a charming card to her penfriend last month.", a: "wrote", dist: ["writes", "write", "is writing"] }
      ],
      2: [
        { q: "I _____ (read) an adventure novel when the room lights suddenly flickered out.", a: "was reading", dist: ["read", "am reading", "have read"] },
        { q: "She has already _____ (finish) calculating every single math problem.", a: "finished", dist: ["finish", "finishing", "finishes"] },
        { q: "Our family _____ (travel) to Hokkaido during the upcoming Christmas break.", a: "will travel", dist: ["traveled", "have traveled", "travel"] },
        { q: "While Tom was studying, his younger brother _____ (play) video games.", a: "was playing", dist: ["played", "is playing", "has played"] },
        { q: "Have you ever _____ (see) a wild pink dolphin in local waters?", a: "seen", dist: ["saw", "see", "seeing"] },
        { q: "We _____ (live) in this residential estate for over seven years now.", a: "have lived", dist: ["lived", "are living", "live"] },
        { q: "He _____ (not finish) packing his sports backpack for tomorrow yet.", a: "has not finished", dist: ["did not finish", "does not finish", "had not finished"] },
        { q: "What _____ (you do) at 9:00 p.m. when I dialed your home telephone?", a: "were you doing", dist: ["did you do", "have you done", "are you doing"] },
        { q: "I firmly believe that our class _____ (win) the inter-house trophy tomorrow.", a: "will win", dist: ["wins", "has won", "won"] },
        { q: "Mr. Wong _____ (teach) mathematics in this school since 2011.", a: "has taught", dist: ["teaches", "taught", "is teaching"] },
        { q: "They were jogging along the promenade when heavy rain _____ (start) falling.", a: "started", dist: ["was starting", "has started", "starts"] },
        { q: "Oh no! She has just accidentally _____ (break) her mother's ceramic vase.", a: "broken", dist: ["broke", "break", "breaking"] },
        { q: "Next term, the school administration _____ (introduce) new coding classes.", a: "will introduce", dist: ["introduced", "has introduced", "introduces"] },
        { q: "How many times _____ (you visit) the Peak Tram this year?", a: "have you visited", dist: ["did you visit", "do you visit", "were you visiting"] },
        { q: "The boys _____ (train) on the football pitch all yesterday afternoon.", a: "were training", dist: ["have trained", "are training", "trained"] },
        { q: "The clumsy boy _____ (lose) his student transit pass twice this month.", a: "has lost", dist: ["lost", "loses", "was losing"] },
        { q: "As soon as the school bell rings, the students _____ (rush) toward the canteen.", a: "will rush", dist: ["rush", "have rushed", "rushed"] },
        { q: "I have not _____ (receive) any postal mail from my cousin in London.", a: "received", dist: ["receive", "receiving", "receives"] },
        { q: "While the chef was searing the steak, the smoke alarm _____ (buzz).", a: "buzzed", dist: ["was buzzing", "has buzzed", "buzzes"] },
        { q: "The Student Council _____ (host) a charity bake sale next Tuesday.", a: "will host", dist: ["hosted", "has hosted", "hosts"] }
      ],
      3: [
        { q: "By the time the fire brigade reached the scene, the blaze _____ (extinguish).", a: "had been extinguished", dist: ["was extinguishing", "has been extinguished", "extinguished"] },
        { q: "If typhoon signal number 8 is hoisted tomorrow, all exams _____ (postpone).", a: "will be postponed", dist: ["are postponed", "would be postponed", "were postponed"] },
        { q: "If I _____ (possess) the master blueprint, I would share it with you.", a: "possessed", dist: ["possess", "had possessed", "would possess"] },
        { q: "The historic cinema hall _____ (demolish) by developers last autumn.", a: "was demolished", dist: ["is demolished", "has been demolished", "had demolished"] },
        { q: "Upon arriving at the exam venue, she realized she _____ (forget) her calculator.", a: "had forgotten", dist: ["forgot", "has forgotten", "was forgetting"] },
        { q: "The annual scholarship _____ (award) to the valedictorian next Friday.", a: "will be awarded", dist: ["is awarded", "was awarded", "has been awarded"] },
        { q: "If the student _____ (review) his lecture notes, he would pass the test.", a: "reviewed", dist: ["reviews", "had reviewed", "would review"] },
        { q: "Forensic auditors found that an unauthorized clerk _____ (alter) the ledgers.", a: "had altered", dist: ["altered", "has altered", "was altering"] },
        { q: "English _____ (speak) by over one billion individuals across the globe.", a: "is spoken", dist: ["speaks", "is speaking", "has spoken"] },
        { q: "Before enrolling in secondary school, she _____ (publish) a poetry chapbook.", a: "had published", dist: ["published", "has published", "was publishing"] },
        { q: "Whenever you heat water past 100 degrees Celsius, it _____ (boil).", a: "boils", dist: ["will boil", "boiled", "would boil"] },
        { q: "Multiple Neolithic ceramic pots _____ (unearth) during the railway works.", a: "were unearthed", dist: ["have unearthed", "are unearthed", "had unearthed"] },
        { q: "The traveler remarked that he _____ (never witness) such glacial beauty before.", a: "had never witnessed", dist: ["has never witnessed", "never witnessed", "was never witnessing"] },
        { q: "If I were the Chief Executive, I _____ (expand) statutory annual leave.", a: "would expand", dist: ["will expand", "expanded", "had expanded"] },
        { q: "The fractured pedestrian footbridge currently _____ (retrofit) by contractors.", a: "is being retrofitted", dist: ["is retrofitted", "was retrofitted", "has retrofitted"] },
        { q: "Hardly had the conductor raised his baton when someone's mobile phone _____ (chime).", a: "chimed", dist: ["had chimed", "chimes", "was chiming"] },
        { q: "Unless you _____ (accelerate) your pace, we will forfeit our flight seats.", a: "accelerate", dist: ["will accelerate", "accelerated", "had accelerated"] },
        { q: "All tickets for the charity gala _____ (sell) out hours before morning.", a: "had been sold", dist: ["were selling", "have been sold", "sold"] },
        { q: "If she _____ (heed) her tutor's advice earlier, she would not be struggling.", a: "had heeded", dist: ["heeded", "heeds", "would heed"] },
        { q: "Strict anti-bullying policies _____ (enforce) in our academy since last year.", a: "have been enforced", dist: ["were enforced", "are enforced", "had enforced"] }
      ],
      4: [
        { q: "Had the public utility company _____ (upgrade) its grids, the blackout would not have occurred.", a: "upgraded", dist: ["upgrade", "would upgrade", "has upgraded"] },
        { q: "By this time next autumn, the postgraduate scholar _____ (defend) her thesis.", a: "will have defended", dist: ["will defend", "defends", "has defended"] },
        { q: "Scarcely _____ (alight) from the aircraft when customs agents approached him.", a: "had he alighted", dist: ["he had alighted", "did he alight", "was he alighting"] },
        { q: "Had you provided prior notification, our administration _____ (reserve) seats for you.", a: "would have reserved", dist: ["will reserve", "reserved", "had reserved"] },
        { q: "By next September, the oceanographers _____ (monitor) this trench for 30 years.", a: "will have been monitoring", dist: ["will monitor", "monitors", "has monitored"] },
        { q: "Never before _____ (human society experience) such interconnected disruption.", a: "has human society experienced", dist: ["human society has experienced", "experienced society", "did society experienced"] },
        { q: "The defendant responded with defiance, speaking as though he _____ (own) the courtroom.", a: "owned", dist: ["owns", "has owned", "is owning"] },
        { q: "Seldom _____ (the school board intervene) in routine pedagogical choices.", a: "does the school board intervene", dist: ["the board intervenes", "did the board intervened", "intervenes the board"] },
        { q: "If the candidate had earned top honors, he _____ (work) in diplomacy today.", a: "would be working", dist: ["would have worked", "had worked", "works"] },
        { q: "By 2035, green power _____ (supplant) traditional coal generators completely.", a: "will have supplanted", dist: ["will supplant", "has supplanted", "supplants"] },
        { q: "Only upon reviewing the archived logs _____ (the programmer discover) the bug.", a: "did the programmer discover", dist: ["the programmer discovered", "had he discovered", "was he discovering"] },
        { q: "It is indispensable that each applicant _____ (furnish) authenticated transcripts.", a: "furnish", dist: ["furnishes", "furnished", "will furnish"] },
        { q: "Little _____ (the executive dream) that corporate fraud investigators were outside.", a: "did the executive dream", dist: ["the executive dreamed", "had he dreamed", "was he dreaming"] },
        { q: "If it _____ (not be) for your emergency loan, our retail startup would have collapsed.", a: "had not been", dist: ["were not", "was not", "would not be"] },
        { q: "By the close of this fiscal quarter, the audit firm _____ (inspect) all branch ledgers.", a: "will have inspected", dist: ["inspected", "will inspect", "has inspected"] },
        { q: "No sooner _____ (the bell sound) than the candidates dropped their pens.", a: "had the bell sounded", dist: ["did the bell sound", "the bell sounded", "was the bell sounding"] },
        { q: "It is high time that legislative authorities _____ (regulate) predatory micro-lending.", a: "regulated", dist: ["regulate", "regulates", "has regulated"] },
        { q: "Should an applicant _____ (encounter) technical anomalies, call the hotline immediately.", a: "encounter", dist: ["encountered", "encounters", "will encounter"] },
        { q: "If we had departed before daybreak, we _____ (not be) caught in this jam now.", a: "would not be", dist: ["would not have been", "were not", "had not been"] },
        { q: "Under no circumstances _____ (employees disclose) client financial profiles.", a: "may employees disclose", dist: ["employees may disclose", "can employees disclosed", "employees disclose"] }
      ],
      5: [
        { q: "Were the sovereign republic _____ (repudiate) its treaty debts, currency contagion would strike.", a: "to repudiate", dist: ["repudiates", "repudiated", "will repudiate"] },
        { q: "The supreme magistrate directed that the defense attorney _____ (retract) the accusation.", a: "retract", dist: ["retracts", "retracted", "has retracted"] },
        { q: "Not until the conclusive forensic dossier emerged _____ (the syndicate yield).", a: "did the syndicate yield", dist: ["the syndicate yielded", "had the syndicate yielded", "was it yielding"] },
        { q: "Had it not been for her strategic acumen, the commercial alliance _____ (disintegrate).", a: "would have disintegrated", dist: ["disintegrated", "would disintegrate", "had disintegrated"] },
        { q: "The regulatory commission recommended that an independent receiver _____ (appoint).", a: "be appointed", dist: ["is appointed", "was appointed", "would be appointed"] },
        { q: "In hindsight, macroeconomic planners _____ (curtail) liquidity during the housing bubble.", a: "ought to have curtailed", dist: ["must curtail", "would curtail", "had curtailed"] },
        { q: "Scarcely _____ (the verdict be read) when furious outcries resonated through the hall.", a: "had the verdict been read", dist: ["was the verdict read", "did the verdict read", "the verdict was read"] },
        { q: "So complex _____ (the treaty stipulations prove) that seasoned diplomats were deadlocked.", a: "did the treaty stipulations prove", dist: ["the stipulations proved", "had they proven", "were they proving"] },
        { q: "Statutory labor mandates insist that every employer _____ (compensate) overtime labor.", a: "compensate", dist: ["compensates", "compensated", "should compensated"] },
        { q: "Had the accord passed ratification in spring, tax harmonizations _____ (take) effect today.", a: "would be taking", dist: ["would have taken", "took", "had taken"] },
        { q: "Rarely _____ (a classical composition evoke) such unanimous awe among austere critics.", a: "has a classical composition evoked", dist: ["a composition has evoked", "did it evoked", "it evoked"] },
        { q: "The international tribunal decreed that the junta _____ (surrender) all captured hostages.", a: "surrender", dist: ["surrenders", "surrendered", "has surrendered"] },
        { q: "Only when public records were formally declassified _____ (the geopolitical scandal unravel).", a: "did the geopolitical scandal unravel", dist: ["the scandal unraveled", "had it unraveled", "was it unraveling"] },
        { q: "Lest the delicate cease-fire _____ (jeopardize), all reconnaissance flights were grounded.", a: "be jeopardized", dist: ["is jeopardized", "was jeopardized", "would be jeopardized"] },
        { q: "Much though the minister _____ (endeavor) to obfuscate his involvement, emails convicted him.", a: "endeavored", dist: ["endeavors", "has endeavored", "had endeavored"] },
        { q: "Were the director _____ (withdraw) her abrupt resignation, the company would recover.", a: "to withdraw", dist: ["withdrew", "withdraws", "has withdrawn"] },
        { q: "Charter bylaws demand that internal accounts _____ (audit) annually by external certifiers.", a: "be audited", dist: ["is audited", "was audited", "will be audited"] },
        { q: "Had the navigators recognized the ice floe's extent, they _____ (not enter) the channel.", a: "would not have entered", dist: ["did not enter", "had not entered", "would not enter"] },
        { q: "Hardly _____ (the treaty ink dried) when border skirmishes ignited once more.", a: "had the treaty ink dried", dist: ["did the ink dry", "the ink dried", "was the ink dried"] },
        { q: "It is strictly required that the biosecurity personnel _____ (maintain) full PPE suits.", a: "maintain", dist: ["maintains", "maintained", "must maintain"] }
      ]
    },

    "Articles": {
      1: [
        { q: "I enjoyed eating _____ sweet red apple after school today.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "There is _____ fluffy orange cat sitting quietly by our front porch.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "Look up at _____ bright yellow sun shining over Victoria Peak!", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "It looks like rain, so carry _____ sturdy umbrella with you.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "She bought _____ interesting illustrated comic book yesterday.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "Many international business firms are located on _____ Hong Kong Island.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "Could you please hand me _____ red crayon lying by your elbow?", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "My uncle drives _____ vintage green sedan on weekends.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "Every morning, I drink _____ tall glass of fresh milk.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "Remember to switch off _____ television before heading to sleep.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "My grandmother packed _____ juicy orange for my afternoon snack.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "Do your classmates enjoy playing _____ badminton after school?", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The animal shelter volunteers rescued _____ adorable stray puppy.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "Tonight, _____ luminous moon looks completely round and clear.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "My cousin wants to become _____ honest and brave police officer.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "Each primary student must wear _____ clean uniform to assembly.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "During summer break, our family explored _____ Ocean Park.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "Please unlock _____ front entrance gate for the mailman.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "The challenging spelling test took _____ full hour to complete.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "I enjoy relaxing while listening to _____ classical piano music.", a: "[No Article]", dist: ["the", "a", "an"] }
      ],
      2: [
        { q: "My younger sister practices playing _____ acoustic guitar every evening.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "_____ Atlantic Ocean separates North America from Western Europe.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "Our family spent two wonderful weeks backpacking across _____ Germany.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The ambitious boy dreams of becoming _____ aerospace engineer.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "Nutritionists agree that _____ breakfast fuels active learners.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "Tourists took scenic snapshots overlooking _____ Victoria Harbour.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "Mount Everest is officially celebrated as _____ highest peak on Earth.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "Exhausted after sports practice, he collapsed straight into _____ bed.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "_____ United States consists of fifty individual states.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "We spent the weekend at _____ seaside hotel overlooking the bay.", a: "a", dist: ["the", "an", "[No Article]"] },
        { q: "She excels at _____ competitive swimming in inter-school galas.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "_____ blue whale is celebrated as the largest mammal to have existed.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "Bedouin nomads journeyed through _____ Gobi Desert with pack animals.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "Because of a severe fever, he stayed in _____ bed with medicine.", a: "[No Article]", dist: ["a", "the", "an"] },
        { q: "_____ spring water bottled from alpine glaciers is remarkably pure.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "Her brother graduated with honors from _____ Chinese University of Hong Kong.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "Do you happen to carry _____ spare pen that I might borrow?", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "The faithful congregation gathered at _____ church for Sunday mass.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "_____ Amazon River carries the greatest water discharge in the world.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "The veteran teacher gave me _____ constructive advice on essay structure.", a: "[No Article]", dist: ["a", "an", "the"] }
      ],
      3: [
        { q: "_____ immense generosity shown by local donors rebuilt the school clinic.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "He was unanimously selected as _____ head prefect for this academic year.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The convicted burglar was sentenced to _____ prison for five years.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "Social caseworkers visited _____ prison to evaluate rehabilitation classes.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "Philosophers note that _____ knowledge dispels superstition and fear.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "She holds _____ Swiss passport and travels extensively without visas.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "The clinic treated patients experiencing _____ acute shortage of medical fluids.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "The Sherpa guide led the expedition across _____ Himalayas safely.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "_____ rampant inflation continues to diminish consumers' buying power.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "She was appointed _____ director of the regional humanities council.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "He demonstrated _____ astonishing understanding of theoretical astrophysics.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "_____ Netherlands is globally celebrated for water management systems.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "Literary critics often praise _____ exquisite lyrical beauty of Tang poetry.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "The injured motorist was transported swiftly to _____ hospital by ambulance.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The concerned father visited _____ school to consult his son's tutor.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "Many artists believe that _____ modern life moves at too frantic a tempo.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The boutique features garments with _____ unique blend of silk and linen.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "Global leaders must protect _____ biosphere from uncontrolled toxic dumping.", a: "the", dist: ["an", "a", "[No Article]"] },
        { q: "He booked _____ one-way train ticket from Paris to Vienna.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "Eliminating _____ extreme poverty remains the foremost UN development goal.", a: "[No Article]", dist: ["the", "a", "an"] }
      ],
      4: [
        { q: "_____ printing press revolutionized the spread of literacy across Europe.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "She graduated from Oxford with _____ Master of Science in Economics.", a: "a", dist: ["an", "the", "[No Article]"] },
        { q: "Fiscal policies should ensure that _____ wealthy shoulder progressive taxation.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "Ethical inquiries surrounding _____ gene editing demand public transparency.", a: "[No Article]", dist: ["the", "an", "a"] },
        { q: "Biographers described the physicist as _____ Einstein of genomic sequencing.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "The peace conference was hosted under _____ auspices of international mediators.", a: "the", dist: ["an", "a", "[No Article]"] },
        { q: "The council demonstrated _____ unprecedented degree of fiscal austerity.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "_____ Philippines is home to extraordinary marine coral biodiversity.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "He served in _____ capacity of senior legal counsel during the arbitration.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "She harbors _____ profound aversion to sensationalist media gossip.", a: "a", dist: ["the", "an", "[No Article]"] },
        { q: "Depletion of _____ stratospheric ozone layer permits excessive ultraviolet radiation.", a: "the", dist: ["an", "a", "[No Article]"] },
        { q: "Bilateral relations must be resolved at _____ ministerial level.", a: "a", dist: ["the", "an", "[No Article]"] },
        { q: "Submersible crafts descended into _____ abyssal depths of the trench.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "The executive declined to accept _____ blame for the supply chain breakdown.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "It required _____ courage of steel to expose corporate embezzlement.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "She was awarded _____ OBE for services rendered to youth social work.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "_____ Industrial Revolution transformed agrarian cultures into urban states.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "The fleeing war criminal was judged in _____ absentia by the tribunal.", a: "[No Article]", dist: ["the", "an", "a"] },
        { q: "Financial planners must weigh _____ long-term merits and demerits of the bond.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "She displayed _____ instinctive empathy that endeared her to hospice patients.", a: "an", dist: ["the", "a", "[No Article]"] }
      ],
      5: [
        { q: "The board gave the managing director _____ carte blanche to overhaul management.", a: "[No Article]", dist: ["a", "the", "an"] },
        { q: "The forged treaty was ruled _____ complete legal nullity by the world court.", a: "a", dist: ["the", "an", "[No Article]"] },
        { q: "The protesters marched in _____ open defiance of the martial decree.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The distinguished chemist was conferred _____ honorary doctorate by Cambridge.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "The judicial panel retired in _____ camera to examine classified state secrets.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The author's essay conveys _____ raw emotional vigor rarely seen in modern criticism.", a: "a", dist: ["the", "an", "[No Article]"] },
        { q: "The rebellious regiment resigned en _____ masse following the decree.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "_____ Hague serves as the historic administrative capital of global arbitration.", a: "The", dist: ["A", "An", "[No Article]"] },
        { q: "Ancient manuscripts were digitized and preserved for _____ posterity.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The fearless whistleblower spoke out at _____ peril of his career and freedom.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "The draconian quota met with _____ fierce opposition across maritime ports.", a: "[No Article]", dist: ["a", "the", "an"] },
        { q: "The scholar demonstrated _____ encyclopedic mastery over Roman jurisprudence.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "Volunteers stood shoulder to _____ shoulder constructing flood defense walls.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The disgraced attache was designated persona non _____ grata by the foreign ministry.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The witness claimed she was overseas at _____ material time of the burglary.", a: "the", dist: ["a", "an", "[No Article]"] },
        { q: "The young pianist showed _____ remarkable flair for polyphonic improvisation.", a: "a", dist: ["the", "an", "[No Article]"] },
        { q: "The military dictator ruled the subjugated province with _____ iron fist.", a: "an", dist: ["a", "the", "[No Article]"] },
        { q: "The DNA findings established his total innocence beyond _____ shadow of a doubt.", a: "a", dist: ["the", "an", "[No Article]"] },
        { q: "Naval destroyers kept pirate vessels at _____ bay throughout the shipping corridor.", a: "[No Article]", dist: ["the", "a", "an"] },
        { q: "The two warring states attained _____ historic rapprochement after summit talks.", a: "a", dist: ["the", "an", "[No Article]"] }
      ]
    },

    "Plurals": {
      1: [
        { q: "Grandmother bought six crunchy red _____ (apple) at the morning market.", a: "apples", dist: ["applees", "applis", "applese"] },
        { q: "The wooden carpenter built four sturdy _____ (box) to store heavy tools.", a: "boxes", dist: ["boxs", "boxies", "boxen"] },
        { q: "The mother cat is nursing four tiny white _____ (kitten) in her basket.", a: "kittens", dist: ["kittenes", "kittenies", "kittenss"] },
        { q: "Dentists recommend cleaning your _____ (tooth) after breakfast and dinner.", a: "teeth", dist: ["tooths", "toothes", "teethes"] },
        { q: "The amusement park is filled with joyful, laughing _____ (child).", a: "children", dist: ["childs", "childrens", "childes"] },
        { q: "Please dry these ceramic _____ (dish) with a clean tea towel.", a: "dishes", dist: ["dishs", "dishies", "dishex"] },
        { q: "The mountain shepherd herds thirty woolly _____ (sheep) across the green valley.", a: "sheep", dist: ["sheeps", "sheepes", "sheepies"] },
        { q: "After wading in the icy brook, both of his _____ (foot) were completely numb.", a: "feet", dist: ["foots", "feets", "footies"] },
        { q: "Our teacher lent us three fascinating story _____ (book) for holiday reading.", a: "books", dist: ["bookes", "bookies", "booken"] },
        { q: "The salad bowl contains diced cucumbers and fresh red _____ (tomato).", a: "tomatoes", dist: ["tomatos", "tomatoies", "tomati"] },
        { q: "Two polite young _____ (man) offered their bus seats to the elderly passenger.", a: "men", dist: ["mans", "manes", "mens"] },
        { q: "She blew out all eight wax _____ (candle) on her birthday cake.", a: "candles", dist: ["candlees", "candlis", "candlez"] },
        { q: "The farm cat chased two swift brown _____ (mouse) behind the grain bags.", a: "mice", dist: ["mouses", "mices", "mouseies"] },
        { q: "The tropical parrot displayed splendid blue and green _____ (feather).", a: "feathers", dist: ["featheres", "featheries", "feathern"] },
        { q: "We placed four tall drinking _____ (glass) on the dining table.", a: "glasses", dist: ["glasss", "glassies", "glassen"] },
        { q: "In late autumn, gold and crimson _____ (leaf) flutter from the trees.", a: "leaves", dist: ["leafs", "leafes", "leavies"] },
        { q: "The pond is home to nine vibrant orange koi _____ (fish).", a: "fish", dist: ["fishes", "fishs", "fishies"] },
        { q: "The maternity ward nurses cared tenderly for six newborn _____ (baby).", a: "babies", dist: ["babys", "babyes", "babi"] },
        { q: "Please sharpen these five colored drawing _____ (pencil) for art class.", a: "pencils", dist: ["penciles", "pencilies", "pencilz"] },
        { q: "Three distinguished _____ (woman) delivered speeches at the school assembly.", a: "women", dist: ["womans", "womens", "womanes"] }
      ],
      2: [
        { q: "The pack of hungry grey _____ (wolf) prowled silently through the snowy pines.", a: "wolves", dist: ["wolfs", "wolfes", "wolvies"] },
        { q: "The artisan bakery prepared thirty golden _____ (loaf) of French sourdough.", a: "loaves", dist: ["loafs", "loafes", "loavs"] },
        { q: "Set the silverware neatly with spoons, forks, and steak _____ (knife).", a: "knives", dist: ["knifes", "knifees", "knivs"] },
        { q: "Heavy storms tore clay shingles from several cottage _____ (roof).", a: "roofs", dist: ["rooves", "roofes", "roofies"] },
        { q: "The bank branch stores currency securely inside two fireproof _____ (safe).", a: "safes", dist: ["saves", "safees", "savies"] },
        { q: "Two masked _____ (thief) broke into the electronics store past midnight.", a: "thieves", dist: ["thiefs", "thiefes", "thievs"] },
        { q: "A formation of wild migratory _____ (goose) flew southward across the sky.", a: "geese", dist: ["gooses", "geeses", "goosies"] },
        { q: "Hundreds of enthusiastic _____ (person) queued outside for concert tickets.", a: "people", dist: ["persons", "peoples", "persones"] },
        { q: "The study room is lined with tall pine _____ (shelf) holding classic literature.", a: "shelves", dist: ["shelfs", "shelfes", "shelvies"] },
        { q: "Tokyo and Kyoto are two of the most visited _____ (city) in Japan.", a: "cities", dist: ["citys", "cityes", "citiez"] },
        { q: "The zoo keeper tossed ripe sweet _____ (banana) to the chimpanzees.", a: "bananas", dist: ["bananaes", "banani", "bananaz"] },
        { q: "Desert merchants loaded silk bundles onto kneeling _____ (camel).", a: "camels", dist: ["cameles", "camelis", "camelz"] },
        { q: "Tourists watched the playful macaque _____ (monkey) swinging in the trees.", a: "monkeys", dist: ["monkies", "monkeyes", "monkeyz"] },
        { q: "The commercial corporation operates seventeen branch _____ (office) globally.", a: "offices", dist: ["officees", "officis", "officen"] },
        { q: "Landslides deposited massive limestone _____ (rock) across the highway.", a: "rocks", dist: ["rockes", "rockies", "rockz"] },
        { q: "Marine biologists studied two endangered _____ (species) of coral trout.", a: "species", dist: ["specie", "specieses", "specii"] },
        { q: "The mountaineers laced their heavy leather climbing _____ (boot).", a: "boots", dist: ["bootes", "booties", "booten"] },
        { q: "How many orchestral brass _____ (instrument) can you name correctly?", a: "instruments", dist: ["instrumentes", "instrumenties", "instrumentz"] },
        { q: "Our shouts generated strange and eerie _____ (echo) in the limestone cavern.", a: "echoes", dist: ["echos", "echoies", "echoen"] },
        { q: "The local _____ (police) were dispatched immediately to direct traffic.", a: "police", dist: ["polices", "policemen", "policers"] }
      ],
      3: [
        { q: "The republic persevered despite weathering multiple acute banking _____ (crisis).", a: "crises", dist: ["crisises", "crisi", "crisisen"] },
        { q: "Astrophysicists documented spectacular celestial _____ (phenomenon) with telescopes.", a: "phenomena", dist: ["phenomenons", "phenomenae", "phenomenas"] },
        { q: "The scholarship board published rigorous assessment _____ (criterion) online.", a: "criteria", dist: ["criterions", "criterias", "criterium"] },
        { q: "The desert greenhouse features rare varieties of flowering _____ (cactus).", a: "cacti", dist: ["cactuses", "cacta", "cactae"] },
        { q: "The university faculty reformed their secondary school _____ (curriculum).", a: "curricula", dist: ["curriculums", "curriculi", "curriculae"] },
        { q: "Students plotted algebraic coordinates along both horizontal and vertical _____ (axis).", a: "axes", dist: ["axises", "axi", "axen"] },
        { q: "Statistical _____ (datum) collected from five thousand clinics confirmed the trend.", a: "data", dist: ["datums", "datas", "dati"] },
        { q: "The forest mycologist classified several rare subterranean _____ (fungus).", a: "fungi", dist: ["funguses", "funga", "fungae"] },
        { q: "The economic research journal published three comparative _____ (analysis).", a: "analyses", dist: ["analysises", "analysi", "analysen"] },
        { q: "Graduate scholars defended their doctoral _____ (thesis) before the academic panel.", a: "theses", dist: ["thesises", "thesi", "thesen"] },
        { q: "The collegiate hall welcomed thousands of distinguished university _____ (alumnus).", a: "alumni", dist: ["alumnuses", "alumnae", "alumnas"] },
        { q: "The geometer calculated the lengths of intersecting circle _____ (radius).", a: "radii", dist: ["radiuses", "radia", "radiae"] },
        { q: "Caravans paused to rest near fertile freshwater _____ (oasis) across the Sahara.", a: "oases", dist: ["oasises", "oasi", "oasen"] },
        { q: "The team formulated three distinct scientific _____ (hypothesis) to explain the data.", a: "hypotheses", dist: ["hypothesises", "hypothesi", "hypothesen"] },
        { q: "The marine exhibit displays reef-dwelling giant _____ (octopus) in coral tanks.", a: "octopuses", dist: ["octopi", "octopodes", "octopa"] },
        { q: "Review the statistical graphs placed in the book's supplementary _____ (appendix).", a: "appendices", dist: ["appendixes", "appendici", "appendixa"] },
        { q: "Optometrists examined high-magnification ocular _____ (lens) in the lab.", a: "lenses", dist: ["lens", "lenseses", "lensi"] },
        { q: "Excavators uncovered ancient marble sacrificial _____ (altar) inside the ruins.", a: "altars", dist: ["altares", "altari", "altarium"] },
        { q: "The orthopedist checked for spinal misalignment across several cervical _____ (vertebra).", a: "vertebrae", dist: ["vertebras", "vertebri", "vertebrata"] },
        { q: "Modern broadcast and digital news _____ (medium) shape public opinion.", a: "media", dist: ["mediums", "medias", "medii"] }
      ],
      4: [
        { q: "The specialized research laboratory ordered five electronic testing _____ (apparatus).", a: "apparatus", dist: ["apparatuses", "apparati", "apparata"] },
        { q: "The defendant retained two senior Queen's _____ (counsel) for the trial.", a: "counsel", dist: ["counsels", "counselors", "counseles"] },
        { q: "Travelers boarded the coach carrying seven leather duffel _____ (bag).", a: "bags", dist: ["baggages", "baggage", "bagges"] },
        { q: "The international aviation fleet operates fifty commercial supersonic _____ (aircraft).", a: "aircraft", dist: ["aircrafts", "aircraftes", "aircraften"] },
        { q: "Hikers in the Scottish Highlands caught sight of four red _____ (deer) grazing.", a: "deer", dist: ["deers", "deeres", "deeries"] },
        { q: "The heritage museum preserves traditional woven silk and cotton _____ (textile).", a: "textiles", dist: ["textilia", "textilies", "textilz"] },
        { q: "The IT department purchased state-of-the-art server _____ (equipment).", a: "equipment", dist: ["equipments", "equipmentes", "equipmentz"] },
        { q: "The monastic archive houses several illuminated medieval _____ (manuscript).", a: "manuscripts", dist: ["manuscripta", "manuscriptex", "manuscripten"] },
        { q: "Biologists examined single-celled aquatic _____ (protozoan) in pond water.", a: "protozoa", dist: ["protozoans", "protozoas", "protozoon"] },
        { q: "The board of directors circulated three confidential executive _____ (memorandum).", a: "memoranda", dist: ["memorandums", "memorandi", "memorandae"] },
        { q: "The mighty river is replenished by four rushing mountain _____ (tributary).", a: "tributaries", dist: ["tributarys", "tributaryes", "tributarii"] },
        { q: "The sculpture garden displays magnificent bronze and granite _____ (sculpture).", a: "sculptures", dist: ["sculptura", "sculpturies", "sculpturez"] },
        { q: "Geologists analyzed sedimentary rock _____ (stratum) spanning millions of years.", a: "strata", dist: ["stratums", "strati", "stratas"] },
        { q: "Engineers computed eigenvalues across four complex mathematical _____ (matrix).", a: "matrices", dist: ["matrixes", "matrici", "matrixen"] },
        { q: "Faculty deans revised the collegiate course _____ (syllabus) for the new term.", a: "syllabi", dist: ["syllabuses", "syllaba", "syllabum"] },
        { q: "The soccer player suffered severe trauma to both of his _____ (knee).", a: "knees", dist: ["knee", "kneees", "kneen"] },
        { q: "Archeologists excavated decorative Grecian funeral _____ (urn) filled with ashes.", a: "urns", dist: ["urnes", "urni", "urnen"] },
        { q: "Guild houses employed scores of skilled stone and wood _____ (craftsman).", a: "craftsmen", dist: ["craftsmans", "craftsmens", "craftsmanes"] },
        { q: "The rancher grazes a herd of over two hundred dairy _____ (cattle).", a: "cattle", dist: ["cattles", "cattlen", "cattlex"] },
        { q: "Microbiologists studied the dividing atomic and cellular _____ (nucleus).", a: "nuclei", dist: ["nucleuses", "nuclea", "nucleis"] }
      ],
      5: [
        { q: "The ecclesiastical council scrutinized orthodox theological _____ (dogma) of the era.", a: "dogmata", dist: ["dogmas", "dogmi", "dogmae"] },
        { q: "Cognitive psychologists categorized internal interpretive _____ (schema) in memory.", a: "schemata", dist: ["schemas", "schemi", "schematae"] },
        { q: "Botanists catalogued reproductive floral _____ (stigma) across rare orchid species.", a: "stigmata", dist: ["stigmas", "stigmi", "stigmae"] },
        { q: "Numismatists inspected ancient Roman copper bronze _____ (as) coins in glass cases.", a: "asses", dist: ["ases", "assi", "asa"] },
        { q: "Geometric proofs require plotting intersecting spatial _____ (locus) of points.", a: "loci", dist: ["locuses", "loca", "locae"] },
        { q: "Medieval physicians attributed plague epidemics to toxic swamp _____ (miasma).", a: "miasmata", dist: ["miasmas", "miasmi", "miasmae"] },
        { q: "Historical linguists traced underlying semantic _____ (lexeme) across Romance dialects.", a: "lexemes", dist: ["lexema", "lexemi", "lexemata"] },
        { q: "Bronze Age archeologists recovered ornate burial garment _____ (fibula) from tombs.", a: "fibulae", dist: ["fibulas", "fibuli", "fibulis"] },
        { q: "Philosophers scrutinized perplexing ethical and political _____ (paradox).", a: "paradoxes", dist: ["paradoxa", "paradoxi", "paradoxen"] },
        { q: "The historic folio featured delicate floral decorative _____ (vignette).", a: "vignettes", dist: ["vignetti", "vignetta", "vignettos"] },
        { q: "Early kinetic clockmakers crafted intricate mechanical _____ (automaton).", a: "automata", dist: ["automatons", "automati", "automatae"] },
        { q: "Deep-space observatories photographed iridescent stellar _____ (nebula).", a: "nebulae", dist: ["nebulas", "nebuli", "nebulata"] },
        { q: "Astronomical charts map the trajectories of eccentric solar _____ (comet).", a: "comets", dist: ["cometa", "cometae", "cometia"] },
        { q: "The treaty editors appended extensive contractual _____ (addendum) to the protocol.", a: "addenda", dist: ["addendums", "addendi", "addendae"] },
        { q: "Comparative grammarians examined case _____ (inflection) across Germanic languages.", a: "inflections", dist: ["inflexions", "inflectia", "inflecti"] },
        { q: "Fungal mycelium networks sprout branching subterranean _____ (mycelium) colonies.", a: "mycelia", dist: ["myceliums", "mycelii", "mycelias"] },
        { q: "The government ombudsman processed dozens of formal public _____ (enquiry).", a: "enquiries", dist: ["enquirys", "enquiryes", "enquiria"] },
        { q: "The coronation hall displayed glittering imperial crown _____ (regalia).", a: "regalia", dist: ["regalias", "regalium", "regalii"] },
        { q: "The legal board archived official bilateral summit _____ (memorandum).", a: "memoranda", dist: ["memorandums", "memorandi", "memorandae"] },
        { q: "Biophysicists simulated the mechanical torsion of twin DNA _____ (helix).", a: "helices", dist: ["helixs", "helixes", "helica"] }
      ]
    },

    "Synonyms": {
      1: [
        { q: "Select the closest synonym for 'happy': The boy had a _____ smile.", a: "cheerful", dist: ["gloomy", "furious", "weary"] },
        { q: "Select the closest synonym for 'large': They saw a _____ elephant.", a: "huge", dist: ["tiny", "slender", "shallow"] },
        { q: "Select the closest synonym for 'fast': The rabbit was a _____ runner.", a: "quick", dist: ["slow", "clumsy", "sluggish"] },
        { q: "Select the closest synonym for 'smart': She is an extremely _____ student.", a: "clever", dist: ["foolish", "lazy", "dull"] },
        { q: "Select the closest synonym for 'begin': Class will _____ at nine.", a: "start", dist: ["finish", "halt", "pause"] },
        { q: "Select the closest synonym for 'quiet': The library is very _____ today.", a: "silent", dist: ["noisy", "rowdy", "loud"] },
        { q: "Select the closest synonym for 'simple': This is an _____ math puzzle.", a: "easy", dist: ["tough", "tricky", "complex"] },
        { q: "Select the closest synonym for 'brave': The firefighter was very _____.", a: "courageous", dist: ["fearful", "timid", "nervous"] },
        { q: "Select the closest synonym for 'tidy': Please keep your bedroom _____.", a: "neat", dist: ["messy", "dirty", "chaotic"] },
        { q: "Select the closest synonym for 'rich': The king was incredibly _____.", a: "wealthy", dist: ["poor", "needy", "destitute"] },
        { q: "Select the closest synonym for 'help': Friends should _____ one another.", a: "assist", dist: ["hinder", "block", "ignore"] },
        { q: "Select the closest synonym for 'small': He lives in a _____ cottage.", a: "little", dist: ["giant", "vast", "broad"] },
        { q: "Select the closest synonym for 'angry': The driver was _____ at the delay.", a: "mad", dist: ["pleased", "calm", "joyful"] },
        { q: "Select the closest synonym for 'scared': The kitten was _____ of the thunder.", a: "frightened", dist: ["bold", "daring", "proud"] },
        { q: "Select the closest synonym for 'correct': All his quiz answers were _____.", a: "right", dist: ["wrong", "false", "flawed"] },
        { q: "Select the closest synonym for 'ill': She stayed home because she was _____.", a: "sick", dist: ["healthy", "robust", "fit"] },
        { q: "Select the closest synonym for 'hard': Diamond is an exceptionally _____ stone.", a: "tough", dist: ["soft", "tender", "brittle"] },
        { q: "Select the closest synonym for 'shout': Don't _____ in the hallway.", a: "yell", dist: ["whisper", "mumble", "murmur"] },
        { q: "Select the closest synonym for 'gift': He unwrapped his birthday _____.", a: "present", dist: ["debt", "penalty", "chore"] },
        { q: "Select the closest synonym for 'tasty': My mother baked a _____ cake.", a: "delicious", dist: ["bland", "sour", "bitter"] }
      ],
      2: [
        { q: "Choose the synonym for 'generous': The merchant was praised for his _____ donations.", a: "benevolent", dist: ["stingy", "miserly", "greedy"] },
        { q: "Choose the synonym for 'accurate': The scientist gave an _____ measurement.", a: "exact", dist: ["vague", "faulty", "distorted"] },
        { q: "Choose the synonym for 'brief': The captain delivered a _____ briefing.", a: "concise", dist: ["lengthy", "tedious", "rambling"] },
        { q: "Choose the synonym for 'hazardous': Climbing that icy peak is highly _____.", a: "perilous", dist: ["safe", "secure", "sheltered"] },
        { q: "Choose the synonym for 'furious': The customer became completely _____.", a: "enraged", dist: ["ecstatic", "content", "placid"] },
        { q: "Choose the synonym for 'ancient': Archeologists found an _____ vessel.", a: "antique", dist: ["modern", "novel", "contemporary"] },
        { q: "Choose the synonym for 'exhausted': Running twenty miles left him _____.", a: "fatigued", dist: ["refreshed", "energetic", "lively"] },
        { q: "Choose the synonym for 'valuable': The museum preserves _____ artifacts.", a: "precious", dist: ["worthless", "trivial", "shabby"] },
        { q: "Choose the synonym for 'diligent': The honors student was remarkably _____.", a: "hardworking", dist: ["slothful", "indolent", "careless"] },
        { q: "Choose the synonym for 'hostile': The wild canine behaved in an _____ manner.", a: "aggressive", dist: ["friendly", "sociable", "docile"] },
        { q: "Choose the synonym for 'vivid': She painted a _____ portrait of life.", a: "graphic", dist: ["dull", "faint", "obscure"] },
        { q: "Choose the synonym for 'prosperous': The trading port grew increasingly _____.", a: "thriving", dist: ["bankrupt", "decaying", "poor"] },
        { q: "Choose the synonym for 'candid': The politician gave a _____ interview.", a: "frank", dist: ["deceptive", "evasive", "sly"] },
        { q: "Choose the synonym for 'fragile': Please take care of this _____ porcelain.", a: "delicate", dist: ["sturdy", "unbreakable", "solid"] },
        { q: "Choose the synonym for 'abundant': Tropical jungles feature _____ rain.", a: "plentiful", dist: ["scarce", "scant", "sparse"] },
        { q: "Choose the synonym for 'gloomy': The sky looked dark and _____ before dawn.", a: "dreary", dist: ["radiant", "luminous", "sunny"] },
        { q: "Choose the synonym for 'peculiar': We heard a _____ noise in the cellar.", a: "strange", dist: ["customary", "typical", "normal"] },
        { q: "Choose the synonym for 'foster': Teachers aim to _____ critical thinking.", a: "encourage", dist: ["suppress", "inhibit", "dampen"] },
        { q: "Choose the synonym for 'authentic': The gallery authenticated the _____ painting.", a: "genuine", dist: ["fake", "counterfeit", "forged"] },
        { q: "Choose the synonym for 'rigid': The instructor enforced _____ rules.", a: "strict", dist: ["flexible", "lenient", "elastic"] }
      ],
      3: [
        { q: "Identify the synonym for 'subsequent': _____ reports verified the trend.", a: "following", dist: ["prior", "preceding", "antecedent"] },
        { q: "Identify the synonym for 'scrutinize': Detectives will _____ every receipt.", a: "examine", dist: ["glance", "overlook", "ignore"] },
        { q: "Identify the synonym for 'feasible': The committee considered whether it was _____.", a: "viable", dist: ["impossible", "impractical", "futile"] },
        { q: "Identify the synonym for 'apprehensive': Candidates felt _____ before the oral.", a: "anxious", dist: ["confident", "serene", "nonchalant"] },
        { q: "Identify the synonym for 'detrimental': Excessive screen glare is _____ to sleep.", a: "harmful", dist: ["salutary", "beneficial", "benign"] },
        { q: "Identify the synonym for 'impartial': The arbitrator rendered an _____ verdict.", a: "unbiased", dist: ["prejudiced", "skewed", "partisan"] },
        { q: "Identify the synonym for 'monotonous': Repeating lines was hopelessly _____.", a: "tedious", dist: ["riveting", "varied", "thrilling"] },
        { q: "Identify the synonym for 'reluctant': The witness seemed _____ to testify.", a: "unwilling", dist: ["eager", "enthusiastic", "keen"] },
        { q: "Identify the synonym for 'pivotal': The general made a _____ tactical choice.", a: "crucial", dist: ["incidental", "peripheral", "minor"] },
        { q: "Identify the synonym for 'conspicuous': The bright red warning was clearly _____.", a: "noticeable", dist: ["subtle", "covert", "hidden"] },
        { q: "Identify the synonym for 'mitigate': Planting trees helps _____ urban heat.", a: "alleviate", dist: ["intensify", "worsen", "aggravate"] },
        { q: "Identify the synonym for 'ambiguous': The statement's phrasing was overly _____.", a: "equivocal", dist: ["explicit", "clear", "definite"] },
        { q: "Identify the synonym for 'resilient': The local economy proved remarkably _____.", a: "durable", dist: ["frail", "vulnerable", "fragile"] },
        { q: "Identify the synonym for 'inevitable': Climate changes made the shift _____.", a: "unavoidable", dist: ["evadable", "uncertain", "preventable"] },
        { q: "Identify the synonym for 'plausible': Her story provided a _____ rationale.", a: "credible", dist: ["implausible", "far-fetched", "absurd"] },
        { q: "Identify the synonym for 'sporadic': We experienced _____ showers all week.", a: "intermittent", dist: ["incessant", "continuous", "constant"] },
        { q: "Identify the synonym for 'superficial': The critic only made _____ commentary.", a: "shallow", dist: ["profound", "penetrating", "deep"] },
        { q: "Identify the synonym for 'perpetual': The clock runs on an almost _____ cycle.", a: "ceaseless", dist: ["ephemeral", "fleeting", "transient"] },
        { q: "Identify the synonym for 'formidable': The defending champions are a _____ team.", a: "daunting", dist: ["puny", "feeble", "weak"] },
        { q: "Identify the synonym for 'indispensable': Water is _____ to biological life.", a: "essential", dist: ["redundant", "superfluous", "optional"] }
      ],
      4: [
        { q: "Choose the DSE Paper 1 synonym for 'ubiquitous': Smartphones have become _____.", a: "omnipresent", dist: ["rare", "sporadic", "localized"] },
        { q: "Choose the synonym for 'disparate': The symposium assembled _____ perspectives.", a: "divergent", dist: ["homogeneous", "identical", "uniform"] },
        { q: "Choose the synonym for 'ameliorate': The program aimed to _____ living conditions.", a: "improve", dist: ["exacerbate", "deteriorate", "impair"] },
        { q: "Choose the synonym for 'pragmatic': Leaders must adopt a _____ fiscal posture.", a: "realistic", dist: ["idealistic", "quixotic", "speculative"] },
        { q: "Choose the synonym for 'lucid': Her treatise was celebrated for its _____ clarity.", a: "articulate", dist: ["opaque", "convoluted", "muddled"] },
        { q: "Choose the synonym for 'ephemeral': Internet celebrity is notoriously _____.", a: "transitory", dist: ["eternal", "perpetual", "abiding"] },
        { q: "Choose the synonym for 'ubiquity': The company leveraged the _____ of mobile tech.", a: "pervasiveness", dist: ["scarcity", "rarity", "dearth"] },
        { q: "Choose the synonym for 'preclude': Legal clauses _____ unauthorized redistribution.", a: "prevent", dist: ["facilitate", "foster", "permit"] },
        { q: "Choose the synonym for 'exemplary': The senior prefect displayed _____ decorum.", a: "meritorious", dist: ["deplorable", "flawed", "substandard"] },
        { q: "Choose the synonym for 'adversary': She shook hands with her courtroom _____.", a: "opponent", dist: ["confederate", "ally", "sponsor"] },
        { q: "Choose the synonym for 'reticent': The suspect remained resolutely _____ during trial.", a: "uncommunicative", dist: ["loquacious", "garrulous", "voluble"] },
        { q: "Choose the synonym for 'precarious': The debt-laden bank stood in a _____ position.", a: "hazardous", dist: ["impregnable", "robust", "secure"] },
        { q: "Choose the synonym for 'superfluous': The editor slashed _____ paragraphs.", a: "redundant", dist: ["pivotal", "indispensable", "vital"] },
        { q: "Choose the synonym for 'clandestine': They held a _____ rendezvous in the cafe.", a: "surreptitious", dist: ["overt", "transparent", "candid"] },
        { q: "Choose the synonym for 'substantiate': The claimant failed to _____ the damages.", a: "corroborate", dist: ["refute", "discredit", "disprove"] },
        { q: "Choose the synonym for 'tenacious': The detective was _____ in pursuing the truth.", a: "unyielding", dist: ["vacillating", "wavering", "irresolute"] },
        { q: "Choose the synonym for 'meticulous': The auditor conducted a _____ examination.", a: "painstaking", dist: ["cursory", "perfunctory", "hasty"] },
        { q: "Choose the synonym for 'complacent': Top scholars cannot become _____ before exams.", a: "smug", dist: ["vigilant", "watchful", "anxious"] },
        { q: "Choose the synonym for 'ostentatious': He avoided wearing _____ diamond jewelry.", a: "flamboyant", dist: ["austere", "modest", "unobtrusive"] },
        { q: "Choose the synonym for 'voracious': She has been a _____ reader since childhood.", a: "insatiable", dist: ["indifferent", "apathetic", "lukewarm"] }
      ],
      5: [
        { q: "Select the Level 5** synonym for 'anachronistic': The antiquated law was _____.", a: "archaic", dist: ["cutting-edge", "fashionable", "contemporary"] },
        { q: "Select the synonym for 'pusillanimous': The minister condemned their _____ retreat.", a: "craven", dist: ["intrepid", "valiant", "audacious"] },
        { q: "Select the synonym for 'sycophant': He was surrounded by fawning _____.", a: "toadies", dist: ["mavericks", "detractors", "adversaries"] },
        { q: "Select the synonym for 'trenchant': Her review offered a _____ deconstruction.", a: "incisive", dist: ["insipid", "banal", "vacuous"] },
        { q: "Select the synonym for 'intransigent': Management faced an _____ labor union.", a: "obdurate", dist: ["pliable", "amenable", "malleable"] },
        { q: "Select the synonym for 'proclivity': She has a marked _____ towards fine arts.", a: "propensity", dist: ["antipathy", "aversion", "disinclination"] },
        { q: "Select the synonym for 'pernicious': The drug had a _____ influence on his health.", a: "deleterious", dist: ["innocuous", "salubrious", "beneficent"] },
        { q: "Select the synonym for 'obfuscate': Bureaucrats sought to _____ budgetary errors.", a: "mystify", dist: ["elucidate", "clarify", "illuminate"] },
        { q: "Select the synonym for 'equivocate': Rather than answering directly, he chose to _____.", a: "prevaricate", dist: ["profess", "assert", "affirm"] },
        { q: "Select the synonym for 'enervating': The oppressive humidity felt truly _____.", a: "debilitating", dist: ["invigorating", "rejuvenating", "tonic"] },
        { q: "Select the synonym for 'meretricious': The critic mocked the film's _____ visual flair.", a: "specious", dist: ["sterling", "unfeigned", "authentic"] },
        { q: "Select the synonym for 'recondite': The doctoral dissertation explored _____ physics.", a: "abstruse", dist: ["elementary", "manifest", "patent"] },
        { q: "Select the synonym for 'supercilious': The aristocrat cast a _____ glance at us.", a: "disdainful", dist: ["deferential", "servile", "humble"] },
        { q: "Select the synonym for 'vicissitudes': Life brings inevitable financial _____.", a: "fluctuations", dist: ["stabilities", "constants", "invariances"] },
        { q: "Select the synonym for 'perfunctory': The guards performed a _____ security pat-down.", a: "cursory", dist: ["exhaustive", "meticulous", "rigorous"] },
        { q: "Select the synonym for 'quixotic': Pursuing that utopian policy was inherently _____.", a: "visionary", dist: ["pragmatic", "utilitarian", "functional"] },
        { q: "Select the synonym for 'ebullient': The graduation audience burst into _____ cheer.", a: "exuberant", dist: ["morose", "crestfallen", "sullen"] },
        { q: "Select the synonym for 'munificent': The philanthropist made a _____ donation.", a: "bounteous", dist: ["parsimonious", "penurious", "churlish"] },
        { q: "Select the synonym for 'insouciant': The defendant entered with an _____ demeanor.", a: "nonchalant", dist: ["perturbed", "fretting", "apprehensive"] },
        { q: "Select the synonym for 'sanctimonious': She delivered a sermon full of _____ rhetoric.", a: "holier-than-thou", dist: ["unpretentious", "sincere", "pious"] }
      ]
    }
  };

  // State Management
  let currentUser = storage.get("gq_user", null);
  let currentAvatar = storage.get("gq_avatar", { name: "Sponge-Lad", skin: "skin-sponge", face: "👀" });
  let activeTopic = "";
  let activeStage = 1;
  let activeQIndex = 0;
  let activeScore = 0;
  let stageLog = [];
  let currentSelection = null;

  // Screen Switcher
  function showScreen(screenId) {
    document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
    document.getElementById(screenId).classList.add("active");
    window.scrollTo({ top: 0, behavior: 'smooth' });
    if (screenId === "screen-dashboard") renderDashboard();
    if (screenId === "screen-leaderboard") renderLeaderboard();
  }

  // Avatar Selection
  function pickAvatar(name, skin, face, el) {
    document.querySelectorAll(".avatar-card").forEach(c => c.classList.remove("selected"));
    el.classList.add("selected");
    currentAvatar = { name, skin, face };
  }

  // Registration
  function registerUser() {
    const input = document.getElementById("inputUsername").value.trim();
    if (!input) {
      alert("Please enter a student name or candidate ID!");
      return;
    }
    currentUser = input;
    storage.set("gq_user", currentUser);
    storage.set("gq_avatar", currentAvatar);

    // Initialize user record
    const records = storage.get("gq_records", {});
    if (!records[currentUser]) {
      records[currentUser] = {
        name: currentUser,
        avatar: currentAvatar,
        cleared: {},
        scores: {},
        relics: [],
        attempts: 0
      };
      storage.set("gq_records", records);
    }
    updateHeaderPill();
    showScreen("screen-dashboard");
  }

  function updateHeaderPill() {
    if (!currentUser) return;
    document.getElementById("topUsername").textContent = currentUser;
    document.getElementById("topAvatarIcon").textContent = currentAvatar.face;
  }

  // Dashboard & Wardrobe Assembly
  function renderDashboard() {
    updateHeaderPill();
    const records = storage.get("gq_records", {});
    const userData = records[currentUser] || { cleared: {}, relics: [] };

    // Update Living Companion Doll
    const sprite = document.getElementById("pedestalSprite");
    sprite.className = `avatar-sprite ${currentAvatar.skin}`;
    document.getElementById("pedestalFace").textContent = currentAvatar.face;
    document.getElementById("pedestalName").textContent = currentAvatar.name;

    // Clear all doll attachment slots
    document.getElementById("pedestalHead").textContent = "";
    document.getElementById("pedestalTorso").textContent = "";
    document.getElementById("pedestalHandL").textContent = "";
    document.getElementById("pedestalHandR").textContent = "";

    const wardrobeContainer = document.getElementById("wardrobeTags");
    wardrobeContainer.innerHTML = "";

    if (!userData.relics || userData.relics.length === 0) {
      wardrobeContainer.innerHTML = '<span style="font-size: 0.82rem; color: #888;">No accessories equipped yet. Clear stages to dress your avatar!</span>';
    } else {
      userData.relics.forEach(relicName => {
        const tag = document.createElement("span");
        tag.className = "item-tag";
        tag.textContent = relicName;
        wardrobeContainer.appendChild(tag);
      });

      // Equip items visually to the pedestal doll based on slot mapping
      Object.keys(REWARD_MAP).forEach(top => {
        REWARD_MAP[top].forEach(item => {
          if (userData.relics.includes(`${item.icon} ${item.name}`)) {
            if (item.slot === "slot-head") document.getElementById("pedestalHead").textContent = item.icon;
            if (item.slot === "slot-torso") document.getElementById("pedestalTorso").textContent = item.icon;
            if (item.slot === "slot-hand-left") document.getElementById("pedestalHandL").textContent = item.icon;
            if (item.slot === "slot-hand-right") document.getElementById("pedestalHandR").textContent = item.icon;
          }
        });
      });
    }

    // Render 6 Topic Cards
    const container = document.getElementById("topicsContainer");
    container.innerHTML = "";

    Object.keys(questionBank).forEach(topic => {
      const card = document.createElement("div");
      card.className = "topic-card";
      let stagesHtml = "";

      for (let s = 1; s <= 5; s++) {
        const key = `${topic}-S${s}`;
        const isCleared = !!userData.cleared[key];
        const isUnlocked = s === 1 || !!userData.cleared[`${topic}-S${s - 1}`];

        let stateClass = "locked";
        if (isCleared) stateClass = "cleared";
        else if (isUnlocked) stateClass = "current";

        stagesHtml += `
          <div class="stage-btn ${stateClass}" onclick="triggerStage('${topic}', ${s}, ${isUnlocked})">
            <span>S${s} ${isCleared ? '✓' : ''}</span>
            <span class="stage-sub">P1-F6</span>
          </div>
        `;
      }

      card.innerHTML = `
        <h4>
          <span>${topic}</span>
          <span style="font-size: 0.8rem; font-weight: normal; color: #666;">5 Stages • 100 Qs</span>
        </h4>
        <p style="font-size: 0.78rem; color: #777;">Passing Mark: 16/20 (80%)</p>
        <div class="stages-bar">${stagesHtml}</div>
      `;
      container.appendChild(card);
    });
  }

  // Quiz Execution
  function triggerStage(topic, stage, unlocked) {
    if (!unlocked) {
      alert(`Stage ${stage} is locked! You must clear Stage ${stage - 1} with at least 16/20 to advance.`);
      return;
    }
    activeTopic = topic;
    activeStage = stage;
    activeQIndex = 0;
    activeScore = 0;
    stageLog = [];
    currentSelection = null;

    showScreen("screen-quiz");
    renderQuestion();
  }

  function renderQuestion() {
    currentSelection = null;
    const questions = questionBank[activeTopic][activeStage];
    const qData = questions[activeQIndex];

    document.getElementById("quizTopicTitle").textContent = `${activeTopic.toUpperCase()}`;
    document.getElementById("quizStageSubtitle").textContent = `${STAGE_TITLES[activeStage]}`;
    document.getElementById("quizProgressCount").textContent = `Question ${activeQIndex + 1} / ${STAGE_QUESTIONS_NUM}`;
    document.getElementById("quizPrompt").textContent = qData.q;

    const choicesGrid = document.getElementById("choicesGrid");
    choicesGrid.innerHTML = "";

    // Shuffle options
    const allChoices = [qData.a, ...qData.dist].sort(() => Math.random() - 0.5);

    allChoices.forEach(choiceText => {
      const btn = document.createElement("button");
      btn.className = "choice-btn";
      btn.textContent = choiceText;
      btn.onclick = () => {
        document.querySelectorAll(".choice-btn").forEach(b => b.classList.remove("selected"));
        btn.classList.add("selected");
        currentSelection = choiceText;
      };
      choicesGrid.appendChild(btn);
    });
  }

  function submitCurrentQuestion() {
    if (!currentSelection) {
      alert("Please select an answer choice before confirming!");
      return;
    }
    const qData = questionBank[activeTopic][activeStage][activeQIndex];
    const isCorrect = currentSelection.trim().toLowerCase() === qData.a.trim().toLowerCase();

    if (isCorrect) activeScore++;

    stageLog.push({
      q: qData.q,
      user: currentSelection,
      key: qData.a,
      isCorrect: isCorrect
    });

    activeQIndex++;
    if (activeQIndex < STAGE_QUESTIONS_NUM) {
      renderQuestion();
    } else {
      finalizeStage();
    }
  }

  function abandonQuiz() {
    if (confirm("Abandon stage? Progress for this attempt will not be recorded.")) {
      showScreen("screen-dashboard");
    }
  }

  // Stage Evaluation & Relic Dispenser
  function finalizeStage() {
    showScreen("screen-result");

    const records = storage.get("gq_records", {});
    const userData = records[currentUser];
    userData.attempts = (userData.attempts || 0) + 1;

    const isPassed = activeScore >= PASS_CRITERIA;
    const stageKey = `${activeTopic}-S${activeStage}`;

    // Update high scores
    userData.scores[stageKey] = Math.max(userData.scores[stageKey] || 0, activeScore);

    const titleEl = document.getElementById("resultTitle");
    const feedEl = document.getElementById("resultFeedback");
    const alertEl = document.getElementById("relicAlert");
    const nextBtn = document.getElementById("btnNextLevel");

    if (isPassed) {
      userData.cleared[stageKey] = true;
      titleEl.textContent = "🎉 Stage Cleared!";
      titleEl.style.color = "var(--success-green)";
      feedEl.innerHTML = `Magnificent performance! You scored <strong>${activeScore} / 20</strong> (Pass mark: 16).`;

      // Reward Equipment
      const relicAward = REWARD_MAP[activeTopic][activeStage - 1];
      const relicFullName = `${relicAward.icon} ${relicAward.name}`;

      if (!userData.relics.includes(relicFullName)) {
        userData.relics.push(relicFullName);
        alertEl.style.display = "block";
        alertEl.innerHTML = `<strong>🎁 Companion Relic Earned:</strong> ${relicFullName} has been attached to ${currentAvatar.name}!`;
      } else {
        alertEl.style.display = "none";
      }

      nextBtn.style.display = activeStage < 5 ? "inline-flex" : "none";
    } else {
      titleEl.textContent = "📚 Stage Incomplete";
      titleEl.style.color = "var(--error-red)";
      feedEl.innerHTML = `You scored <strong>${activeScore} / 20</strong>. A score of 16 or above is required to clear this stage. Review the answer breakdown below and re-attempt!`;
      alertEl.style.display = "none";
      nextBtn.style.display = "none";
    }

    storage.set("gq_records", records);

    // Build Post-Stage Answer Review Table
    const tbody = document.getElementById("resultReviewBody");
    tbody.innerHTML = "";
    stageLog.forEach((item, idx) => {
      const tr = document.createElement("tr");
      tr.innerHTML = `
        <td>${idx + 1}</td>
        <td>${item.q}</td>
        <td class="${item.isCorrect ? 'cell-correct' : 'cell-wrong'}">${item.user}</td>
        <td class="cell-correct">${item.key}</td>
        <td>${item.isCorrect ? '✅ Correct' : '❌ Needs Review'}</td>
      `;
      tbody.appendChild(tr);
    });
  }

  function advanceNextStage() {
    if (activeStage < 5) {
      triggerStage(activeTopic, activeStage + 1, true);
    }
  }

  // Leaderboard Engine
  function renderLeaderboard() {
    const tbody = document.getElementById("leaderboardTbody");
    tbody.innerHTML = "";
    const records = storage.get("gq_records", {});
    const studentList = Object.values(records);

    studentList.sort((a, b) => {
      const aTotal = Object.values(a.scores || {}).reduce((x, y) => x + y, 0);
      const bTotal = Object.values(b.scores || {}).reduce((x, y) => x + y, 0);
      return bTotal - aTotal;
    });

    if (studentList.length === 0) {
      tbody.innerHTML = "<tr><td colspan='5' style='text-align:center;'>No student records recorded yet.</td></tr>";
      return;
    }

    studentList.forEach((st, idx) => {
      const clearedCount = Object.keys(st.cleared || {}).length;
      const totalScore = Object.values(st.scores || {}).reduce((x, y) => x + y, 0);
      const tr = document.createElement("tr");
      tr.innerHTML = `
        <td style="font-weight:bold;">#${idx + 1}</td>
        <td><strong>${st.name}</strong></td>
        <td>${st.avatar ? st.avatar.face : '🧑‍🎓'} ${st.avatar ? st.avatar.name : ''}</td>
        <td>${clearedCount} / 30 Stages</td>
        <td><strong>${totalScore}</strong> pts</td>
      `;
      tbody.appendChild(tr);
    });
  }

  // Teacher Backdoor Module (Protected SHA-256 Authentication)
  async function computeSha256(str) {
    const buffer = await crypto.subtle.digest("SHA-256", new TextEncoder().encode(str));
    return Array.from(new Uint8Array(buffer)).map(b => b.toString(16).padStart(2, "0")).join("");
  }

  function openTeacherModal() {
    document.getElementById("teacherModal").style.display = "flex";
    document.getElementById("teacherAuthArea").style.display = "block";
    document.getElementById("teacherDashboardArea").style.display = "none";
    const input = document.getElementById("teacherSecretInput");
    input.value = "";
    setTimeout(() => input.focus(), 60);
  }

  function closeTeacherModal() {
    document.getElementById("teacherModal").style.display = "none";
  }

  async function verifyTeacherPin() {
    const entered = document.getElementById("teacherSecretInput").value;
    const hashed = await computeSha256(entered);

    if (hashed === AUTH_HASH) {
      document.getElementById("teacherAuthArea").style.display = "none";
      document.getElementById("teacherDashboardArea").style.display = "block";
      populateTeacherManifest();
    } else {
      alert("Authentication failed: Invalid instructor credentials.");
      document.getElementById("teacherSecretInput").value = "";
      document.getElementById("teacherSecretInput").focus();
    }
  }

  function populateTeacherManifest() {
    const tbody = document.getElementById("teacherTableBody");
    tbody.innerHTML = "";
    const records = storage.get("gq_records", {});
    const studentList = Object.values(records);

    if (studentList.length === 0) {
      tbody.innerHTML = "<tr><td colspan='5' style='text-align:center;'>No candidates logged in yet.</td></tr>";
      return;
    }

    studentList.forEach(st => {
      const clearedCount = Object.keys(st.cleared || {}).length;
      const highestScore = Math.max(...Object.values(st.scores || {}), 0);
      const tr = document.createElement("tr");
      tr.innerHTML = `
        <td><strong>${st.name}</strong></td>
        <td>${st.avatar ? st.avatar.face : '🧑‍🎓'} ${st.avatar ? st.avatar.name : ''}</td>
        <td>${clearedCount} / 30</td>
        <td>${highestScore} / 20</td>
        <td>${st.attempts || 0}</td>
      `;
      tbody.appendChild(tr);
    });
  }

  function clearAllData() {
    if (confirm("Reset the entire student database, clear records, and wipe the leaderboard?")) {
      storage.set("gq_records", {});
      populateTeacherManifest();
      renderDashboard();
      alert("Leaderboard and candidate manifests have been wiped.");
    }
  }

  // Client-Side Excel (.xls Binary XML) Generator
  function exportToExcel() {
    const records = storage.get("gq_records", {});
    const students = Object.values(records);
    if (students.length === 0) {
      alert("No student records available to export!");
      return;
    }

    let xml = `<?xml version="1.0"?><?mso-application progid="Excel.Sheet"?>
    <Workbook xmlns="urn:schemas-microsoft-com:office:spreadsheet"
     xmlns:ss="urn:schemas-microsoft-com:office:spreadsheet">
     <Worksheet ss:Name="F6_Grammar_Mastery">
      <Table>
       <Row>
        <Cell><Data ss:Type="String">Candidate Name</Data></Cell>
        <Cell><Data ss:Type="String">Avatar Companion</Data></Cell>
        <Cell><Data ss:Type="String">Stages Cleared (/30)</Data></Cell>
        <Cell><Data ss:Type="String">Total Points</Data></Cell>
        <Cell><Data ss:Type="String">Total Attempts</Data></Cell>
        <Cell><Data ss:Type="String">Relics Unlocked</Data></Cell>
       </Row>`;

    students.forEach(st => {
      const cleared = Object.keys(st.cleared || {}).length;
      const totalPts = Object.values(st.scores || {}).reduce((a, b) => a + b, 0);
      const relicsCount = (st.relics || []).length;
      xml += `
       <Row>
        <Cell><Data ss:Type="String">${st.name}</Data></Cell>
        <Cell><Data ss:Type="String">${st.avatar ? st.avatar.name : 'Cadet'}</Data></Cell>
        <Cell><Data ss:Type="Number">${cleared}</Data></Cell>
        <Cell><Data ss:Type="Number">${totalPts}</Data></Cell>
        <Cell><Data ss:Type="Number">${st.attempts || 0}</Data></Cell>
        <Cell><Data ss:Type="Number">${relicsCount}</Data></Cell>
       </Row>`;
    });

    xml += `</Table></Worksheet></Workbook>`;

    const blob = new Blob([xml], { type: "application/vnd.ms-excel" });
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a");
    a.href = url;
    a.download = `HKDSE_F6_Grammar_Manifest_${new Date().toISOString().slice(0, 10)}.xls`;
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  }

  // Secret Hotkey Shortcut (Ctrl + Shift + T)
  window.addEventListener("keydown", (e) => {
    if (e.ctrlKey && e.shiftKey && (e.key === "T" || e.key === "t")) {
      openTeacherModal();
    }
  });

  // Auto-init on page load
  window.onload = () => {
    if (currentUser) {
      showScreen("screen-dashboard");
    } else {
      showScreen("screen-register");
    }
  };
</script>
</body>
</html>
