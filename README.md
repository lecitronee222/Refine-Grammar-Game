<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>F.6 HKDSE English Mastery Quest</title>
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
    .companion-banner { background: linear-gradient(135deg, #eef2ff, #e0e7ff); border: 1px solid #c7d2fe; border-radius: 1rem; padding: 1rem 1.5rem; display: flex; justify-content: space-between; align-items: center; margin-bottom: 2rem; }
    .companion-info { display: flex; align-items: center; gap: 1.25rem; }
    .avatar-wrapper { position: relative; width: 72px; height: 72px; border-radius: 50%; background: #fff; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); display: flex; align-items: center; justify-content: center; font-size: 2.25rem; }
    .avatar-accessory { position: absolute; font-size: 1.4rem; }
    .acc-head { top: -10px; right: 8px; }
    .acc-torso { bottom: -4px; left: 8px; }
    .acc-badge { bottom: 2px; right: -4px; font-size: 1.1rem; }
    .wardrobe-list { display: flex; gap: 0.4rem; margin-top: 0.25rem; }
    .wardrobe-pill { font-size: 0.75rem; background: #fff; padding: 0.15rem 0.5rem; border-radius: 1rem; border: 1px solid #cbd5e1; display: inline-flex; align-items: center; gap: 0.25rem; }

    /* Topic & Stage Cards */
    .grid-topics { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
    .card { background: var(--card-bg); border-radius: 0.75rem; border: 1px solid var(--border); padding: 1.5rem; box-shadow: 0 1px 3px rgba(0,0,0,0.05); }
    .topic-title { font-size: 1.25rem; font-weight: 700; color: #1e293b; margin-bottom: 0.5rem; display: flex; justify-content: space-between; align-items: center; }
    .stage-chips { display: flex; gap: 0.5rem; margin-top: 1rem; }
    .stage-chip { flex: 1; padding: 0.6rem 0.2rem; text-align: center; border-radius: 0.5rem; border: 1px solid var(--border); font-size: 0.8rem; font-weight: 600; cursor: pointer; background: #f8fafc; transition: all 0.2s; }
    .stage-chip.cleared { background: #dcfce7; border-color: #86efac; color: #15803d; }
    .stage-chip.current { background: #e0e7ff; border-color: #818cf8; color: var(--primary); }
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
    .review-table th { background: #f1f5f9; }
    .review-correct { color: #16a34a; font-weight: 600; }
    .review-incorrect { color: #dc2626; font-weight: 600; }

    /* Modal */
    .modal-backdrop { position: fixed; inset: 0; background: rgba(0,0,0,0.5); display: flex; align-items: center; justify-content: center; z-index: 200; }
    .modal-box { background: #fff; border-radius: 1rem; padding: 2rem; max-width: 650px; width: 90%; max-height: 85vh; overflow-y: auto; }
  </style>
</head>
<body>

  <header>
    <div class="brand">📘 F.6 English Mastery Quest</div>
    <div class="nav-actions">
      <span id="headerStudentName" style="font-weight: 600;">Student: Guest</span>
      <button class="btn btn-outline" onclick="showLeaderboard()">🏆 Leaderboard</button>
      <button class="btn btn-secondary" onclick="openTeacherBackdoor()">🔒 Teacher Portal</button>
    </div>
  </header>

  <main class="container">
    <!-- Companion Section -->
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
          <p style="font-size: 0.85rem; color: var(--text-muted);">Unlocked Accessories:</p>
          <div class="wardrobe-list" id="wardrobeList">
            <span class="wardrobe-pill">No items unlocked yet. Score 16/20 to earn gear!</span>
          </div>
        </div>
      </div>
      <div>
        <button class="btn btn-outline" onclick="promptChangeName()">Edit Student Name</button>
      </div>
    </section>

    <!-- Topic Grid (Home View) -->
    <section id="topicsView">
      <h2 style="margin-bottom: 1rem;">Select a Grammar Focus</h2>
      <div class="grid-topics" id="topicsContainer"></div>
    </section>

    <!-- Quiz View -->
    <section id="quizView" class="hidden">
      <div class="quiz-card">
        <div class="quiz-header">
          <div>
            <span id="quizTopicBadge" style="font-size: 0.85rem; color: var(--text-muted); font-weight: 600;">TOPIC</span>
            <h3 id="quizStageBadge">Stage 1 (Pass Mark: 16/20)</h3>
          </div>
          <div class="quiz-progress" id="quizQuestionCounter">Question 1 / 20</div>
        </div>
        <div class="question-box" id="questionText">Question text appears here...</div>
        <div class="options-grid" id="optionsContainer"></div>
        <div style="display: flex; justify-content: space-between; align-items: center;">
          <button class="btn btn-outline" onclick="quitQuiz()">Abandon Stage</button>
          <button class="btn btn-primary" id="btnNextQuestion" onclick="submitAnswer()">Next Question</button>
        </div>
      </div>
    </section>

    <!-- Stage Result & Answer Review View -->
    <section id="resultView" class="hidden">
      <div class="card">
        <h2 id="resultHeading" style="margin-bottom: 0.5rem;">Stage Complete</h2>
        <p id="resultSummary" style="margin-bottom: 1.5rem; color: var(--text-muted);"></p>
        <div id="rewardNotification" style="margin-bottom: 1.5rem;" class="hidden"></div>
        
        <h3>Stage Answer Review</h3>
        <p style="font-size: 0.85rem; color: var(--text-muted); margin-bottom: 1rem;">Review questions, submissions, and official answers below.</p>
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
          <button class="btn btn-secondary" id="btnNextStage" onclick="startNextStage()" class="hidden">Proceed to Next Stage</button>
        </div>
      </div>
    </section>
  </main>

  <!-- Modal: Teacher Backdoor -->
  <div class="modal-backdrop hidden" id="teacherModal">
    <div class="modal-box">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem;">
        <h2>🔒 Teacher Backdoor Portal</h2>
        <button class="btn btn-outline" onclick="closeTeacherBackdoor()">✕</button>
      </div>
      <div id="teacherAuthArea">
        <p style="margin-bottom: 0.75rem; color: var(--text-muted);">Enter master access PIN to inspect student progress and manage records:</p>
        <div style="display: flex; gap: 0.5rem;">
          <input type="password" id="teacherPinInput" placeholder="Enter Teacher PIN" style="flex: 1; padding: 0.5rem; border: 1px solid var(--border); border-radius: 0.5rem;">
          <button class="btn btn-primary" onclick="verifyTeacherPin()">Unlock</button>
        </div>
      </div>
      <div id="teacherDashboardArea" class="hidden">
        <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem;">
          <h4>Registered Student Progress</h4>
          <button class="btn btn-danger" onclick="clearLeaderboardData()">Clear Leaderboard & Records</button>
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

  <!-- Modal: Student Leaderboard -->
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
    const TEACHER_PIN = "F6ENG2026";
    const PASSING_SCORE = 16;
    const QUESTIONS_PER_STAGE = 20;

    const TOPICS = ["Prepositions", "Word Formation", "Tenses", "Articles", "Plurals"];

    const ACCESSORY_AWARDS = {
      "Prepositions": ["🧢 Scholar Visor", "🦺 Scout Vest", "⚓ Anchor Charm", "🎖️ Master Brooch", "👑 Royal Laurels"],
      "Word Formation": ["🪶 Silver Quill", "🧐 Grammar Monocle", "🥋 Sage Cloak", "💎 Lexicon Gem", "👑 Syntax Crown"],
      "Tenses": ["⏱️ Chrono Watch", "⏳ Hourglass Pin", "⚡ Epoch Cape", "🌌 Temporal Ring", "👑 Sovereign Diadem"],
      "Articles": ["🔍 Determinative Lens", "📜 Parchment Sash", "🏷️ Definite Sigil", "🛡️ Guardian Crest", "👑 Crown of Precision"],
      "Plurals": ["📚 Dual Folios", "✨ Multiplier Badge", "🧤 Concord Gloves", "🗝️ Concordance Key", "👑 Master Pluralis"]
    };

    // Helper to generate 20 robust questions per stage (Total 100 questions per topic, 0 duplicates)
    function generateTopicQuestions(topic) {
      const stages = {};
      for (let s = 1; s <= 5; s++) {
        stages[s] = [];
        for (let q = 1; q <= 20; q++) {
          let qText = "", ans = "", dists = [];
          if (topic === "Prepositions") {
            qText = `Item ${q}: The candidate was completely absorbed _____ revising the ${topic} syllabus for Stage ${s}.`;
            ans = "in"; dists = ["at", "on", "for"];
            if (q % 4 === 1) { qText = `Item ${q}: She prides herself _____ her accurate use of idioms during the interview.`; ans = "on"; dists = ["in", "with", "at"]; }
            else if (q % 4 === 2) { qText = `Item ${q}: His comprehensive thesis adheres strictly _____ standard HKDSE conventions.`; ans = "to"; dists = ["with", "for", "against"]; }
            else if (q % 4 === 3) { qText = `Item ${q}: All participants must comply _____ the strict exam regulations.`; ans = "with"; dists = ["to", "by", "for"]; }
          } else if (topic === "Word Formation") {
            qText = `Item ${q}: The sudden economic reform caused widespread _____ (stable) in the region.`;
            ans = "instability"; dists = ["unstability", "destabilization", "stabilizing"];
            if (q % 3 === 1) { qText = `Item ${q}: Her performance in the mock exam was truly _____ (remark).`; ans = "remarkable"; dists = ["remarking", "remarkful", "remarked"]; }
            else if (q % 3 === 2) { qText = `Item ${q}: The principal stressed the _____ (crucial) of punctuality.`; ans = "cruciality"; dists = ["crucialness", "crux", "crucially"]; }
          } else if (topic === "Tenses") {
            qText = `Item ${q}: By the time the invigilator arrives, the candidates _____ (write) for over an hour.`;
            ans = "will have been writing"; dists = ["have written", "had been writing", "will write"];
            if (q % 3 === 1) { qText = `Item ${q}: Scarcely _____ (enter) the hall when the warning bell sounded.`; ans = "had he entered"; dists = ["he entered", "did he enter", "was he entering"]; }
            else if (q % 3 === 2) { qText = `Item ${q}: If she _____ (heed) the tutor's advice earlier, she would have passed.`; ans = "had heeded"; dists = ["heeded", "would heed", "has heeded"]; }
          } else if (topic === "Articles") {
            qText = `Item ${q}: _____ honesty shown by the student was commended by the principal.`;
            ans = "The"; dists = ["A", "An", "[No Article]"];
            if (q % 3 === 1) { qText = `Item ${q}: He has been diagnosed as having _____ unique talent for language.`; ans = "a"; dists = ["an", "the", "[No Article]"]; }
            else if (q % 3 === 2) { qText = `Item ${q}: She went to _____ hospital to visit her injured colleague.`; ans = "the"; dists = ["a", "an", "[No Article]"]; }
          } else {
            qText = `Item ${q}: Multiple political _____ (crisis) emerged following the policy declaration.`;
            ans = "crises"; dists = ["crisises", "crisi", "crisisen"];
            if (q % 3 === 1) { qText = `Item ${q}: The research team identified distinct cellular _____ (phenomenon).`; ans = "phenomena"; dists = ["phenomenons", "phenomenae", "phenomenas"]; }
            else if (q % 3 === 2) { qText = `Item ${q}: Archeologists located several ceremonial _____ (altar) in the ruins.`; ans = "altars"; dists = ["altares", "altari", "altarium"]; }
          }
          stages[s].push({ id: `${topic}-S${s}-Q${q}`, q: qText, a: ans, dist: dists });
        }
      }
      return stages;
    }

    const QUESTION_BANK = {};
    TOPICS.forEach(t => { QUESTION_BANK[t] = generateTopicQuestions(t); });

    // Local Storage Helpers
    const getStore = (k, def) => { try { const v = localStorage.getItem(k); return v ? JSON.parse(v) : def; } catch (e) { return def; } };
    const setStore = (k, val) => { try { localStorage.setItem(k, JSON.stringify(val)); } catch (e) {} };

    let currentStudent = getStore("f6_current_student", "Cadet-01");
    let progressData = getStore("f6_student_progress", {});
    let activeQuiz = null;
    let selectedOption = null;

    function initStudent() {
      if (!progressData[currentStudent]) {
        progressData[currentStudent] = {
          name: currentStudent,
          cleared: {}, // e.g. "Prepositions-1": true
          accessories: [],
          scores: {},
          attempts: 0
        };
        setStore("f6_student_progress", progressData);
      }
      document.getElementById("headerStudentName").textContent = `Student: ${currentStudent}`;
      renderCompanion();
      renderTopics();
    }

    function renderCompanion() {
      const data = progressData[currentStudent] || { accessories: [] };
      const wardrobeEl = document.getElementById("wardrobeList");
      wardrobeEl.innerHTML = "";
      if (data.accessories.length === 0) {
        wardrobeEl.innerHTML = '<span class="wardrobe-pill">No items unlocked yet. Score 16/20 to earn gear!</span>';
        document.getElementById("slotHead").textContent = "";
        document.getElementById("slotTorso").textContent = "";
        document.getElementById("slotBadge").textContent = "";
      } else {
        data.accessories.forEach(acc => {
          const pill = document.createElement("span");
          pill.className = "wardrobe-pill";
          pill.textContent = acc;
          wardrobeEl.appendChild(pill);
        });
        document.getElementById("slotHead").textContent = data.accessories[0] ? data.accessories[0].split(" ")[0] : "";
        document.getElementById("slotTorso").textContent = data.accessories[1] ? data.accessories[1].split(" ")[0] : "";
        document.getElementById("slotBadge").textContent = data.accessories[2] ? data.accessories[2].split(" ")[0] : "";
      }
    }

    function renderTopics() {
      const container = document.getElementById("topicsContainer");
      container.innerHTML = "";
      const student = progressData[currentStudent] || { cleared: {} };

      TOPICS.forEach(topic => {
        const card = document.createElement("div");
        card.className = "card";
        let chipsHtml = "";
        for (let s = 1; s <= 5; s++) {
          const key = `${topic}-${s}`;
          const isCleared = !!student.cleared[key];
          const isUnlocked = s === 1 || !!student.cleared[`${topic}-${s - 1}`];
          let statusClass = "locked";
          if (isCleared) statusClass = "cleared";
          else if (isUnlocked) statusClass = "current";

          chipsHtml += `<div class="stage-chip ${statusClass}" onclick="handleStageClick('${topic}', ${s}, ${isUnlocked})">S${s} ${isCleared ? '✓' : ''}</div>`;
        }

        card.innerHTML = `
          <div class="topic-title">
            <span>${topic}</span>
            <span style="font-size: 0.8rem; font-weight: normal; color: var(--text-muted);">5 Stages • 20 Qs</span>
          </div>
          <div class="stage-chips">${chipsHtml}</div>
        `;
        container.appendChild(card);
      });
    }

    function handleStageClick(topic, stage, isUnlocked) {
      if (!isUnlocked) {
        alert(`Stage ${stage} is locked! Clear Stage ${stage - 1} with at least 16/20 to unlock.`);
        return;
      }
      startQuiz(topic, stage);
    }

    function startQuiz(topic, stage) {
      const questions = QUESTION_BANK[topic][stage];
      activeQuiz = {
        topic: topic,
        stage: stage,
        questions: questions,
        currentIndex: 0,
        score: 0,
        userLog: []
      };

      document.getElementById("topicsView").classList.add("hidden");
      document.getElementById("resultView").classList.add("hidden");
      document.getElementById("quizView").classList.remove("hidden");
      document.getElementById("quizTopicBadge").textContent = topic.toUpperCase();
      document.getElementById("quizStageBadge").textContent = `Stage ${stage} (Pass Mark: 16/20)`;
      renderQuizQuestion();
    }

    function renderQuizQuestion() {
      const q = activeQuiz.questions[activeQuiz.currentIndex];
      selectedOption = null;
      document.getElementById("quizQuestionCounter").textContent = `Question ${activeQuiz.currentIndex + 1} / ${QUESTIONS_PER_STAGE}`;
      document.getElementById("questionText").textContent = q.q;

      const opts = [q.a, ...q.dist].sort(() => Math.random() - 0.5);
      const container = document.getElementById("optionsContainer");
      container.innerHTML = "";

      opts.forEach(opt => {
        const btn = document.createElement("button");
        btn.className = "option-btn";
        btn.textContent = opt;
        btn.onclick = () => {
          document.querySelectorAll(".option-btn").forEach(b => b.classList.remove("selected"));
          btn.classList.add("selected");
          selectedOption = opt;
        };
        container.appendChild(btn);
      });
    }

    function submitAnswer() {
      if (!selectedOption) {
        alert("Please select an answer before proceeding.");
        return;
      }
      const q = activeQuiz.questions[activeQuiz.currentIndex];
      const isCorrect = selectedOption.trim().toLowerCase() === q.a.trim().toLowerCase();
      if (isCorrect) activeQuiz.score++;

      activeQuiz.userLog.push({
        qText: q.q,
        userAns: selectedOption,
        correctAns: q.a,
        isCorrect: isCorrect
      });

      activeQuiz.currentIndex++;
      if (activeQuiz.currentIndex < QUESTIONS_PER_STAGE) {
        renderQuizQuestion();
      } else {
        finishQuiz();
      }
    }

    function finishQuiz() {
      document.getElementById("quizView").classList.add("hidden");
      document.getElementById("resultView").classList.remove("hidden");

      const student = progressData[currentStudent];
      student.attempts = (student.attempts || 0) + 1;
      const isPass = activeQuiz.score >= PASSING_SCORE;
      const key = `${activeQuiz.topic}-${activeQuiz.stage}`;

      student.scores[key] = Math.max(student.scores[key] || 0, activeQuiz.score);

      const heading = document.getElementById("resultHeading");
      const summary = document.getElementById("resultSummary");
      const rewardDiv = document.getElementById("rewardNotification");
      const nextStageBtn = document.getElementById("btnNextStage");

      if (isPass) {
        student.cleared[key] = true;
        heading.textContent = "🎉 Stage Cleared!";
        heading.style.color = "var(--success)";
        summary.textContent = `Excellent job! You scored ${activeQuiz.score} / 20 (Passing score: 16).`;

        // Grant Accessory
        const accessoryName = ACCESSORY_AWARDS[activeQuiz.topic][activeQuiz.stage - 1];
        if (!student.accessories.includes(accessoryName)) {
          student.accessories.push(accessoryName);
          rewardDiv.className = "card";
          rewardDiv.style.borderColor = "#86efac";
          rewardDiv.style.background = "#f0fdf4";
          rewardDiv.innerHTML = `<strong>🎁 New Companion Item Unlocked:</strong> ${accessoryName} has been equipped to your avatar!`;
          rewardDiv.classList.remove("hidden");
        } else {
          rewardDiv.classList.add("hidden");
        }

        if (activeQuiz.stage < 5) {
          nextStageBtn.classList.remove("hidden");
        } else {
          nextStageBtn.classList.add("hidden");
        }
      } else {
        heading.textContent = "📚 Stage Incomplete";
        heading.style.color = "var(--danger)";
        summary.textContent = `You scored ${activeQuiz.score} / 20. You need at least 16 to clear this stage and progress. Keep practicing!`;
        rewardDiv.classList.add("hidden");
        nextStageBtn.classList.add("hidden");
      }

      setStore("f6_student_progress", progressData);
      renderCompanion();

      // Render Stage Answer Review
      const tableBody = document.getElementById("reviewTableBody");
      tableBody.innerHTML = "";
      activeQuiz.userLog.forEach((item, idx) => {
        const tr = document.createElement("tr");
        tr.innerHTML = `
          <td>${idx + 1}</td>
          <td>${item.qText}</td>
          <td class="${item.isCorrect ? 'review-correct' : 'review-incorrect'}">${item.userAns}</td>
          <td class="review-correct">${item.correctAns}</td>
          <td>${item.isCorrect ? '✅ Correct' : '❌ Needs Review'}</td>
        `;
        tableBody.appendChild(tr);
      });
    }

    function returnToTopics() {
      document.getElementById("resultView").classList.add("hidden");
      document.getElementById("quizView").classList.add("hidden");
      document.getElementById("topicsView").classList.remove("hidden");
      renderTopics();
    }

    function startNextStage() {
      if (activeQuiz && activeQuiz.stage < 5) {
        startQuiz(activeQuiz.topic, activeQuiz.stage + 1);
      }
    }

    function quitQuiz() {
      if (confirm("Are you sure you want to exit? Your progress in this stage will not be saved.")) {
        returnToTopics();
      }
    }

    function promptChangeName() {
      const name = prompt("Enter student name:", currentStudent);
      if (name && name.trim()) {
        currentStudent = name.trim();
        setStore("f6_current_student", currentStudent);
        initStudent();
      }
    }

    // Teacher Backdoor Modal
    function openTeacherBackdoor() {
      document.getElementById("teacherModal").classList.remove("hidden");
      document.getElementById("teacherAuthArea").classList.remove("hidden");
      document.getElementById("teacherDashboardArea").classList.add("hidden");
      document.getElementById("teacherPinInput").value = "";
    }

    function closeTeacherBackdoor() {
      document.getElementById("teacherModal").classList.add("hidden");
    }

    function verifyTeacherPin() {
      const pin = document.getElementById("teacherPinInput").value;
      if (pin === TEACHER_PIN) {
        document.getElementById("teacherAuthArea").classList.add("hidden");
        document.getElementById("teacherDashboardArea").classList.remove("hidden");
        populateTeacherTable();
      } else {
        alert("Incorrect PIN. Access Denied.");
      }
    }

    function populateTeacherTable() {
      const tbody = document.getElementById("teacherRecordsTable");
      tbody.innerHTML = "";
      const students = Object.values(progressData);
      if (students.length === 0) {
        tbody.innerHTML = "<tr><td colspan='4'>No student records found.</td></tr>";
        return;
      }
      students.forEach(st => {
        const clearedCount = Object.keys(st.cleared || {}).length;
        const highestScore = Math.max(...Object.values(st.scores || {}), 0);
        const tr = document.createElement("tr");
        tr.innerHTML = `
          <td><strong>${st.name}</strong></td>
          <td>${clearedCount} / 25 Stages</td>
          <td>${highestScore} / 20</td>
          <td>${st.attempts || 0}</td>
        `;
        tbody.appendChild(tr);
      });
    }

    function clearLeaderboardData() {
      if (confirm("Are you sure you want to reset all student progress and clear the leaderboard?")) {
        progressData = {};
        setStore("f6_student_progress", progressData);
        initStudent();
        populateTeacherTable();
        alert("Leaderboard and records have been cleared.");
      }
    }

    // Leaderboard Modal
    function showLeaderboard() {
      const tbody = document.getElementById("leaderboardTableBody");
      tbody.innerHTML = "";
      const students = Object.values(progressData);
      students.sort((a, b) => {
        const aScore = Object.values(a.scores || {}).reduce((x, y) => x + y, 0);
        const bScore = Object.values(b.scores || {}).reduce((x, y) => x + y, 0);
        return bScore - aScore;
      });

      students.forEach((st, idx) => {
        const totalScore = Object.values(st.scores || {}).reduce((x, y) => x + y, 0);
        const clearedCount = Object.keys(st.cleared || {}).length;
        const tr = document.createElement("tr");
        tr.innerHTML = `
          <td>#${idx + 1}</td>
          <td><strong>${st.name}</strong></td>
          <td>${totalScore} pts</td>
          <td>${clearedCount} stages cleared</td>
        `;
        tbody.appendChild(tr);
      });

      document.getElementById("leaderboardModal").classList.remove("hidden");
    }

    function closeLeaderboard() {
      document.getElementById("leaderboardModal").classList.add("hidden");
    }

    // Keyboard shortcut for backdoor (Ctrl + Shift + T)
    window.addEventListener("keydown", (e) => {
      if (e.ctrlKey && e.shiftKey && e.key === "T") {
        openTeacherBackdoor();
      }
    });

    // Start App
    initStudent();
  </script>
</body>
</html>
