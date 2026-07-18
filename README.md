<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">


</head>
<body>
<div class="wrap">

<header class="title">
  <h1>⚙️ Op-Amp & Analog IC — Key Performance Parameters</h1>
  <p>Complete Revision Notes — Definitions • Formulas • Diagrams • Examples • Exam Tips</p>
</header>

<div class="toc">
  <h2>📑 Contents</h2>
  <ol>
    <li><a href="#psrr">PSRR — Power Supply Rejection Ratio</a></li>
    <li><a href="#cmrr">CMRR — Common Mode Rejection Ratio</a></li>
    <li><a href="#gbw">GBW — Gain Bandwidth Product</a></li>
    <li><a href="#sr">Slew Rate (SR)</a></li>
    <li><a href="#vos">Input Offset Voltage (V<sub>os</sub>)</a></li>
    <li><a href="#thd">THD — Total Harmonic Distortion</a></li>
    <li><a href="#nf">NF — Noise Figure</a></li>
  </ol>
</div>

<!-- 1. PSRR -->
<img width="357" height="340" alt="image" src="https://github.com/user-attachments/assets/cc57504a-cb2f-4aa5-970c-16ec69b14e82" />

<div class="card" id="psrr">
  <h2 class="qtitle"><span class="num-badge">1</span> PSRR (Power Supply Rejection Ratio)</h2>
  <div class="grid2">
    <div>
      <div class="answer"><b>Definition:</b> PSRR measures how well a circuit rejects (ignores) unwanted variations or ripple/noise coming from its power supply lines, instead of letting them appear at the output.</div>
      <div class="formula-box">PSRR = ΔV<sub>S</sub> / ΔV<sub>OUT</sub> &nbsp;&nbsp;or in dB:&nbsp;&nbsp; PSRR(dB) = 20 log₁₀(ΔV<sub>S</sub>/ΔV<sub>OUT</sub>)</div>
      <div class="example"><b>Example:</b> If supply ripple is 100 mV and it produces only 10 µV at the output, PSRR is very high (~80 dB) — meaning the amp barely "feels" the supply noise.</div>
      <div class="tips"><b>Exam Tip:</b> Higher PSRR (in dB) = Better. Typical op-amp PSRR ranges from 60–120 dB. PSRR usually degrades (drops) at higher frequencies.</div>
    </div>
    <div class="diagram">
      <svg viewBox="0 0 260 200" xmlns="http://www.w3.org/2000/svg">
        <rect x="5" y="5" width="250" height="190" rx="10" fill="#fff" stroke="#c9c2a0"/>
        <text x="130" y="24" text-anchor="middle" font-size="11" fill="#c0392b" font-family="Segoe UI">PSRR Concept</text>
        <polygon points="80,70 80,130 150,100" fill="#dff2e6" stroke="#1e8a5f" stroke-width="1.5"/>
        <text x="72" y="80" font-size="9" text-anchor="end">+</text>
        <text x="72" y="126" font-size="9" text-anchor="end">−</text>
        <line x1="30" y1="100" x2="80" y2="100" stroke="#333"/>
        <text x="32" y="94" font-size="8">Vin</text>
        <line x1="150" y1="100" x2="200" y2="100" stroke="#333"/>
        <text x="180" y="94" font-size="8">Vout</text>
        <line x1="115" y1="70" x2="115" y2="50" stroke="#c0392b"/>
        <path d="M115,50 q5,-8 10,0 q5,-8 10,0" stroke="#c0392b" fill="none" stroke-width="1.2"/>
        <text x="118" y="42" font-size="8" fill="#c0392b">VDD+ΔV</text>
        <line x1="115" y1="130" x2="115" y2="160" stroke="#333"/>
        <text x="105" y="172" font-size="8">GND</text>
      </svg>
      <div class="diagram-caption">Supply ripple ΔV vs. resulting output ripple ΔVout</div>
    </div>
  </div>
</div>

<!-- 2. CMRR -->
<img width="354" height="339" alt="image" src="https://github.com/user-attachments/assets/9aaf1f96-e2ff-4928-8ca2-7431991b9e1d" />

<div class="card" id="cmrr">
  <h2 class="qtitle"><span class="num-badge">2</span> CMRR (Common Mode Rejection Ratio)</h2>
  <div class="grid2">
    <div>
      <div class="answer"><b>Definition:</b> CMRR is the ability of a differential amplifier to reject signals that are common to both inputs (common-mode signals/noise), while amplifying only the difference between the two inputs.</div>
      <div class="formula-box">CMRR = A<sub>d</sub> / A<sub>cm</sub> &nbsp;&nbsp;(dB): CMRR = 20 log₁₀(A<sub>d</sub>/A<sub>cm</sub>)</div>
      <div class="answer" style="margin-top:6px;">Where <b>A<sub>d</sub></b> = Differential Gain, <b>A<sub>cm</sub></b> = Common Mode Gain</div>
      <div class="example"><b>Example:</b> In ECG/biomedical amplifiers, both electrodes pick up the same 50/60 Hz mains hum (common-mode). High CMRR cancels this hum while still amplifying the tiny heart signal (differential).</div>
      <div class="tips"><b>Exam Tip:</b> Ideal op-amp has CMRR = ∞. Practical values: 80–120 dB. CMRR is crucial for instrumentation amplifiers.</div>
    </div>
    <div class="diagram">
      <svg viewBox="0 0 260 200" xmlns="http://www.w3.org/2000/svg">
        <rect x="5" y="5" width="250" height="190" rx="10" fill="#fff" stroke="#c9c2a0"/>
        <text x="130" y="22" text-anchor="middle" font-size="11" fill="#c0392b" font-family="Segoe UI">CMRR Concept</text>
        <polygon points="90,60 90,140 165,100" fill="#dff2e6" stroke="#1e8a5f" stroke-width="1.5"/>
        <text x="82" y="70" font-size="9" text-anchor="end">+</text>
        <text x="82" y="136" font-size="9" text-anchor="end">−</text>
        <line x1="30" y1="70" x2="90" y2="70" stroke="#333"/>
        <text x="32" y="64" font-size="8">Vin+</text>
        <line x1="30" y1="130" x2="90" y2="130" stroke="#333"/>
        <text x="32" y="146" font-size="8">Vin-</text>
        <line x1="165" y1="100" x2="210" y2="100" stroke="#333"/>
        <text x="185" y="94" font-size="8">Vout</text>
        <circle cx="30" cy="100" r="10" fill="#fde9e9" stroke="#c0392b"/>
        <text x="30" y="103" font-size="9" text-anchor="middle">VCM</text>
      </svg>
      <div class="diagram-caption">Differential inputs + common-mode signal Vcm</div>
    </div>
  </div>
</div>

<!-- 3. GBW -->
<img width="358" height="330" alt="image" src="https://github.com/user-attachments/assets/7af5bb0c-ffb8-4efe-aa1e-dca4309cf721" />

<div class="card" id="gbw">
  <h2 class="qtitle"><span class="num-badge">3</span> GBW (Gain Bandwidth Product)</h2>
  <div class="grid2">
    <div>
      <div class="answer"><b>Definition:</b> GBW is the product of an amplifier's open-loop gain and the bandwidth (frequency) at which that gain is measured. It tells you the frequency range over which the amp works effectively, and it is (approximately) constant for a single-pole op-amp.</div>
      <div class="formula-box">GBW = A<sub>o</sub> × f<sub>p</sub> &nbsp;&nbsp;(roll-off: −20 dB/decade after f<sub>p</sub>)</div>
      <div class="example"><b>Example:</b> An op-amp with GBW = 1 MHz gives gain of 100 at 10 kHz, but only gain of 10 at 100 kHz — gain × bandwidth stays ≈ constant.</div>
      <div class="tips"><b>Exam Tip:</b> Closed-loop bandwidth = GBW ÷ Closed-loop Gain. Higher gain circuits ⇒ lower usable bandwidth — a key design trade-off.</div>
    </div>
    <div class="diagram">
      <svg viewBox="0 0 260 190" xmlns="http://www.w3.org/2000/svg">
        <rect x="5" y="5" width="250" height="180" rx="10" fill="#fff" stroke="#c9c2a0"/>
        <text x="130" y="20" text-anchor="middle" font-size="11" fill="#c0392b" font-family="Segoe UI">Gain vs Frequency</text>
        <line x1="40" y1="150" x2="230" y2="150" stroke="#333"/>
        <line x1="40" y1="35" x2="40" y2="150" stroke="#333"/>
        <text x="15" y="45" font-size="8">Gain</text>
        <text x="180" y="165" font-size="8">Frequency (Hz)</text>
        <line x1="40" y1="45" x2="120" y2="45" stroke="#2457a8" stroke-width="2"/>
        <line x1="120" y1="45" x2="220" y2="130" stroke="#2457a8" stroke-width="2"/>
        <line x1="120" y1="45" x2="120" y2="150" stroke="#999" stroke-dasharray="3,3"/>
        <text x="112" y="162" font-size="8">fp</text>
        <text x="140" y="60" font-size="8" fill="#2457a8">−20 dB/dec</text>
      </svg>
      <div class="diagram-caption">Open-loop gain roll-off; area under curve region = GBW</div>
    </div>
  </div>
</div>

<!-- 4. SR -->
<div class="card" id="sr">
  <h2 class="qtitle"><span class="num-badge">4</span> Slew Rate (SR)</h2>
  <div class="grid2">
    <div>
      <div class="answer"><b>Definition:</b> Slew Rate is the maximum rate at which the output voltage of an op-amp can change with time. It limits how fast/large a signal the amplifier can faithfully reproduce, especially for large-amplitude, high-frequency signals.</div>
      <div class="formula-box">SR = max(dV<sub>out</sub>/dt) &nbsp;&nbsp;— units: V/µs</div>
      <div class="example"><b>Example:</b> If a fast square/step input is applied but SR is too low, the output ramps up as a straight sloped line (triangular shape) instead of a sharp square edge — this is called "slew-rate limiting" or "slew distortion."</div>
      <div class="tips"><b>Exam Tip:</b> Full-power bandwidth: f<sub>max</sub> = SR / (2πV<sub>p</sub>). Typical general-purpose op-amp SR ≈ 0.5–20 V/µs; high-speed amps can exceed 1000 V/µs.</div>
    </div>
    <div class="diagram">
      <svg viewBox="0 0 260 190" xmlns="http://www.w3.org/2000/svg">
        <rect x="5" y="5" width="250" height="180" rx="10" fill="#fff" stroke="#c9c2a0"/>
        <text x="130" y="20" text-anchor="middle" font-size="11" fill="#c0392b" font-family="Segoe UI">Slew Rate Concept</text>
        <line x1="30" y1="150" x2="230" y2="150" stroke="#333"/>
        <line x1="30" y1="30" x2="30" y2="150" stroke="#333"/>
        <path d="M30,120 L30,50 L100,50 L170,120 L170,50 L230,50" fill="none" stroke="#2457a8" stroke-dasharray="4,3"/>
        <path d="M30,120 L60,50 L140,50 L170,120 L200,50" fill="none" stroke="#c0392b" stroke-width="2"/>
        <text x="10" y="45" font-size="8">+Vp</text>
        <text x="10" y="128" font-size="8">−Vp</text>
        <text x="190" y="165" font-size="8">Time</text>
      </svg>
      <div class="diagram-caption">Ideal square edge (dashed) vs. real slope-limited output (red)</div>
    </div>
  </div>
</div>

<!-- 5. Vos -->
<div class="card" id="vos">
  <h2 class="qtitle"><span class="num-badge">5</span> Input Offset Voltage (V<sub>os</sub>)</h2>
  <div class="grid2">
    <div>
      <div class="answer"><b>Definition:</b> Input Offset Voltage is the small DC differential voltage that must be applied between the two input terminals of a real op-amp to force the output voltage to exactly zero (compensating internal mismatches).</div>
      <div class="formula-box">V<sub>out</sub> = 0 &nbsp;when&nbsp; V<sub>in+</sub> − V<sub>in−</sub> = V<sub>os</sub></div>
      <div class="example"><b>Example:</b> Even with both inputs "shorted together" and grounded, a real op-amp's output won't sit exactly at 0 V — it drifts due to V<sub>os</sub> (caused by mismatched input transistors).</div>
      <div class="tips"><b>Exam Tip:</b> Typical V<sub>os</sub> ranges from a few µV (precision amps) to a few mV (general-purpose). It causes DC output error, especially significant in high-gain DC amplifier stages.</div>
    </div>
    <div class="diagram">
      <svg viewBox="0 0 260 170" xmlns="http://www.w3.org/2000/svg">
        <rect x="5" y="5" width="250" height="160" rx="10" fill="#fff" stroke="#c9c2a0"/>
        <text x="130" y="20" text-anchor="middle" font-size="11" fill="#c0392b" font-family="Segoe UI">Input Offset Concept</text>
        <polygon points="90,55 90,115 160,85" fill="#dff2e6" stroke="#1e8a5f" stroke-width="1.5"/>
        <text x="82" y="63" font-size="9" text-anchor="end">+</text>
        <text x="82" y="112" font-size="9" text-anchor="end">−</text>
        <line x1="30" y1="55" x2="90" y2="55" stroke="#333"/>
        <text x="32" y="50" font-size="8">Vin+</text>
        <line x1="30" y1="115" x2="90" y2="115" stroke="#333"/>
        <text x="32" y="130" font-size="8">Vin-</text>
        <line x1="160" y1="85" x2="210" y2="85" stroke="#333"/>
        <text x="180" y="80" font-size="8">Vout</text>
        <line x1="60" y1="55" x2="60" y2="35" stroke="#333"/>
        <line x1="60" y1="115" x2="60" y2="135" stroke="#333"/>
      </svg>
      <div class="diagram-caption">Ideal-input diff. amp — offset appears purely as internal mismatch</div>
    </div>
  </div>
</div>

<!-- 6. THD -->
<div class="card" id="thd">
  <h2 class="qtitle"><span class="num-badge">6</span> THD (Total Harmonic Distortion)</h2>
  <div class="grid2">
    <div>
      <div class="answer"><b>Definition:</b> THD is the ratio of the combined power (or RMS value) of all harmonic frequency components to the power of the fundamental frequency component. It quantifies how much a circuit distorts a pure input signal.</div>
      <div class="formula-box">THD = √(V₂²+V₃²+V₄²+...) / V₁ × 100%</div>
      <div class="answer" style="margin-top:6px;">Where V₁ = Fundamental RMS, V₂,V₃,... = Harmonic RMS values</div>
      <div class="example"><b>Example:</b> A pure 1 kHz sine input, when passed through a nonlinear amplifier, may come out with small 2 kHz, 3 kHz "echoes" mixed in — the output sine looks slightly "clipped" or warped.</div>
      <div class="tips"><b>Exam Tip:</b> Lower THD = More faithful (linear) amplification. Audio amplifiers typically target THD &lt; 0.1%; hi-fi/precision systems aim for &lt; 0.01%.</div>
    </div>
    <div class="diagram">
      <svg viewBox="0 0 260 170" xmlns="http://www.w3.org/2000/svg">
        <rect x="5" y="5" width="250" height="160" rx="10" fill="#fff" stroke="#c9c2a0"/>
        <text x="130" y="20" text-anchor="middle" font-size="11" fill="#c0392b" font-family="Segoe UI">THD Concept</text>
        <text x="55" y="35" font-size="8">Input (Pure)</text>
        <path d="M20,60 Q40,35 60,60 T100,60" fill="none" stroke="#2457a8" stroke-width="1.5"/>
        <text x="170" y="35" font-size="8">Output (Distorted)</text>
        <path d="M140,60 Q150,40 160,60 Q168,50 175,60 T210,60" fill="none" stroke="#c0392b" stroke-width="1.5"/>
        <line x1="20" y1="60" x2="100" y2="60" stroke="#999" stroke-dasharray="2,2"/>
        <line x1="140" y1="60" x2="220" y2="60" stroke="#999" stroke-dasharray="2,2"/>
      </svg>
      <div class="diagram-caption">Pure sine input vs. harmonically distorted output</div>
    </div>
  </div>
</div>

<!-- 7. NF -->
<div class="card" id="nf">
  <h2 class="qtitle"><span class="num-badge">7</span> NF (Noise Figure)</h2>
  <div class="grid2">
    <div>
      <div class="answer"><b>Definition:</b> Noise Figure measures how much a circuit degrades the Signal-to-Noise Ratio (SNR) as a signal passes through it — i.e., how much extra noise the circuit itself adds.</div>
      <div class="formula-box">NF = SNR<sub>in</sub> / SNR<sub>out</sub> = (P<sub>in</sub>/N<sub>in</sub>) / (P<sub>out</sub>/N<sub>out</sub>) &nbsp;&nbsp;NF(dB) = 10 log₁₀(NF)</div>
      <div class="example"><b>Example:</b> An RF LNA (Low Noise Amplifier) with NF = 1 dB adds very little noise — critical for receiving weak satellite or wireless signals.</div>
      <div class="tips"><b>Exam Tip:</b> Lower NF = Better (less noise added). NF = 0 dB is the ideal, noiseless case. Very important in RF front-ends and sensor signal chains.</div>
    </div>
    <div class="diagram">
      <svg viewBox="0 0 260 150" xmlns="http://www.w3.org/2000/svg">
        <rect x="5" y="5" width="250" height="140" rx="10" fill="#fff" stroke="#c9c2a0"/>
        <text x="130" y="20" text-anchor="middle" font-size="11" fill="#c0392b" font-family="Segoe UI">Noise Figure Concept</text>
        <rect x="15" y="55" width="55" height="35" rx="6" fill="#fde9e9" stroke="#c0392b"/>
        <text x="42" y="76" font-size="7" text-anchor="middle">Noisy Source</text>
        <rect x="105" y="50" width="70" height="45" rx="6" fill="#dff2e6" stroke="#1e8a5f"/>
        <text x="140" y="70" font-size="7" text-anchor="middle">Amplifier</text>
        <text x="140" y="82" font-size="6" text-anchor="middle">(Under Test)</text>
        <line x1="70" y1="72" x2="105" y2="72" stroke="#333"/>
        <text x="75" y="66" font-size="7">Pin, Nin</text>
        <line x1="175" y1="72" x2="225" y2="72" stroke="#333"/>
        <text x="182" y="66" font-size="7">Pout, Nout</text>
      </svg>
      <div class="diagram-caption">Noise added by the amplifier itself, beyond source noise</div>
    </div>
  </div>
</div>

<!-- Summary Table -->
<div class="summary-table">
  <h2>⚡ Quick Revision Summary</h2>
  <table>
    <tr><th>Parameter</th><th>Formula</th><th>Ideal Value</th><th>Typical Real Value</th><th>Better When</th></tr>
    <tr><td>PSRR</td><td>ΔV<sub>S</sub>/ΔV<sub>OUT</sub></td><td>∞ (0 output change)</td><td>60–120 dB</td><td>Higher (dB) ↑</td></tr>
    <tr><td>CMRR</td><td>A<sub>d</sub>/A<sub>cm</sub></td><td>∞</td><td>80–120 dB</td><td>Higher (dB) ↑</td></tr>
    <tr><td>GBW</td><td>A<sub>o</sub> × f<sub>p</sub></td><td>Constant (any gain)</td><td>1 MHz – 1 GHz</td><td>Higher ↑</td></tr>
    <tr><td>Slew Rate</td><td>max(dV<sub>out</sub>/dt)</td><td>∞ (instant)</td><td>0.5 – 1000+ V/µs</td><td>Higher ↑</td></tr>
    <tr><td>V<sub>os</sub></td><td>V<sub>in+</sub> − V<sub>in−</sub> at V<sub>out</sub>=0</td><td>0 V</td><td>µV – few mV</td><td>Lower ↓</td></tr>
    <tr><td>THD</td><td>√(V₂²+V₃²+...)/V₁ ×100%</td><td>0%</td><td>0.001% – 1%</td><td>Lower ↓</td></tr>
    <tr><td>Noise Figure</td><td>SNR<sub>in</sub>/SNR<sub>out</sub></td><td>0 dB (1 in ratio)</td><td>0.5 – 10 dB</td><td>Lower ↓</td></tr>
  </table>
</div>

<footer>Notes compiled for quick revision • Op-Amp & Analog IC Design Parameters</footer>

</div>
</body>
</html>
