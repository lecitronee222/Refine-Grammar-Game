<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>HKDSE English Ladder: P1 to F6</title>
  <style>
    :root {
      --primary: #4338ca;
      --primary-hover: #3730a3;
      --secondary: #06b6d4;
      --accent: #f59e0b;
      --success: #10b981;
      --danger: #ef4444;
      --bg: #f8fafc;
      --card-bg: #ffffff;
      --text: #1e293b;
      --text-muted: #64748b;
      --border: #e2e8f0;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif; }
    body { background-color: var(--bg); color: var(--text); min-height: 100vh; display: flex; flex-direction: column; }
    header { background: #fff; border-bottom: 1px solid var(--border); padding: 1rem 2rem; display: flex; justify-content: space-between; align-items: center; position: sticky; top: 0; z-index: 100; }
    .brand { font-size: 1.25rem; font-weight: 700; color: var(--primary); display: flex; align-items: center; gap: 0.5rem; }
    .nav-actions { display: flex; gap: 0.75rem; align-items: center; }
    .btn { padding: 0.5rem 1rem; border-radius: 0.5rem; border: none; font-weight: 600; cursor: pointer; transition: all 0.2s; font-size: 0.875rem; }
    .btn-primary { background: var(--primary); color: #fff; }
    .btn-primary:hover { background: var(--primary-hover); }
    .btn-secondary { background: #e0e7ff; color: var(--primary); }
    .btn-secondary:hover { background: #c7d2fe; }
    .btn-danger { background: var(--danger); color: #fff; }
    .btn-danger:hover { background: #dc2626; }
    .btn-outline { background: transparent; border: 1px solid var(--border); color: var(--text); }
    .btn-outline:hover { background: #f1f5f9; }

    .container { max-width: 1100px; margin: 2rem auto; padding: 0 1rem; width: 100%; flex: 1; }
    .hidden { display: none !important; }

    /* Companion Bar */
    .companion-banner { background: linear-gradient(135deg, #eef2ff, #e0e7ff); border: 1px solid #c7d2fe; border-radius: 1rem; padding: 1.25rem 1.75rem; display: flex; justify-content: space-between; align-items: center; margin-bottom: 2rem; }
    .companion-info { display: flex; align-items: center; gap: 1.5rem; }
    .avatar-wrapper { position: relative; width: 76px; height: 76px; border-radius: 50%; background: #fff; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); display: flex; align-items: center; justify-content: center; font-size: 2.5rem; }
    .avatar-accessory { position: absolute; font-size: 1.4rem; pointer-events: none; }
    .acc-head { top: -10px; right: 6px; }
    .acc-torso { bottom: -6px; left: 6px; }
    .acc-badge { bottom: 2px; right: -4px; font-size: 1.15rem; }
    .wardrobe-list { display: flex; gap: 0.4rem; margin-top: 0.35rem; flex-wrap: wrap; }
    .wardrobe-pill { font-size: 0.75rem; background: #fff; padding: 0.2rem 0.55rem; border-radius: 1rem; border: 1px solid #cbd5e1; display: inline-flex; align-items: center; gap: 0.25rem; font-weight: 500; }

    /* Topic & Stage Cards */
    .grid-topics { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 1.5rem; }
    .card { background: var(--card-bg); border-radius: 0.75rem; border: 1px solid var(--border); padding: 1.5rem; box-shadow: 0 1px 3px rgba(0,0,0,0.05); }
    .topic-title { font-size: 1.25rem; font-weight: 700; color: #1e293b; margin-bottom: 0.25rem; display: flex; justify-content: space-between; align-items: center; }
    .stage-chips { display: grid; grid-template-columns: repeat(5, 1fr); gap: 0.4rem; margin-top: 1rem; }
    .stage-chip { padding: 0.6rem 0.2rem; text-align: center; border-radius: 0.5rem; border: 1px solid var(--border); font-size: 0.75rem; font-weight: 600; cursor: pointer; background: #f8fafc; transition: all 0.2s; display: flex; flex-direction: column; gap: 2px; }
    .stage-chip span.label { font-size: 0.65rem; color: var(--text-muted); }
    .stage-chip.cleared { background: #dcfce7; border-color: #86efac; color: #15803d; }
    .stage-chip.cleared span.label { color: #16a34a; }
    .stage-chip.current { background: #e0e7ff; border-color: #818cf8; color: var(--primary); }
    .stage-chip.current span.label { color: var(--primary); }
    .stage-chip.locked { opacity: 0.45; cursor: not-allowed; }

    /* Quiz Area */
    .quiz-card { background: #fff; border-radius: 1rem; border: 1px solid var(--border); padding: 2rem; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05); }
    .quiz-header { display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid var(--border); padding-bottom: 1rem; margin-bottom: 1.5rem; }
    .quiz-progress { font-weight: 700; color: var(--primary); }
    .question-box { font-size: 1.15rem; font-weight: 600; margin-bottom: 1.5rem; line-height: 1.5; color: #0f172a; }
    .options-grid { display: grid; grid-template-columns: 1fr; gap: 0.75rem; margin-bottom: 1.5rem; }
    .option-btn { padding: 1rem; border-radius: 0.5rem; border: 1.5px solid var(--border); background: #fff; font-size: 1rem; text-align: left; cursor: pointer; transition: all 0.15s; }
    .option-btn:hover { border-color: var(--primary); background: #f5f3ff; }
    .option-btn.selected { border-color: var(--primary); background: #ede9fe; font-weight: 600; }

    /* Review Area */
    .review-table { width: 100%; border-collapse: collapse; margin-top: 1rem; }
    .review-table th, .review-table td { padding: 0.75rem 1rem; border: 1px solid var(--border); text-align: left; font-size: 0.875rem; }
    .review-table th { background: #f1f5f9; font-weight: 600; }
    .review-correct { color: #16a34a; font-weight: 600; }
    .review-incorrect { color: #dc2626; font-weight: 600; }

    /* Modal Backdrop */
    .modal-backdrop { position: fixed; inset: 0; background: rgba(0,0,0,0.5); display: flex; align-items: center; justify-content: center; z-index: 200; }
    .modal-box { background: #fff; border-radius: 1rem; padding: 2rem; max-width: 680px; width: 90%; max-height: 85vh; overflow-y: auto; }
  </style>
</head>
<body>

  <header>
    <div class="brand">📘 HKDSE English Ladder (P1 – F6)</div>
    <div class="nav-actions">
      <span id="headerStudentName" style="font-weight: 600;">Student: Cadet-01</span>
      <button class="btn btn-outline" onclick="showLeaderboard()">🏆 Leaderboard</button>
      <button class="btn btn-secondary" onclick="openTeacherBackdoor()">🔒 Teacher Portal</button>
    </div>
  </header>

  <main class="container">
    <!-- Companion Banner -->
    <section class="companion-banner" id="companionSection">
      <div class="companion-info">
        <div class="avatar-wrapper" id="avatarDisplay">
          <span id="baseAvatarEmoji">🧑‍🎓</span>
          <span class="avatar-accessory acc-head" id="slotHead"></span>
          <span class="avatar-accessory acc-torso" id="slotTorso"></span>
          <span class="avatar-accessory acc-badge" id="slotBadge"></span>
        </div>
        <div>
          <h3 id="avatarNameDisplay">Grammar Cadet</h3>
          <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 0.2rem;">Unlocked Avatar Gear (Requires 16/20 on each stage):</p>
          <div class="wardrobe-list" id="wardrobeList">
            <span class="wardrobe-pill">No items unlocked yet. Clear a stage to earn gear!</span>
          </div>
        </div>
      </div>
      <div>
        <button class="btn btn-outline" onclick="promptChangeName()">Edit Name</button>
      </div>
    </section>

    <!-- Topics Grid (Home Screen) -->
    <section id="topicsView">
      <h2 style="margin-bottom: 0.5rem;">Select Grammar Topic</h2>
      <p style="color: var(--text-muted); margin-bottom: 1.5rem; font-size: 0.9rem;">
        Complete all 5 stages from Primary 1 to Form 6. Passing grade is <strong>16 / 20</strong> for each stage.
      </p>
      <div class="grid-topics" id="topicsContainer"></div>
    </section>

    <!-- Quiz Question Screen -->
    <section id="quizView" class="hidden">
      <div class="quiz-card">
        <div class="quiz-header">
          <div>
            <span id="quizTopicBadge" style="font-size: 0.85rem; color: var(--text-muted); font-weight: 600;">TOPIC</span>
            <h3 id="quizStageBadge">Stage 1 (Pass Mark: 16/20)</h3>
          </div>
          <div class="quiz-progress" id="quizQuestionCounter">Question 1 / 20</div>
        </div>
        <div class="question-box" id="questionText">Question prompt loading...</div>
        <div class="options-grid" id="optionsContainer"></div>
        <div style="display: flex; justify-content: space-between; align-items: center;">
          <button class="btn btn-outline" onclick="quitQuiz()">Abandon Stage</button>
          <button class="btn btn-primary" id="btnNextQuestion" onclick="submitAnswer()">Next Question</button>
        </div>
      </div>
    </section>

    <!-- Stage Results & Answer Review Screen -->
    <section id="resultView" class="hidden">
      <div class="card">
        <h2 id="resultHeading" style="margin-bottom: 0.5rem;">Stage Complete</h2>
        <p id="resultSummary" style="margin-bottom: 1.5rem; color: var(--text-muted);"></p>
        <div id="rewardNotification" style="margin-bottom: 1.5rem;" class="hidden"></div>
        
        <h3>Full Stage Answer Key & Review</h3>
        <p style="font-size: 0.85rem; color: var(--text-muted); margin-bottom: 1rem;">Check your choices and the correct answers below.</p>
        <div style="overflow-x: auto;">
          <table class="review-table">
            <thead>
              <tr>
                <th>#</th>
                <th>Question</th>
                <th>Your Answer</th>
                <th>Correct Answer</th>
                <th>Result</th>
              </tr>
            </thead>
            <tbody id="reviewTableBody"></tbody>
          </table>
        </div>
        <div style="margin-top: 1.5rem; display: flex; gap: 1rem;">
          <button class="btn btn-primary" onclick="returnToTopics()">Return to Topics</button>
          <button class="btn btn-secondary hidden" id="btnNextStage" onclick="startNextStage()">Proceed to Next Stage</button>
        </div>
      </div>
    </section>
  </main>

  <!-- Modal: Teacher Backdoor (Zero PIN displayed in HTML) -->
  <div class="modal-backdrop hidden" id="teacherModal">
    <div class="modal-box">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem;">
        <h2>🔒 Instructor Administrative Portal</h2>
        <button class="btn btn-outline" onclick="closeTeacherBackdoor()">✕</button>
      </div>
      <div id="teacherAuthArea">
        <p style="margin-bottom: 0.75rem; color: var(--text-muted);">
          Enter instructor credentials to inspect student data and manage system state:
        </p>
        <div style="display: flex; gap: 0.5rem;">
          <input 
            type="password" 
            id="teacherPinInput" 
            placeholder="••••••••" 
            autocomplete="off"
            style="flex: 1; padding: 0.5rem; border: 1px solid var(--border); border-radius: 0.5rem;"
            onkeydown="if(event.key==='Enter') verifyTeacherPin()"
          >
          <button class="btn btn-primary" onclick="verifyTeacherPin()">Authenticate</button>
        </div>
      </div>
      <div id="teacherDashboardArea" class="hidden">
        <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem;">
          <h4>Registered Student Progress</h4>
          <button class="btn btn-danger" onclick="clearLeaderboardData()">Reset Leaderboard & Records</button>
        </div>
        <div style="max-height: 350px; overflow-y: auto;">
          <table class="review-table">
            <thead>
              <tr>
                <th>Student</th>
                <th>Cleared Stages</th>
                <th>High Score</th>
                <th>Total Attempts</th>
              </tr>
            </thead>
            <tbody id="teacherRecordsTable"></tbody>
          </table>
        </div>
      </div>
    </div>
  </div>

  <!-- Modal: Leaderboard -->
  <div class="modal-backdrop hidden" id="leaderboardModal">
    <div class="modal-box">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem;">
        <h2>🏆 Student Leaderboard</h2>
        <button class="btn btn-outline" onclick="closeLeaderboard()">✕</button>
      </div>
      <table class="review-table">
        <thead>
          <tr>
            <th>Rank</th>
            <th>Student</th>
            <th>Total Score</th>
            <th>Stages Cleared</th>
          </tr>
        </thead>
        <tbody id="leaderboardTableBody"></tbody>
      </table>
    </div>
  </div>

  <script>
    const PASSING_SCORE = 16;
    const QUESTIONS_PER_STAGE = 20;

    // Secure SHA-256 hash of the master password (no plain password anywhere in UI or script)
    const AUTH_HASH = "8c0a87a6d8beecb2bfba2725e6ffc6cf91054ee5b565012e848df87a327fcfa8";

    const STAGE_LABELS = {
      1: "P.1–3 (Novice)",
      2: "P.4–6 (Junior)",
      3: "S.1–3 (Mid)",
      4: "S.4 (Senior)",
      5: "S.5–6 (DSE)"
    };

    const ACCESSORY_AWARDS = {
      "Prepositions": ["🧢 Scholar Visor", "🦺 Scout Vest", "⚓ Anchor Charm", "🎖️ Master Brooch", "👑 Royal Laurels"],
      "Word Formation": ["🪶 Silver Quill", "🧐 Grammar Monocle", "🥋 Sage Cloak", "💎 Lexicon Gem", "👑 Syntax Crown"],
      "Tenses": ["⏱️ Chrono Watch", "⏳ Hourglass Pin", "⚡ Epoch Cape", "🌌 Temporal Ring", "👑 Sovereign Diadem"],
      "Articles": ["🔍 Determinative Lens", "📜 Parchment Sash", "🏷️ Definite Sigil", "🛡️ Guardian Crest", "👑 Crown of Precision"],
      "Plurals": ["📚 Dual Folios", "✨ Multiplier Badge", "🧤 Concord Gloves", "🗝️ Concordance Key", "👑 Master Pluralis"]
    };

    // 500 Unique Questions: 5 Topics x 5 Stages x 20 Questions
    const QUESTION_BANK = {
      "Prepositions": {
        // Stage 1: P.1 - P.3 (Concrete spatial & basic time: on, in, at, under, by)
        1: [
          { q: "The apple is _____ the table.", a: "on", dist: ["at", "to", "into"] },
          { q: "My cat likes to sleep _____ the bed.", a: "under", dist: ["of", "to", "off"] },
          { q: "We go to school _____ 8 o'clock.", a: "at", dist: ["on", "in", "to"] },
          { q: "The toys are kept _____ the big box.", a: "in", dist: ["on", "at", "to"] },
          { q: "My birthday is _____ May.", a: "in", dist: ["on", "at", "of"] },
          { q: "We play football _____ Sunday morning.", a: "on", dist: ["in", "at", "to"] },
          { q: "He sits _____ his best friend in class.", a: "next to", dist: ["at", "on", "into"] },
          { q: "Look _____ the blackboard, please.", a: "at", dist: ["in", "on", "to"] },
          { q: "The bird flew _____ the open window.", a: "through", dist: ["at", "on", "of"] },
          { q: "Put the pencil _____ your pencil case.", a: "into", dist: ["on", "at", "to"] },
          { q: "She lives _____ Hong Kong.", a: "in", dist: ["at", "on", "to"] },
          { q: "I wake up _____ 7:00 a.m. every day.", a: "at", dist: ["on", "in", "by"] },
          { q: "The dog is hiding _____ the door.", a: "behind", dist: ["on", "at", "into"] },
          { q: "We eat dinner together _____ night.", a: "at", dist: ["in", "on", "to"] },
          { q: "There is a painting _____ the wall.", a: "on", dist: ["in", "at", "to"] },
          { q: "The little boy walked _____ his mother.", a: "with", dist: ["at", "on", "in"] },
          { q: "The park is very close _____ our home.", a: "to", dist: ["with", "for", "at"] },
          { q: "Santa Claus comes _____ Christmas Day.", a: "on", dist: ["in", "at", "of"] },
          { q: "She jumped _____ the puddle playfully.", a: "over", dist: ["at", "in", "on"] },
          { q: "The duck is swimming _____ the pond.", a: "in", dist: ["on", "at", "to"] }
        ],
        // Stage 2: P.4 - P.6 (Collocations, common idioms, travel, basic dependent prepositions)
        2: [
          { q: "She is very good _____ playing the piano.", a: "at", dist: ["in", "on", "with"] },
          { q: "We traveled to Macau _____ ferry.", a: "by", dist: ["on", "in", "with"] },
          { q: "He is afraid _____ big spiders.", a: "of", dist: ["from", "with", "about"] },
          { q: "Are you interested _____ science and nature?", a: "in", dist: ["at", "on", "about"] },
          { q: "They arrived _____ the airport on time.", a: "at", dist: ["to", "in", "on"] },
          { q: "My brother is proud _____ his high test score.", a: "of", dist: ["with", "for", "about"] },
          { q: "Please listen carefully _____ the teacher.", a: "to", dist: ["at", "with", "for"] },
          { q: "We stayed indoors because _____ the heavy rain.", a: "of", dist: ["from", "with", "by"] },
          { q: "She thanked her uncle _____ the birthday gift.", a: "for", dist: ["of", "to", "with"] },
          { q: "Hong Kong is famous _____ delicious dim sum.", a: "for", dist: ["with", "about", "of"] },
          { q: "He borrowed a storybook _____ the school library.", a: "from", dist: ["to", "at", "by"] },
          { q: "Don't shout _____ your classmates in anger.", a: "at", dist: ["to", "with", "on"] },
          { q: "She was surprised _____ the sudden birthday party.", a: "by", dist: ["with", "on", "to"] },
          { q: "I agree _____ your suggestions completely.", a: "with", dist: ["to", "on", "for"] },
          { q: "He has been waiting for the bus _____ thirty minutes.", a: "for", dist: ["since", "during", "at"] },
          { q: "We have lived in Kowloon _____ 2015.", a: "since", dist: ["for", "in", "from"] },
          { q: "The classroom is full _____ cheerful children.", a: "of", dist: ["with", "by", "in"] },
          { q: "She apologized _____ breaking her brother's ruler.", a: "for", dist: ["to", "about", "with"] },
          { q: "Take care _____ your younger sister at the playground.", a: "of", dist: ["to", "with", "about"] },
          { q: "The teacher divided the class _____ four teams.", a: "into", dist: ["to", "in", "for"] }
        ],
        // Stage 3: S.1 - S.3 (Complex prepositions, phrasal combinations, intermediate collocations)
        3: [
          { q: "The students succeeded _____ winning the regional debate.", a: "in", dist: ["at", "to", "for"] },
          { q: "He has always suffered _____ chronic migraines.", a: "from", dist: ["of", "with", "by"] },
          { q: "She insisted _____ paying for everyone's lunch.", a: "on", dist: ["in", "at", "to"] },
          { q: "Students must conform _____ school safety standards.", a: "to", dist: ["with", "by", "for"] },
          { q: "The committee approved the plan _____ behalf of all members.", a: "on", dist: ["in", "at", "for"] },
          { q: "He congratulated his friend _____ passing the driving test.", a: "on", dist: ["for", "in", "at"] },
          { q: "We were totally unaware _____ the impending schedule change.", a: "of", dist: ["about", "with", "to"] },
          { q: "The company aims to cater _____ the needs of elderly citizens.", a: "to", dist: ["for", "with", "at"] },
          { q: "Smoking is strictly prohibited _____ the school campus.", a: "on", dist: ["at", "over", "with"] },
          { q: "She prides herself _____ her immaculate handwriting.", a: "on", dist: ["in", "with", "for"] },
          { q: "He is accustomed _____ waking up early for cross-country training.", a: "to", dist: ["with", "for", "in"] },
          { q: "The scientist contributed significantly _____ the medical breakthrough.", a: "to", dist: ["for", "in", "with"] },
          { q: "They prevented the leak _____ spreading throughout the laboratory.", a: "from", dist: ["to", "by", "of"] },
          { q: "Her novel is based _____ real historical events during the war.", a: "on", dist: ["in", "at", "from"] },
          { q: "The project must be finished _____ the stipulated deadline.", a: "by", dist: ["until", "for", "during"] },
          { q: "He was disqualified from the race _____ account of cheating.", a: "on", dist: ["in", "by", "for"] },
          { q: "The principal expressed sympathy _____ the injured athlete.", a: "for", dist: ["with", "to", "towards"] },
          { q: "Children are often dependent _____ their parents for guidance.", a: "on", dist: ["with", "to", "of"] },
          { q: "She apologized to the host _____ arriving ten minutes late.", a: "for", dist: ["with", "to", "about"] },
          { q: "The detective searched everywhere _____ tangible clues.", a: "for", dist: ["to", "after", "with"] }
        ],
        // Stage 4: S.4 (Senior Secondary transitional collocations, formal prose)
        4: [
          { q: "The regulations were revised in accordance _____ the new statutory ordinance.", a: "with", dist: ["to", "by", "for"] },
          { q: "Young athletes are particularly prone _____ muscular strain during winter.", a: "to", dist: ["for", "with", "at"] },
          { q: "The witness testimonies were compatible _____ the forensic evidence.", a: "with", dist: ["to", "for", "against"] },
          { q: "He is oblivious _____ the severe criticism surrounding his proposal.", a: "to", dist: ["of", "with", "about"] },
         
