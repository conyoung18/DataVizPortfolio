| [home page](https://conyoung18.github.io/tswd-portfolio-templates/) | [data viz examples](dataviz-examples) | [critique by design](critique-by-design) | [final project I](final-project-part-one) | [final project II](final-project-part-two) | [final project III](final-project-part-three) |

# Final Project — Part I: The Illusion of Learning

**Author:** Connor Young  
**Audience:** High school administrators and teachers

# Outline

## Project overview

Generative AI gives students a powerful way to solve practice problems and complete academic work, but does better performance with AI translate into better learning? This project examines that relationship through a high school mathematics experiment in Turkey. Students were assigned by classroom to one of three conditions: no AI, a standard GPT-based assistant, or a GPT-based tutor designed to provide hints rather than direct answers. They completed practice problems with their assigned resources and then took an independent assessment without those resources.

The story begins by highlighting AI's significant advantage during practice, then shows that the advantage does not carry over to independent assessments (exams). The conclusion will ask what schools should require before adopting educational AI. The intended audience is high school educators and administrators who make decisions about classroom technology. The goal is not to claim all AI is harmful; I want to persuade decision-makers to measure independent learning.

**One-sentence summary:** Better answers with AI do not necessarily mean better learning; schools should evaluate what students can do independently.

**Call to action:** Before scaling AI classroom tools, compare students' independent assessment performance with an appropriate no-AI benchmark. Do not treat higher assisted scores as sufficient evidence of learning.

## Story structure

The presentation follows a narrative arc from an apparently promising result to a surprising contrast and, finally, a decision rule for schools. The sketches below are just layouts. The exact formatting and interactions may change.

1. **“Does access to AI actually help students learn?”** Introduce the no-AI, standard-AI, and safeguarded-AI-tutor groups and show the sequence from practice to an independent assessment.
2. **“AI-assisted students solve far more practice problems successfully.”** Show average practice scores: 28.4% (no AI), 47.4% (standard AI), and 66.9% (AI tutor) and compare it to how they perform on the independent exam. Independent averages: 32.1% (no AI), 28.7% (standard AI), and 31.5% (AI tutor)
3. **“Did students feel they learned?”** Examine the percentage answering “Quite a lot” or “A great deal” to the learning survey: approximately 27.0% (no AI), 25.1% (standard AI), and 28.7% (AI tutor).
4. **“Avoiding harm isn't the same as demonstrating better learning.”** Compare published adjusted effects on the independent exam. The researchers report a roughly 17% relative decline for standard AI compared with no AI and no statistically significant learning gain for the safeguarded tutor.
5. **“Better assignments ≠ better learning.”** Conclude with a split-screen comparison of assisted performance versus independent learning. **Recommendation:** schools should evaluate AI using independent assessments against a meaningful comparison group.

## Initial sketches

These images sketch the intended story, headlines, visual hierarchy, and transitions. They are mockups, not final Tableau charts.

### Sketch 1

<img width="2332" height="1561" alt="IMG_3911" src="https://github.com/user-attachments/assets/a062fee7-c0a6-4acf-af14-7c815fc52060" />

**Source:** CSV treatment fields [[1]](#references) and original study design [[2]](#references).

### Sketch 2

<img width="2468" height="858" alt="IMG_3913" src="https://github.com/user-attachments/assets/8543c532-95b5-4eb8-a3eb-3ba8849bb21b" />

**Source:** `Part2Tot`, `Treatment arm`, `Honors` [[1]](#references).

### Sketch 3

<img width="2194" height="949" alt="IMG_3914" src="https://github.com/user-attachments/assets/1e16ef00-859c-4699-9fb4-c2b29666b06d" />

**Source:** `Part3Tot`, `Treatment arm`, `Honors` [[1]](#references).

### Sketch 4

<img width="2523" height="1858" alt="IMG_3915" src="https://github.com/user-attachments/assets/561ac383-0089-4aa5-baae-06856a27b939" />

**Source:** `Part3Tot`, `Treatment arm`, `Honors` [[1]](#references).

### Sketch 5

<img width="2340" height="1178" alt="IMG_3916" src="https://github.com/user-attachments/assets/fc59ae99-2d0f-4841-8d0b-348d92f49ac3" />

**Source:** `Survey Q1`, `Treatment arm`, `Honors` [[1]](#references).

### Sketch 6

<img width="2894" height="871" alt="IMG_3917" src="https://github.com/user-attachments/assets/fd70d159-4f80-4753-b2ce-cd40e290a525" />

**Source:** Bastani et al. (2025) [[2]](#references). The “17% worse” statistic is an adjusted *relative* result, not a 17-percentage-point drop.

# The data

My primary datasetis the public `ai-learning.csv` from the Carnegie Mellon University Statistics & Data Science Data Repository. The working copy has 3,255 student-session records, 943 unique students, and 31 variables, covering four sessions. Because students appear more than once, these are not 3,255 independent student observations. The experiment took place in Turkish high school mathematics classrooms; CMU hosts a cleaned version of the data and was not the location of the experiment [[1]](#references), [[2]](#references).

I will build the main Tableau charts using `Part2Tot` for practice performance, `Part3Tot` for independent assessment performance, `Treatment arm` for experimental group, and `Honors` to restrict the main descriptive comparisons to non-honors records. I will keep group colors, order, and chart scales consistent throughout. All CSV-based charts will be labeled descriptive averages, and the published paper will be cited separately for adjusted effects and statistical significance. If time allows, I may explore grade level (`Year`) or prior GPA (`gpa_prev`)..

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

I used ChatGPT to help organize my existing project outline into the course-provided Markdown template. I also used it to brainstorm ways I could describe the data in a more creative fashion. In addition, I used ChatGPT to help format my citations and convert them to markdown. I came up with the proposed narrative, selected the message and audience, and remain responsible for verifying the statistics, citations, and final Tableau analyses.
