# Module 01: Lab Submission Report

**Student Name:** Abdullahi Gideon Ngbede  
**GitHub Username:** @ngbedeabdull  
**Track Selected:** Track 3: The Tech Incident Report  
**Model & Engine:** Gemini 3.8 Flash (High) / Google AI Studio  

---

## 1. Frozen Prompt

### System Prompt
```text
You are a cognitive science educator and senior software mentor who synthesizes the principles of Barbara Oakley's Learning How to Learn (focused vs. diffuse thinking modes, chunking, and the Einstellung effect) with Angela Duckworth's research on Grit.
```

### User Prompt
```text
A junior engineer transitioning into technical problem solving is struggling with cognitive overload, feeling stuck on a complex debugging bug, and experiencing intense imposter syndrome.
Write a 3-part mentorship breakdown:
1. Neural Mechanics: Explain how shifting from focused mode to diffuse mode physically works in the brain when tackling a stubborn engineering problem.
2. Actionable Chunking: Give a 3-step practical protocol to deconstruct overwhelming concepts into compact mental chunks without succumbing to the Einstellung effect (getting trapped in a flawed initial approach).
3. The Engineering Mindset: Provide a concise, grounding insight on building grit and a growth mindset when debugging code feels demoralizing.
```

---

## 2. 7-Run Calibration Matrix

| Run ID | Temp | Top-K | Top-P | Tokens | Coherence (1-10) | Qualitative Observations |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Run 1** | 0.0 | 1 | 1.0 | 478 | 10/10 | Deterministic baseline (Greedy decoding; zero variance) |
| **Run 2** | 0.2 | 40 | 0.8 | 504 | 9.5/10 | Focused coherence with minor syntactic variation |
| **Run 3** | 0.7 | 40 | 0.9 | 552 | 10/10 | Balanced standard (Optimal sweet-spot baseline) |
| **Run 4** | 1.2 | 40 | 0.5 | 472 | 8.5/10 | High Temp / Constrained Nucleus (punchy, no hallucinations) |
| **Run 5** | 0.9 | 10 | 0.95 | 420 | 7.5/10 | High Nucleus / Constrained Top-K (severe vocabulary strangulation) |
| **Run 6** | 1.4 | 100 | 0.98 | 585 | 5.5/10 | High entropy exploration (semantic drift, hyperbolic analogies) |
| **Run 7** | 1.9 | 200+ | 1.0 | 395 | 1.5/10 | Degeneration stress test (phonetic looping, pseudo-science salad) |

---

## 3. Empirical Analysis
See full empirical analysis, mathematical softmax proofs, and failure boundary breakdowns in [SUBMISSION.md](SUBMISSION.md).

---

## 4. Production Sweet Spot
* **Recommended Vector:** `Temp = 0.65 - 0.70`, `Top-K = 40`, `Top-P = 0.90`
* **Engineering Justification:** Optimal trade-off between semantic richness, empathetic tone, and strict constraint adherence, verified on Track 3: The Tech Incident Report.
