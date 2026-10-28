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
    .choice-btn.selected { backgroun
