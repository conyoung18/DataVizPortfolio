# The Illusion of Learning: Is AI Helping Students Learn—or Just Helping Them Finish?

**Final Project — Part I | Telling Stories with Data**  
**Author:** Connor Young  
**Status:** Project proposal and initial storyboard (November 2026)

**Navigation:** [Portfolio home](https://conyoung18.github.io/DataVizPortfolio/) · [Project outline](#project-outline) · [Initial sketches](#initial-sketches) · [The data](#the-data) · [Method and medium](#method-and-medium) · [Sources](#sources)

## High-level project summary

Generative AI has quickly become part of how teenagers do schoolwork. It can explain difficult concepts, help solve problems, and produce polished answers in seconds. However, a completed assignment is not necessarily evidence of learning. My project investigates whether AI-assisted performance translates into the independent understanding that education is intended to develop. Rather than arguing that all AI use is harmful, I want to distinguish between uses that *replace* students' thinking and uses that *support* it. The story will focus on secondary education, with high school students as its primary population, and mathematics as the setting for the strongest experimental evidence.

The project is intended for **high school teachers, principals, and curriculum leaders** who are developing policies and classroom practices for AI. I will use a U.S. teen survey to establish that AI use is common, a published randomized classroom experiment to reveal the difference between AI-assisted and independent performance, and emerging intervention studies to examine what useful AI literacy education might involve. The intended conclusion is practical: schools should move beyond simple permission or prohibition and teach students to verify AI responses, ask for guidance instead of final answers, and demonstrate understanding without AI. I will acknowledge that findings from different countries, grades, and research designs cannot establish one universally effective curriculum.

**One-sentence story:** AI can help students finish schoolwork without necessarily helping them learn; educators should teach and assess AI use in ways that preserve critical thinking and independent understanding.

**Intended audience:** High school educators and school administrators. Secondary: parents and high school students.

**Desired audience action:** Pilot a short, interactive AI-literacy unit with practice in verification, guided questioning, and independent checks; evaluate the pilot before expanding it.

## Project outline

I plan a **guided, three-act scrolling narrative plus a brief actionable conclusion**, not a standalone dashboard. Each section should create a reason to read the next.

### Act I — The new homework assistant (setup)

**Question:** How much has AI entered students' schoolwork?  
**Message:** AI use is already widespread, while many students say they have not received guidance about safe use.  
**Evidence:** Common Sense Media's 2026 survey of U.S. teenagers: 70% report AI use for schoolwork; 27% report a teacher ever discussing safe use.  
**Visualization:** A large headline figure transitioning to a few clearly labeled horizontal bars (with denominators specified).  
**Transition:** If AI makes schoolwork easier, is it also making students better learners?

### Act II — The illusion of learning (conflict / reveal)

**Question:** What happens when students must work without AI?  
**Message:** An AI tool may boost performance while it is available without improving performance when it is removed.  
**Evidence:** Bastani et al.'s 2025 randomized study of Turkish high-school mathematics classrooms. Students used regular resources, GPT Base, or a more guided GPT Tutor. Published results report a 48% practice-performance improvement with GPT Base and a 17% reduction on subsequent unassisted performance relative to controls. These percentages refer to different outcomes, not a before/after decline for the same measure.  
**Visualization:** A two-stage reveal of treatment-group performance—practice with available resources versus a subsequent independent exam—followed by a three-group comparison showing the safeguarded tutoring arm.  
**Original analytical angle:** Investigate results by prior GPA and, if the survey questions are correctly documented, perceived versus actual learning. These are hypotheses to test, not findings to assume.  
**Transition:** If unrestricted AI use can undermine independent learning, could the right instruction or safeguards reduce this risk?

### Act III — Teaching judgment, not just AI facts (resolution)

**Question:** What kinds of AI-literacy approaches show promise—and which may fall short?  
**Evidence A:** A small randomized Estonian grade-12 experiment (n=36) found that a brief text-based lesson did **not significantly reduce** acceptance of incorrect AI advice and increased rejection of correct advice (19.1% control versus 36.8% intervention).  
**Evidence B:** A French quasi-experimental study of 116 grade-8/9 students found that a two-hour interactive workshop was associated with greater use of follow-up questions (59.2% trained versus 27.9% control) and modestly stronger science task scores.  
**Visualization:** Two small, separately titled comparisons: the limitations of passive informational training; and changes in critical interaction behavior after hands-on training. **Do not treat the two studies as a head-to-head randomized comparison.**  
**Transition:** What should schools try, and what evidence would tell them it works?

### Closing — AI should support thinking, not replace it (call to action)

**Recommendation:** Pilot a practical AI-literacy approach with three parts: (1) **verify** AI answers against evidence, (2) **question** AI by requesting reasoning, hints, and feedback instead of finished work, and (3) **demonstrate** learning on short tasks without AI. The combined three-part workshop is **my proposed synthesis**, not a curriculum already established as effective by a single experiment.

**How to judge success:** Compare student performance on independent tasks before and after the pilot, with a comparison group where feasible; record how well students distinguish correct from incorrect AI advice and whether they genuinely use follow-up questions. Track implementation and avoid claiming causality without an appropriate design.

**Closing line:** *Getting the answer is not the same as learning how to find it.*

## Initial sketches

The following annotated digital sketches show the intended layout and narrative sequence. They are **storyboards, not final data visualizations**; the finished Tableau charts may differ after data cleaning and analysis.

### Sketch 1 — Opening and adoption

![Storyboard sketch of AI adoption](sketches/act-1.svg)

**Purpose:** Capture attention with a single meaningful figure and immediately introduce the question of learning versus task completion. Source: Common Sense Media (2026).

### Sketch 2 — The central reveal

![Storyboard sketch of AI performance paradox](sketches/act-2.svg)

**Purpose:** Use a staged reveal to contrast assisted practice with an independent test. The two published effect estimates are relative to controls in separate assessment conditions. Final design should add the GPT Tutor group and use cleaned data rather than presenting those two percentages as a direct before/after difference.

### Sketch 3 — Evidence about instruction

![Storyboard sketch of intervention workshop](sketches/act-3.svg)

**Purpose:** Show the concrete behavior that training may change—students asking follow-up questions—rather than relying on vague satisfaction ratings. Source: French classroom study (2026). This is an association within a quasi-experiment, not definitive evidence of long-term learning gains.

### Sketch 4 — Recommended classroom actions

![Storyboard sketch of recommended classroom actions](sketches/act-4.svg)

**Purpose:** End with a memorable and actionable framework—verify, question, demonstrate—and define what schools should measure after a pilot. This is an evidence-informed proposal, not an evaluated combined curriculum.

## The data

The **primary dataset** is the anonymized data associated with Bastani et al. (2025), *Generative AI without guardrails can harm learning: Evidence from high school mathematics*. The original research team provides its data and code in a [public GitHub repository](https://github.com/obastani/GenAICanHarmLearning), with a data dictionary identifying `Part2Tot` (practice score), `Part3Tot` (independent exam score), `GPTBase`, `GPTTutor`, `Treatment_arm`, `gpa_prev`, student and classroom identifiers, and session. The [Carnegie Mellon Statistics & Data Science repository](https://cmustatistics.github.io/data-repository/technology/ai-learning.html) also hosts a documented `ai-learning.csv`. I plan to compare the three experimental groups and examine whether performance patterns vary across prior academic achievement. As students can appear in multiple sessions, and the original study excludes honors classrooms for its main analysis, I will account for repeated observations and clearly distinguish descriptive Tableau group averages from the authors' adjusted causal estimates. I will not automatically compare raw practice and test score levels if assessments use different scales or difficulties.

To establish the real-world context, I will use [Common Sense Media's *Teens in the AI Era* (2026)](https://about.commonsensemedia.org/research/reports/teens-ai-era-schoolwork-and-skills-matter). Its published national survey figures document how often teens use AI for schoolwork and how often teachers discuss safe AI use. These published percentages will be entered in a small, clearly labeled summary CSV—not misrepresented as respondent-level microdata. For the final section, I will use published results from an [Estonian AI-literacy intervention](https://arxiv.org/abs/2503.10556) and a [French interactive workshop](https://arxiv.org/abs/2604.01955). The studies involve different student ages, locations, activities, and designs; they will be displayed as **separate** examples of intervention evidence, not pooled into an overall effectiveness estimate. A source-labeled CSV of the relevant published numbers is included in this project package: [published_summary_statistics.csv](data/published_summary_statistics.csv).

**Data access status (important for Part I):** The public research repositories, data dictionary, and summary statistics have been verified, and the summary-statistics CSV is included here. The student-level `ai-learning.csv` **has not yet been downloaded into this project package** because retrieval failed from this working environment. I must download and open that file from the [CMU CSV link](https://cmustatistics.github.io/data-repository/data/ai-learning.csv), or the authors' repository, and upload the working copy before claiming the data collection requirement is fully complete. The intervention studies' individual-level records have not been verified as publicly available; all intervention comparisons will use published aggregate numbers.

**Data dictionary / source notes:** [PNAS authors' GitHub repository](https://github.com/obastani/GenAICanHarmLearning); [CMU data documentation](https://cmustatistics.github.io/data-repository/technology/ai-learning.html); [Common Sense Media report](https://about.commonsensemedia.org/research/reports/teens-ai-era-schoolwork-and-skills-matter). My locally curated summary CSV provides source URLs and population/denominator notes on every row.

## Method and medium

I plan to create an interactive, stand-alone **scrolling data story hosted on GitHub Pages**, with **Tableau Public** for the main charts and responsive HTML/CSS for narrative pacing, annotation, and transitions. This allows the reader to follow a specific argument in sequence instead of exploring an unstructured dashboard. I will use Tableau to clean and analyze the primary experimental dataset, create group comparisons, and introduce optional filters or annotations only where they advance the narrative. The final site will include accessible chart labels, descriptions of data limitations, responsive layouts, and links to the underlying research. I will avoid copyrighted stock photography and use original storyboards and charts or images with appropriate usage rights and attribution.

## Sources

1. Bastani, H., Bastani, O., Sungu, A., Ge, H., Kabakcı, Ö., & Mariman, R. (2025). *Generative AI without guardrails can harm learning: Evidence from high school mathematics*. *Proceedings of the National Academy of Sciences*, 122(26), e2422633122. https://doi.org/10.1073/pnas.2422633122
2. Carnegie Mellon University, Department of Statistics & Data Science. (2026). *Can generative AI harm student learning?* https://cmustatistics.github.io/data-repository/technology/ai-learning.html
3. Common Sense Media. (2026, August 18). *Teens in the AI era: Schoolwork and skills that matter*. https://about.commonsensemedia.org/research/reports/teens-ai-era-schoolwork-and-skills-matter
4. Puppart, B., & Aru, J. *A brief AI literacy intervention does not significantly reduce over-reliance and increases under-reliance on ChatGPT: A randomized study*. arXiv:2503.10556. https://arxiv.org/abs/2503.10556
5. *Teaching students to question the machine: An AI literacy intervention improves students' regulation of LLM use in a science task*. arXiv:2604.01955. https://arxiv.org/abs/2604.01955

---

*Planning note: These claims and visualizations will be updated after inspecting the source CSV, confirming variable encodings, and checking how each reported statistic is defined. The completed project will separate experimental evidence of effects on independent performance from observational survey evidence about adoption and opinions.*
