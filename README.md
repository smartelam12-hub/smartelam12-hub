<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 320" width="100%" height="100%" preserveAspectRatio="xMidYMid meet">
  <defs>
    <!-- Dark Cyber Grid Background Pattern -->
    <pattern id="cyber-grid" width="30" height="30" patternUnits="userSpaceOnUse">
      <path d="M 30 0 L 0 0 0 30" fill="none" stroke="#00F0FF" stroke-width="0.5" stroke-opacity="0.08" />
      <circle cx="30" cy="0" r="1" fill="#00F0FF" fill-opacity="0.2" />
    </pattern>

    <!-- Liquid Blob Gradients -->
    <linearGradient id="liquid-grad-1" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#00F0FF" stop-opacity="0.85" />
      <stop offset="50%" stop-color="#7000FF" stop-opacity="0.75" />
      <stop offset="100%" stop-color="#FF007A" stop-opacity="0.6" />
    </linearGradient>

    <linearGradient id="liquid-grad-2" x1="100%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" stop-color="#FF007A" stop-opacity="0.8" />
      <stop offset="40%" stop-color="#9E00FF" stop-opacity="0.7" />
      <stop offset="100%" stop-color="#00FFA3" stop-opacity="0.65" />
    </linearGradient>

    <radialGradient id="cyber-orb" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="#00F0FF" stop-opacity="0.4" />
      <stop offset="50%" stop-color="#7000FF" stop-opacity="0.15" />
      <stop offset="100%" stop-color="#080B14" stop-opacity="0" />
    </radialGradient>

    <!-- Glass Refractive Border Gradient -->
    <linearGradient id="glass-border-grad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#00F0FF" stop-opacity="0.8" />
      <stop offset="35%" stop-color="#FFFFFF" stop-opacity="0.3" />
      <stop offset="70%" stop-color="#FF007A" stop-opacity="0.6" />
      <stop offset="100%" stop-color="#00FFA3" stop-opacity="0.4" />
    </linearGradient>

    <!-- Glass Surface Gradient (Translucent Frosted Core) -->
    <linearGradient id="glass-surface" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" stop-color="#0B132B" stop-opacity="0.65" />
      <stop offset="50%" stop-color="#060913" stop-opacity="0.75" />
      <stop offset="100%" stop-color="#030712" stop-opacity="0.85" />
    </linearGradient>

    <!-- Glass Specular Reflection Highlight -->
    <linearGradient id="glass-specular" x1="0%" y1="0%" x2="100%" y2="50%">
      <stop offset="0%" stop-color="#FFFFFF" stop-opacity="0.18" />
      <stop offset="30%" stop-color="#FFFFFF" stop-opacity="0.05" />
      <stop offset="100%" stop-color="#FFFFFF" stop-opacity="0" />
    </linearGradient>

    <!-- Neon Glow Filter -->
    <filter id="neon-glow-cyan" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur stdDeviation="6" result="blur1" />
      <feGaussianBlur stdDeviation="15" result="blur2" />
      <feMerge>
        <feMergeNode in="blur2" />
        <feMergeNode in="blur1" />
        <feMergeNode in="SourceGraphic" />
      </feMerge>
    </filter>

    <filter id="liquid-blur" x="-30%" y="-30%" width="160%" height="160%">
      <feGaussianBlur stdDeviation="40" result="blur" />
    </filter>

    <filter id="glass-shadow" x="-10%" y="-10%" width="120%" height="130%">
      <feDropShadow dx="0" dy="18" stdDeviation="25" flood-color="#00F0FF" flood-opacity="0.15" />
      <feDropShadow dx="0" dy="8" stdDeviation="12" flood-color="#000000" flood-opacity="0.8" />
    </filter>
  </defs>

  <style>
    @keyframes floatBlob {
      0%, 100% { transform: translate(0px, 0px) rotate(0deg); }
      33% { transform: translate(25px, -15px) rotate(4deg); }
      66% { transform: translate(-20px, 12px) rotate(-3deg); }
    }
    @keyframes cyberBlink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.25; }
    }
    @keyframes hudScan {
      0% { transform: translateY(-5px); opacity: 0; }
      50% { opacity: 0.6; }
      100% { transform: translateY(290px); opacity: 0; }
    }
    @keyframes eqBar {
      0%, 100% { height: 6px; }
      50% { height: 22px; }
    }
    .blob1 { animation: floatBlob 14s ease-in-out infinite alternate; transform-origin: center; }
    .blob2 { animation: floatBlob 18s ease-in-out infinite alternate-reverse; transform-origin: center; }
    .status-dot { animation: cyberBlink 1.8s ease-in-out infinite; }
    .hud-scanner { animation: hudScan 5s linear infinite; }
    .eq-1 { animation: eqBar 0.9s ease-in-out infinite; }
    .eq-2 { animation: eqBar 1.3s ease-in-out infinite 0.2s; }
    .eq-3 { animation: eqBar 0.8s ease-in-out infinite 0.4s; }
    .eq-4 { animation: eqBar 1.1s ease-in-out infinite 0.1s; }
    .eq-5 { animation: eqBar 1.4s ease-in-out infinite 0.3s; }
    .cyber-font-mono { font-family: 'SF Pro Text', 'Fira Code', 'JetBrains Mono', 'Segoe UI', monospace; }
    .cyber-font-sans { font-family: 'Space Grotesk', 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; }
  </style>

  <!-- Deep Obsidian Cyber Canvas -->
  <rect width="100%" height="100%" fill="#05070D" rx="20" />

  <!-- Ambient Cyber Lighting Radiance -->
  <circle cx="180" cy="90" r="220" fill="url(#cyber-orb)" />
  <circle cx="750" cy="220" r="260" fill="url(#cyber-orb)" />

  <!-- Cyber Matrix Hex Grid -->
  <rect width="100%" height="100%" fill="url(#cyber-grid)" rx="20" />

  <!-- ================= LIQUID ORGANIC BLOBS (Behind Glass) ================= -->
  <g filter="url(#liquid-blur)">
    <!-- Liquid Blob 1 (Cyan to Magenta) -->
    <path class="blob1" fill="url(#liquid-grad-1)" d="M120,60 C210,10 320,40 360,110 C410,190 320,260 220,270 C120,280 40,220 50,150 C60,80 80,90 120,60 Z" />
    
    <!-- Liquid Blob 2 (Magenta to Emerald) -->
    <path class="blob2" fill="url(#liquid-grad-2)" d="M620,80 C720,30 830,70 850,140 C880,220 780,280 700,270 C600,260 550,210 570,140 C590,80 560,110 620,80 Z" />

    <!-- Center Accent Plasma Drop -->
    <ellipse cx="460" cy="180" rx="140" ry="70" fill="#7000FF" opacity="0.65" />
  </g>

  <!-- ================= THE LIQUID GLASS MORPHIC CARD ================= -->
  <g filter="url(#glass-shadow)">
    <!-- Card Base with Frosted Gradient -->
    <rect x="40" y="30" width="820" height="260" rx="22" ry="22" 
          fill="url(#glass-surface)" 
          stroke="url(#glass-border-grad)" 
          stroke-width="1.5" />

    <!-- Card Specular Light Sheen (Top Left Liquid Glare) -->
    <path d="M 42 52 C 42 40 52 32 64 32 L 836 32 C 848 32 858 40 858 52 C 858 75 800 130 500 100 C 200 70 42 120 42 52 Z" 
          fill="url(#glass-specular)" />

    <!-- Liquid Ripple Accent Ring on Glass -->
    <ellipse cx="780" cy="70" rx="45" ry="45" fill="none" stroke="#00F0FF" stroke-opacity="0.2" stroke-width="1" stroke-dasharray="4,6" />
    <circle cx="780" cy="70" r="28" fill="none" stroke="#FF007A" stroke-opacity="0.25" stroke-width="1" />
  </g>

  <!-- ================= CYBER HUD OVERLAY & ACCENTS ================= -->
  <!-- Corner Brackets -->
  <g stroke="#00F0FF" stroke-width="2" stroke-linecap="round" opacity="0.85">
    <path d="M 55 58 L 55 45 L 68 45" fill="none" />
    <path d="M 845 58 L 845 45 L 832 45" fill="none" />
    <path d="M 55 262 L 55 275 L 68 275" fill="none" />
    <path d="M 845 262 L 845 275 L 832 275" fill="none" />
  </g>

  <!-- Glass Card Header Telemetry Strip -->
  <g class="cyber-font-mono" font-size="11" letter-spacing="1.5">
    <!-- Status Beacon Badge -->
    <rect x="68" y="52" width="185" height="24" rx="12" fill="#030816" stroke="#00F0FF" stroke-width="0.8" stroke-opacity="0.6" />
    <circle class="status-dot" cx="84" cy="64" r="4.5" fill="#00FFA3" filter="url(#neon-glow-cyan)" />
    <text x="96" y="68" fill="#A5F3FC" font-weight="600">SYS_CORE // ONLINE</text>

    <!-- Top Right HUD Metadata -->
    <text x="610" y="68" fill="#64748B" font-size="10" letter-spacing="1">LOC: 0x7F.0.0.1 // LATENCY: 14MS</text>
    
    <!-- Audio / Frequency Equalizer Wave -->
    <g transform="translate(805, 70)" fill="#00F0FF" opacity="0.85">
      <rect class="eq-1" x="0" y="-12" width="2.5" rx="1" />
      <rect class="eq-2" x="5" y="-18" width="2.5" rx="1" />
      <rect class="eq-3" x="10" y="-10" width="2.5" rx="1" />
      <rect class="eq-4" x="15" y="-15" width="2.5" rx="1" />
      <rect class="eq-5" x="20" y="-8" width="2.5" rx="1" />
    </g>
  </g>

  <!-- Subtle Horizontal HUD Guide Line -->
  <line x1="68" y1="88" x2="832" y2="88" stroke="#1E293B" stroke-width="1" />
  <line x1="68" y1="88" x2="160" y2="88" stroke="#00F0FF" stroke-width="1.5" opacity="0.8" />
  <line x1="450" y1="88" x2="490" y2="88" stroke="#FF007A" stroke-width="1.5" opacity="0.8" />

  <!-- ================= MAIN IDENTITY CONTENT ================= -->
  <g transform="translate(68, 122)">
    <text class="cyber-font-mono" font-size="12" fill="#38BDF8" letter-spacing="2.5" font-weight="600">
      &gt; INITIALIZING_NEURAL_INTERFACE...
    </text>

    <text class="cyber-font-sans" y="44" font-size="38" font-weight="900" fill="#FFFFFF" letter-spacing="-0.5">
      HELLO, WORLD. I'M <tspan fill="#00F0FF">SHERU</tspan><tspan fill="#FF007A">BHAI</tspan>
    </text>

    <text class="cyber-font-mono" y="74" font-size="14.5" fill="#94A3B8" letter-spacing="1">
      FULL-STACK CYBERNETIC ARCHITECT <tspan fill="#00FFA3">//</tspan> LIQUID UI &amp; CREATIVE DEV
    </text>
  </g>

  <!-- ================= INTERACTIVE HUD PILLS & CHIPS ================= -->
  <g transform="translate(68, 224)" class="cyber-font-mono" font-size="11">
    <g>
      <rect x="0" y="0" width="170" height="30" rx="8" fill="#091024" stroke="#00F0FF" stroke-opacity="0.4" stroke-width="1" />
      <text x="14" y="19" fill="#E2E8F0" font-weight="500">
        <tspan fill="#00F0FF">⚡</tspan> LIQUID GLASS UI
      </text>
    </g>

    <g transform="translate(182, 0)">
      <rect x="0" y="0" width="180" height="30" rx="8" fill="#091024" stroke="#FF007A" stroke-opacity="0.4" stroke-width="1" />
      <text x="14" y="19" fill="#E2E8F0" font-weight="500">
        <tspan fill="#FF007A">🔮</tspan> NEXT.JS / REACT / TS
      </text>
    </g>

    <g transform="translate(374, 0)">
      <rect x="0" y="0" width="195" height="30" rx="8" fill="#091024" stroke="#00FFA3" stroke-opacity="0.4" stroke-width="1" />
      <text x="14" y="19" fill="#E2E8F0" font-weight="500">
        <tspan fill="#00FFA3">🛡️</tspan> OPEN FOR OPS / COLLABS
      </text>
    </g>

    <g transform="translate(581, 0)">
      <rect x="0" y="0" width="183" height="30" rx="8" fill="#070C1B" stroke="#6366F1" stroke-opacity="0.4" stroke-width="1" />
      <text x="14" y="19" fill="#CBD5E1" font-weight="500">
        <tspan fill="#818CF8">❖</tspan> SEC LEVEL: LVL_99_ROOT
      </text>
    </g>
  </g>

  <!-- Ambient Scanning Neon Beam -->
  <line class="hud-scanner" x1="42" y1="35" x2="858" y2="35" stroke="url(#liquid-grad-1)" stroke-width="1.5" opacity="0.6" />
</svg>
