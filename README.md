<svg width="900" height="300" viewBox="0 0 900 300" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Surya Pratap Singh — ML Systems HUD banner">
  <defs>
    <!-- ====== gradients ====== -->
    <linearGradient id="bgGrad" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0" stop-color="#05050c"/>
      <stop offset="0.7" stop-color="#0a0a14"/>
      <stop offset="1" stop-color="#0d0618"/>
    </linearGradient>
    <linearGradient id="edgeStrip" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0" stop-color="#FF00E5"/>
      <stop offset="0.5" stop-color="#8B00FF"/>
      <stop offset="1" stop-color="#00F0FF"/>
    </linearGradient>
    <radialGradient id="radarGlow" cx="0.5" cy="0.5" r="0.5">
      <stop offset="0" stop-color="#00F0FF" stop-opacity="0.16"/>
      <stop offset="0.8" stop-color="#00F0FF" stop-opacity="0.03"/>
      <stop offset="1" stop-color="#00F0FF" stop-opacity="0"/>
    </radialGradient>
    <linearGradient id="sweepGrad" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0" stop-color="#00F0FF" stop-opacity="0"/>
      <stop offset="0.85" stop-color="#00F0FF" stop-opacity="0.25"/>
      <stop offset="1" stop-color="#00F0FF" stop-opacity="0.85"/>
    </linearGradient>
    <radialGradient id="nodeCore" cx="0.5" cy="0.5" r="0.5">
      <stop offset="0" stop-color="#ffffff"/>
      <stop offset="0.35" stop-color="#FF2E9F"/>
      <stop offset="1" stop-color="#FF2E9F" stop-opacity="0"/>
    </radialGradient>
    <filter id="glow" x="-60%" y="-60%" width="220%" height="220%">
      <feGaussianBlur stdDeviation="2.2" result="b"/>
      <feMerge><feMergeNode in="b"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <filter id="bigGlow" x="-80%" y="-80%" width="260%" height="260%">
      <feGaussianBlur stdDeviation="5" result="b"/>
      <feMerge><feMergeNode in="b"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <!-- perspective floor grid, built once, reused -->
    <pattern id="scan" width="4" height="4" patternUnits="userSpaceOnUse">
      <rect width="4" height="2" fill="#000000" opacity="0.14"/>
    </pattern>
    <clipPath id="frame"><rect width="900" height="300" rx="10"/></clipPath>
  </defs>

  <g clip-path="url(#frame)">
    <!-- ====== backdrop ====== -->
    <rect width="900" height="300" fill="url(#bgGrad)"/>

    <!-- perspective wireframe floor -->
    <g stroke="#8B00FF" stroke-width="0.6" opacity="0.35">
      <line x1="450" y1="180" x2="-140" y2="300"/>
      <line x1="450" y1="180" x2="80"  y2="300"/>
      <line x1="450" y1="180" x2="270" y2="300"/>
      <line x1="450" y1="180" x2="450" y2="300"/>
      <line x1="450" y1="180" x2="630" y2="300"/>
      <line x1="450" y1="180" x2="820" y2="300"/>
      <line x1="450" y1="180" x2="1040" y2="300"/>
      <path d="M 240 218 H 660" opacity="0.8"/>
      <path d="M 150 244 H 750" opacity="0.6"/>
      <path d="M 30 274 H 870" opacity="0.4"/>
      <!-- horizon shimmer -->
      <line x1="0" y1="180" x2="900" y2="180" stroke="#FF00E5" stroke-width="1" opacity="0.5">
        <animate attributeName="opacity" values="0.5;0.15;0.5" dur="4s" repeatCount="indefinite"/>
      </line>
    </g>

    <!-- ====== LEFT: neural lattice (MAIRA) ====== -->
    <g transform="translate(70,52)">
      <!-- connection wires: dash-flow gives 'signal' movement, staggered -->
      <g stroke-width="1" fill="none" stroke-linecap="round">
        <path d="M 0 20 C 40 20 40 0 80 6"    stroke="#00F0FF" opacity="0.55" stroke-dasharray="6 46">
          <animate attributeName="stroke-dashoffset" from="52" to="0" dur="1.7s" repeatCount="indefinite"/>
        </path>
        <path d="M 0 60 C 40 60 40 10 80 6"   stroke="#FF2E9F" opacity="0.55" stroke-dasharray="6 52">
          <animate attributeName="stroke-dashoffset" from="58" to="0" dur="2.3s" repeatCount="indefinite"/>
        </path>
        <path d="M 0 60 C 44 60 44 52 80 50"  stroke="#00F0FF" opacity="0.55" stroke-dasharray="6 44">
          <animate attributeName="stroke-dashoffset" from="50" to="0" dur="1.4s" repeatCount="indefinite"/>
        </path>
        <path d="M 0 100 C 40 100 40 56 80 50" stroke="#8B00FF" opacity="0.7" stroke-dasharray="6 50">
          <animate attributeName="stroke-dashoffset" from="56" to="0" dur="2.0s" repeatCount="indefinite"/>
        </path>
        <path d="M 0 100 C 46 100 46 92 80 94" stroke="#FF2E9F" opacity="0.55" stroke-dasharray="6 46">
          <animate attributeName="stroke-dashoffset" from="52" to="0" dur="2.6s" repeatCount="indefinite"/>
        </path>
        <path d="M 0 20 C 46 20 46 88 80 94"  stroke="#8B00FF" opacity="0.55" stroke-dasharray="6 58">
          <animate attributeName="stroke-dashoffset" from="64" to="0" dur="1.9s" repeatCount="indefinite"/>
        </path>
        <path d="M 80 6 C 116 6 116 40 150 46"  stroke="#00F0FF" opacity="0.7" stroke-dasharray="6 48">
          <animate attributeName="stroke-dashoffset" from="54" to="0" dur="1.5s" repeatCount="indefinite"/>
        </path>
        <path d="M 80 50 C 116 50 116 46 150 46" stroke="#FF2E9F" opacity="0.7" stroke-dasharray="6 40">
          <animate attributeName="stroke-dashoffset" from="46" to="0" dur="1.2s" repeatCount="indefinite"/>
        </path>
        <path d="M 80 94 C 116 94 116 52 150 46" stroke="#8B00FF" opacity="0.7" stroke-dasharray="6 50">
          <animate attributeName="stroke-dashoffset" from="56" to="0" dur="2.1s" repeatCount="indefinite"/>
        </path>
      </g>
      <!-- input layer -->
      <g fill="#0a0a14" stroke="#00F0FF" stroke-width="1.2">
        <circle cx="0" cy="20"  r="4"><animate attributeName="stroke-opacity" values="1;0.3;1" dur="1.7s" repeatCount="indefinite"/></circle>
        <circle cx="0" cy="60"  r="4"><animate attributeName="stroke-opacity" values="0.3;1;0.3" dur="2.3s" repeatCount="indefinite"/></circle>
        <circle cx="0" cy="100" r="4"><animate attributeName="stroke-opacity" values="1;0.4;1" dur="2.0s" repeatCount="indefinite"/></circle>
      </g>
      <!-- hidden layer -->
      <g fill="#0a0a14" stroke="#FF2E9F" stroke-width="1.2">
        <circle cx="80" cy="6"  r="4.5"><animate attributeName="r" values="4.5;5.5;4.5" dur="1.5s" repeatCount="indefinite"/></circle>
        <circle cx="80" cy="50" r="4.5"><animate attributeName="r" values="4.5;5.5;4.5" dur="1.9s" begin="0.4s" repeatCount="indefinite"/></circle>
        <circle cx="80" cy="94" r="4.5"><animate attributeName="r" values="4.5;5.5;4.5" dur="1.7s" begin="0.8s" repeatCount="indefinite"/></circle>
      </g>
      <!-- output node: bright pulsing core -->
      <circle cx="150" cy="46" r="13" fill="url(#nodeCore)" opacity="0.9">
        <animate attributeName="r" values="11;16;11" dur="2.4s" repeatCount="indefinite"/>
      </circle>
      <circle cx="150" cy="46" r="5" fill="#0a0a14" stroke="#FF2E9F" stroke-width="1.6" filter="url(#glow)"/>
      <text x="150" y="76" text-anchor="middle" font-family="'Courier New',monospace" font-size="9" fill="#FF2E9F" opacity="0.85" letter-spacing="2">MAIRA</text>
      <!-- packets riding the final wires -->
      <circle r="2" fill="#ffffff" filter="url(#glow)">
        <animateMotion dur="1.5s" repeatCount="indefinite" path="M 80 6 C 116 6 116 40 150 46"/>
      </circle>
      <circle r="2" fill="#ffffff" filter="url(#glow)">
        <animateMotion dur="2.1s" repeatCount="indefinite" path="M 80 94 C 116 94 116 52 150 46"/>
      </circle>
    </g>

    <!-- ====== RIGHT: combat radar (DRL Aerial) ====== -->
    <g transform="translate(755,105)">
      <circle r="86" fill="url(#radarGlow)"/>
      <g stroke="#00F0FF" fill="none" opacity="0.5" stroke-width="0.8">
        <circle r="78"/><circle r="56"/><circle r="34"/><circle r="13"/>
        <line x1="-78" y1="0" x2="78" y2="0"/>
        <line x1="0" y1="-78" x2="0" y2="78"/>
        <line x1="-55" y1="-55" x2="55" y2="55" opacity="0.4"/>
        <line x1="-55" y1="55" x2="55" y2="-55" opacity="0.4"/>
      </g>
      <!-- bearing ticks -->
      <g stroke="#00F0FF" stroke-width="1.4" opacity="0.7">
        <line x1="0" y1="-78" x2="0" y2="-72"/><line x1="78" y1="0" x2="72" y2="0"/>
        <line x1="0" y1="78" x2="0" y2="72"/><line x1="-78" y1="0" x2="-72" y2="0"/>
      </g>
      <!-- rotating sweep wedge -->
      <g>
        <path d="M 0 0 L 78 0 A 78 78 0 0 0 67.5 -39 Z" fill="url(#sweepGrad)" opacity="0.9"/>
        <line x1="0" y1="0" x2="78" y2="0" stroke="#00F0FF" stroke-width="1.6" filter="url(#glow)"/>
        <animateTransform attributeName="transform" type="rotate" from="0" to="360" dur="4s" repeatCount="indefinite"/>
      </g>
      <!-- contacts: each blips as the 4s sweep passes its bearing -->
      <g>
        <path d="M 30 -38 l 5 8 l -5 -2.4 l -5 2.4 Z" fill="#FF2E9F" filter="url(#glow)" opacity="0">
          <animate attributeName="opacity" values="0;1;1;0.12;0" keyTimes="0;0.04;0.3;0.8;1" dur="4s" begin="3.44s" repeatCount="indefinite"/>
        </path>
        <path d="M -45 -20 l 5 8 l -5 -2.4 l -5 2.4 Z" fill="#FF2E9F" filter="url(#glow)" opacity="0" transform="rotate(40 -45 -20)">
          <animate attributeName="opacity" values="0;1;1;0.12;0" keyTimes="0;0.04;0.3;0.8;1" dur="4s" begin="2.27s" repeatCount="indefinite"/>
        </path>
        <path d="M -22 48 l 5 8 l -5 -2.4 l -5 2.4 Z" fill="#00F0FF" filter="url(#glow)" opacity="0" transform="rotate(200 -22 48)">
          <animate attributeName="opacity" values="0;1;1;0.12;0" keyTimes="0;0.04;0.3;0.8;1" dur="4s" begin="1.28s" repeatCount="indefinite"/>
        </path>
        <path d="M 52 30 l 5 8 l -5 -2.4 l -5 2.4 Z" fill="#8B00FF" filter="url(#glow)" opacity="0" transform="rotate(150 52 30)">
          <animate attributeName="opacity" values="0;1;1;0.12;0" keyTimes="0;0.04;0.3;0.8;1" dur="4s" begin="0.33s" repeatCount="indefinite"/>
        </path>
      </g>
      <!-- friendly craft orbiting -->
      <g>
        <path d="M 0 -6 l 4.6 8 l -4.6 -2 l -4.6 2 Z" fill="#00F0FF" filter="url(#glow)">
          <animateTransform attributeName="transform" type="rotate" from="0" to="-360" dur="9s" repeatCount="indefinite"/>
        </path>
        <animateMotion dur="9s" repeatCount="indefinite" path="M 0 -45 A 45 45 0 1 0 0.1 -45"/>
      </g>
      <text y="98" text-anchor="middle" font-family="'Courier New',monospace" font-size="9" fill="#00F0FF" opacity="0.85" letter-spacing="2">DRL·AIRSPACE</text>
    </g>

    <!-- ====== CENTER: name with RGB-split glitch ====== -->
    <g font-family="'Arial Black','Segoe UI',system-ui,sans-serif" font-weight="900" font-size="43" text-anchor="middle" letter-spacing="2">
      <!-- chromatic ghosts: offset copies flicker in briefly on a 6s cycle -->
      <text x="448" y="118" fill="#FF00E5" opacity="0">
        SURYA PRATAP SINGH
        <animate attributeName="opacity" values="0;0;0.8;0;0.55;0;0" keyTimes="0;0.62;0.635;0.65;0.665;0.68;1" dur="6s" repeatCount="indefinite"/>
        <animateTransform attributeName="transform" type="translate" values="0 0;-3 1;2 -1;0 0" keyTimes="0;0.63;0.67;1" dur="6s" repeatCount="indefinite"/>
      </text>
      <text x="452" y="118" fill="#00F0FF" opacity="0">
        SURYA PRATAP SINGH
        <animate attributeName="opacity" values="0;0;0.8;0;0.55;0;0" keyTimes="0;0.62;0.635;0.65;0.665;0.68;1" dur="6s" repeatCount="indefinite"/>
        <animateTransform attributeName="transform" type="translate" values="0 0;3 -1;-2 1;0 0" keyTimes="0;0.63;0.67;1" dur="6s" repeatCount="indefinite"/>
      </text>
      <!-- main plate -->
      <text x="450" y="118" fill="#f2f4ff" filter="url(#bigGlow)">SURYA PRATAP SINGH</text>
      <!-- slice-band that shears across during the glitch window -->
      <g clip-path="url(#sliceClip)">
        <text x="450" y="118" fill="#f2f4ff">
          SURYA PRATAP SINGH
          <animateTransform attributeName="transform" type="translate" values="0 0;0 0;7 0;-6 0;0 0;0 0" keyTimes="0;0.62;0.64;0.66;0.68;1" dur="6s" repeatCount="indefinite"/>
        </text>
      </g>
    </g>
    <clipPath id="sliceClip"><rect x="180" y="96" width="540" height="9"/></clipPath>

    <!-- subtitle: typed on, cursor blinks -->
    <g font-family="'Courier New',monospace" font-size="13" letter-spacing="3">
      <clipPath id="typeClip">
        <rect x="290" y="130" width="0" height="20">
          <animate attributeName="width" values="0;0;330;330" keyTimes="0;0.08;0.45;1" dur="6s" repeatCount="indefinite"/>
        </rect>
      </clipPath>
      <text x="450" y="145" text-anchor="middle" fill="#00F0FF" clip-path="url(#typeClip)">&gt; ML SYSTEMS · DEEP RL · AGENTS</text>
      <rect x="622" y="133" width="7" height="15" fill="#FF2E9F">
        <animate attributeName="opacity" values="1;0;1" dur="0.9s" repeatCount="indefinite"/>
      </rect>
    </g>

    <!-- status readout, bottom-left -->
    <g font-family="'Courier New',monospace" font-size="9" fill="#8B00FF" opacity="0.9">
      <text x="26" y="262">SYS: NOMINAL</text>
      <text x="26" y="276" fill="#00F0FF">OPEN_TO_WORK = <tspan fill="#FF2E9F">TRUE</tspan></text>
      <text x="26" y="290" opacity="0.7">uptime: <tspan>
        <animate attributeName="opacity" values="1;0.4;1" dur="2s" repeatCount="indefinite"/>∞</tspan></text>
    </g>

    <!-- telemetry bars, bottom-right of center -->
    <g transform="translate(560,252)">
      <g fill="#00F0FF">
        <rect x="0"  width="5" y="-12" height="12"><animate attributeName="height" values="12;26;7;18;12" dur="2.2s" repeatCount="indefinite"/><animate attributeName="y" values="-12;-26;-7;-18;-12" dur="2.2s" repeatCount="indefinite"/></rect>
        <rect x="9"  width="5" y="-20" height="20" fill="#FF2E9F"><animate attributeName="height" values="20;9;28;14;20" dur="1.8s" repeatCount="indefinite"/><animate attributeName="y" values="-20;-9;-28;-14;-20" dur="1.8s" repeatCount="indefinite"/></rect>
        <rect x="18" width="5" y="-8" height="8" fill="#8B00FF"><animate attributeName="height" values="8;22;13;30;8" dur="2.6s" repeatCount="indefinite"/><animate attributeName="y" values="-8;-22;-13;-30;-8" dur="2.6s" repeatCount="indefinite"/></rect>
        <rect x="27" width="5" y="-16" height="16"><animate attributeName="height" values="16;30;10;24;16" dur="2.0s" repeatCount="indefinite"/><animate attributeName="y" values="-16;-30;-10;-24;-16" dur="2.0s" repeatCount="indefinite"/></rect>
      </g>
      <text y="14" font-family="'Courier New',monospace" font-size="8" fill="#00F0FF" opacity="0.7" letter-spacing="1">TELEMETRY</text>
    </g>

    <!-- corner brackets: HUD frame -->
    <g stroke="#00F0FF" stroke-width="2" fill="none" opacity="0.9" filter="url(#glow)">
      <path d="M 14 34 V 14 H 34"/>
      <path d="M 866 14 H 886 V 34"/>
      <path d="M 886 266 V 286 H 866"/>
      <path d="M 34 286 H 14 V 266"/>
    </g>

    <!-- edge gradient strips -->
    <rect x="0" y="0" width="900" height="3" fill="url(#edgeStrip)"/>
    <rect x="0" y="297" width="900" height="3" fill="url(#edgeStrip)"/>

    <!-- CRT scanlines + drifting scan bar over everything -->
    <rect width="900" height="300" fill="url(#scan)"/>
    <rect x="0" y="-40" width="900" height="26" fill="#00F0FF" opacity="0.045">
      <animate attributeName="y" from="-40" to="300" dur="7s" repeatCount="indefinite"/>
    </rect>
  </g>
</svg>
