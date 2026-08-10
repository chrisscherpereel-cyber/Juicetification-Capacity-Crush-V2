# 🧃 Juicetification: Capacity Crush

**An experiential, browser-based simulation for teaching the Theory of Constraints (TOC) and core operations-management concepts.**

Juicetification: Capacity Crush reimagines Goldratt's classic "dice game" as a juice-bottling
line. Students don't just *read* about bottlenecks, work-in-process, and yield — they run a line,
predict what will happen, watch it unfold, and then redesign it to hit a goal. The tool is built
around evidence-based learning mechanisms (prediction, elaborated feedback, self-explanation,
interleaving, and productive failure) so that the pedagogy is baked into the software rather than
left to facilitation.

![The simulation dashboard](figures/Figure1_Dashboard.png)

---

## Why it exists

Operations concepts are famously counterintuitive: a balanced line finishes *below* the average
capacity of its stations; adding capacity to a non-constraint does nothing; capping work-in-process
shortens lead time without costing output; and a *fast* station can be the real constraint if it
scraps most of what it makes. Told these results in a lecture, students often assimilate them to
prior (wrong) intuitions. Juicetification makes each result something the student **predicts, sees,
and then has to engineer** — which is where the idea actually lands.

---

## Features

- **Sandbox mode** — a full dashboard with every control: per-station dice (capacity), work-in-process
  caps, supply reliability, demand variability, scrap/yield, safety stock, and the line's economics
  (throughput, operating expense, inventory investment, EOQ). Multi-year replications show the *distribution*
  of outcomes, not just one run.
- **Guided Lab mode** — a sequenced set of laboratories that introduce one concept at a time:
  1. Operations — the Five Focusing Steps
  2. Little's Law
  3. Push vs. Pull
  4. Variability
  5. Quality & Yield
  6. Economics of the line
  7. Throughput Accounting
  8. EOQ Drivers
  9. EOQ Limits
  10. Safety Stock
  11. **Capstone — Diagnose & Fix** (an interleaved, unlabeled diagnostic challenge)
- **Predict → Run → Reveal** on every step (commit to a prediction before you see the answer).
- **Distractor-specific feedback** — each wrong answer gets a one-line explanation aimed at the exact
  misconception behind it.
- **Numeric-estimate steps** graded on a tolerance band with a number-line readout.
- **Open design challenges** with an automated pass/fail check and limited tries.
- **Self-explanation prompts** after the key reveals; the count is folded into a tamper-evident
  completion code.
- **Progress tracking & completion codes** — students generate a checksum-protected code; instructors
  decode it to see per-lab completion and how many explanations were written.

---

## Quick start

**Requirements:** Python 3.9+ and the packages in `requirements.txt` (Streamlit and pandas).

```bash
# 1. (optional) create a virtual environment
python -m venv .venv && source .venv/bin/activate      # Windows: .venv\Scripts\activate

# 2. install dependencies
pip install -r requirements.txt

# 3. run the app
streamlit run juicetification.py
```

Streamlit will open the simulation in your browser (usually at http://localhost:8501).

---

## Using it in a course

- **Students** work through the Guided Labs in order; the Capstone is best saved for last. See
  `instructions.pdf` for a one-page visual guide.
- **Progress is stored in the page URL**, so a student can bookmark or copy the link to resume.
  Work runs entirely in the browser session — no accounts, no server-side data.
- **To collect work**, have each student open **Your progress → Get my completion code** and submit
  the generated code. Instructors decode it inside the same panel (paste the code into the decoder)
  to see per-lab completion, overall percentage, and the number of self-explanations written.
- **Everything is instructor-controllable**: the lab sequence, the difficulty of each challenge, and
  the number of tries are all defined in `juicetification.py`.

---

## How the design maps to learning theory

The `paper/` folder contains the full manuscript describing the theoretical grounding and design
rationale, with figures. In brief, each guided step traverses Kolb's experiential learning cycle:

![Design features mapped to Kolb's cycle](figures/Figure8_Kolb_Cycle_Mapping.png)

Additional figures in `figures/` illustrate the guided step, distractor feedback, numeric estimation,
the design challenge, the capstone diagnosis, and the self-explanation prompt.

---

## Repository contents

```
Juicetification-Capacity-Crush/
├── juicetification.py     # the simulation (single-file Streamlit app)
├── instructions.pdf       # one-page visual student guide
├── requirements.txt
├── README.md
├── LICENSE
├── paper/                 # academic write-up (design rationale + theory)
│   └── Juicetification_Capacity_Crush_Paper.docx
└── figures/               # publication-quality figures (PNG + editable SVG)
```

---

## Citing / attribution

If you use or adapt this simulation, please cite the accompanying paper (see `paper/`).
Author: Christopher M. Scherpereel, W. A. Franke College of Business, Northern Arizona University.

---

## License

Released under the MIT License (see `LICENSE`). You are free to use and adapt it for teaching and
research; please confirm this license suits your institution's requirements before publishing.

---

*Version 1.0*
