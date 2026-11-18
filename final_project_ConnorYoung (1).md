# The Illusion of Learning
### Are AI-powered classrooms measuring better performance—or better learning?

**Final Project — Part I: Storyboard and Data Plan**  
**Author:** Connor Young  
**Audience:** High school administrators, teachers, and curriculum leaders  
**Primary data:** [AI Learning Experiment — CMU Statistics & Data Science Repository](https://cmustatistics.github.io/data-repository/technology/ai-learning.html)  

[← Back to Data Visualization Portfolio](index.md)

---

## 1. Project overview

Generative AI offers students a powerful way to solve practice problems and complete academic work. But does better performance *with* AI translate into better learning *without* it? This project examines that distinction through a randomized high school mathematics experiment in Turkey. Students were assigned by classroom to one of three conditions: no AI, a relatively standard GPT-based assistant, or a GPT-based tutor designed to provide hints rather than direct answers. They completed practice problems with their assigned resources and then took an independent assessment without those resources. [1][2]

The story begins by highlighting AI's striking advantage during practice, then reveals that the advantage does not carry over to independent assessments. It concludes by asking what schools should demand before adopting educational AI. The intended audience is high school educators and administrators who make decisions about classroom technology. The goal is **not** to claim all AI is harmful, but to persuade decision-makers to measure **independent learning**, not simply the quality of AI-assisted work.

**One-sentence message:** Better answers with AI do not necessarily mean better learning; schools should evaluate AI based on what students can do independently.

**Call to action:** Before scaling AI classroom tools, compare students' independent assessment performance with an appropriate no-AI benchmark. Consider safeguards and other benefits, but do not treat higher assisted scores as sufficient evidence of learning.

---

## 2. Story arc and visualization storyboard

The six scenes below are proposed visualizations, not final designs. Illustrative values are **descriptive averages calculated from `ai-learning.csv`**, unless explicitly labeled as findings from the published study. Scores use the 0–100 scale. For the primary descriptive views, exclude honors records (`Honors = 0`), consistent with the researchers' main analysis. [1][2]

### Scene 1 — The experiment: Three ways to learn

**Narrative role:** Setup; help readers understand exactly what is being compared.

**Headline:** *Does access to AI actually help high school students learn?*

**Sketch / visual plan:** A simple flow diagram featuring three parallel lanes:

```text
                  HIGH SCHOOL MATH EXPERIMENT

    ┌───────────────┐ ┌────────────────┐ ┌────────────────┐
    │ NO AI         │ │ STANDARD AI    │ │ AI TUTOR       │
    │ Books & notes │ │ GPT Base       │ │ GPT Tutor      │
    └───────┬───────┘ └────────┬───────┘ └────────┬───────┘
            │                  │                  │
            └──────────────────┼──────────────────┘
                               ▼
             PRACTICE PROBLEMS (assigned resources)
                               ▼
                INDEPENDENT EXAM (no resources)
```

**Claim supported:** The experiment compares three learning conditions and measures both resource-assisted practice and resource-free assessment. Classroom assignments remained in place across four sessions.

**Evidence:** `ai-learning.csv`: `Treatment arm`, `Student ID`, `Class`, `Session`; experimental design and testing conditions described in [1] and [2].

**Planned interaction:** Hover over each experimental group for its definition; optionally display how many distinct students/records appear in each group.

### Scene 2 — The promise: AI boosts practice performance

**Narrative role:** Build an expectation that AI is improving student results.

**Headline:** *AI-assisted students solve far more practice problems successfully.*

**Sketch / visual plan:** A three-bar horizontal or vertical chart, with the no-AI group first and consistent colors for all scenes.

```text
              AVG. PRACTICE SCORE (non-honors)

No AI         ██████████████                       28.4%
Standard AI   ████████████████████████             47.4%
AI Tutor      █████████████████████████████████    66.9%
              0%                              80%
```

**Claim supported:** In the uploaded data, average practice scores are substantially higher in both AI conditions than in the control condition.

**Evidence:** `ai-learning.csv`: mean `Part2Tot` by `Treatment arm`, filtered to `Honors = 0`. Values calculated from 2,899 non-honors student-session records: control **28.4%**, standard AI (`vanilla`) **47.4%**, AI Tutor (`augmented`) **66.9%**. [1]

**Tableau approach:** `Treatment arm` on Columns, `AVG(Part2Tot)` on Rows; format scores as percentages. Add a filter for `Honors = 0`.

**Transition:** *But solving problems with assistance is not the same as being able to solve them alone.*

### Scene 3 — The reveal: What happens when AI disappears?

**Narrative role:** Climax; challenge the meaning of the practice-score improvement.

**Headline:** *The advantage disappears on the independent exam.*

**Sketch / visual plan:** Use **the same axis, colors, and group order as Scene 2**, now displaying independent test scores. A scroll-triggered transition between the two charts would strengthen the reveal.

```text
           AVG. INDEPENDENT EXAM SCORE (non-honors)

No AI         ████████████████                     32.1%
Standard AI   ██████████████                       28.7%
AI Tutor      ████████████████                     31.5%
              0%                              80%
```

**Claim supported:** The large practice advantage does not appear in the unassisted exam means. Students assigned standard AI have a lower mean independent score than those assigned no AI.

**Evidence:** `ai-learning.csv`: mean `Part3Tot` by `Treatment arm`, `Honors = 0`. Values: control **32.1%**, standard AI **28.7%**, AI Tutor **31.5%**. [1] The published paper reports a **17% relative reduction** for standard AI on the independent exam under its adjusted analysis; that is **not** the same as the unadjusted 3.4-percentage-point difference in this chart. [2]

**Tableau approach:** Duplicate Scene 2, replace `AVG(Part2Tot)` with `AVG(Part3Tot)`, keep the same 0–80% scale.

**Interpretation guardrail:** Practice and exam questions are different assessments. Do **not** calculate “learning lost” by subtracting practice scores from exam scores. Compare treatment groups *within* each assessment.

### Scene 4 — The perception question: Did students feel they learned?

**Narrative role:** Explore the gap between perceived learning and measured outcomes without assuming students were fooled.

**Headline:** *Students' reported learning looks much more similar than their practice scores.*

**Sketch / visual plan:** A three-bar chart reporting the share of valid respondents who answered “Quite a lot” or “A great deal” to the learning-perception question. Put a small annotation next to the chart reminding readers of the independent exam result.

```text
             REPORTED LEARNING: QUITE A LOT / A GREAT DEAL

No AI         ██████████████                        27.0%
Standard AI   █████████████                         25.1%
AI Tutor      ███████████████                       28.7%
              0%                               40%
```

**Claim supported:** The share reporting substantial learning is relatively similar among the three groups. These data do **not** show that AI students felt they learned more.

**Evidence:** `ai-learning.csv`: `Survey Q1`, `Treatment arm`, `Honors`; source question and coding described in [1]. Filter `Honors = 0`, drop missing and dash-only responses, standardize capitalization, and count “quite a lot” or “a great deal” among valid survey responses. Calculated rates: control **27.0%** (n=995), standard AI **25.1%** (n=757), AI Tutor **28.7%** (n=899). [1]

**Tableau approach:** Create a calculated field identifying valid answers and a second binary field for substantial learning. Chart the average of that indicator by treatment, restricting to valid responses. Clearly label this as **self-report**, not a knowledge test.

**Transition:** *If practice success doesn't guarantee independent performance, does the design of the AI tool change the result?*

### Scene 5 — The nuance: Tool design matters, but what is the benefit?

**Narrative role:** Resolution; avoid the misleading conclusion that all AI has identical effects.

**Headline:** *Safeguards may prevent harm, but preventing harm is not the same as proving better learning.*

**Sketch / visual plan:** A coefficient/dot plot comparing the **published, adjusted** effects of each AI condition on the independent exam, relative to no AI. Use confidence intervals if their values are extracted carefully from the publication.

```text
        INDEPENDENT EXAM EFFECT VS. NO AI

Standard AI       ●  negative (reported: -17% relative)
AI Tutor          ●  no statistically significant effect
                  |  zero-effect reference line

          [Final graphic: dots + confidence intervals]
```

**Claim supported:** The published study found a significant negative effect of GPT Base on independent performance, while the GPT Tutor condition did not show a statistically significant change from the control condition. This makes the tutor a promising *safeguard*, not proof of increased learning. [2]

**Evidence:** Bastani et al. (2025), adjusted experimental results and interpretation. [2] The CSV supports the direction of descriptive differences but should not be used to present published regression estimates as if they were simple Tableau means.

**Tableau approach:** Optionally create a small, manually sourced table of published effect estimates and confidence intervals, clearly labeling it “Published adjusted estimates.” **Do not invent confidence intervals or treat a nonsignificant finding as proof of exactly zero effect.**

### Scene 6 — The decision: What should schools measure?

**Narrative role:** Final synthesis and call to action.

**Headline:** *Better assignments ≠ better learning.*

**Sketch / visual plan:** Split-screen conclusion with two measures and a final recommendation.

```text
 ┌──────────────────────────┐   ┌────────────────────────────┐
 │ ASSISTED PERFORMANCE     │   │ INDEPENDENT LEARNING       │
 │ How good is the work     │   │ What can the student do    │
 │ produced with AI?        │   │ without the tool?          │
 └──────────────────────────┘   └────────────────────────────┘

      RECOMMENDATION: Judge educational AI on independent
      learning outcomes, not only assisted assignment scores.
```

**Claim supported:** These two measurements can tell sharply different stories in the same experiment. An increase in assisted practice performance is insufficient by itself to establish improved learning. [1][2]

**Evidence:** The paired, treatment-group comparisons in Scenes 2 and 3, interpreted alongside the research findings in [2]. The policy recommendation is **my synthesis**, not a directly tested school policy.

---

## 3. Primary dataset and access

I will primarily use **one dataset**, `ai-learning.csv`, available as an open CSV through the Carnegie Mellon University Statistics & Data Science Data Repository:

- **Download:** [ai-learning.csv](https://cmustatistics.github.io/data-repository/data/ai-learning.csv)
- **Data dictionary and study description:** [CMU repository page](https://cmustatistics.github.io/data-repository/technology/ai-learning.html)
- **Original research article:** [Bastani et al. (2025), *Generative AI without guardrails can harm learning*](https://pmc.ncbi.nlm.nih.gov/articles/PMC12232635/)

My working copy contains **3,255 student-session records**, **943 unique students**, **31 columns**, and data from four study sessions. This is *not* a dataset of 3,255 independent students; students appear in repeated sessions. The experiment took place in Turkish high school mathematics classrooms in 2023. [1][2]

**Relevant fields:**

| Field in CSV | Intended use |
|---|---|
| `Treatment arm` | Compare `control`, `vanilla` (GPT Base), and `augmented` (GPT Tutor) |
| `Part2Tot` | Practice score (0–1 scale) |
| `Part3Tot` | Independent exam score (0–1 scale) |
| `Survey Q1` | Student's perceived learning in the session |
| `Honors` | Exclude honors classes from main descriptive charts (`0` only) |
| `Student ID` | Count unique students, recognize repeated observations |
| `Class`, `Session`, `Year` | Explore classroom/session/grade structure |

**Analysis plan:** I will start with descriptive group averages in Tableau, using consistent y-axis scales and clear labeling. I will distinguish **my descriptive calculations** from the published paper's **adjusted experimental findings**. Repeated records, classroom-level treatment assignment, and differences between the practice and exam tasks mean that raw bar charts alone cannot establish statistical significance or precisely replicate the study's causal estimates. [1][2]

**Potential extension if time allows:** Explore whether results differ across grade level or prior GPA. This is secondary and will only be included if the comparisons are interpretable and reliable.

---

## 4. Method and medium

I plan to build the data visualizations in **Tableau Public** and embed them in a **scrolling narrative on my GitHub Pages portfolio**. The project will use a fixed color for each experimental group, minimal annotations, deliberate transitions, and consistent scales to create a guided reveal rather than a stand-alone dashboard. The first version will be designed for desktop and checked for readability on mobile.

My initial sketches above show the anticipated headers, diagrams, charts, transitions, and concluding message. In the final piece, interactive tooltips will define terms and show exact values, but the main findings will remain understandable without requiring the reader to interact.

---

## 5. Caveats and responsible communication

- **Scope:** This study examines mathematics in one high-school setting in Turkey, not all subjects or all students worldwide. [2]
- **Repeated observations:** The CSV contains multiple sessions per student; observations are not independent.
- **Different tests:** Assisted practice and independent assessments measure performance on different questions. Their absolute averages should not be treated as a before/after learning change. [1]
- **Statistical results:** The paper's adjusted 17% relative effect cannot be recreated by simply subtracting average exam percentages from the CSV. [2]
- **AI tutor:** A statistically nonsignificant independent exam effect does not prove no effect, and this experiment does not evaluate a general school-wide AI literacy curriculum. [2]
- **Conclusion:** The proposed evaluation standard is a recommendation inferred from these findings, not an intervention tested by this dataset.

---

## 6. References

**[1]** Sagasta Pereira, V. (2026). *Can generative AI harm student learning?* Carnegie Mellon University Statistics & Data Science Data Repository. Dataset and documentation. https://cmustatistics.github.io/data-repository/technology/ai-learning.html

**[2]** Bastani, H., Bastani, O., Sungu, A., Ge, H., Kabakcı, Ö., & Mariman, R. (2025). *Generative AI without guardrails can harm learning: Evidence from high school mathematics.* Proceedings of the National Academy of Sciences, 122(26), e2422633122. https://doi.org/10.1073/pnas.2422633122

**Data visualization attribution:** Original visualization designs and descriptive calculations using the publicly available dataset above. Any published adjusted effect estimates will be attributed to Bastani et al. and clearly distinguished from original descriptive charts.

---

[← Back to Data Visualization Portfolio](index.md)
