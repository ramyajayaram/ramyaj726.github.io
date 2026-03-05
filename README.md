<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GitHub Bio – AI Product Manager</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --border: #1e1e2e;
    --accent: #7cffd4;
    --accent2: #a78bfa;
    --accent3: #f472b6;
    --text: #e2e8f0;
    --muted: #64748b;
    --mono: 'DM Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 40px 20px;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(124,255,212,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,255,212,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    animation: gridShift 20s linear infinite;
    pointer-events: none;
    z-index: 0;
  }

  @keyframes gridShift {
    0% { transform: translateY(0); }
    100% { transform: translateY(40px); }
  }

  .wrapper {
    max-width: 740px;
    width: 100%;
    position: relative;
    z-index: 1;
  }

  /* Header */
  .profile-header {
    display: flex;
    align-items: flex-start;
    gap: 28px;
    margin-bottom: 36px;
    animation: fadeUp 0.6s ease both;
  }

  .avatar {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent2), var(--accent3));
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 32px;
    position: relative;
  }

  .avatar::after {
    content: '';
    position: absolute;
    inset: -3px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent3));
    z-index: -1;
    animation: spin 4s linear infinite;
  }

  @keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }

  .name-block h1 {
    font-family: var(--sans);
    font-size: 28px;
    font-weight: 800;
    letter-spacing: -0.5px;
    line-height: 1.1;
    background: linear-gradient(90deg, var(--text), var(--accent));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 4px;
  }

  .handle {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--accent);
    letter-spacing: 0.05em;
    margin-bottom: 8px;
  }

  .title-tag {
    display: inline-block;
    font-family: var(--mono);
    font-size: 11px;
    background: rgba(124,255,212,0.08);
    border: 1px solid rgba(124,255,212,0.2);
    color: var(--accent);
    padding: 3px 10px;
    border-radius: 2px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  /* Bio Card */
  .bio-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 28px 32px;
    margin-bottom: 24px;
    position: relative;
    overflow: hidden;
    animation: fadeUp 0.6s 0.1s ease both;
  }

  .bio-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
  }

  .bio-label {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 14px;
  }

  .bio-text {
    font-family: var(--sans);
    font-size: 15px;
    line-height: 1.75;
    color: #c8d3e0;
    font-weight: 400;
  }

  .bio-text .highlight {
    color: var(--accent);
    font-weight: 600;
  }

  .bio-text .highlight2 {
    color: var(--accent2);
    font-weight: 600;
  }

  .bio-text .highlight3 {
    color: var(--accent3);
    font-weight: 600;
  }

  /* Stats row */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 24px;
    animation: fadeUp 0.6s 0.2s ease both;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 18px;
    transition: border-color 0.2s, transform 0.2s;
  }

  .stat-card:hover {
    border-color: rgba(124,255,212,0.3);
    transform: translateY(-2px);
  }

  .stat-value {
    font-family: var(--mono);
    font-size: 22px;
    font-weight: 500;
    color: var(--accent);
    display: block;
    margin-bottom: 2px;
  }

  .stat-label {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  /* Skills */
  .skills-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 22px 28px;
    margin-bottom: 24px;
    animation: fadeUp 0.6s 0.3s ease both;
  }

  .section-label {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 14px;
  }

  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag {
    font-family: var(--mono);
    font-size: 11.5px;
    padding: 5px 12px;
    border-radius: 3px;
    border: 1px solid;
    letter-spacing: 0.04em;
    transition: opacity 0.2s;
  }

  .tag:hover { opacity: 0.75; }

  .tag-green  { border-color: rgba(124,255,212,0.25); color: var(--accent);  background: rgba(124,255,212,0.05); }
  .tag-purple { border-color: rgba(167,139,250,0.25); color: var(--accent2); background: rgba(167,139,250,0.05); }
  .tag-pink   { border-color: rgba(244,114,182,0.25); color: var(--accent3); background: rgba(244,114,182,0.05); }

  /* Current focus */
  .focus-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 22px 28px;
    margin-bottom: 24px;
    animation: fadeUp 0.6s 0.4s ease both;
  }

  .focus-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .focus-list li {
    font-family: var(--mono);
    font-size: 13px;
    color: #a0aec0;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .focus-list li::before {
    content: '▸';
    color: var(--accent);
    font-size: 10px;
    flex-shrink: 0;
  }

  /* Links */
  .links-row {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    animation: fadeUp 0.6s 0.5s ease both;
  }

  .link-btn {
    font-family: var(--mono);
    font-size: 12px;
    padding: 9px 18px;
    border-radius: 4px;
    text-decoration: none;
    letter-spacing: 0.06em;
    transition: all 0.2s;
    border: 1px solid;
    cursor: pointer;
  }

  .link-primary {
    background: rgba(124,255,212,0.1);
    border-color: rgba(124,255,212,0.4);
    color: var(--accent);
  }

  .link-primary:hover {
    background: rgba(124,255,212,0.2);
    border-color: var(--accent);
  }

  .link-secondary {
    background: transparent;
    border-color: var(--border);
    color: var(--muted);
  }

  .link-secondary:hover {
    border-color: var(--accent2);
    color: var(--accent2);
  }

  /* Copy section */
  .copy-section {
    margin-top: 40px;
    border-top: 1px solid var(--border);
    padding-top: 28px;
    animation: fadeUp 0.6s 0.6s ease both;
  }

  .copy-label {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .copy-box {
    background: #0d0d14;
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 20px 24px;
    font-family: var(--mono);
    font-size: 13px;
    line-height: 1.8;
    color: #94a3b8;
    white-space: pre-wrap;
    position: relative;
  }

  .copy-btn {
    position: absolute;
    top: 12px;
    right: 12px;
    background: rgba(124,255,212,0.08);
    border: 1px solid rgba(124,255,212,0.2);
    color: var(--accent);
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.1em;
    padding: 4px 10px;
    border-radius: 3px;
    cursor: pointer;
    transition: all 0.2s;
    text-transform: uppercase;
  }

  .copy-btn:hover { background: rgba(124,255,212,0.18); }
  .copy-btn.copied { color: #4ade80; border-color: #4ade80; }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @media (max-width: 520px) {
    .stats-row { grid-template-columns: repeat(2, 1fr); }
    .profile-header { flex-direction: column; gap: 16px; }
    .bio-card { padding: 20px; }
  }
</style>
</head>
<body>

<div class="wrapper">

  <!-- Header -->
  <div class="profile-header">
    <div class="avatar">🤖</div>
    <div class="name-block">
      <h1>Ramya Jayaram</h1>
      <div class="handle">@ramyajayaram_ai</div>
      <span class="title-tag">AI Product Manager</span>
    </div>
  </div>

  <!-- Bio -->
  <div class="bio-card">
    <div class="bio-label">// bio.md</div>
    <p class="bio-text">
      Building products at the intersection of <span class="highlight">human intent</span> and <span class="highlight2">machine intelligence</span>.
      I ship AI features that people actually use — obsessing over the gap between what models <em>can</em> do
      and what users <em>need</em>.<br><br>
      From <span class="highlight3">zero-to-one LLM products</span> to scaling inference pipelines, I translate
      between researchers, engineers, and humans. Formerly @ [Company]. Currently making AI
      <span class="highlight">less scary and more useful</span>, one sprint at a time.
    </p>
  </div>

  <!-- Stats -->
  <div class="stats-row">
    <div class="stat-card">
      <span class="stat-value">12+</span>
      <span class="stat-label">AI products shipped</span>
    </div>
    <div class="stat-card">
      <span class="stat-value">4yr</span>
      <span class="stat-label">In the AI trenches</span>
    </div>
    <div class="stat-card">
      <span class="stat-value">∞</span>
      <span class="stat-label">PRDs written (roughly)</span>
    </div>
  </div>

  <!-- Skills -->
  <div class="skills-block">
    <div class="section-label">// tech_stack && domain_expertise</div>
    <div class="tags">
      <span class="tag tag-green">LLM Product</span>
      <span class="tag tag-green">Prompt Engineering</span>
      <span class="tag tag-green">RAG Systems</span>
      <span class="tag tag-purple">User Research</span>
      <span class="tag tag-purple">Roadmapping</span>
      <span class="tag tag-purple">A/B Testing</span>
      <span class="tag tag-pink">Python</span>
      <span class="tag tag-pink">SQL</span>
      <span class="tag tag-pink">Figma</span>
      <span class="tag tag-green">Agentic AI</span>
      <span class="tag tag-purple">Evaluation Frameworks</span>
      <span class="tag tag-pink">OpenAI API</span>
      <span class="tag tag-green">Claude API</span>
    </div>
  </div>

  <!-- Current Focus -->
  <div class="focus-block">
    <div class="section-label">// currently_building</div>
    <ul class="focus-list">
      <li>Designing agentic workflows that don't hallucinate on prod</li>
      <li>Writing about AI PM craft — strategy, evals, and user trust</li>
      <li>Exploring multimodal product experiences</li>
      <li>Open to collabs on responsible AI tooling</li>
    </ul>
  </div>

  <!-- Links -->
  <div class="links-row">
    <a class="link-btn link-primary" href="#">📝 substack / blog</a>
    <a class="link-btn link-secondary" href="#">💼 linkedin</a>
    <a class="link-btn link-secondary" href="#">🐦 twitter / x</a>
    <a class="link-btn link-secondary" href="#">📧 reach out</a>
  </div>

  <!-- Copyable Raw Text -->
  <div class="copy-section">
    <div class="copy-label">// raw_bio — copy & paste to GitHub</div>
    <div class="copy-box" id="rawBio">🤖 AI Product Manager | Building at the intersection of human intent & machine intelligence

Shipping AI products people actually use. I obsess over the gap between what models *can* do and what users *need*.

→ 12+ AI features shipped end-to-end
→ LLMs · RAG · Agentic Systems · Evals
→ Translating between researchers, engineers & humans
→ Formerly @ [Company] · Currently making AI less scary, more useful

Writing about AI PM craft · Open to collabs on responsible AI tooling
      <button class="copy-btn" id="copyBtn" onclick="copyBio()">COPY</button>
    </div>
  </div>

</div>

<script>
  function copyBio() {
    const text = `🤖 AI Product Manager | Building at the intersection of human intent & machine intelligence

Shipping AI products people actually use. I obsess over the gap between what models *can* do and what users *need*.

→ 12+ AI features shipped end-to-end
→ LLMs · RAG · Agentic Systems · Evals
→ Translating between researchers, engineers & humans
→ Formerly @ [Company] · Currently making AI less scary, more useful

Writing about AI PM craft · Open to collabs on responsible AI tooling`;
    navigator.clipboard.writeText(text).then(() => {
      const btn = document.getElementById('copyBtn');
      btn.textContent = '✓ COPIED';
      btn.classList.add('copied');
      setTimeout(() => { btn.textContent = 'COPY'; btn.classList.remove('copied'); }, 2000);
    });
  }
</script>

</body>
</html>
