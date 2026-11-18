| [home page](https://conyoung18.github.io/tswd-portfolio-templates/) | [data viz examples](dataviz-examples) | [critique by design](critique-by-design) | [final project I](final-project-part-one) | [final project II](final-project-part-two) | [final project III](final-project-part-three) |

# Final Project — Part I: The Illusion of Learning

**Author:** Connor Young  
**Audience:** High school administrators and teachers

# Outline

## Project overview

Generative AI gives students a powerful way to solve practice problems and complete academic work, but does better performance with AI translate into better learning? This project examines that relationship through a high school mathematics experiment in Turkey. Students were assigned by classroom to one of three conditions: no AI, a standard GPT-based assistant, or a GPT-based tutor designed to provide hints rather than direct answers. They completed practice problems with their assigned resources and then took an independent assessment without those resources.

The story begins by highlighting AI's significant advantage during practice, then shows that the advantage does not carry over to independent assessments (exams). The conclusion will ask what schools should require before adopting educational AI. The intended audience is high school educators and administrators who make decisions about classroom technology. The goal is not to claim all AI is harmful; I want to persuade decision-makers to measure independent learning.

**One-sentence summary:** Better answers with AI do not necessarily mean better learning; schools should evaluate what students can do independently.

**Call to action:** Before scaling classroom AI tools, compare independent assessment outcomes against an appropriate no-AI benchmark. Higher assisted scores alone are not sufficient evidence of learning.

## Story structure

The presentation follows a six-scene narrative arc, moving from an apparently promising result to a surprising contrast and, finally, a decision rule for schools. The sketches below are preliminary layouts; exact formatting and interactions may change.

1. **The experiment — “Does access to AI actually help students learn?”** Introduce the no-AI, standard-AI, and safeguarded-AI-tutor groups and show the sequence from practice to an independent assessment. **Evidence:** experiment design in Bastani et al. [[2]](#references), treatment fields in `ai-learning.csv` [[1]](#references).
2. **The promise — “AI-assisted students solve far more practice problems successfully.”** Show average practice scores: 28.4% (no AI), 47.4% (standard AI), and 66.9% (AI tutor). **Evidence:** descriptive, non-honors averages calculated from `Part2Tot`, `Treatment arm`, and `Honors` in `ai-learning.csv` [[1]](#references).
3. **The reveal — “The advantage disappears on the independent exam.”** Reuse the previous chart's visual design, changing only the outcome measure. Independent averages: 32.1% (no AI), 28.7% (standard AI), and 31.5% (AI tutor). **Evidence:** descriptive, non-honors averages from `Part3Tot`, `Treatment arm`, and `Honors` in the CSV [[1]](#references). These are **unadjusted** results, not published experimental estimates.
4. **The question — “Did students feel they learned?”** Examine the percentage answering “Quite a lot” or “A great deal” to the learning survey: approximately 27.0% (no AI), 25.1% (standard AI), and 28.7% (AI tutor). **Evidence:** `Survey Q1`, `Treatment arm`, and `Honors` in the CSV [[1]](#references); results require excluding missing/invalid responses and standardizing text categories. This visual will not claim that students were deceived or overconfident.
5. **The distinction — “Avoiding harm isn't the same as demonstrating better learning.”** Compare published *adjusted* effects on the independent exam. The researchers report a roughly 17% **relative** decline for standard AI compared with no AI and no statistically significant learning gain for the safeguarded tutor. **Evidence:** Bastani et al. [[2]](#references), *not* a percentage calculated directly from the CSV. A final coefficient plot will use the reported model estimates and their uncertainty, if accurately extracted.
6. **The decision — “Better assignments ≠ better learning.”** Conclude with a split-screen comparison of assisted performance versus independent learning. **Evidence:** synthesis of the study's two outcomes (`Part2Tot`, `Part3Tot`) [[1]](#references) and the authors' analysis [[2]](#references). **Recommendation:** schools should evaluate AI using independent assessments against a meaningful comparison group.

## Initial sketches

These six images sketch the intended story, headlines, visual hierarchy, and transitions. **They are mockups, not final Tableau charts.** Scenes 2–4 use rounded descriptive values from the public CSV, and Scene 5 illustrates reported findings from the paper.

### Scene 1 — Three ways to learn

![Sketch 1: Flow diagram comparing the no-AI, standard-AI and safeguarded tutor groups before practice and independent assessment](images/01-experiment.png)

**Visual plan:** A three-lane experiment diagram introduces the treatment groups. **Source:** CSV treatment fields [[1]](#references) and original study design [[2]](#references).

### Scene 2 — AI boosts practice performance

![Sketch 2: Average practice scores for no AI, standard AI and AI tutor groups](images/02-practice.png)

**Visual plan:** Three horizontal bars for practice results, with a consistent 0–80% axis and a fixed color per group. **Source:** `Part2Tot`, `Treatment arm`, `Honors` [[1]](#references).

### Scene 3 — What happens when AI disappears?

![Sketch 3: Independent assessment scores for the same three groups](images/03-independent.png)

**Visual plan:** Repeat the previous chart's scale, colors, and order to make the difference immediately visible; consider a scroll-triggered transition in the final piece. **Source:** `Part3Tot`, `Treatment arm`, `Honors` [[1]](#references).

### Scene 4 — Did students feel they learned?

![Sketch 4: Proportion of students who report learning quite a lot or a great deal](images/04-perception.png)

**Visual plan:** Show the share reporting substantial learning, with a small note referring back to independent results. **Source:** `Survey Q1`, `Treatment arm`, `Honors` [[1]](#references).

### Scene 5 — What is the benefit?

![Sketch 5: Comparison of published adjusted standard AI and safeguarded tutor effects](images/05-adjusted-effects.png)

**Visual plan:** A coefficient/dot plot with a zero-effect reference line and confidence intervals, once the published estimates and intervals have been extracted. **Source:** Bastani et al. (2025) [[2]](#references). The “17% worse” statistic is an adjusted *relative* result, not a 17-percentage-point drop.

### Scene 6 — What should schools measure?

![Sketch 6: Split-screen conclusion distinguishing assisted performance and independent learning](images/06-recommendation.png)

**Visual plan:** End with a two-column decision graphic and a clear recommendation rather than another dashboard. **Source:** synthesis of the two outcome measures [[1]](#references) and published interpretation [[2]](#references).

# The data

My primary—and only planned chart-level dataset—is the public `ai-learning.csv` from the Carnegie Mellon University Statistics & Data Science Data Repository. The working copy has **3,255 student-session records, 943 unique students, and 31 variables**, covering four sessions. Because students appear more than once, these are *not* 3,255 independent student observations. The experiment took place in Turkish high school mathematics classrooms; CMU hosts a cleaned version of the data and was not the location of the experiment [[1]](#references), [[2]](#references).

I will build the main Tableau charts using `Part2Tot` for practice performance, `Part3Tot` for independent assessment performance, `Treatment arm` for experimental group, and `Honors` to restrict the main descriptive comparisons to non-honors records, consistent with the paper's primary analysis population. `Survey Q1` supports a separate perceived-learning visual. I will keep group colors, order, and chart scales consistent throughout. All CSV-based charts will be labeled descriptive averages; the published paper will be cited separately for adjusted effects and statistical significance. If time allows, I may explore grade level (`Year`) or prior GPA (`gpa_prev`), but only if those comparisons are interpretable and reliable.

| Name | URL | Description |
|------|-----|-------------|
| AI Learning Dataset (CSV) | [Download CSV](https://cmustatistics.github.io/data-repository/data/ai-learning.csv) | Student-session data used for all proposed Tableau charts. |
| CMU dataset documentation | [Data dictionary and description](https://cmustatistics.github.io/data-repository/technology/ai-learning.html) | Variable definitions, study overview, and data preparation notes. |
| Original peer-reviewed study | [Bastani et al. (2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC12232635/) | Experimental design, adjusted effects, uncertainty, and interpretation. |

# Method and medium

I plan to build the data visualizations in Tableau Public and embed them in Shorthand. The project will use a fixed color for each experimental group, minimal annotations, deliberate transitions, and consistent scales to create a guided reveal rather than a stand-alone dashboard. The first version will be designed for desktop and checked for readability on mobile.

My initial sketches above show the anticipated headers, diagrams, charts, transitions, and concluding message. In the final piece, interactive tooltips will define terms and show exact values, but the main findings will remain understandable without requiring the reader to interact.

## References

[1] Sagasta Pereira, V. (2026). *Can generative AI harm student learning?* Carnegie Mellon University Statistics & Data Science Data Repository. https://cmustatistics.github.io/data-repository/technology/ai-learning.html

[2] Bastani, H., Bastani, O., Sungu, A., Ge, H., Kabakcı, Ö., & Mariman, R. (2025). *Generative AI without guardrails can harm learning: Evidence from high school mathematics.* *Proceedings of the National Academy of Sciences, 122*(26), e2422633122. https://doi.org/10.1073/pnas.2422633122

## AI acknowledgements

I used ChatGPT to help organize my existing project outline into the course-provided Markdown template, draft and refine the storyboard descriptions, and generate preliminary visualization sketches from the publicly accessible dataset and study findings. I reviewed the proposed narrative, selected the central message and audience, and remain responsible for verifying the statistics, citations, and final Tableau analyses. AI-generated sketches are explicitly identified as conceptual designs rather than completed visualizations.
