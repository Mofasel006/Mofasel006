<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 400" width="100%" height="100%">
  <defs>
    <!-- Sleek Neon-Green glow for the outer container and text -->
    <filter id="neon-glow-green" x="-30%" y="-30%" width="160%" height="160%">
      <feGaussianBlur stdDeviation="6" result="blur1" />
      <feGaussianBlur stdDeviation="12" result="blur2" />
      <feColorMatrix type="matrix" values="
        0 0 0 0 0.0
        0 1 0 0 1.0
        0 0 0 0 0.4
        0 0 0 0 0.5 0
      " in="blur2" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur" />
        <feMergeNode in="blur1" />
        <feMergeNode in="SourceGraphic" />
      </feMerge>
    </filter>
    
    <filter id="neon-glow-green-text" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur stdDeviation="2.5" result="blur" />
      <feMerge>
        <feMergeNode in="blur" />
        <feMergeNode in="SourceGraphic" />
      </feMerge>
    </filter>

    <!-- Intense magenta/pink glow for system indicators -->
    <filter id="neon-glow-magenta" x="-30%" y="-30%" width="160%" height="160%">
      <feGaussianBlur stdDeviation="4" result="blur" />
      <feColorMatrix type="matrix" values="
        1 0 0 0 1.0
        0 0 0 0 0.0
        0 0 1 0 1.0
        0 0 0 0.7 0
      " in="blur" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur" />
        <feMergeNode in="SourceGraphic" />
      </feMerge>
    </filter>

    <!-- Cyber CRT Scanline Overlay Pattern -->
    <pattern id="scanlines" width="100" height="4" patternUnits="userSpaceOnUse">
      <line x1="0" y1="0" x2="100" y2="0" stroke="#000" stroke-width="1.2" opacity="0.15" />
    </pattern>

    <!-- HUD Grid Background Pattern -->
    <pattern id="grid" width="30" height="30" patternUnits="userSpaceOnUse">
      <path d="M 30 0 L 0 0 0 30" fill="none" stroke="#00FF66" stroke-width="0.5" opacity="0.04" />
    </pattern>

    <!-- Fluid Typing Animation Clip Path -->
    <clipPath id="typing-clip">
      <rect x="0" y="0" width="0" height="400">
        <animate attributeName="width" values="0; 300; 300; 0" keyTimes="0; 0.45; 0.95; 1" dur="6s" repeatCount="indefinite" />
      </rect>
    </clipPath>

    <!-- Animated Linear Gradient flowing electric colors through the brand watermark -->
    <linearGradient id="electric-flow" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#00f2fe">
        <animate attributeName="stop-color" values="#00f2fe; #00E5FF; #00FF66; #00E5FF; #00f2fe" dur="5s" repeatCount="indefinite" />
      </stop>
      <stop offset="25%" stop-color="#00E5FF">
        <animate attributeName="stop-color" values="#00E5FF; #00FF66; #00f2fe; #00E5FF; #00FF66" dur="5s" repeatCount="indefinite" />
      </stop>
      <stop offset="50%" stop-color="#00FF66">
        <animate attributeName="stop-color" values="#00FF66; #00E5FF; #00f2fe; #00E5FF; #00FF66" dur="5s" repeatCount="indefinite" />
      </stop>
      <stop offset="75%" stop-color="#00E5FF">
        <animate attributeName="stop-color" values="#00E5FF; #00f2fe; #00E5FF; #00FF66; #00E5FF" dur="5s" repeatCount="indefinite" />
      </stop>
      <stop offset="100%" stop-color="#00f2fe">
        <animate attributeName="stop-color" values="#00f2fe; #00E5FF; #00FF66; #00E5FF; #00f2fe" dur="5s" repeatCount="indefinite" />
      </stop>
    </linearGradient>
  </defs>

  <style>
    /* Styling terminal interface */
    .terminal {
      font-family: 'Fira Code', 'Courier New', Courier, Consolas, Monaco, monospace;
      font-weight: bold;
      user-select: none;
    }
    .title-bar-text {
      font-size: 13px;
      fill: #8b949e;
      font-weight: 500;
      letter-spacing: 1px;
    }
    .watermark {
      font-family: 'Courier New', Courier, Consolas, monospace;
      font-size: 105px;
      font-weight: 900;
      letter-spacing: 14px;
      text-anchor: middle;
    }
    .sub-header {
      font-size: 19px;
      font-weight: 700;
      letter-spacing: 8px;
      fill: #FF00FF;
      text-anchor: middle;
      filter: url(#neon-glow-magenta);
      animation: pulse 3s infinite ease-in-out;
    }
    .metrics {
      font-size: 13.5px;
      fill: #00FF66;
      letter-spacing: 1.5px;
      text-anchor: middle;
      font-weight: 600;
    }
    .terminal-green {
      fill: #00FF66;
      filter: url(#neon-glow-green-text);
    }
    .terminal-text {
      font-size: 15px;
      font-weight: 600;
      letter-spacing: 1.5px;
    }
    .typing-text {
      clip-path: url(#typing-clip);
    }
    
    /* Neon glow breathing animation */
    @keyframes pulse {
      0%, 100% { opacity: 0.6; filter: drop-shadow(0 0 2px #FF00FF); }
      50% { opacity: 1; filter: drop-shadow(0 0 8px #FF00FF); }
    }
    
    /* Blinking cursors and terminal indicators */
    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }
    .blink {
      animation: blink 1s infinite;
    }
    .pulse-dot {
      animation: blink 1.5s infinite;
    }
  </style>

  <!-- Outer terminal body with neon outer glow -->
  <rect x="2" y="2" width="996" height="396" rx="16" fill="#0d1117" stroke="#00FF66" stroke-width="2" filter="url(#neon-glow-green)" />
  <rect x="2" y="2" width="996" height="396" rx="16" fill="#0d1117" stroke="#00FF66" stroke-width="2" />

  <!-- Multi-layer glass stroke -->
  <rect x="6" y="6" width="988" height="388" rx="12" fill="none" stroke="#00f2fe" stroke-width="0.7" opacity="0.3" />

  <!-- Grid overlay -->
  <rect x="6" y="6" width="988" height="388" rx="12" fill="url(#grid)" pointer-events="none" />

  <!-- Scanlines overlay -->
  <rect x="6" y="6" width="988" height="388" rx="12" fill="url(#scanlines)" pointer-events="none" />

  <!-- Window Header Bar -->
  <rect x="6" y="6" width="988" height="35" rx="12" fill="#161b22" />
  <rect x="6" y="20" width="988" height="21" fill="#161b22" />
  <line x1="6" y1="41" x2="994" y2="41" stroke="#00FF66" stroke-width="1" opacity="0.25" />

  <!-- Mac Window Buttons -->
  <circle cx="28" cy="23" r="6" fill="#ff5f56" />
  <circle cx="48" cy="23" r="6" fill="#ffbd2e" />
  <circle cx="68" cy="23" r="6" fill="#27c93f" />

  <!-- Center Header Title -->
  <text x="500" y="27" class="terminal title-bar-text">mofasel@cyber_core: ~/profile_readme</text>

  <!-- Connection Status Widget -->
  <g class="terminal" font-size="11">
    <text x="955" y="27" fill="#8b949e" text-anchor="end" letter-spacing="1">
      SECURE LINK ACTIVE <tspan class="pulse-dot" fill="#00FF66">●</tspan>
    </text>
  </g>

  <!-- Decorative Corner HUD Brackets -->
  <path d="M 25 70 L 25 60 L 35 60" fill="none" stroke="#00FF66" stroke-width="1.5" opacity="0.6" />
  <path d="M 975 70 L 975 60 L 965 60" fill="none" stroke="#00FF66" stroke-width="1.5" opacity="0.6" />
  <path d="M 25 340 L 25 350 L 35 350" fill="none" stroke="#00FF66" stroke-width="1.5" opacity="0.6" />
  <path d="M 975 340 L 975 350 L 965 350" fill="none" stroke="#00FF66" stroke-width="1.5" opacity="0.6" />

  <!-- ================= BACKGROUND WATERMARK "MOFASEL" ================= -->
  <!-- Ambient green glowing layer -->
  <text x="500" y="205" class="terminal watermark" fill="#00FF66" opacity="0.1" filter="url(#neon-glow-green)">MOFASEL</text>
  <!-- Foreground animated glowing text -->
  <text x="500" y="205" class="terminal watermark" fill="url(#electric-flow)">MOFASEL</text>

  <!-- Cybernetic HUD horizontal slices through the watermark -->
  <rect x="100" y="145" width="800" height="2" fill="#0d1117" opacity="0.8" />
  <rect x="100" y="172" width="800" height="3" fill="#0d1117" opacity="0.8" />

  <!-- ================= FLOATING TERMINAL ROWS ================= -->

  <!-- Row 1: Animated typing text & cursor tracker -->
  <g class="terminal terminal-green">
    <text x="40" y="78" class="terminal-text typing-text">&gt; initializing_profile...</text>
  </g>
  <!-- Auto-tracking typing cursor box -->
  <rect y="64" width="8" height="17" fill="#00FF66">
    <animate attributeName="x" values="40; 288; 288; 40" keyTimes="0; 0.45; 0.95; 1" dur="6s" repeatCount="indefinite" />
    <animate attributeName="opacity" values="1;0;1" dur="0.8s" repeatCount="indefinite" />
  </rect>

  <!-- Server load readout widget -->
  <text x="960" y="78" class="terminal terminal-green" font-size="12" letter-spacing="1" text-anchor="end" opacity="0.75">
    SYS_LOAD: <tspan fill="#00E5FF">0.42</tspan> | PING: <tspan fill="#00E5FF">12ms</tspan> | NODE: <tspan fill="#00FF66">ONLINE</tspan>
  </text>

  <!-- Sub-header (Magenta Glow) -->
  <text x="500" y="248" class="terminal sub-header">[ SYSTEM ONLINE ]</text>

  <!-- Metrics Container & Status Readout -->
  <rect x="210" y="280" width="580" height="34" rx="6" fill="#161b22" fill-opacity="0.5" stroke="#00FF66" stroke-width="1.2" stroke-opacity="0.25" />
  <!-- Corner ticks on box -->
  <path d="M 215 280 L 210 280 L 210 285" fill="none" stroke="#00FF66" stroke-width="1.5" opacity="0.7" />
  <path d="M 785 280 L 790 280 L 790 285" fill="none" stroke="#00FF66" stroke-width="1.5" opacity="0.7" />
  <path d="M 215 314 L 210 314 L 210 309" fill="none" stroke="#00FF66" stroke-width="1.5" opacity="0.7" />
  <path d="M 785 314 L 790 314 L 790 309" fill="none" stroke="#00FF66" stroke-width="1.5" opacity="0.7" />

  <!-- Active Status Dots inside the metrics container -->
  <circle cx="225" cy="297" r="3.5" fill="#00FF66" class="pulse-dot" />
  <circle cx="775" cy="297" r="3.5" fill="#00FF66" class="pulse-dot" />

  <!-- Metrics Row Content -->
  <text x="500" y="302" class="terminal metrics">PID: 001 [FULLSTACK]  PID: 002 [AI_CORE]  PID: 003 [SEC_OPS]</text>

  <!-- Row 4: Awaiting Input (Bottom Left) -->
  <text x="40" y="362" class="terminal terminal-green terminal-text">
    <tspan fill="#00E5FF">$ </tspan>awaiting_input<tspan class="blink" fill="#00FF66">_</tspan>
  </text>

  <!-- Dynamic Signal Oscilloscope Widget (Bottom Right) -->
  <g class="terminal">
    <text x="960" y="333" fill="#8b949e" font-size="9" text-anchor="end" letter-spacing="1">OSCILLOSCOPE: LOCK_98.4%</text>
    <rect x="780" y="338" width="180" height="28" rx="4" fill="#0d1117" fill-opacity="0.7" stroke="#00FF66" stroke-width="1" stroke-opacity="0.2" />
    <path d="M785,352 L800,352 L810,342 L820,362 L830,352 L850,352 L860,340 L870,364 L880,352 L910,352 L920,342 L930,362 L940,352 L955,352" 
          stroke="#00f2fe" stroke-width="1.5" fill="none" stroke-linecap="round" stroke-linejoin="round">
      <animate attributeName="d" 
               values="M785,352 L800,352 L810,342 L820,362 L830,352 L850,352 L860,340 L870,364 L880,352 L910,352 L920,342 L930,362 L940,352 L955,352;
                       M785,352 L795,352 L805,340 L815,364 L825,352 L845,352 L855,342 L865,362 L875,352 L905,352 L915,340 L925,364 L935,352 L955,352;
                       M785,352 L800,352 L810,342 L820,362 L830,352 L850,352 L860,340 L870,364 L880,352 L910,352 L920,342 L930,362 L940,352 L955,352" 
               dur="2.5s" repeatCount="indefinite" />
    </path>
  </g>
</svg>



#  About Me:
I am a forward-thinking software engineer and researcher working at the intersection of full-stack development, artificial intelligence, and cloud infrastructure. I architect scalable systems, train intelligent models, and automate cloud-native deployments.<br><br>* 🌐 **Full-Stack Engineering:** Specializing in the MERN stack to design high-performance, responsive web applications and robust REST/GraphQL APIs.<br>* 🤖 **AI/ML Research:** Dedicated to deep learning, natural language processing (LLMs), and computer vision using frameworks like PyTorch.<br>* ☸️ **DevOps & Infrastructure:** Experienced in containerization, orchestration, and automated CI/CD pipelines using Docker and Kubernetes.<br><br>📌 **Current Focus:** Scaling neural networks on distributed Kubernetes clusters and optimizing cloud-native workflows.<br>


# 💻 Tech Stack:
![Go](https://img.shields.io/badge/go-%2300ADD8.svg?style=for-the-badge&logo=go&logoColor=white) ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white) ![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white) ![Datadog](https://img.shields.io/badge/datadog-%23632CA6.svg?style=for-the-badge&logo=datadog&logoColor=white) ![Firebase](https://img.shields.io/badge/firebase-%23039BE5.svg?style=for-the-badge&logo=firebase) ![Vercel](https://img.shields.io/badge/vercel-%23000000.svg?style=for-the-badge&logo=vercel&logoColor=white) ![Azure](https://img.shields.io/badge/azure-%230072C6.svg?style=for-the-badge&logo=microsoftazure&logoColor=white) ![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white) ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white) ![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white) ![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Firebase](https://img.shields.io/badge/firebase-a08021?style=for-the-badge&logo=firebase&logoColor=ffcd34) ![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white) ![Redis](https://img.shields.io/badge/redis-%23DD0031.svg?style=for-the-badge&logo=redis&logoColor=white) ![AmazonDynamoDB](https://img.shields.io/badge/Amazon%20DynamoDB-4053D6?style=for-the-badge&logo=Amazon%20DynamoDB&logoColor=white) ![Prisma](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white) ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) ![Next JS](https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white) ![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB) ![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white) ![Vite](https://img.shields.io/badge/vite-%23646CFF.svg?style=for-the-badge&logo=vite&logoColor=white) ![Vue.js](https://img.shields.io/badge/vue.js-%2335495e.svg?style=for-the-badge&logo=vuedotjs&logoColor=%234FC08D) ![Canva](https://img.shields.io/badge/Canva-%2300C4CC.svg?style=for-the-badge&logo=Canva&logoColor=white) ![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white) ![Framer](https://img.shields.io/badge/Framer-black?style=for-the-badge&logo=framer&logoColor=blue) ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white) ![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white) ![Keras](https://img.shields.io/badge/Keras-%23D00000.svg?style=for-the-badge&logo=Keras&logoColor=white) ![mlflow](https://img.shields.io/badge/mlflow-%23d9ead3.svg?style=for-the-badge&logo=numpy&logoColor=blue) ![Plotly](https://img.shields.io/badge/Plotly-%233F4F75.svg?style=for-the-badge&logo=plotly&logoColor=white) ![Scipy](https://img.shields.io/badge/SciPy-%230C55A5.svg?style=for-the-badge&logo=scipy&logoColor=%white) ![Apache Maven](https://img.shields.io/badge/Apache%20Maven-C71A36?style=for-the-badge&logo=Apache%20Maven&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) ![Sentry](https://img.shields.io/badge/sentry-%23362D59.svg?style=for-the-badge&logo=sentry&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white) ![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white) ![Prettier](https://img.shields.io/badge/prettier-%23F7B93E.svg?style=for-the-badge&logo=prettier&logoColor=black) ![XFCE](https://img.shields.io/badge/XFCE-%232284F2.svg?style=for-the-badge&logo=xfce&logoColor=white) ![ESLint](https://img.shields.io/badge/ESLint-4B3263?style=for-the-badge&logo=eslint&logoColor=white)
# 📊 GitHub Stats:
![](https://github-readme-stats.shion.dev/api?username=Mofasel006&theme=radical&hide_border=false&include_all_commits=false&count_private=false)<br/>
![](https://streak-stats.demolab.com/?user=Mofasel006&theme=radical&hide_border=false)<br/>
![](https://github-readme-stats.shion.dev/api/top-langs/?username=Mofasel006&theme=radical&hide_border=false&include_all_commits=false&count_private=false&layout=compact)

## 🏆 GitHub Trophies
![](https://github-profile-trophy.vercel.app/?username=Mofasel006&theme=radical&no-frame=false&no-bg=false&margin-w=4)

### 🔝 Top Contributed Repo
![](https://github-contributor-stats.vercel.app/api?username=Mofasel006&limit=5&theme=dark&combine_all_yearly_contributions=true)

---
[![](https://komarev.com/ghpvc/?username=Mofasel006&icon=2&color=0)](https://visitcount.itsvg.in)

<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->
