---
layout: default
title: ""
---

<link rel="stylesheet"
      href="{{````markdown name=index.md
---
layout: default
title: ""
 '/assets/css/style.css' | relative_url }}?v={{ site.github.build_revision | default: site.time | date: '%s' }}">
<script src---

<link rel="stylesheet"
      href="{{ '/assets/css/style.css' | relative_url }}?v={{ site.github.build_revision | default: site.time | date: '%s' }}">
<script src="{{ '/assets/js/reveal.js' | relative_url }}" defer="{{ '/assets/js/reveal.js' | relative_url }}" defer></script>
<script src="{{ '/assets/js/nn-bg.js></script>
<script src="{{ '/assets' | relative_url }}" defer></script>

<!-- MathJax/js/nn-bg.js' | relative_url }}" defer></script>

<!-- MathJax inline config -->
<script>
  window.MathJax = { tex: inline config -->
<script>
  window.MathJax = { tex: { inlineMath: [["$","$"],["\\(","\\)"]] } };
  // Always start at chosen edge (top|bottom via data-start)
  history.scrollRestoration = 'manual';
  document.addEventListener('DOMContentLoaded', () => {
    const start = (document.querySelector('main.snap')?.dataset.start || 'top').toLowerCase();
    requestAnimationFrame(() => {
      window.scrollTo({ top: start === 'bottom' ? document.documentElement.scrollHeight : 0, left: 0, behavior: 'auto' });
    });
  });
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js" defer></script>

<!-- Preload the PNG to reduce the initial white flash -->
<link rel="preload" as="image" href="{{ '/assets/img/Poster_session (1)/Poster_session (1)-1.png' | relative_url }}?v={{ site.github.build_revision | default: site.time | date: '%s' }}">

<!-- Page-local CSS for the circular loader (safe to keep even if style.scss has similar rules) -->
<style>
  .poster-click{ position:relative; display:block; text-align:center; }

  /* Loader overlay — same box as the poster image */
.poster-loader{
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  max-width: 40%;
  width: 100%;
  aspect-ratio: 0.75;
  display: grid;
  place-items: center;
  gap: .65rem;
  border-radius: 14px;
  border: 1px solid var(--card-border);
  background: linear-gradient(180deg, rgba(10,15,31,.65), rgba(10,15,31,.55));
  backdrop-filter: blur(2px);
  -webkit-backdrop-filter: blur(2px);
  box-shadow: var(--shadow);
  transition: opacity .22s ease;
  z-index: 2;
}
.poster-loader.is-done{
  opacity: 0;
  pointer-events: none;
  visibility: hidden;
}
 { inlineMath: [["$","$"],["\\(","\\)"]] } };
.spinner{
  width: 56px;
  height: 56px;
  border-radius: 50%;
  border: 4px solid rgba(148,163,184,.25);
  border-top-color: rgba(148,163,184,.9);
  animation: spin .9s linear infinite;
}
@keyframes spin { to { transform: rotate(360deg); } }
.poster-img{  history.scrollRestoration = 'manual';
  document.add opacity:0; visibility:hidden; transition: opacity .28EventListener('DOMContentLoaded', () => {
    const start =s ease-out; }
.poster-img.is-ready{ opacity:1; visibility: (document.querySelector('main.snap')?.dataset.startvisible; }
</style>

<main class="snap" data-start="top">

  <!-- Screen 1: Title (t || 'top').toLowerCase();
    requestAnimationFramealler hero,(() => {
      window.scrollTo({ top: start === 'bottom neural bg) -->
  <header class="hero reveal snap-section" data-loop>
    <canvas id="nn-hero" class="' ? document.documentElement.scrollHeight : 0, left: 0, behavior: 'auto' });
    });
  });
</script>
hero-canvas" aria-hidden="true"></canvas>
    <div class="hero-content">
      <div class="logo-strip" aria-label="Affiliations">
        <img class="brand" src="{{ '/assets/img/logo.png'  | relative_url }}">
        <img class="brand" src="{{ '/assets/img/riml-logo.png'  | relative_url }}">
        <img class="brand" src="{{ '/assets/img/drl-logo.png' | relative_url }}" style="display:block; transform:scale(1.18); transform-origin:center;">
      </div>
      <h1 class="title-xl">Decision Making in Reinforcement Learning</h1>
    </div>
  </header>

  <!-- Screen 2: Creators -->
  <section id="creators" class="reveal snap-section" data-loop>
    <div class="container">
      <h2 class="section-title">Created by</h2>
      <div class="creators">
        <div class="creator-card">
          <div class="avatar"
               style="background-image:url('{{ '/assets/img/iman.jpg' | relative_url }}')"
               title="Iman Ahmadi" aria-label="Iman Ahmadi"></div>
          <div class="creator-name">Iman Ahmadi</div>
          <p class="creator-contact">
            <svg class="icon-mail" viewBox="0 0 24 24" aria-hidden="true">
              <path d="M3 7.5l9 6 9-6M4.5 6h15a1.5 1.5 0 0 1 1.5 1.5v9A1.5 1.5 0 0 1 19.5 18h<script src="https://cdn.jsdelivr.net/npm/math-15A1.5 1.5 0 0 1 3 16.5v-9A1.5 1.5 0 0 1 4.5 6z"/>
            </svg>
            <a href="mailto:iman1234ahmadi@gmail.com">iman1234ahmadi@gmail.com</a>
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Screen 3: Poster (PNG preview with circular loader; image NOT clickable) -->
  <section id="poster" class="reveal snap-section">
    <div class="container">
      <h2 class="section-title">Check out our poster on Decision RL!</h2>
      <div class="poster-block" style="text-align:center; positionjax@3/es5/tex-mml-chtml.js" defer></script>

<!-- Preload the PNG to reduce the initial white flash -->
<link rel="preload" as="image" href="{{ '/assets/img/Poster_session (1)/Poster_session (1)-1.png' | relative_url:relative;">
        <div class="poster-loader" id="poster-wait" role="status" aria-live="polite" aria-busy="true">
          <div class="spinner" aria-hidden="true"></div>
          <div class="loader-text">Preparing preview…</div>
        </div>
        <img
          id="poster-img"
          class="poster-img"
          alt="Decision Making in RL — poster preview"
 }}?v={{ site.github.build_revision | default: site.time          loading="eager"
          decoding="async | date: '%s' }}">

<style>
  .poster-click{ position"
          src="{{ '/assets/img/Poster_session (1:relative; display:block; text-align:center; }
  .)/Poster_session (1)-1.png' | relative_url }}?v={{ siteposter-loader{
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    max-width: 40%;
    width: 100%;
    aspect-ratio: 0.75;
    display: grid;
    place-items: center;
    gap: .65rem;
    border-radius: 14px;
    border: 1px solid var(--card-border);
    background: linear-gradient(180deg, rgba(10,15,31,.65), rgba(10,15,31,.55));
    backdrop-filter: blur(2px);
    -webkit-backdrop-filter: blur(2px);
    box-shadow: var(--shadow);
    transition: opacity .22s ease;
    z-index: 2;
  }
  .poster-loader.is-done{
    opacity: 0;
    pointer-events: none;
    visibility: hidden;
  }
.github.build_revision | default: site.time | date: '%s' }}"
          style="max-width:100%; height:auto; border-radius:14px; border:1px solid var(--card-border); background:#fff; box-shadow:var(--shadow);">
        <div style="margin-top:.9rem;">
          <a class="btn" href="{{ '/assets/img/Poster_session (1).pdf' | relative_url }}" download>Download the PDF</a>
        </div>
      </div>
    </div>
    <noscript>
      <div class="note" style="margin-top:1rem">
        JavaScript is disabled.
        <a href="{{ '/assets/img/Poster_session (1)/Poster_session (1)-1.png' | relative_url }}">Open the PNG</a> or
        <a href="{{ '/assets/img/Poster_session (1).pdf' | relative_url }}">download the PDF</a>.
      </div>
    </noscript>
  </section>

  <!-- Screen 4: Content -->
  <section id="content" class="snap-section">
    <div class="container prose">
      <h2 class="section-title reveal">Decision Making in Reinforcement Learning</h2>

      <!-- Abstract -->
      <h3>Abstract</h3>
      <p>
      We introduce a framework that abstracts Reinforcement Learning (RL) as a sequence modeling problem. This allows us to draw upon the simplicity and scalability of the Transformer architecture, and associated advances in language modeling such as GPT-x and BERT. In particular, we present Decision Transformer, an architecture that casts the problem of RL as conditional sequence modeling. Unlike prior approaches to RL that fit value functions or compute policy gradients, Decision Transformer simply outputs the optimal actions by leveraging a causally masked Transformer. By conditioning an autoregressive model on the desired return (reward), past states, and actions, our Decision Transformer model can  .spinner{
    width: 56px;
    height: 56px;
    border-radius: 50%;
    border: 4px solid rgba(148,163,184,.25);
    border-top-color: rgba(148,163,184,.9);
    animation: spin .9s linear infinite;
  }
  @keyframes spin { to { transform: rotate(360deg); } }
  .poster-img{ opacity:0; visibility:hidden; transition: opacity .28s ease-out; }
  .poster-img.is-ready{ opacity:1; visibility:visible; }
</style>

<main class="snap" data-start="top">

  <!-- Screen 1 generate future actions that achieve the desired: Title -->
  <header class="hero reveal snap-section" data-loop>
    <canvas id="nn-hero" class="hero-canvas" aria-hidden="true return. Despite its simplicity, Decision Transformer matches"></canvas>
    <div class=" or exceeds the performance of state-of-the-art model-free offline RL baselines on Atari, OpenAIhero-content">
      <div class="logo-strip" aria-label Gym, and Key-to-Door tasks.
      </p>

      <!-- Methodology="Affiliations">
        <img class="brand" src="{{ Summary -->
      <h3>Methodology Summary</h '/assets/img/logo.png'  | relative_url }}">
        <img class="brand" src="{{ '/assets/img/riml-logo.png3>
      <ul>
        <li>
          <b>Framing RL as Sequence Modeling:</b> RL trajectories (sequences of states, actions, rewards) are treated as sequences for sequence modeling, instead of using value functions or policy gradients. The method is designed for <i>offline RL</i> using pre-collected datasets.
        </li>
        <li>
          <b>Data Representation:</b> Each trajectory is represented with past states, past actions, and a “return-to-go” (future reward sum from the current timestep), which is used as a conditioning signal. Timestep/positional embeddings are included.
        </li>
        <li>
          <b>Model Architecture:</b> A causally masked (autoregressive) Transformer is used. Each input (state, action, return-to-go) is embedded. High-dimensional data is encoded (e.g., pixels via convnet). The model attends over a window of recent timesteps.
        </li>
        <li>
          <b>Training Objective:</b> The Transformer is'  | relative_url }}">
        <img class="brand" src="{{ '/assets/img/drl-logo.png' | relative_url }}" style="display:block; transform:scale(1.18); transform-origin:center;">
      </div>
      <h1 class="title-xl">Decision Making in Reinforcement Learning</h1>
    </div>
  </header>

  <!-- Screen 2: Creators -->
  <section id="creators" class="reveal snap-section" data-loop>
    <div class="container">
      <h2 class="section-title">Created by</h2>
      <div class="creators">
        <div class="creator-card">
          <div class="avatar"
               style="background-image:url('{{ '/assets/img/iman.jpg' | relative_url }}')"
               title="Iman Ahmadi" aria-label="Iman Ahmadi"></div>
          <div class="creator-name">Iman Ahmadi</div>
          <p class="creator-contact">
            <svg class="icon-mail" viewBox="0 0 24 24" aria-hidden="true">
              <path trained to predict the next action, given the return-to-go and observed sequence. Supervised loss is used (MSE for continuous, classification for discrete).
        </li>
        <li>
          <b>Inference:</b> At test time, a desired return and the past sequence are input; the model produces the next action. After executing, the return-to-go is updated and the sequence extended.
        </li>
        <li>
          <b>Ablations & Hyperparameters:</b> Studies include varying context length, comparing to Behavior Cloning (BC) and Percentile BC (%BC), and tests on sparse/delayed reward settings.
        </li>
      </ul>

      <!-- Results Summary -->
      <h3>Results d="M3 7.5l9 6 9-6M4.5 6h15a1.5 1.5 0 0 1 1.5 1.5v9A1.5 1.5 0 0 1 19.5 18h-15A1.5 1.5 0 0 1 3 16. Summary</h3>
      <ul>
        <li>
          <b>Atari (Discrete Tasks):</b> Decision Transformer (DT) matches or beats strong baselines (CQL, REM, QR-DQN, BC) on several Atari games (e.g., Breakout, Pong) even with small datasets.
        </li>
        <li>
          <b>Continuous Control (D4RL Benchmarks):</b> DT achieves state-of-the-art or near-best scores5v-9A1.5 1.5 0 0 1 4.5 6z"/>
            </svg>
            < on HalfCheetah, Hopper, Walker, and Reacher tasks across various dataset types (Medium, Medium-Expert, Medium-Replay).
        </li>
        <li>
          <b>Behavior Cloning & %BC:</a href="mailto:iman1234ahmadi@gmail.com">iman1234ahmadi@gmail.com</a>
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Screen 3: Poster -->
  <section id="poster" class="reveal snap-section">
    <div class="container">
      <h2 class="section-title">Check out our poster on Decision RL!</h2>
      <div class="poster-block" style="text-align:center; position:relative;">
        <div class="poster-loader" id="poster-wait" role="status" aria-live="polite" aria-busy="true">
          <div class="b> DT is competitive with or outperforms BC and %BC, especially in low-data Atari settings.
        </li>
        <li>
          <b>Return Conditioning & Generalization:</b> DT reliably tracks the target return. With higher return-to-go targets, it can sometimes generate trajectories achieving higher returns than in the dataset.
        </li>
        <li>
          <b>Sparse/Delayed Rewards:</b> DT is robust to sparse/delayed reward tasks (e.g., “Key-to-Door”). It outperforms TD-based methods (like CQL) in such settings.
        </li>
        <li>
          <b>Context Length Ablation:</b> Using longer context windows (e.g., K = 30 or 50) significantly improves performance over short context (K = 1).
        </li>
      </ul>
   spinner" aria-hidden="true"></div>
          <div class </div>
  </section>

</main>

<!-- Loader → fade-in="loader-text">Preparing preview…</div>
        </ handler -->
<script>
document.addEventListener('DOMContentLoaded', function(){
  const img       = document.getElementdiv>
        <img
          id="poster-img"
          class="poster-img"
          alt="Decision Making inById('poster-img');
  const wait      = RL — poster preview"
 document.getElementById('poster-wait');
  const posterSec = document.getElementById('poster');
  if (!          loading="eager"
          decoding="async"
          src="{{ '/assets/img/img || !wait || !posterSec) return;
  wait.classList.removePoster_session (1)/Poster_session (1)-1.png' | relative_url }}?v={{ site.github.build_revision | default('is-done');
  wait.setAttribute('aria-busy','true');

  function startSequence(){
: site.time | date: '%s' }}"
          style="max-width:100%; height:auto; border-radius:14px; border:1px solid var(--card-border); background:#fff; box-shadow:var(--shadow);">
        <div style="    if (startSequence._started) return;
    startSequence._started = true;

    const MIN_SPIN_MS = 3000;
    const timer  = new Promise(res => setTimeout(res, MIN_SPIN_MSmargin-top:.9rem;">
          <a class="btn" href="{{));
    const loaded = (img.complete && img.naturalWidth > 0)
      ? Promise.resolve()
      : '/assets/img/Poster_session (1).pdf' | relative_url }}" download>Download the PDF</a>
        </div>
      </div>
    </div>
    <noscript>
      <div class new Promise((res, rej) => {
          img.addEventListener('load', res, { once:true });
          img.addEventListener('error', rej, { once:true });
        });

    Promise.all([timer, loaded]).then(() => {
      requestAnimationFrame(() => requestAnimationFrame(() => {
        img.classList.add('is-ready');
        wait.classList.add('is-done');
        wait.set="note" style="margin-top:1rem">
        JavaScript is disabled.
        <a href="{{ '/assets/img/Poster_session (1)/Poster_session (1)-1.png' | relative_url }}">Open the PNG</a> or
        <a href="{{ '/assets/img/Poster_session (1).pdf' | relative_url }}">download the PDF</a>.
      </div>
    </noscript>
 Attribute('aria-busy','false');
      }));
    }).catch(() => {
      timer.then(() => {
        wait.setAttribute('aria-busy','false');
        const spin = wait.querySelector('.spinner'); if (spin) spin.remove();
        wait.innerHTML =
          '<div </section>

  <!-- Screen 4: Content -->
  <section id="content" class="snap-section">
    <div class=" class="loader-text" style="opacity:.9">Could not load image.container prose">
      <h2 class="section-title reveal ' +
          '<a href="{{ "/assets/img/Poster_session">Decision Making in Reinforcement Learning</ (1).pdf" | relative_url }}">Download the PDF</h2>

      <!-- Abstract -->
      <h3>Abstract</h3>
      <p>
        We introduce a framework that abstracts Reinforcement Learning (RL) as a sequence modeling problem. This allows us to draw upon the simplicity and scalability of the Transformer architecture, and associated advances in language modeling such as GPTa>.</div>';
      });
    });
  }

  if ('IntersectionObserver' in window) {
    const io = new IntersectionObserver((entries) => {
      for (const e of entries) {
        if (e.isIntersecting) {
          startSequence();
          io.disconnect();
          break;
        }
      }
    }, {
      root: null,
      threshold: 0.12,
      rootMargin: '0px 0px -10%'
    });
    io.observe(posterSec);
  } else {
    startSequence();
  }
});
</script>
````-x and BERT. In particular, we present Decision Transformer, an architecture that casts the problem of RL as conditional sequence modeling. Unlike prior approaches to RL that fit value functions or compute policy gradients, Decision Transformer simply outputs the optimal actions by leveraging a caus
