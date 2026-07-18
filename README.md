<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 280" width="900" height="280" role="img" aria-label="Animated astronaut walking into a black hole, then Welcome to My GitHub text fades in">
  <defs>
    <radialGradient id="holeGlow" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="#c084ff" stop-opacity="0.9"/>
      <stop offset="45%" stop-color="#7c3aed" stop-opacity="0.45"/>
      <stop offset="100%" stop-color="#7c3aed" stop-opacity="0"/>
    </radialGradient>
    <radialGradient id="holeCore" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="#04000f"/>
      <stop offset="65%" stop-color="#0a0020"/>
      <stop offset="100%" stop-color="#22014d"/>
    </radialGradient>
    <linearGradient id="diskGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#00d9ff" stop-opacity="0"/>
      <stop offset="50%" stop-color="#00e5ff" stop-opacity="0.95"/>
      <stop offset="100%" stop-color="#b026ff" stop-opacity="0"/>
    </linearGradient>
    <linearGradient id="suitGrad" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" stop-color="#f7f7ff"/>
      <stop offset="100%" stop-color="#d6d6f2"/>
    </linearGradient>
    <radialGradient id="visorGrad" cx="35%" cy="32%" r="75%">
      <stop offset="0%" stop-color="#8ff0ff"/>
      <stop offset="55%" stop-color="#3aa0ff"/>
      <stop offset="100%" stop-color="#8a2be2"/>
    </radialGradient>
    <filter id="blurGlow" x="-100%" y="-100%" width="300%" height="300%">
      <feGaussianBlur stdDeviation="9"/>
    </filter>
    <style>
      @keyframes pulseGlow {
        0%, 100% { opacity: 0.55; transform: scale(1); }
        50%      { opacity: 0.95; transform: scale(1.12); }
      }
      @keyframes spinDisk {
        from { transform: rotate(0deg); }
        to   { transform: rotate(360deg); }
      }
      @keyframes textGlow {
        0%, 100% { filter: drop-shadow(0 0 4px #b026ff) drop-shadow(0 0 10px #00d9ff); }
        50%      { filter: drop-shadow(0 0 10px #b026ff) drop-shadow(0 0 20px #00d9ff); }
      }
      @keyframes twinkle {
        0%, 100% { opacity: 0.15; }
        50%      { opacity: 0.9; }
      }
      .glow-ring   { transform-origin: 720px 100px; animation: pulseGlow 2.4s ease-in-out infinite; }
      .disk-a      { transform-origin: 720px 100px; animation: spinDisk 5s linear infinite; }
      .disk-b      { transform-origin: 720px 100px; animation: spinDisk 3.6s linear infinite reverse; }
      .welcome-text{ font-family: 'Trebuchet MS','Segoe UI',sans-serif; animation: textGlow 2.2s ease-in-out infinite; }
      .star        { animation: twinkle 2.6s ease-in-out infinite; }
    </style>
  </defs>

  <!-- background stars -->
  <g fill="#c9b8ff">
    <circle class="star" cx="90"  cy="40"  r="1.4" style="animation-delay:0s"/>
    <circle class="star" cx="190" cy="90"  r="1.1" style="animation-delay:.4s"/>
    <circle class="star" cx="340" cy="35"  r="1.6" style="animation-delay:.9s"/>
    <circle class="star" cx="470" cy="60"  r="1.1" style="animation-delay:1.3s"/>
    <circle class="star" cx="590" cy="30"  r="1.3" style="animation-delay:.2s"/>
    <circle class="star" cx="150" cy="200" r="1.2" style="animation-delay:1.7s"/>
    <circle class="star" cx="820" cy="200" r="1.4" style="animation-delay:.6s"/>
    <circle class="star" cx="850" cy="60"  r="1.1" style="animation-delay:1.1s"/>
    <circle class="star" cx="30"  cy="150" r="1.3" style="animation-delay:2s"/>
  </g>

  <!-- black hole -->
  <g id="blackhole">
    <circle class="glow-ring" cx="720" cy="100" r="55" fill="url(#holeGlow)" filter="url(#blurGlow)"/>
    <ellipse class="disk-a" cx="720" cy="100" rx="82" ry="17" fill="none" stroke="url(#diskGrad)" stroke-width="4" opacity="0.9"/>
    <ellipse class="disk-b" cx="720" cy="100" rx="64" ry="13" fill="none" stroke="url(#diskGrad)" stroke-width="3" opacity="0.55"/>
    <circle cx="720" cy="100" r="25" fill="url(#holeCore)"/>
  </g>

  <!-- astronaut -->
  <g id="astro-pos">
    <animateMotion dur="10s" repeatCount="indefinite"
      keyTimes="0;0.3;0.35;0.42;0.46;0.5;1"
      keyPoints="0;0.42;0.58;0.7;0.85;0.95;1"
      calcMode="linear"
      path="M60,190 L260,188 L420,183 L500,178 Q560,158 610,132 Q655,108 680,102 C692,98 700,110 690,115 C680,120 676,104 686,100 C696,97 712,99 720,100"/>

    <g id="astro-spin">
      <animateTransform attributeName="transform" type="rotate"
        values="0;0;900;900" keyTimes="0;0.35;0.5;1"
        calcMode="spline" keySplines="0.3 0 0.7 1;0.2 0 0.8 1;0 0 1 1"
        dur="10s" repeatCount="indefinite"/>

      <g id="astro-scale">
        <animateTransform attributeName="transform" type="scale"
          values="1;1;0.05;0.05" keyTimes="0;0.35;0.5;1"
          calcMode="spline" keySplines="0.3 0 0.7 1;0.2 0 0.8 1;0 0 1 1"
          dur="10s" repeatCount="indefinite"/>

        <g id="astro-body">
          <!-- backpack -->
          <rect x="-9" y="-14" width="10" height="20" rx="3" fill="#9aa0c0"/>
          <rect x="-8" y="-12" width="8" height="6" rx="1" fill="#00d9ff" opacity="0.85"/>

          <!-- back leg -->
          <g transform="translate(-6,16)">
            <animateTransform attributeName="transform" type="rotate" additive="sum"
              values="0;22;-22;0" keyTimes="0;0.33;0.66;1" dur="0.9s" repeatCount="indefinite"/>
            <rect x="-3" y="0" width="6" height="18" rx="3" fill="#d6d6f2"/>
            <rect x="-3" y="14" width="6" height="6" rx="2" fill="#00d9ff"/>
          </g>
          <!-- front leg -->
          <g transform="translate(6,16)">
            <animateTransform attributeName="transform" type="rotate" additive="sum"
              values="0;-22;22;0" keyTimes="0;0.33;0.66;1" dur="0.9s" repeatCount="indefinite"/>
            <rect x="-3" y="0" width="6" height="18" rx="3" fill="#d6d6f2"/>
            <rect x="-3" y="14" width="6" height="6" rx="2" fill="#00d9ff"/>
          </g>

          <!-- body -->
          <rect x="-13" y="-16" width="26" height="32" rx="10" fill="url(#suitGrad)"/>
          <rect x="-13" y="-2" width="26" height="6" fill="#b026ff" opacity="0.85"/>

          <!-- back arm -->
          <g transform="translate(-13,-8)">
            <animateTransform attributeName="transform" type="rotate" additive="sum"
              values="0;-15;15;0" keyTimes="0;0.33;0.66;1" dur="0.9s" repeatCount="indefinite"/>
            <rect x="-4" y="0" width="5" height="16" rx="2.5" fill="url(#suitGrad)"/>
          </g>
          <!-- front arm -->
          <g transform="translate(13,-8)">
            <animateTransform attributeName="transform" type="rotate" additive="sum"
              values="0;15;-15;0" keyTimes="0;0.33;0.66;1" dur="0.9s" repeatCount="indefinite"/>
            <rect x="-1" y="0" width="5" height="16" rx="2.5" fill="url(#suitGrad)"/>
          </g>

          <!-- helmet -->
          <circle cx="0" cy="-24" r="15" fill="url(#suitGrad)"/>
          <circle cx="0" cy="-24" r="15" fill="none" stroke="#8a2be2" stroke-width="1.5" opacity="0.6"/>
          <ellipse cx="2" cy="-24" rx="10" ry="10" fill="url(#visorGrad)"/>
          <circle cx="-2" cy="-27" r="2.4" fill="#ffffff" opacity="0.85"/>

          <!-- surprise mark -->
          <g id="surprise" opacity="0">
            <animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.29;0.31;0.34;1" dur="10s" repeatCount="indefinite"/>
            <rect x="-1.5" y="-48" width="3" height="10" rx="1.5" fill="#faff00"/>
            <circle cx="0" cy="-34" r="1.8" fill="#faff00"/>
          </g>
        </g>
      </g>
    </g>
  </g>

  <!-- welcome text -->
  <g id="welcome-group" opacity="0">
    <animate attributeName="opacity" values="0;0;1;1;0;0" keyTimes="0;0.5;0.6;0.85;0.92;1" dur="10s" repeatCount="indefinite"/>
    <text class="welcome-text" x="450" y="235" text-anchor="middle" font-size="34" font-weight="700"
      fill="#ffffff" stroke="#b026ff" stroke-width="0.6">Welcome to My GitHub</text>
  </g>
</svg>
