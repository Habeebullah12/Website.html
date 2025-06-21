<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Chemistry: Acids, Bases & Salts</title>
  <style>
  :root {
    --primary: #6c5ce7;
    --highlight: #f1c40f;

   --bg-light: #f5f7fa;
    --text-light: #2c3e50;
    --box-light: #ffffff;
    --border-light: #dcdcdc;

  --bg-dark: #121212;
    --text-dark: #e0e0e0;
    --box-dark: #1e1e1e;
    --border-dark: #333;
  }

  html {
    scroll-behavior: smooth;
  }

  * {
    box-sizing: border-box;
  }

  body {
    font-family: 'Segoe UI', sans-serif;
    background-color: var(--bg-light);
    color: var(--text-light);
    padding: 40px 20px;
    line-height: 1.8;
    transition: all 0.4s ease;
    opacity: 0;
  }

  body.loaded {
    opacity: 1;
  }

  body.dark {
    background-color: var(--bg-dark);
    color: var(--text-dark);
  }
 
header {
  background: linear-gradient(to right, #1a237e, #283593); 
  color: #f1f1f1; /* Soft white for contrast */
  padding: 120px 30px;
  text-align: center;
  font-family: 'Merriweather', serif; /* Classic serif for elegance */
  border-radius: 10px 10px 0 0;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15); /* Soft shadow for refinement */
  position: relative;
  overflow: hidden;
  transition: all 0.3s ease;
}

header h1 {
  font-size: 3.5rem;
  font-weight: 800;
  letter-spacing: 3px;
  margin: 0;
  text-transform: uppercase;
  color: #ffd700; /* Classic gold for a presidential touch */
  transition: transform 0.3s ease;
}

header h1:hover {
  transform: scale(1.05); /* Slight zoom effect on hover */
}

header p {
  font-size: 1.4rem;
  color: rgba(255, 255, 255, 0.8); /* Light gray text */
  margin-top: 20px;
  font-weight: 400;
  letter-spacing: 1px;
  transition: color 0.3s ease;
}

header p:hover {
  color: #ffd700; /* Gold hover for subtitle */
}

/* Background overlay for elegance */
header::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.2); /* Subtle dark overlay */
  z-index: 1;
  transition: all 0.3s ease;
}

header:hover::before {
  background: rgba(0, 0, 0, 0.3); /* Darker on hover for emphasis */
}

header .content {
  position: relative;
  z-index: 2;
}

  h1, h2, h3 {
    color: var(--primary);
    transition: color 0.4s ease;
  }

  li::marker {
    color: #6c5ce7;
  }
  h1 {
    text-align: center;
    margin-bottom: 30px;
    font-size: 2.4rem;
  }

  .section {
    max-width: 1000px;
    margin: 0 auto 50px;
    background: var(--box-light);
    padding: 30px;
    border-radius: 12px;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.06);
    border: 1px solid var(--border-light);
    transition: background 0.4s, box-shadow 0.4s, border 0.4s, transform 0.4s ease;
    opacity: 0;
    transform: translateY(40px);
  }

  .section.visible {
    animation: fadeInUp 0.6s ease-out forwards;
  }

  body.dark .section {
    background: var(--box-dark);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4);
    border: 1px solid var(--border-dark);
  }

  table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
    transition: all 0.3s ease;
  }

  th, td {
    padding: 10px;
    text-align: left;
    border: 1px solid var(--border-light);
    transition: border 0.3s, background 0.3s ease;
  }

  th {
    background-color: var(--primary);
    color: white;
  }

  body.dark td, body.dark th {
    border-color: var(--border-dark);
  }

  ul, ol {
    margin-left: 20px;
  }

  code {
    background: #eee;
    padding: 4px 8px;
    border-radius: 6px;
    font-size: 90%;
    transition: background 0.3s ease;
  }

  body.dark code {
    background: #2c2c2c;
    color: #e5e5e5;
  }

  .highlight {
    color: var(--highlight);
    font-weight: bold;
    transition: color 0.3s;
  }

  .toggle-theme {
    position: fixed;
    top: 20px;
    right: 20px;
    background: var(--primary);
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 30px;
    font-weight: 600;
    cursor: pointer;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
    z-index: 1000;
    transition: background 0.3s, transform 0.3s, box-shadow 0.3s ease;
  }

  .toggle-theme:hover {
    background: #574b90;
    transform: scale(1.08);
    box-shadow: 0 6px 16px rgba(0, 0, 0, 0.25);
  }
  
  #topBtn {
    position: fixed;
    bottom: 30px;
    right: 20px;
    padding: 10px 16px;
    font-size: 18px;
    background: var(--primary);
    color: #fff;
    border: none;
    border-radius: 50px;
    display: none;
    cursor: pointer;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    z-index: 1000;
    transition: background 0.3s ease, transform 0.3s;
  }

  #topBtn:hover {
    background: #574b90;
    transform: scale(1.08);
  }

  body::before {
    content: "";
    position: fixed;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background: radial-gradient(circle at 30% 30%, rgba(100,100,255,0.03), transparent),
                radial-gradient(circle at 70% 70%, rgba(255,255,100,0.03), transparent);
    animation: moveBG 20s linear infinite;
    z-index: -1;
  }

  @keyframes moveBG {
    0% {
      background-position: 0% 0%;
    }
    100% {
      background-position: 100% 100%;
    }
  }

  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(40px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .footer {
    background: linear-gradient(to right, #1f1f1f, #2c3e50);
    color: #f0f0f0;
    padding: 3rem 1rem 2rem;
    text-align: center;
    font-family: 'Segoe UI', 'Roboto', sans-serif;
    font-size: 1.05rem;
    box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.4);
    border-top: 2px solid #444;
    margin-top: 4rem;
  }

  .footer-content {
    max-width: 900px;
    margin: 0 auto;
    animation: fadeSlide 1.2s ease-out;
  }

  .footer strong {
    color: #00bcd4;
    font-weight: 600;
    font-size: 1.15rem;
  }

  .footer-name {
    color: #f1c40f;
    font-weight: bold;
  }

  .footer-sub {
    font-size: 0.95rem;
    color: #bbb;
    margin-top: 0.4rem;
    letter-spacing: 0.3px;
  }

  body.dark .footer {
    background: linear-gradient(to right, #111, #222);
    color: #ccc;
    border-top: 2px solid #333;
  }

  @keyframes fadeSlide {
    0% {
      opacity: 0;
      transform: translateY(40px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }
</style>
</head>
<body>
  <header>
  <h1>Acids, Bases & Salts</h1>
  </header>
  <button class="toggle-theme" onclick="toggleTheme()" aria-label="Toggle dark/light theme">Toggle Theme</button>
  <button onclick="scrollToTop()" id="topBtn">↑ Top</button>
   <section class="section" id="section-acids">
    <h2>What are Acids</h2>
    <p>Acids are substances in which when dissolved in water liberates <span class="highlight">hydrogen ions (H⁺) or hydroxonium ion </span> as the only positive ion.</p>
    <h2>physical properties of an acid</h2>
    <ul>
      <li>They have a sour taste</li>
      <li>They turn moist blue litmus paper red</li>
      <li>Concentrated acids are corrosive</li>
      <li>They are slighly soluble in water</li>
    </ul>
  </section>

  <section class="section" id="section-bases">
    <h2> What are Bases?</h2>
    <p>Bases release <span class="highlight">hydroxide ions (OH⁻)</span> in water. Those that dissolve are called <strong>alkalis</strong>.</p>
    <h2>physical properties of a base</h2>
    <ul>
      <li>Bitter taste</li>
      <li>Soapy/slippery feel</li>
      <li>Turn red litmus blue</li>
      <li>pH greater than 7</li>
    </ul>
  </section>

  <section class="section" id="section-salts">
    <h2>What are Salts?</h2>
    <p>A salt is formed when the <span class="highlight">hydrogen ion (H⁺)</span> in an acid is replaced by a <span class="highlight">metal or ammonium ion</span>. It results from neutralization.</p>
    <ul>
      <li>Sodium chloride (NaCl) – table salt</li>
      <li>Potassium nitrate (KNO₃) – fertilizers</li>
      <li>Calcium carbonate (CaCO₃) – toothpaste, chalk</li>
    </ul>
  </section>

  <section class="section" id="section-reactions">
    <h2>Important Reactions</h2>
    <p><code>HCl + NaOH → NaCl + H₂O</code> (Neutralization)</p>
    <p><code>2HCl + Zn → ZnCl₂ + H₂</code> (Acid + Metal)</p>
    <p><code>2HCl + CaCO₃ → CaCl₂ + H₂O + CO₂</code> (Acid + Carbonate)</p>
    <p><code>NaOH + NH₄Cl → NaCl + H₂O + NH₃</code> (Base + Ammonium Salt)</p>
  </section>

  <section class="section" id="section-uses">
    <h2>Uses in Everyday Life</h2>
    <ul>
      <li><strong>Hydrochloric Acid</strong> – digestion</li>
      <li><strong>Sulfuric Acid</strong> – battery acid</li>
      <li><strong>Sodium Hydroxide</strong> – making soap</li>
      <li><strong>Calcium Hydroxide</strong> – treating acidic soil</li>
      <li><strong>Sodium Chloride</strong> – preserving food</li>
    </ul>
  </section>

  <section class="section" id="section-exercises">
    <h2>Practice Exercises</h2>
    <ol>
      <li>What acid is found in vinegar?</li>
      <li>Write the chemical equation for acid + base reaction.</li>
      <li>Name one salt formed from nitric acid.</li>
      <li>Which ion do acids release in water?</li>
      <li>Give 2 examples of bases used in everyday life.</li>
    </ol>
  </section>
  <footer class="footer">
  <div class="footer-content">
    <hr style="width: 60px; margin: 0 auto 1rem; border: 2px solid #00bcd4; border-radius: 4px;" />
    <p><strong>Builded </strong> by <span class="footer-name">Habeebullah</span></p>
     </div>
</footer>
<script>
  function toggleTheme() {
    document.body.classList.toggle('dark');
    localStorage.setItem('theme', document.body.classList.contains('dark') ? 'dark' : 'light');
  }

  function scrollToTop() {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  window.onload = () => {
    document.body.classList.add('loaded');

  // Restore theme
    if (localStorage.getItem('theme') === 'dark') {
      document.body.classList.add('dark');
    }

  // Animate sections on scroll
    const sections = document.querySelectorAll('.section');
    const observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.1 });

   sections.forEach(section => observer.observe(section));
  };

  // Show back-to-top button
  window.addEventListener('scroll', () => {
    document.getElementById('topBtn').style.display = window.scrollY > 300 ? 'block' : 'none';
  });
  //scroll
  const topBtn = document.getElementById('topBtn');

window.addEventListener('scroll', () => {
  if (window.scrollY > 300) {
    topBtn.style.opacity = '1';
    topBtn.style.transform = 'scale(1)';
  } else {
    topBtn.style.opacity = '0';
    topBtn.style.transform = 'scale(0)';
  }
});

topBtn.addEventListener('click', () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
});
  </script>
</body>
</html>
