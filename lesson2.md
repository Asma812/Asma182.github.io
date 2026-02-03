---
layout: page
title: Lesson 2: Physics & Signals
permalink: /lesson2/
---
Understanding signals as the core of information transmission.

**Key Concepts:**
- Signal types (analog vs digital)
- Energy vs power signals
- Time domain vs frequency domain
- Bandwidth
- Noise (AWGN)
- SNR, BER

**Why It Matters:** Telecom is about transmitting information over noisy channels; this lesson teaches reliability in imperfect environments.

**Labs/Practice:** Simulated signal propagation and noise effects; measured SNR in basic transmission setups.

**Tools Used:** MATLAB, Wireshark for signal capture.


This is the bridge from pure math (Lesson 1) to actual telecom engineering. Signals & Systems is where you start thinking like a telecom engineer: how do we process, sample, filter, and digitize signals without losing (or corrupting) the information? This topic is foundational for digital communications (Lesson 3), RF/wireless, cellular, and almost every tool/project later (MATLAB, GNU Radio, srsRAN, etc.).
We'll go deep: concepts, intuition, telecom relevance, math glimpses (without overwhelming), and lots of practical insight. Aim for 15–20 min read if you pause to absorb the visuals and think through examples.
Why Signals & Systems Is the "Core Brain" of Telecom

Real-world signals are continuous-time analog (voice, radio waves).
Modern telecom is almost entirely digital after the antenna.
To go from analog → digital reliably → you need sampling, quantization, filtering, and system analysis.
Every modulation scheme, equalizer, channel estimator, beamformer, etc., is built on LTI system theory.
Skip or rush this → you'll understand what OFDM or QAM does, but not why it survives multipath or noise.

1. Continuous-Time vs Discrete-Time Systems

Continuous-time (analog): Signals defined for all real t (e.g., s(t) = cos(2π1000t)). Systems process them continuously (analog filters, amplifiers).
Discrete-time (digital): Signals only at integer multiples of sampling period: x[n] = x(nT_s), n = ..., -2, -1, 0, 1, 2,...
After ADC (analog-to-digital conversion).
Processed by DSP chips, FPGAs, software (Python/MATLAB).


Telecom reality:

RF front-end is analog/continuous.
Baseband processing (after down-conversion) is discrete/digital.
5G NR, Wi-Fi 6, LTE — massive digital signal processing at baseband.

2. LTI Systems (Linear Time-Invariant) — The Golden Assumption
Almost every telecom system we analyze is modeled as LTI:

Linear: If input ax1 + bx2 → output a y1 + b y2 (scaling + superposition).
Time-Invariant: Shift input by τ → output shifts by τ (no internal clocks changing behavior).

Why LTI is huge in telecom:

Filters (channel filters, anti-aliasing, matched filters)
Channels themselves (in many models, especially AWGN)
Equalizers, interpolators, beamformers
Allows powerful math: convolution, frequency response, z-transform/DFT.

3. Impulse Response — The DNA of an LTI System
The impulse response h(t) or h[n] completely characterizes an LTI system.

Apply δ(t) (Dirac delta, ideal instantaneous pulse) → output = h(t).
For any input x(t), output y(t) = x(t) * h(t)  (convolution).
Discrete: y[n] = ∑ x[k] h[n-k]

Intuition: h(t) tells you "how the system rings" after a sharp impulse.
Telecom examples:

Matched filter in receiver: h(t) = conjugate time-reversed transmitted pulse → maximizes SNR in AWGN.
Channel impulse response in multipath: multiple delayed copies → causes ISI (inter-symbol interference), fixed by OFDM or equalizers.

Here’s a visual example of an impulse response for a simple RC low-pass filter (common in analog front-ends):
etti.unibw.deLTI system example: RC low-pass filter - labAlive experiment
This shows the exponential decay — the "memory" of the filter.
4. Sampling Theorem (Nyquist-Shannon) — The Most Important Rule in Digital Telecom
To convert continuous → discrete without information loss:
Theorem: If a signal is bandlimited to maximum frequency f_max (i.e., no energy above f_max), then sampling at f_s ≥ 2 f_max perfectly reconstructs the original signal (using ideal sinc interpolation).

Nyquist rate = 2 f_max
Nyquist frequency = f_s / 2 (highest recoverable frequency)

Telecom examples:

Audio: human hearing ~20 kHz → CD uses 44.1 kHz (> 40 kHz Nyquist).
Cellular baseband: 5G channels up to ~100–400 MHz bandwidth → sampling rates in Gsamples/s in high-end radios.
Undersampling intentionally used in some bandpass sampling schemes (but risky).

Here are classic illustrations showing proper sampling vs aliasing:
medium.comgeeksforgeeks.org

Left: Proper sampling (f_s > 2 f_max) → reconstructs sine wave.
Right: Undersampling → high frequencies "fold" into low ones (aliasing distortion).
5. Aliasing — The Enemy You Must Understand
When f_s < 2 f_max, frequencies above f_s/2 fold back:
f_alias = |f - k f_s| for integer k that brings it into [-f_s/2, f_s/2]
Visual example — sine wave sampled too slowly appears as lower frequency:
visionbook.mit.edudsp.stackexchange.com

Prevention in telecom:

Always use anti-aliasing low-pass filter before ADC (cutoff ≤ f_s/2).
In software-defined radio (SDR): digital down-conversion + decimation carefully avoids aliasing.

6. Filtering: LPF, HPF, BPF
Filters remove unwanted frequencies.

Low-Pass Filter (LPF): Passes below cutoff, attenuates above → anti-aliasing, channel selection.
High-Pass Filter (HPF): Opposite — removes DC offset, low-freq noise.
Band-Pass Filter (BPF): Passes a band (e.g., around carrier) → selects channel in receiver.

Frequency response examples (ideal vs real approximations like Butterworth, Chebyshev):
allaboutcircuits.comfoxmusicproduction.com

Telecom: Digital FIR/IIR filters in baseband (Python SciPy, MATLAB filter designer).
7. Analog-to-Digital & Digital-to-Analog Conversion (ADC/DAC)
ADC chain:

Anti-aliasing LPF
Sample-and-hold (freezes value)
Quantization (map to discrete levels → quantization noise)
Encoding (binary)

DAC: Reverse — reconstruction filter smooths stair-steps.
Block diagram overview:
schaumont.dyn.wpi.eduhackatronic.com

Key impairments:

Quantization noise: increases with fewer bits (e.g., 8-bit vs 16-bit ADC).
Aperture jitter in high-speed sampling.
In telecom: high-resolution ADCs (12–16 bits) in base stations for dynamic range.
