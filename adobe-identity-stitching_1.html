<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>How Adobe stitches identity into one profile</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<!-- Adobe Clean is proprietary. If you have an Adobe Fonts (Typekit) kit
     that includes Adobe Clean + Adobe Clean Mono, paste your kit link below
     and the deck will use it automatically. Otherwise the fallback is
     Source Sans 3 + Source Code Pro — Adobe's own open-source sister faces. -->
<!-- <link rel="stylesheet" href="https://use.typekit.net/YOUR_KIT_ID.css" /> -->
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,300;0,400;0,500;0,600;0,700;0,900;1,400;1,600&family=Source+Code+Pro:wght@400;500&display=swap" rel="stylesheet" />
<style>
  :root {
    --bg: #FFFFFF;
    --paper: #FFFFFF;
    --ink: #0E0E0E;
    --ink-soft: #6B6B6B;
    --ink-faint: #A8A8A2;
    --line: #E5E5E0;
    --line-strong: #1A1A1A;
    --adobe-red: #EB1000;
    --adobe-red-bright: #FA0F00;
    --graph-blue: #1473E6;
    --graph-blue-soft: #B7D6FA;
    --stitch-gold: #EB1000;      /* the "linked" accent — now Adobe red */
    --stitch-gold-soft: #FFD4D1; /* soft red wash for shadows */
    --slot-ghost: #D5D5D0;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  html, body {
    height: 100%;
    background: var(--bg);
    color: var(--ink);
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-weight: 400;
    overflow: hidden;
    -webkit-font-smoothing: antialiased;
    text-rendering: optimizeLegibility;
  }

  .stage-wrap {
    position: fixed;
    inset: 0;
    display: grid;
    place-items: center;
    background: var(--paper);
    overflow: hidden;
  }

  .stage {
    width: 1920px;
    height: 1080px;
    position: relative;
    background: var(--paper);
    transform-origin: center center;
    overflow: hidden;
  }

  .slide {
    position: absolute;
    inset: 0;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.55s cubic-bezier(0.4, 0, 0.2, 1);
    padding: 96px 112px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 48px;
  }

  .slide.active {
    opacity: 1;
    pointer-events: all;
  }

  /* TYPOGRAPHY */
  h1 {
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-weight: 900;
    font-size: 124px;
    line-height: 0.96;
    letter-spacing: -0.04em;
  }
  h1 em { font-style: italic; font-weight: 900; color: var(--adobe-red); }

  h2 {
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-weight: 800;
    font-size: 84px;
    line-height: 1.02;
    letter-spacing: -0.035em;
  }
  h2 em { font-style: italic; font-weight: 800; color: var(--adobe-red); }

  .eyebrow {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 14px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--ink);
    font-weight: 600;
  }
  .eyebrow::before {
    content: '';
    display: inline-block;
    width: 6px;
    height: 6px;
    background: var(--adobe-red);
    margin-right: 10px;
    vertical-align: 2px;
  }

  .lede {
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-style: normal;
    font-weight: 300;
    font-size: 32px;
    line-height: 1.35;
    color: var(--ink-soft);
    max-width: 1100px;
  }

  .body {
    font-size: 22px;
    line-height: 1.55;
    color: var(--ink);
    max-width: 720px;
  }

  .mono {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 14px;
    letter-spacing: 0.04em;
  }

  /* HEADER + FOOTER */
  .slide-header {
    position: absolute;
    top: 56px;
    left: 0;
    right: 0;
    padding: 0 112px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .brand {
    display: flex;
    align-items: center;
    gap: 12px;
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 12px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--ink);
    font-weight: 600;
  }

  .brand .mark {
    width: 22px;
    height: 20px;
    background: var(--adobe-red);
    display: grid;
    place-items: center;
    color: #fff;
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-weight: 900;
    font-size: 14px;
    line-height: 1;
    letter-spacing: 0;
    padding-bottom: 1px;
  }

  .slide-number {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 12px;
    letter-spacing: 0.15em;
    color: var(--ink-faint);
  }

  /* SLIDE 1 - TITLE */
  .slide-title h1 { max-width: 1500px; }
  .title-meta {
    display: flex;
    justify-content: space-between;
    align-items: end;
    margin-top: 48px;
  }
  .title-meta .lede { max-width: 760px; font-size: 28px; }

  /* SLIDE 2 - PROBLEM */
  .problem-stage {
    height: 720px;
    position: relative;
  }

  .silhouette {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 280px;
    height: 280px;
    border-radius: 50%;
    background: var(--bg);
    border: 1.5px dashed var(--ink-faint);
    display: grid;
    place-items: center;
  }

  .silhouette-label {
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    color: var(--ink-soft);
    text-align: center;
    line-height: 1.2;
    letter-spacing: -0.01em;
  }
  .silhouette-label small {
    display: block;
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-style: normal;
    font-size: 11px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--ink-faint);
    margin-bottom: 8px;
  }

  .floater {
    position: absolute;
    padding: 12px 20px;
    background: var(--paper);
    border: 1.5px solid var(--slot-ghost);
    border-radius: 999px;
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 13px;
    color: var(--ink-soft);
    white-space: nowrap;
    animation: float 6s ease-in-out infinite;
  }
  .floater::before {
    content: '';
    display: inline-block;
    width: 6px;
    height: 6px;
    background: var(--ink-faint);
    border-radius: 50%;
    margin-right: 8px;
    vertical-align: middle;
  }

  @keyframes float {
    0%, 100% { transform: translate(0, 0); }
    50% { transform: translate(0, -10px); }
  }

  /* HERO STITCH SLIDE */
  .stitch-slide { padding: 64px 80px; }
  .stitch-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
  }
  .stitch-header h2 {
    font-size: 56px;
    max-width: 900px;
  }
  .stitch-stage {
    height: 740px;
    position: relative;
    display: grid;
    grid-template-columns: 1fr 360px;
    gap: 32px;
  }

  .canvas {
    position: relative;
    background:
      linear-gradient(var(--line) 1px, transparent 1px) 0 0 / 64px 64px,
      linear-gradient(90deg, var(--line) 1px, transparent 1px) 0 0 / 64px 64px,
      var(--paper);
    border: 1px solid var(--line);
    overflow: hidden;
  }

  .stitch-svg {
    position: absolute;
    inset: 0;
    pointer-events: none;
  }

  .chip {
    position: absolute;
    padding: 14px 18px;
    background: var(--paper);
    border: 1.5px solid var(--slot-ghost);
    border-radius: 999px;
    display: flex;
    align-items: center;
    gap: 12px;
    opacity: 0.35;
    transform: translate(-50%, -50%);
    transition:
      opacity 0.7s cubic-bezier(0.4, 0, 0.2, 1),
      border-color 0.7s ease,
      box-shadow 0.7s ease,
      color 0.7s ease;
    white-space: nowrap;
    z-index: 3;
  }

  .chip.pulse {
    opacity: 1;
    border-color: var(--graph-blue);
    box-shadow: 0 0 0 6px rgba(20,115,230,0.12);
    animation: chipPulse 0.8s ease-out;
  }

  @keyframes chipPulse {
    0% { transform: translate(-50%, -50%) scale(1); }
    50% { transform: translate(-50%, -50%) scale(1.08); }
    100% { transform: translate(-50%, -50%) scale(1); }
  }

  .chip.linked {
    opacity: 1;
    border-color: var(--stitch-gold);
    box-shadow: 0 0 0 4px rgba(235,16,0,0.10);
  }

  .chip-ns {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--ink-faint);
    font-weight: 500;
  }
  .chip.pulse .chip-ns { color: var(--graph-blue); }
  .chip.linked .chip-ns { color: var(--stitch-gold); }

  .chip-val {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 14px;
    color: var(--ink-soft);
  }
  .chip.pulse .chip-val,
  .chip.linked .chip-val { color: var(--ink); }

  .stitch-line {
    fill: none;
    stroke: var(--stitch-gold);
    stroke-width: 1.5;
    opacity: 0;
    transition: opacity 0.4s ease;
  }
  .stitch-line.drawing { opacity: 0.55; }
  .stitch-line.drawn { opacity: 0.35; }

  .profile-card {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 360px;
    background: var(--paper);
    border: 1.5px solid var(--ink);
    border-left: 6px solid var(--stitch-gold);
    padding: 28px 32px 24px;
    z-index: 5;
    transition: box-shadow 0.5s ease;
  }
  .profile-card.complete {
    box-shadow: 0 20px 50px -20px rgba(235,16,0,0.35);
  }

  .profile-eyebrow {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 10px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--ink-soft);
  }

  .profile-name {
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-weight: 700;
    font-size: 28px;
    letter-spacing: -0.02em;
    line-height: 1.1;
    margin-top: 8px;
    transition: color 0.5s ease;
  }

  .profile-meta {
    margin-top: 18px;
    padding-top: 14px;
    border-top: 1px solid var(--line);
    display: flex;
    justify-content: space-between;
    align-items: baseline;
  }
  .profile-meta-label {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--ink-faint);
  }
  .profile-count {
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-weight: 800;
    font-size: 32px;
    color: var(--adobe-red);
    letter-spacing: -0.02em;
  }

  /* RIGHT-SIDE EVENT LOG */
  .event-log {
    background: var(--paper);
    border: 1px solid var(--line);
    padding: 28px 28px 20px;
    display: flex;
    flex-direction: column;
  }

  .log-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    padding-bottom: 16px;
    border-bottom: 1px solid var(--line);
    margin-bottom: 12px;
  }
  .log-title {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 11px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--ink-soft);
  }
  .log-pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 10px;
    letter-spacing: 0.12em;
    color: var(--ink-soft);
  }
  .log-pill .live {
    width: 6px;
    height: 6px;
    background: var(--adobe-red);
    border-radius: 50%;
    animation: livePulse 1.6s ease-in-out infinite;
  }
  @keyframes livePulse {
    0%, 100% { opacity: 0.3; }
    50% { opacity: 1; }
  }

  .log-list {
    list-style: none;
    flex: 1;
    overflow: hidden;
  }
  .log-item {
    padding: 12px 0;
    border-bottom: 1px solid var(--line);
    opacity: 0;
    transform: translateY(8px);
    transition: opacity 0.5s ease, transform 0.5s ease;
  }
  .log-item.shown {
    opacity: 1;
    transform: translateY(0);
  }
  .log-item:last-child { border-bottom: 0; }

  .log-time {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    color: var(--ink-faint);
  }
  .log-event {
    font-size: 14px;
    margin-top: 2px;
    color: var(--ink);
  }
  .log-id {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 11px;
    color: var(--stitch-gold);
    margin-top: 4px;
  }

  .replay-btn {
    position: absolute;
    bottom: 24px;
    right: 24px;
    background: var(--ink);
    color: var(--paper);
    border: none;
    padding: 10px 18px;
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 11px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    cursor: pointer;
    opacity: 0;
    transition: opacity 0.5s ease, background 0.2s ease;
    z-index: 20;
  }
  .replay-btn.shown { opacity: 1; }
  .replay-btn:hover { background: var(--adobe-red); }

  /* MECHANISM SLIDE */
  .mech-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }
  .mech-svg {
    width: 100%;
    height: auto;
  }
  .mech-points {
    display: flex;
    flex-direction: column;
    gap: 28px;
  }
  .mech-point {
    display: grid;
    grid-template-columns: 56px 1fr;
    gap: 20px;
    align-items: start;
  }
  .mech-num {
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-style: normal;
    font-weight: 900;
    font-size: 56px;
    color: var(--adobe-red);
    line-height: 0.9;
    letter-spacing: -0.04em;
  }
  .mech-point-title {
    font-size: 22px;
    font-weight: 700;
    margin-bottom: 4px;
    letter-spacing: -0.01em;
  }
  .mech-point-body {
    font-size: 17px;
    color: var(--ink-soft);
    line-height: 1.5;
  }

  /* ARCHITECTURE SLIDE */
  .arch-stage {
    display: grid;
    grid-template-columns: 480px 1fr;
    gap: 80px;
    align-items: center;
  }
  .arch-stack {
    position: relative;
    padding: 32px;
    border: 2px dashed var(--ink-faint);
  }
  .arch-stack::before {
    content: 'SANDBOX BOUNDARY · TENANT-ISOLATED';
    position: absolute;
    top: -10px;
    left: 24px;
    background: var(--paper);
    padding: 0 12px;
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 10px;
    letter-spacing: 0.16em;
    color: var(--ink-soft);
  }
  .arch-layer {
    background: var(--paper);
    border: 1.5px solid var(--ink);
    padding: 20px 24px;
    margin-bottom: 12px;
    transition: transform 0.3s ease;
  }
  .arch-layer:last-child { margin-bottom: 0; }
  .arch-layer.top {
    border-left: 6px solid var(--stitch-gold);
  }
  .arch-layer.mid {
    border-left: 6px solid var(--graph-blue);
  }
  .arch-layer-eyebrow {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 10px;
    letter-spacing: 0.16em;
    text-transform: uppercase;
    color: var(--ink-soft);
  }
  .arch-layer-name {
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-weight: 700;
    font-size: 26px;
    letter-spacing: -0.015em;
    margin-top: 4px;
  }
  .arch-layer-sub {
    font-size: 14px;
    color: var(--ink-soft);
    margin-top: 4px;
  }

  /* OUTCOMES SLIDE */
  .outcomes {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 56px;
    align-items: start;
  }
  .outcome {
    border-top: 2px solid var(--adobe-red);
    padding-top: 28px;
  }
  .outcome-num {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 12px;
    letter-spacing: 0.16em;
    color: var(--adobe-red);
    font-weight: 600;
    margin-bottom: 32px;
  }
  .outcome-title {
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-style: normal;
    font-weight: 800;
    font-size: 38px;
    line-height: 1.05;
    letter-spacing: -0.025em;
    margin-bottom: 18px;
  }
  .outcome-body {
    font-size: 17px;
    line-height: 1.55;
    color: var(--ink-soft);
  }

  /* SUMMARY */
  .summary {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  .summary h2 {
    font-size: 96px;
    max-width: 1400px;
  }
  .summary-arc {
    display: flex;
    align-items: center;
    gap: 40px;
    margin-top: 80px;
  }
  .summary-step {
    text-align: center;
  }
  .summary-step-icon {
    width: 80px;
    height: 80px;
    border: 1.5px solid var(--ink);
    border-radius: 50%;
    display: grid;
    place-items: center;
    margin: 0 auto 16px;
    background: var(--paper);
  }
  .summary-step-icon.fragments { border-style: dashed; }
  .summary-step-icon.graph { background: var(--paper); }
  .summary-step-icon.profile {
    background: var(--ink);
    border-color: var(--ink);
  }
  .summary-step-label {
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 12px;
    letter-spacing: 0.16em;
    text-transform: uppercase;
    color: var(--ink);
  }
  .summary-arrow {
    color: var(--ink-faint);
    font-size: 24px;
  }

  /* PERSISTENT BRAND MARK */
  .stage-mark {
    position: absolute;
    bottom: 48px;
    left: 56px;
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 11px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--ink-soft);
    z-index: 50;
    pointer-events: none;
  }
  .stage-mark .mark {
    width: 20px;
    height: 18px;
    background: var(--adobe-red);
    display: grid;
    place-items: center;
    color: #fff;
    font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif;
    font-weight: 900;
    font-size: 13px;
    line-height: 1;
    padding-bottom: 1px;
  }

  /* NAV */
  .nav {
    position: fixed;
    bottom: 16px;
    right: 16px;
    display: flex;
    gap: 8px;
    align-items: center;
    z-index: 100;
    background: rgba(255,255,255,0.7);
    backdrop-filter: blur(8px);
    border: 1px solid var(--line);
    padding: 6px 10px;
    border-radius: 999px;
    font-family: 'Adobe Clean Mono', 'Source Code Pro', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    color: var(--ink-soft);
    opacity: 0.25;
    transition: opacity 0.4s ease;
  }
  .nav:hover,
  .nav.active {
    opacity: 1;
  }
  .nav-btn {
    background: none;
    border: none;
    cursor: pointer;
    color: var(--ink);
    font-family: inherit;
    font-size: inherit;
    padding: 2px 6px;
    border-radius: 999px;
    transition: background 0.2s ease;
  }
  .nav-btn:hover { background: var(--bg); }
  .nav-counter {
    letter-spacing: 0.14em;
    color: var(--ink-faint);
  }
</style>
</head>
<body>

<div class="stage-wrap">
<div class="stage" id="stage">

  <!-- SLIDE 1: TITLE -->
  <section class="slide slide-title active" data-slide="1">
    <div class="slide-header">
      <div class="brand"><span class="mark">A</span><span>Adobe · Real-Time CDP</span></div>
      <div class="slide-number">01 / 07</div>
    </div>
    <h1>How Adobe stitches<br><em>identity</em> into one<br>customer profile.</h1>
    <div class="title-meta">
      <div class="lede">A short explainer on identity namespaces, private graphs, and real-time profile assembly.</div>
      <div class="eyebrow">Press → to begin</div>
    </div>
  </section>

  <!-- SLIDE 2: THE PROBLEM -->
  <section class="slide" data-slide="2">
    <div class="slide-header">
      <div class="eyebrow">01 — The Problem</div>
      <div class="slide-number">02 / 07</div>
    </div>
    <h2>One customer.<br><em>Many fragments.</em></h2>
    <div class="problem-stage" id="problemStage">
      <div class="silhouette">
        <div class="silhouette-label">
          <small>Who is this person?</small>
          unknown
        </div>
      </div>
      <!-- floaters positioned via JS to spread evenly -->
    </div>
  </section>

  <!-- SLIDE 3: HERO STITCH ANIMATION -->
  <section class="slide stitch-slide" data-slide="3">
    <div class="slide-header">
      <div class="eyebrow">02 — Watch the Stitch</div>
      <div class="slide-number">03 / 07</div>
    </div>
    <div class="stitch-header">
      <h2>Identifiers link to the profile <em>one event at a time.</em></h2>
    </div>
    <div class="stitch-stage">
      <div class="canvas" id="canvas">
        <svg class="stitch-svg" id="stitchSvg" preserveAspectRatio="none"></svg>

        <div class="profile-card" id="profileCard">
          <div class="profile-eyebrow">Real-Time Customer Profile</div>
          <div class="profile-name" id="profileName">Unidentified visitor</div>
          <div class="profile-meta">
            <span class="profile-meta-label">Linked identifiers</span>
            <span class="profile-count" id="profileCount">0</span>
          </div>
        </div>

        <button class="replay-btn" id="replayBtn">↻ Replay</button>
      </div>

      <div class="event-log">
        <div class="log-header">
          <span class="log-title">Event Stream</span>
          <span class="log-pill"><span class="live"></span>LIVE</span>
        </div>
        <ul class="log-list" id="logList"></ul>
      </div>
    </div>
  </section>

  <!-- SLIDE 4: HOW IT WORKS -->
  <section class="slide" data-slide="4">
    <div class="slide-header">
      <div class="eyebrow">03 — Mechanism</div>
      <div class="slide-number">04 / 07</div>
    </div>
    <h2>Links form from <em>shared identifiers</em> in real events.</h2>
    <div class="mech-grid">
      <div>
        <svg class="mech-svg" viewBox="0 0 600 480" xmlns="http://www.w3.org/2000/svg">
          <!-- nodes -->
          <g font-family="Adobe Clean Mono, Source Code Pro, monospace" font-size="11" letter-spacing="0.05em">
            <!-- ECID -->
            <circle cx="120" cy="120" r="48" fill="#FFF" stroke="#1473E6" stroke-width="1.5"/>
            <text x="120" y="116" text-anchor="middle" fill="#1473E6" font-weight="500">ECID</text>
            <text x="120" y="132" text-anchor="middle" fill="#6B6B6B" font-size="10">4839…7c2</text>

            <!-- Email -->
            <circle cx="380" cy="80" r="48" fill="#FFF" stroke="#1473E6" stroke-width="1.5"/>
            <text x="380" y="76" text-anchor="middle" fill="#1473E6" font-weight="500">EMAIL</text>
            <text x="380" y="92" text-anchor="middle" fill="#6B6B6B" font-size="10">6f3b…91d</text>

            <!-- CRMID -->
            <circle cx="490" cy="280" r="48" fill="#FFF" stroke="#1473E6" stroke-width="1.5"/>
            <text x="490" y="276" text-anchor="middle" fill="#1473E6" font-weight="500">CRMID</text>
            <text x="490" y="292" text-anchor="middle" fill="#6B6B6B" font-size="10">C-77419</text>

            <!-- Mobile ECID -->
            <circle cx="310" cy="400" r="48" fill="#FFF" stroke="#1473E6" stroke-width="1.5"/>
            <text x="310" y="396" text-anchor="middle" fill="#1473E6" font-weight="500">ECID</text>
            <text x="310" y="412" text-anchor="middle" fill="#6B6B6B" font-size="10">a91e…03b</text>

            <!-- Loyalty -->
            <circle cx="80" cy="340" r="48" fill="#FFF" stroke="#1473E6" stroke-width="1.5"/>
            <text x="80" y="336" text-anchor="middle" fill="#1473E6" font-weight="500">LOYAL</text>
            <text x="80" y="352" text-anchor="middle" fill="#6B6B6B" font-size="10">L-2241</text>
          </g>

          <!-- edges with event labels -->
          <g stroke="#EB1000" stroke-width="1.2" fill="none" opacity="0.7">
            <line x1="168" y1="120" x2="332" y2="80" />
            <line x1="428" y1="80" x2="490" y2="232" />
            <line x1="442" y1="280" x2="358" y2="400" />
            <line x1="262" y1="400" x2="128" y2="340" />
            <line x1="80" y1="292" x2="120" y2="168" />
          </g>

          <g font-family="Adobe Clean Mono, Source Code Pro, monospace" font-size="9" fill="#6B6B6B" letter-spacing="0.06em">
            <text x="250" y="92" text-anchor="middle">newsletter signup</text>
            <text x="468" y="172" text-anchor="middle" transform="rotate(58 468 172)">account login</text>
            <text x="412" y="350" text-anchor="middle" transform="rotate(-55 412 350)">app login</text>
            <text x="195" y="378" text-anchor="middle">loyalty enroll</text>
            <text x="92" y="232" text-anchor="middle" transform="rotate(-90 92 232)">SMS opt-in</text>
          </g>
        </svg>
      </div>

      <div class="mech-points">
        <div class="mech-point">
          <div class="mech-num">1</div>
          <div>
            <div class="mech-point-title">Every event carries identifiers.</div>
            <div class="mech-point-body">A login event ships an ECID and a CRMID together. A purchase ships an ECID and a hashed email. Each pairing is evidence.</div>
          </div>
        </div>
        <div class="mech-point">
          <div class="mech-num">2</div>
          <div>
            <div class="mech-point-title">The Identity Service writes the link.</div>
            <div class="mech-point-body">Two identifiers seen in the same event become connected nodes in your private graph. Deterministic. No probabilistic inference.</div>
          </div>
        </div>
        <div class="mech-point">
          <div class="mech-num">3</div>
          <div>
            <div class="mech-point-title">The graph resolves the cluster.</div>
            <div class="mech-point-body">When a new event arrives, the service returns every identifier transitively linked to it — and the profile is assembled from all of them.</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- SLIDE 5: ARCHITECTURE -->
  <section class="slide" data-slide="5">
    <div class="slide-header">
      <div class="eyebrow">04 — Architecture</div>
      <div class="slide-number">05 / 07</div>
    </div>
    <h2>Private graph. <em>Real-time</em> profile.</h2>
    <div class="arch-stage">
      <div class="arch-stack">
        <div class="arch-layer top">
          <div class="arch-layer-eyebrow">Output</div>
          <div class="arch-layer-name">Real-Time Customer Profile</div>
          <div class="arch-layer-sub">Assembled record · &lt; 1 second to activation</div>
        </div>
        <div class="arch-layer mid">
          <div class="arch-layer-eyebrow">Linking</div>
          <div class="arch-layer-name">Identity Service</div>
          <div class="arch-layer-sub">Maintains the private identity graph</div>
        </div>
        <div class="arch-layer">
          <div class="arch-layer-eyebrow">Input</div>
          <div class="arch-layer-name">Events in XDM</div>
          <div class="arch-layer-sub">Each event carries one or more identifiers</div>
        </div>
      </div>
      <div class="body" style="max-width: 620px;">
        <p style="font-family: 'Adobe Clean', 'Source Sans 3', system-ui, sans-serif; font-weight: 700; font-size: 30px; line-height: 1.25; letter-spacing: -0.02em; color: var(--ink); margin-bottom: 28px;">Every identity graph is per-customer and per-sandbox. <em style="color: var(--adobe-red); font-style: normal;">No cross-tenant linkage.</em></p>
        <p style="font-size: 18px; color: var(--ink-soft); line-height: 1.55;">Adobe also offers a separate, opt-in device co-op graph for partners who want shared reach. It's a distinct product — never conflated with your private graph.</p>
      </div>
    </div>
  </section>

  <!-- SLIDE 6: OUTCOMES -->
  <section class="slide" data-slide="6">
    <div class="slide-header">
      <div class="eyebrow">05 — Outcomes</div>
      <div class="slide-number">06 / 07</div>
    </div>
    <h2>What stitching <em>unlocks.</em></h2>
    <div class="outcomes">
      <div class="outcome">
        <div class="outcome-num">01</div>
        <div class="outcome-title">Consistent experience.</div>
        <div class="outcome-body">The same person is recognized on web, app, email, and in-store — even when they switch devices mid-journey.</div>
      </div>
      <div class="outcome">
        <div class="outcome-num">02</div>
        <div class="outcome-title">Suppression that works.</div>
        <div class="outcome-body">No re-targeting someone who just bought. The profile knows about the conversion within seconds, not days.</div>
      </div>
      <div class="outcome">
        <div class="outcome-num">03</div>
        <div class="outcome-title">Audiences built on people.</div>
        <div class="outcome-body">Segments resolve against unified profiles, not cookies. Reach numbers match reality, not double-counted devices.</div>
      </div>
    </div>
  </section>

  <!-- SLIDE 7: SUMMARY -->
  <section class="slide" data-slide="7">
    <div class="slide-header">
      <div class="eyebrow">06 — In Summary</div>
      <div class="slide-number">07 / 07</div>
    </div>
    <div class="summary">
      <h2>Scattered identifiers become a<br><em>real-time, resolved profile</em> —<br>deterministically, in a <em>private graph.</em></h2>
      <div class="summary-arc">
        <div class="summary-step">
          <div class="summary-step-icon fragments">
            <svg width="32" height="32" viewBox="0 0 32 32"><circle cx="8" cy="10" r="2.5" fill="#6B6B6B"/><circle cx="22" cy="8" r="2.5" fill="#6B6B6B"/><circle cx="16" cy="20" r="2.5" fill="#6B6B6B"/><circle cx="6" cy="24" r="2.5" fill="#6B6B6B"/><circle cx="24" cy="22" r="2.5" fill="#6B6B6B"/></svg>
          </div>
          <div class="summary-step-label">Fragments</div>
        </div>
        <div class="summary-arrow">→</div>
        <div class="summary-step">
          <div class="summary-step-icon graph">
            <svg width="36" height="36" viewBox="0 0 36 36"><g stroke="#EB1000" stroke-width="1.2" fill="none"><line x1="10" y1="10" x2="26" y2="12"/><line x1="26" y1="12" x2="18" y2="26"/><line x1="18" y1="26" x2="10" y2="10"/><line x1="26" y1="12" x2="28" y2="24"/></g><g fill="#EB1000"><circle cx="10" cy="10" r="2.5"/><circle cx="26" cy="12" r="2.5"/><circle cx="18" cy="26" r="2.5"/><circle cx="28" cy="24" r="2.5"/></g></svg>
          </div>
          <div class="summary-step-label">Identity Graph</div>
        </div>
        <div class="summary-arrow">→</div>
        <div class="summary-step">
          <div class="summary-step-icon profile">
            <svg width="32" height="32" viewBox="0 0 32 32"><circle cx="16" cy="12" r="5" fill="none" stroke="#FAFAF7" stroke-width="1.5"/><path d="M 6 26 Q 16 18 26 26" fill="none" stroke="#FAFAF7" stroke-width="1.5"/></svg>
          </div>
          <div class="summary-step-label">One Profile</div>
        </div>
      </div>
    </div>
  </section>

  <div class="stage-mark">
    <span class="mark">A</span>
    <span>Adobe · Real-Time CDP</span>
  </div>

</div>
</div>

<div class="nav" id="nav">
  <button class="nav-btn" id="prevBtn">←</button>
  <span class="nav-counter" id="navCounter">01 / 07</span>
  <button class="nav-btn" id="nextBtn">→</button>
</div>

<script>
  // ============================================================
  // STAGE SCALING — keep 1920×1080 stage centered & scaled
  // ============================================================
  const stage = document.getElementById('stage');
  function fitStage() {
    const sx = window.innerWidth / 1920;
    const sy = window.innerHeight / 1080;
    const s = Math.min(sx, sy);
    stage.style.transform = `scale(${s})`;
  }
  window.addEventListener('resize', fitStage);
  fitStage();

  // ============================================================
  // NAVIGATION
  // ============================================================
  const slides = document.querySelectorAll('.slide');
  const navCounter = document.getElementById('navCounter');
  const prevBtn = document.getElementById('prevBtn');
  const nextBtn = document.getElementById('nextBtn');
  let current = 0;
  const total = slides.length;

  function go(i) {
    if (i < 0 || i >= total) return;
    slides[current].classList.remove('active');
    current = i;
    slides[current].classList.add('active');
    navCounter.textContent = String(current + 1).padStart(2, '0') + ' / ' + String(total).padStart(2, '0');
    if (slides[current].dataset.slide === '3') {
      // restart hero animation when entering the stitch slide
      setTimeout(runStitch, 350);
    }
  }

  document.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowRight' || e.key === ' ' || e.key === 'PageDown') {
      e.preventDefault();
      go(current + 1);
    } else if (e.key === 'ArrowLeft' || e.key === 'PageUp') {
      e.preventDefault();
      go(current - 1);
    }
  });
  prevBtn.addEventListener('click', () => go(current - 1));
  nextBtn.addEventListener('click', () => go(current + 1));

  // ============================================================
  // SLIDE 2 — scatter the "fragment" floaters around silhouette
  // ============================================================
  const problemStage = document.getElementById('problemStage');
  const fragments = [
    { ns: 'ECID', val: '4839…7c2',  x: 22, y: 18 },
    { ns: 'EMAIL', val: '6f3b…91d', x: 76, y: 22 },
    { ns: 'CRMID', val: 'C-77419',  x: 14, y: 48 },
    { ns: 'LOYAL', val: 'L-2241',   x: 82, y: 50 },
    { ns: 'IDFA',  val: 'EE…4D-A9', x: 28, y: 78 },
    { ns: 'PHONE', val: '8c2a…ff1', x: 70, y: 80 },
    { ns: 'ECID',  val: 'a91e…03b', x: 50, y: 88 },
    { ns: 'GAID',  val: 'a8c0…ff2', x: 12, y: 70 },
  ];
  fragments.forEach((f, i) => {
    const el = document.createElement('div');
    el.className = 'floater';
    el.style.left = f.x + '%';
    el.style.top = f.y + '%';
    el.style.animationDelay = (i * 0.4) + 's';
    el.innerHTML = `<span style="font-weight:500; color: var(--ink); margin-right: 4px;">${f.ns}</span> ${f.val}`;
    problemStage.appendChild(el);
  });

  // ============================================================
  // SLIDE 3 — HERO STITCH ANIMATION
  // ============================================================
  // Each identifier docks at a fixed angle around the profile card.
  // Sequence: event banner shows in the log → chip pulses (blue) →
  // line draws from chip to profile → chip becomes "linked" (gold) →
  // profile counter increments. Names also update at key moments.

  const canvas = document.getElementById('canvas');
  const svg = document.getElementById('stitchSvg');
  const profileCard = document.getElementById('profileCard');
  const profileName = document.getElementById('profileName');
  const profileCount = document.getElementById('profileCount');
  const logList = document.getElementById('logList');
  const replayBtn = document.getElementById('replayBtn');

  const identifiers = [
    { id: 'web-ecid',    ns: 'ECID',            val: '4839…7c2',  angle: 200, time: '09:14:02', event: 'Anonymous visit · adobe.com',  profileName: 'Anonymous web visitor' },
    { id: 'email',       ns: 'Email (SHA-256)', val: '6f3b…91d',  angle: 245, time: '09:14:48', event: 'Newsletter signup',            profileName: 'Newsletter subscriber' },
    { id: 'crmid',       ns: 'CRMID',           val: 'C-77419',   angle: 290, time: '11:23:09', event: 'Account login · web',          profileName: 'Maya Chen' },
    { id: 'loyalty',     ns: 'Loyalty ID',      val: 'L-2241',    angle: 335, time: '14:51:33', event: 'Loyalty enrollment',           profileName: 'Maya Chen' },
    { id: 'mobile-ecid', ns: 'ECID',            val: 'a91e…03b',  angle: 20,  time: '17:02:11', event: 'App opened · iOS',             profileName: 'Maya Chen' },
    { id: 'idfa',        ns: 'IDFA',            val: 'EE…4D-A9',  angle: 65,  time: '17:02:14', event: 'In-app product view',          profileName: 'Maya Chen' },
    { id: 'phone',       ns: 'Phone (SHA-256)', val: '8c2a…ff1',  angle: 110, time: '19:30:00', event: 'SMS opt-in',                   profileName: 'Maya Chen' },
  ];

  // Layout — compute chip positions around the canvas center,
  // wait until canvas has dimensions
  function layoutChips() {
    // Clear existing
    canvas.querySelectorAll('.chip').forEach(el => el.remove());
    svg.innerHTML = '';

    const rect = canvas.getBoundingClientRect();
    // canvas is scaled by the stage transform; compute in stage coordinates
    const cw = canvas.offsetWidth;
    const ch = canvas.offsetHeight;
    const cx = cw / 2;
    const cy = ch / 2;
    const radius = Math.min(cw, ch) * 0.36;

    svg.setAttribute('viewBox', `0 0 ${cw} ${ch}`);

    identifiers.forEach((d, i) => {
      const rad = (d.angle * Math.PI) / 180;
      const x = cx + Math.cos(rad) * radius;
      const y = cy + Math.sin(rad) * radius;

      // chip
      const chip = document.createElement('div');
      chip.className = 'chip';
      chip.dataset.id = d.id;
      chip.style.left = x + 'px';
      chip.style.top = y + 'px';
      chip.innerHTML = `
        <div>
          <div class="chip-ns">${d.ns}</div>
          <div class="chip-val">${d.val}</div>
        </div>`;
      canvas.appendChild(chip);

      // SVG line (curved slightly toward center)
      const path = document.createElementNS('http://www.w3.org/2000/svg', 'path');
      // gentle curve: control point pulled perpendicular to the line
      const mx = (x + cx) / 2;
      const my = (y + cy) / 2;
      const dx = cx - x, dy = cy - y;
      const len = Math.sqrt(dx*dx + dy*dy);
      const px = -dy / len, py = dx / len;
      const curl = 18;
      const ctrlX = mx + px * curl;
      const ctrlY = my + py * curl;
      const dStr = `M ${x} ${y} Q ${ctrlX} ${ctrlY} ${cx} ${cy}`;
      path.setAttribute('d', dStr);
      path.setAttribute('class', 'stitch-line');
      path.dataset.id = d.id;

      // measure length for the draw effect
      svg.appendChild(path);
      const length = path.getTotalLength();
      path.style.strokeDasharray = length;
      path.style.strokeDashoffset = length;
      path.style.transition = 'stroke-dashoffset 1s cubic-bezier(0.4, 0, 0.2, 1), opacity 0.4s ease';
    });
  }

  function buildLog() {
    logList.innerHTML = '';
    identifiers.forEach((d) => {
      const li = document.createElement('li');
      li.className = 'log-item';
      li.dataset.id = d.id;
      li.innerHTML = `
        <div class="log-time">${d.time}</div>
        <div class="log-event">${d.event}</div>
        <div class="log-id">+ ${d.ns} ${d.val}</div>`;
      logList.appendChild(li);
    });
  }

  let stitchTimers = [];
  function clearStitch() {
    stitchTimers.forEach(t => clearTimeout(t));
    stitchTimers = [];
    profileName.textContent = 'Unidentified visitor';
    profileCount.textContent = '0';
    profileCard.classList.remove('complete');
    replayBtn.classList.remove('shown');
    canvas.querySelectorAll('.chip').forEach(el => {
      el.classList.remove('pulse', 'linked');
    });
    svg.querySelectorAll('.stitch-line').forEach(el => {
      el.classList.remove('drawing', 'drawn');
      const length = el.getTotalLength();
      el.style.strokeDashoffset = length;
    });
    logList.querySelectorAll('.log-item').forEach(el => el.classList.remove('shown'));
  }

  function stitchOne(idx) {
    const d = identifiers[idx];
    const chip = canvas.querySelector(`.chip[data-id="${d.id}"]`);
    const line = svg.querySelector(`.stitch-line[data-id="${d.id}"]`);
    const logItem = logList.querySelector(`.log-item[data-id="${d.id}"]`);

    // 1. log entry appears
    logItem.classList.add('shown');

    // 2. chip pulses (event recognized)
    stitchTimers.push(setTimeout(() => {
      chip.classList.add('pulse');
    }, 200));

    // 3. line draws
    stitchTimers.push(setTimeout(() => {
      line.classList.add('drawing');
      line.style.strokeDashoffset = '0';
    }, 600));

    // 4. chip transitions to linked, counter increments, name updates
    stitchTimers.push(setTimeout(() => {
      chip.classList.remove('pulse');
      chip.classList.add('linked');
      line.classList.remove('drawing');
      line.classList.add('drawn');
      profileCount.textContent = (idx + 1);
      profileName.textContent = d.profileName;
    }, 1500));
  }

  function runStitch() {
    layoutChips();
    buildLog();
    clearStitch();

    const stagger = 1900; // ms between events
    identifiers.forEach((_, i) => {
      stitchTimers.push(setTimeout(() => stitchOne(i), 800 + i * stagger));
    });

    // final flourish
    const totalDuration = 800 + identifiers.length * stagger + 1200;
    stitchTimers.push(setTimeout(() => {
      profileCard.classList.add('complete');
      replayBtn.classList.add('shown');
    }, totalDuration));
  }

  replayBtn.addEventListener('click', (e) => {
    e.stopPropagation();
    runStitch();
  });

  // re-layout chips if window resizes & this slide is active
  window.addEventListener('resize', () => {
    if (slides[current].dataset.slide === '3') {
      // brief debounce
      clearTimeout(window.__relayout);
      window.__relayout = setTimeout(() => {
        runStitch();
      }, 200);
    }
  });

  // ============================================================
  // NAV — show on mouse movement, fade out after idle
  // ============================================================
  const navEl = document.getElementById('nav');
  let navIdleTimer;
  function nudgeNav() {
    navEl.classList.add('active');
    clearTimeout(navIdleTimer);
    navIdleTimer = setTimeout(() => navEl.classList.remove('active'), 2200);
  }
  document.addEventListener('mousemove', nudgeNav);
  document.addEventListener('keydown', nudgeNav);
  nudgeNav();
</script>

</body>
</html>
