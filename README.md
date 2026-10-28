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

  // Precomputed SHA-256 hash of F6ENG2026
  const AUTH_HASH = "a93ebd1455589815a699ebe1f9c67c60c725e0978c6b4258915e618448ccbf41";
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
        
