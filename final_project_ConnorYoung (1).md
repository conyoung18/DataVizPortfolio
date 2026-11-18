# Final Project — Part I: Storyboard and Data Plan
**Author:** Connor Young  
**Audience:** High school administrators and teachers

## 1. Project overview

Generative AI gives students a powerful way to solve practice problems and complete academic work, but does better performance with AI translate into better learning? This project examines that relationship through a high school mathematics experiment in Turkey. Students were assigned by classroom to one of three conditions: no AI, a standard GPT-based assistant, or a GPT-based tutor designed to provide hints rather than direct answers. They completed practice problems with their assigned resources and then took an independent assessment without those resources.

The story begins by highlighting AI's significant advantage during practice, then shows that the advantage does not carry over to independent assessments (exams). The conclusion will ask what schools should require before adopting educational AI. The intended audience is high school educators and administrators who make decisions about classroom technology. The goal is not to claim all AI is harmful; I want to persuade decision-makers to measure independent learning.

**Summary:** Better answers with AI do not necessarily mean better learning; schools should evaluate AI based on what students can do independently.

**Call to action:** Before scaling AI classroom tools, compare students' independent assessment performance with an appropriate no-AI benchmark. Do not treat higher assisted scores as sufficient evidence of learning.

## 2. Outline

### 1 — Layout of the experiment

The purpose is to help readers understand exactly what is being compared.

**Headline:** *Does access to AI actually help high school students learn?*

**Initial sketch:** A simple flow diagram featuring three parallel lanes:

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

### 2 — AI boosts practice performance

This section builds an expectation that AI is improving student results.

**Headline:** *AI-assisted students solve far more practice problems successfully.*

**Initial sketch:** A three-bar horizontal or vertical chart, with the no-AI group first and consistent colors for all scenes.

```text
              AVG. PRACTICE SCORE (non-honors)

No AI         ██████████████                       28.4%
Standard AI   ████████████████████████             47.4%
AI Tutor      █████████████████████████████████    66.9%
              0%                              80%
```

### 3 — What happens when AI disappears?

This section challenges the significance of an improvement in practice scores.

**Headline:** *The advantage disappears on the independent exam.*

**Initial sketch:** Use **the same axis, colors, and group order as Scene 2**, now displaying independent test scores. A scroll-triggered transition between the two charts would strengthen the reveal.

```text
           AVG. INDEPENDENT EXAM SCORE (non-honors)

No AI         ████████████████                     32.1%
Standard AI   ██████████████                       28.7%
AI Tutor      ████████████████                     31.5%
              0%                              80%
```

### 4 — Did students feel they learned?

The purpose of this section is to explore the gap between perceived learning and measured outcomes.

**Headline:** *Students' reported learning looks much more similar than their practice scores.*

**Initial sketch:** A three-bar chart reporting the share of valid respondents who answered “Quite a lot” or “A great deal” to the learning-perception question. Put a small annotation next to the chart reminding readers of the independent exam result.

```text
             REPORTED LEARNING: QUITE A LOT / A GREAT DEAL

No AI         ██████████████                        27.0%
Standard AI   █████████████                         25.1%
AI Tutor      ███████████████                       28.7%
              0%                               40%
```

### 5 — What is the benefit?

The purpose is to avoid the misleading conclusion that all AI has identical effects.

**Headline:** *Safeguards may prevent harm, but preventing harm is not the same as proving better learning.*

**Sketch / visual plan:** A coefficient/dot plot comparing the **published, adjusted** effects of each AI condition on the independent exam, relative to no AI. Use confidence intervals if their values are extracted carefully from the publication.

```text
        INDEPENDENT EXAM EFFECT VS. NO AI

Standard AI       ●  negative (reported: -17% relative)
AI Tutor          ●  no statistically significant effect
                  |  zero-effect reference line

          [Final graphic: dots + confidence intervals]
```

### 6 — What should schools measure?

This is the final synthesis and call to action.

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

## 3. Primary dataset and access

I will primarily use the `ai-learning.csv` dataset. It is available as an open CSV through the Carnegie Mellon University Statistics & Data Science Data Repository:

- **Download:** [ai-learning.csv](https://cmustatistics.github.io/data-repository/data/ai-learning.csv)
- **Data dictionary and study description:** [CMU repository page](https://cmustatistics.github.io/data-repository/technology/ai-learning.html)
- **Original research article:** [Bastani et al. (2025), *Generative AI without guardrails can harm learning*](https://pmc.ncbi.nlm.nih.gov/articles/PMC12232635/)

My working copy contains 3,255 student-session records, 943 unique students, 31 columns, and data from four study sessions. This is not a dataset of 3,255 independent students; students appear in repeated sessions. The experiment took place in Turkish high school mathematics classrooms in 2023. 

I will start with descriptive group averages in Tableau, using consistent y-axis scales and clear labeling. I will distinguish my descriptive calculations from the published paper's findings. If I have time, I would like to explore whether results differ across grade level or prior GPA. This will only be included if the comparisons are interpretable and reliable.

## 4. Method and medium

I plan to build the data visualizations in Tableau Public and embed them in Shorthand. The project will use a fixed color for each experimental group, minimal annotations, deliberate transitions, and consistent scales to create a guided reveal rather than a stand-alone dashboard. The first version will be designed for desktop and checked for readability on mobile.

My initial sketches above show the anticipated headers, diagrams, charts, transitions, and concluding message. In the final piece, interactive tooltips will define terms and show exact values, but the main findings will remain understandable without requiring the reader to interact.

## 6. References

**[1]** Sagasta Pereira, V. (2026). *Can generative AI harm student learning?* Carnegie Mellon University Statistics & Data Science Data Repository. Dataset and documentation. https://cmustatistics.github.io/data-repository/technology/ai-learning.html

**[2]** Bastani, H., Bastani, O., Sungu, A., Ge, H., Kabakcı, Ö., & Mariman, R. (2025). *Generative AI without guardrails can harm learning: Evidence from high school mathematics.* Proceedings of the National Academy of Sciences, 122(26), e2422633122. https://doi.org/10.1073/pnas.2422633122
