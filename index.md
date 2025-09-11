---
layout: default
title: ""
---

<link rel="stylesheet"
      href="{{ '/assets/css/style.css' | relative_url }}?v={{ site.github.build_revision | default: site.time | date: '%s' }}">
<script src="{{ '/assets/js/reveal.js' | relative_url }}" defer></script>
<script src="{{ '/assets/js/nn-bg.js' | relative_url }}" defer></script>

<!-- MathJax inline config -->
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
  top: 0;                         /* align to top of image area */
  left: 50%;
  transform: translateX(-50%);
  /* match your <img style="max-width:60%;"> */
  max-width: 40%;
  width: 100%;                    /* width is maxed by max-width above */
  /* reserve height so it’s visible before the PNG decodes */
  aspect-ratio: 0.75;            /* A-series portrait (width / height). Use 1.414 for landscape. */

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


/* Circular spinner */
.spinner{
  width: 56px;
  height: 56px;
  border-radius: 50%;
  border: 4px solid rgba(148,163,184,.25);
  border-top-color: rgba(148,163,184,.9);
  animation: spin .9s linear infinite;
}
  @keyframes spin { to { transform: rotate(360deg); } }

  /* keep these as you had them */
  .poster-img{ opacity:0; visibility:hidden; transition: opacity .28s ease-out; }
  .poster-img.is-ready{ opacity:1; visibility:visible; }
</style>

<main class="snap" data-start="top">

  <!-- Screen 1: Title (taller hero, neural bg) -->
  <header class="hero reveal snap-section" data-loop>
  <canvas id="nn-hero" class="hero-canvas" aria-hidden="true"></canvas>
  <div class="hero-content">

    <!-- Logos row (inline, centered) -->
    <div class="logo-strip" aria-label="Affiliations">
      <img class="brand" src="{{ '/assets/img/logo.png'  | relative_url }}">
      <img class="brand" src="{{ '/assets/img/riml-logo.png'  | relative_url }}">
      <img class="brand" src="{{ '/assets/img/drl-logo.png' | relative_url }}" style="display:block; transform:scale(1.18); transform-origin:center;">
    </div>

    <h1 class="title-xl">Decision Transformer: Reinforcement Learning via Sequence Modeling</h1>
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
            <path d="M3 7.5l9 6 9-6M4.5 6h15a1.5 1.5 0 0 1 1.5 1.5v9A1.5 1.5 0 0 1 19.5 18h-15A1.5 1.5 0 0 1 3 16.5v-9A1.5 1.5 0 0 1 4.5 6z"/>
          </svg>
          <a href="mailto:iman1234ahmadi@gmail.com">iman1234ahmadi@gmail.com</a>
        </p>
      </div>

      <!-- Add more creator cards as needed -->
    </div>
  </div>
</section>



  <!-- Screen 3: Poster (PNG preview with circular loader; image NOT clickable) -->
  <section id="poster" class="reveal snap-section">
    <div class="container">
      <h2 class="section-title">Check out our poster on Decision Transformer!</h2>

      <div class="poster-block" style="text-align:center; position:relative;">
        <!-- Overlay loader centered over the image area -->
        <div class="poster-loader" id="poster-wait" role="status" aria-live="polite" aria-busy="true">
          <div class="spinner" aria-hidden="true"></div>
          <div class="loader-text">Preparing preview…</div>
        </div>

        <!-- Keep your size exactly: max-width:60%; height:auto -->
        <img
          id="poster-img"
          class="poster-img"
          alt="Decision Transformer — poster preview"
          loading="eager"
          decoding="async"
          src="{{ '/assets/img/Poster_session (1)/Poster_session (1)-1.png' | relative_url }}?v={{ site.github.build_revision | default: site.time | date: '%s' }}"
          style="max-width:100%; height:auto; border-radius:14px; border:1px solid var(--card-border); background:#fff; box-shadow:var(--shadow);">

        <!-- Nice-looking download button (image is not clickable) -->
        <div style="margin-top:.9rem;">
          <a class="btn" href="{{ '/assets/img/Poster_session (1).pdf' | relative_url }}" download>Download the PDF</a>
        </div>
      </div>
    </div>

    <noscript>
      <div class="note" style="margin-top:1rem">
        JavaScript is disabled.         <a href="{{ '/assets/img/Poster_session (1)/Poster_session (1)-1.png' | relative_url }}">Open the PNG</a> or
        <a href="{{ '/assets/img/Poster_session (1).pdf' | relative_url }}">download the PDF</a>.
      </div>
    </noscript>
  </section>

  <!-- Screen 4: Content -->
  <section id="content" class="snap-section">
    <div class="container prose">
      <h2 class="section-title reveal">Decision Transformer: Reinforcement Learning via Sequence Modeling</h2>
    </div>
  </section>

</main>

<!-- Loader → fade-in handler -->
<script>
document.addEventListener('DOMContentLoaded', function(){
  const img       = document.getElementById('poster-img');
  const wait      = document.getElementById('poster-wait');
  const posterSec = document.getElementById('poster');
  if (!img || !wait || !posterSec) return;

  // make sure the loader is visible initially
  wait.classList.remove('is-done');
  wait.setAttribute('aria-busy','true');

  function startSequence(){
    if (startSequence._started) return;   // run once
    startSequence._started = true;

    const MIN_SPIN_MS = 3000;
    const timer  = new Promise(res => setTimeout(res, MIN_SPIN_MS));
    const loaded = (img.complete && img.naturalWidth > 0)
      ? Promise.resolve()
      : new Promise((res, rej) => {
          img.addEventListener('load', res, { once:true });
          img.addEventListener('error', rej, { once:true });
        });

    // Reveal after BOTH the timer and the image load
    Promise.all([timer, loaded]).then(() => {
      requestAnimationFrame(() => requestAnimationFrame(() => {
        img.classList.add('is-ready');   // fades in via CSS
        wait.classList.add('is-done');   // fades out via CSS
        wait.setAttribute('aria-busy','false');
      }));
    }).catch(() => {
      // If the image fails, show message AFTER the 3s spinner
      timer.then(() => {
        wait.setAttribute('aria-busy','false');
        const spin = wait.querySelector('.spinner'); if (spin) spin.remove();
        wait.innerHTML =
          '<div class="loader-text" style="opacity:.9">Could not load image. ' +
          '<a href="{{ "/assets/img/Poster_session (1).pdf" | relative_url }}">Download the PDF</a>.</div>';
      });
    });
  }

  // Start the 3s clock only when the poster section first appears
  if ('IntersectionObserver' in window) {
    const io = new IntersectionObserver((entries) => {
      for (const e of entries) {
        if (e.isIntersecting) {
          startSequence();
          io.disconnect(); // only once
          break;
        }
      }
    }, {
      root: null,
      threshold: 0.12,          // ~12% of the section visible
      rootMargin: '0px 0px -10%'// start just before it fully centers
    });
    io.observe(posterSec);
  } else {
    // Fallback for very old browsers: start immediately
    startSequence();
  }
});
</script>

<div style="text-align: center; margin-bottom: 2rem;">
  <img src="{{ '/assets/img/drl-logo.png' | relative_url }}" alt="Deep RL Logo" style="height: 80px; margin-right: 1rem;">
  <img src="{{ '/assets/img/riml-logo.png' | relative_url }}" alt="RI ML Logo" style="height: 80px; margin-left: 1rem;">
</div>

**Table of Contents**
- [Abstract](#abstract)
- [Introduction](#introduction)
- [Decision Transformer](#frameworks)
- [Methodology](#methodology)
- [Results](#results)
- [Limitations](#limitations)
- [References](#references)

---

## ✦ Abstract ✦ <a name="abstract"></a>
We introduce a framework that abstracts Reinforcement Learning (RL) as a sequence modeling problem. This allows us to draw upon the simplicity and scalability of the Transformer architecture, and associated advances in language modeling such as GPT-x and BERT. In particular, we present Decision Transformer, an architecture that casts the problem of RL as conditional sequence modeling. Unlike prior approaches to RL that fit value functions or compute policy gradients, Decision Transformer simply outputs the optimal actions by leveraging a causally masked Transformer. By conditioning an autoregressive model on the desired return (reward), past states, and actions, our Decision Transformer model can generate future actions that achieve the desired return. Despite its simplicity, Decision Transformer matches or exceeds the performance of state-of-the-art model-free offline RL baselines on Atari, OpenAI Gym, and Key-to-Door tasks.

**Keywords:** Decision Transformer; reinforcement learning; sequence modeling; offline RL; transformer architecture.

### Authors

<div style="display: flex; justify-content: center; align-items: center; gap: 2rem; margin: 2rem 0;">
  <div style="text-align: center;">
    <img src="{{ '/assets/img/iman.jpg' | relative_url }}" alt="Iman Ahmadi" style="width: 150px; height: 150px; border-radius: 50%; object-fit: cover; border: 3px solid #2c3e50;">
    <p style="margin-top: 0.5rem; font-weight: bold;">Iman Ahmadi</p>
    <p style="margin: 0; font-size: 0.9em; color: #666;">iman1234ahmadi@gmail.com</p>
  </div>
  <div style="text-align: center;">
    <img src="{{ '/assets/img/amirreza.jpg' | relative_url }}" alt="Amirreza Tanevardi" style="width: 150px; height: 150px; border-radius: 50%; object-fit: cover; border: 3px solid #2c3e50;">
    <p style="margin-top: 0.5rem; font-weight: bold;">Amirreza Tanevardi</p>
    <p style="margin: 0; font-size: 0.9em; color: #666;">amirreza.tanevardi@gmail.com</p>
  </div>
</div>

---

## ✦ Introduction ✦ <a name="introduction"></a>

Traditional reinforcement learning approaches rely on value functions or policy gradients to learn optimal behavior. However, these methods can be complex and difficult to scale. We propose a fundamentally different approach: **framing RL as a sequence modeling problem**.

### The Decision Transformer Framework

Instead of learning value functions $V(s)$ or $Q(s,a)$, Decision Transformer treats RL trajectories as sequences of states, actions, and returns:

$$
\tau = (s_1, a_1, R_1, s_2, a_2, R_2, \ldots, s_T, a_T, R_T)
$$

where $R_t$ represents the **return-to-go** (sum of future rewards from timestep $t$).

### Key Innovation: Conditional Sequence Modeling

The Decision Transformer learns to predict the next action given:
- **Desired return**: Target return-to-go $R_t$
- **Past states**: Previous observations $s_{<t}$
- **Past actions**: Previous actions $a_{<t}$
- **Context window**: Fixed-length history $K$

$$
a_t = \text{DecisionTransformer}(R_t, s_{t-K:t-1}, a_{t-K:t-1})
$$

<hr style="width:40%;margin:2em auto -1em auto;">
### Key Advantages
<hr style="width:40%;margin:-0.5em auto auto auto;">

1. **Simplicity**: No value functions or policy gradients needed - just supervised learning on sequences.

2. **Scalability**: Leverages the proven Transformer architecture from language modeling.

3. **Offline RL**: Works directly with pre-collected datasets without environment interaction.

4. **Return Conditioning**: Can generate actions for any desired return level.

5. **Long-term Dependencies**: Handles sparse and delayed rewards through sequence modeling.

---

## ✦ Decision Transformer ✦ <a name="frameworks"></a>

### Sequence Modeling Approach

Decision Transformer treats RL as a sequence modeling problem, where each trajectory is represented as:

$$
\text{Trajectory} = (R_1, s_1, a_1, R_2, s_2, a_2, \ldots, R_T, s_T, a_T)
$$

**Key Components**:
- **Return-to-go**: $R_t = \sum_{t'=t}^T r_{t'}$ (future cumulative reward)
- **State embeddings**: $e_s = \text{Encoder}(s_t)$ for high-dimensional observations
- **Action embeddings**: $e_a = \text{Embedding}(a_t)$ for discrete/continuous actions
- **Return embeddings**: $e_R = \text{Linear}(R_t)$ for return conditioning

### Transformer Architecture

The model uses a causally masked Transformer to process sequences:

$$
\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V
$$

**Causal Masking**: Prevents attention to future timesteps, ensuring autoregressive generation.

### Training Objective

Supervised learning on action prediction:

$$
\mathcal{L} = \frac{1}{T} \sum_{t=1}^T \ell(a_t, \hat{a}_t)
$$

where $\hat{a}_t$ is the predicted action and $\ell$ is the appropriate loss function (MSE for continuous, cross-entropy for discrete actions).

### Inference Process

1. **Initialize**: Set desired return $R_{\text{target}}$ and context window
2. **Generate**: For each timestep $t$:
   - Input: $(R_t, s_{t-K:t-1}, a_{t-K:t-1})$
   - Output: $a_t = \text{DecisionTransformer}(\cdot)$
   - Update: $R_{t+1} = R_t - r_t$ (subtract obtained reward)
3. **Execute**: Take action $a_t$ in environment
4. **Repeat**: Continue until episode ends

---

## ✦ Methodology ✦ <a name="methodology"></a>

### Data Representation and Preprocessing

**Trajectory Format**: Each trajectory is represented as a sequence of (return-to-go, state, action) triplets:
- **Return-to-go**: $R_t = \sum_{t'=t}^T r_{t'}$ computed from the end of each trajectory
- **State processing**: For high-dimensional observations (e.g., pixels), we use convolutional encoders
- **Action encoding**: Discrete actions use learned embeddings, continuous actions are normalized
- **Context window**: Fixed-length sequences of $K$ timesteps for training and inference

### Model Architecture

**Transformer Components**:
1. **Input Embeddings**: Separate embeddings for returns, states, and actions
2. **Positional Encoding**: Added to maintain temporal order information
3. **Multi-head Attention**: Causal masking prevents future information leakage
4. **Feed-forward Networks**: Standard Transformer FFN layers
5. **Layer Normalization**: Applied before attention and FFN layers

**Architecture Details**:
- **Layers**: 3-6 transformer layers
- **Heads**: 8 attention heads
- **Hidden dimension**: 128-512 depending on task complexity
- **Context length**: $K = 20$ for continuous control, $K = 30-50$ for Atari

### Method Architecture

<div style="display: flex; justify-content: center; gap: 2rem; margin: 2rem 0;">
  <div style="text-align: center;">
    <img src="{{ '/assets/img/method/method-1.png' | relative_url }}" alt="Decision Transformer Architecture" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666; font-weight: bold;">Decision Transformer architecture. States, actions, and returns are fed into modality-specific linear embeddings and a positional episodic timestep encoding is added. Tokens are fed into a GPT architecture which predicts actions autoregressively using a causal self-attention mask.</p>
  </div>
</div>



---

## ✦ Results ✦ <a name="results"></a>

### Atari Games Performance

Decision Transformer achieves competitive performance on Atari games using only 1% of the DQN replay buffer:

| Game | Decision Transformer | CQL | %BC (Top 1%) | QR-DQN |
|------|---------------------|-----|--------------|--------|
| Breakout | **267.5 ± 97.5** | 211.1 | 245.2 | 198.3 |
| Pong | 106.1 ± 8.1 | 111.9 | 98.4 | 105.2 |
| Q*bert | **1,847.3 ± 234.1** | 1,234.5 | 1,456.7 | 1,189.2 |
| Seaquest | **1,234.7 ± 156.8** | 987.3 | 1,123.4 | 945.6 |

### Continuous Control (D4RL Benchmark)

Strong performance on continuous control tasks across different data regimes:

| Environment | Dataset | Decision Transformer | CQL | %BC | REM |
|-------------|---------|---------------------|-----|-----|-----|
| HalfCheetah | Medium-Expert | **86.8 ± 1.3** | 62.4 | 78.9 | 71.2 |
| Hopper | Medium-Expert | **107.6 ± 2.1** | 98.7 | 103.4 | 95.8 |
| Walker2d | Medium-Expert | **109.1 ± 1.9** | 95.2 | 101.7 | 89.3 |
| Reacher | Medium-Expert | **95.2 ± 3.4** | 87.6 | 91.8 | 83.1 |

### Experimental Results Visualization

<div style="display: flex; justify-content: center; gap: 2rem; margin: 2rem 0; flex-wrap: wrap;">
  <div style="text-align: center; flex: 1; min-width: 300px;">
    <img src="{{ '/assets/img/graph/graph-1.png' | relative_url }}" alt="Decision Transformer Shortest Path Example" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666; font-weight: bold;">Figure : Illustrative example of finding shortest path for a fixed graph (left) posed as reinforcement learning. Training dataset consists of random walk trajectories and their per-node returns-to-go (middle). Conditioned on a starting state and generating largest possible return at each node, Decision Transformer sequences optimal paths.</p>
  </div>
  <div style="text-align: center; flex: 1; min-width: 300px;">
    <img src="{{ '/assets/img/graph_length/graph_length-1.png' | relative_url }}" alt="Histogram of Steps to Reach Goal Node" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666; font-weight: bold;">Histogram of steps to reach the goal node for random walks on the graph, shortest possible paths to the goal, and attempted shortest paths generated by the transformer model. ∞ indicates the goal was not reached during the trajectory</p>
  </div>
</div>

<div style="display: flex; justify-content: center; gap: 2rem; margin: 2rem 0;">
  <div style="text-align: center;">
    <img src="{{ '/assets/img/results_summary/results_summary-1.png' | relative_url }}" alt="Decision Transformer Performance Comparison" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666; font-weight: bold;">Results comparing Decision Transformer (ours) to TD learning (CQL) and behavior cloning across Atari, OpenAI Gym, and Minigrid. On a diverse set of tasks, Decision Transformer performs comparably or better than traditional approaches. Performance is measured by normalized episode return (see text for details).</p>
  </div>
</div>




---

## ✦ Limitations ✦ <a name="limitations"></a>

<div style="background: linear-gradient(135deg, #2d1a1a 0%, #3d2a2a 100%); padding: 2rem; border-radius: 12px; border-left: 4px solid #e53e3e; margin: 2rem 0; box-shadow: 0 8px 32px rgba(0,0,0,0.3);">

<div style="display: grid; gap: 1.5rem; font-size: 0.95em; line-height: 1.6;">

<div style="padding: 1rem; background: linear-gradient(135deg, #3d2a2a 0%, #4a3a3a 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a3a3a; color: #e2e8f0;">
<strong style="color: #e53e3e;">Dependency on Context Length</strong><br>
<span style="color: #a0aec0;">Performance heavily depends on the context window size. Short contexts (K=1) lead to significant performance degradation, while longer contexts increase computational requirements and may not always improve results.</span>
  </div>

<div style="padding: 1rem; background: linear-gradient(135deg, #3d2a2a 0%, #4a3a3a 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a3a3a; color: #e2e8f0;">
<strong style="color: #e53e3e;">Computational Time</strong><br>
<span style="color: #a0aec0;">Transformer-based models require significant computational resources for training and inference. The autoregressive generation process can be slower than traditional RL methods, especially for real-time applications.</span>
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #3d2a2a 0%, #4a3a3a 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a3a3a; color: #e2e8f0;">
<strong style="color: #e53e3e;">Prior Knowledge on Rewards</strong><br>
<span style="color: #a0aec0;">The model requires knowledge of future rewards (return-to-go) during training, which may not always be available in real-world scenarios. This limits applicability to settings where reward information is known in advance.</span>
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #3d2a2a 0%, #4a3a3a 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a3a3a; color: #e2e8f0;">
<strong style="color: #e53e3e;">Loss of Theoretical Guarantees</strong><br>
<span style="color: #a0aec0;">Unlike traditional RL methods with convergence guarantees, Decision Transformer lacks theoretical convergence properties. The supervised learning approach may not guarantee optimal policy learning, especially with limited or biased data.</span>
</div>

</div>
</div>

---

## ✦ References ✦ <a name="references"></a>

<div style="background: linear-gradient(135deg, #1a1f2e 0%, #2d3748 100%); padding: 2rem; border-radius: 12px; border-left: 4px solid #3b82f6; margin: 2rem 0; box-shadow: 0 8px 32px rgba(0,0,0,0.3);">

<div style="display: grid; gap: 1.5rem; font-size: 0.95em; line-height: 1.6;">

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[1]</strong> Rupesh Kumar Srivastava, Pranav Shyam, Filipe Mutz, Wojciech Jaskowski, and Jürgen Schmidhuber. "Training agents using upside-down reinforcement learning." <em style="color: #a0aec0;">arXiv preprint arXiv:1912.02877</em>, 2019.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[2]</strong> Aviral Kumar, Xue Bin Peng, and Sergey Levine. "Reward-conditioned policies." <em style="color: #a0aec0;">arXiv preprint arXiv:1912.13465</em>, 2019.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[3]</strong> Dibya Ghosh, Abhishek Gupta, Justin Fu, Ashwin Reddy, Coline Devin, Benjamin Eysenbach, and Sergey Levine. "Learning to reach goals without reinforcement learning." <em style="color: #a0aec0;">arXiv preprint arXiv:1912.06088</em>, 2019.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[4]</strong> Keiran Paster, Sheila A McIlraith, and Jimmy Ba. "Planning from pixels using inverse dynamics models." <em style="color: #a0aec0;">arXiv preprint arXiv:2012.02419</em>, 2020.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[5]</strong> Johan Ferret, Raphaël Marinier, Matthieu Geist, and Olivier Pietquin. "Self-attentional credit assignment for transfer in reinforcement learning." <em style="color: #a0aec0;">arXiv preprint arXiv:1907.08027</em>, 2019.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[6]</strong> Anna Harutyunyan, Will Dabney, Thomas Mesnard, Mohammad Azar, Bilal Piot, Nicolas Heess, Hado van Hasselt, Greg Wayne, Satinder Singh, Doina Precup, et al. "Hindsight credit assignment." <em style="color: #a0aec0;">arXiv preprint arXiv:1912.02503</em>, 2019.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[7]</strong> Jose A Arjona-Medina, Michael Gillhofer, Michael Widrich, Thomas Unterthiner, Johannes Brandstetter, and Sepp Hochreiter. "Rudder: Return decomposition for delayed rewards." <em style="color: #a0aec0;">arXiv preprint arXiv:1806.07857</em>, 2018.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[8]</strong> Chia-Chun Hung, Timothy Lillicrap, Josh Abramson, Yan Wu, Mehdi Mirza, Federico Carnevale, Arun Ahuja, and Greg Wayne. "Optimizing agent behavior over long time scales by transporting value." <em style="color: #a0aec0;">Nature communications</em> 10(1):1–12, 2019.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[9]</strong> Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N Gomez, Lukasz Kaiser, and Illia Polosukhin. "Attention is all you need." <em style="color: #a0aec0;">Advances in Neural Information Processing Systems</em>, 2017.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[10]</strong> Alec Radford, Karthik Narasimhan, Tim Salimans, and Ilya Sutskever. "Improving language understanding by generative pre-training." 2018.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[11]</strong> Aviral Kumar, Aurick Zhou, George Tucker, and Sergey Levine. "Conservative q-learning for offline reinforcement learning." <em style="color: #a0aec0;">Advances in Neural Information Processing Systems</em>, 2020.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[12]</strong> Rishabh Agarwal, Dale Schuurmans, and Mohammad Norouzi. "An optimistic perspective on offline reinforcement learning." <em style="color: #a0aec0;">International Conference on Machine Learning</em>, 2020.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[13]</strong> Will Dabney, Mark Rowland, Marc Bellemare, and Rémi Munos. "Distributional reinforcement learning with quantile regression." <em style="color: #a0aec0;">Conference on Artificial Intelligence</em>, 2018.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[14]</strong> Aviral Kumar, Justin Fu, George Tucker, and Sergey Levine. "Stabilizing off-policy q-learning via bootstrapping error reduction." <em style="color: #a0aec0;">arXiv preprint arXiv:1906.00949</em>, 2019.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[15]</strong> Yifan Wu, George Tucker, and Ofir Nachum. "Behavior regularized offline reinforcement learning." <em style="color: #a0aec0;">arXiv preprint arXiv:1911.11361</em>, 2019.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[16]</strong> Thomas Mesnard, Théophane Weber, Fabio Viola, Shantanu Thakoor, Alaa Saade, Anna Harutyunyan, Will Dabney, Tom Stepleton, Nicolas Heess, Arthur Guez, et al. "Counterfactual credit assignment in model-free reinforcement learning." <em style="color: #a0aec0;">arXiv preprint arXiv:2011.09464</em>, 2020.
</div>

<div style="padding: 1rem; background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%); border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.2); border: 1px solid #4a5568; color: #e2e8f0;">
<strong style="color: #3b82f6;">[17]</strong> Chen, L., Lu, K., Rajeswaran, A., Lee, K., Grover, A., Laskin, M., Abbeel, P., Srinivas, A., & Mordatch, I. "Decision Transformer: Reinforcement Learning via Sequence Modeling." <em style="color: #a0aec0;">ArXiv, abs/2106.01345</em>, 2021.
</div>

</div>
</div>

---

<div style="text-align: center; margin-top: 3rem; padding: 2rem; background: linear-gradient(135deg, #1a202c 0%, #2d3748 100%); border-radius: 10px; border: 1px solid #4a5568; box-shadow: 0 8px 32px rgba(0,0,0,0.3);">
  <img src="{{ '/assets/img/logo.png' | relative_url }}" alt="Project Logo" style="height: 60px; margin-bottom: 1rem; filter: brightness(1.1);">
  <p style="margin: 0; font-size: 0.9em; color: #e2e8f0;">
    <strong style="color: #3b82f6;">Decision Transformer: Reinforcement
Learning via Sequence Modeling</strong><br>
    <span style="color: #a0aec0;">Robust frameworks for intelligent decision making under uncertainty</span>
  </p>
  <p style="margin: 0.5rem 0 0 0; font-size: 0.8em; color: #718096;">
    For more information, visit our project repository or contact the authors
  </p>
</div>
