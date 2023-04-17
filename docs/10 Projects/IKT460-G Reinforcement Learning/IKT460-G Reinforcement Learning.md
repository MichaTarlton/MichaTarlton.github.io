---
aliases: IKT460
type: [project, course]
project: phd-courses/IKT460-G
status: active
priority: p2
creationtag: 2023-01-25 11:53
infotags: [RL, UiA, course]
people: "Per-Arne Andersen"
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"IKT460-G")
GROUP BY type
SORT file.ctime asc 
```
# Questions
- [ ] Where are the pre approved subjects?
- [ ] Maybe I can set my prjectt to be about the same paper I’m reviewing in [[PENG9560 Topics in Artificial Intelligence and Machine Learning]]

# Quick Info
**When:** Tuesdays at 1:00
**Where:** [Zoom Meeting](https://uiano.zoom.us/j/64486888372?pwd=S3l1czlJZ1JhSTN4UWw0MmprNnJtdz09)
 - Meeting ID: 644 8688 8372  
- Password: 123456
**Info:**
[Reinforcement Learning - Universitetet i Agder](https://www.uia.no/studieplaner/topic/IKT460-G)

# [Updated notion site:](https://perara.notion.site/IKT460-Reinforcement-Learning-2023-944d295c2d1244d4a5bfd446942d21e7)
<iframe src="https://perara.notion.site/IKT460-Reinforcement-Learning-2023-944d295c2d1244d4a5bfd446942d21e7" allow="fullscreen" allowfullscreen="" style="height:100%;width:100%; aspect-ratio: 16 / 9; "></iframe>





# ToDos
```todoist
{
"name": "",
"filter": "(##IKT460-G Reinforcement Learning)",
"sorting": ["date"],
"group": true
}
```
## Project Overview 
TLDR: You are tasked to do practical or theoretical work in the study of reinforcement learning. 

When you're done, you will write an article in the standards of scientific writing. 

You should start writing the article early. Groups will peer-review each other's work before the final deadline. 

The peer review is graded and has a strict deadline, giving your peers time to improve their work based on the received feedback. 

**Step-by-step** 
1. Propose a project or select one of the pre-approved ones. Get your proposal accepted by your supervisor. 
2. Start project work along with drafting your article. You should include failed experiments as well as successful ones. 
3. Perform assigned peer review of other group’s draft article (See schedule) GRADED 
4. Improve your report based on feedback (See schedule) 5. Deliver the report before the deadline. GRADED

The project is a chance to explore RL in more depth. Novel research ideas are welcome but are not expected nor required to receive full credit. In addition, projects do not always work: in such cases, a careful illustration (using theoretical proofs and experimental results, plus a discussion) of why the proposed idea did not work and was substantially more work than anticipated is encouraged. If the reason is that not enough coding was done, this will not be considered a compelling reason. Projects can be done in groups of up to 2 students.


## Project Proposal

The project proposal should be about **200-400 words**, including the names of the project team members. The proposal should  also include a brief overview of the proposed project and project plan that includes the following:

- What is the problem that you will be investigating? Why is it interesting?
- If relevant, what data, simulator, or real-world RL domain will you be looking at? If you are collecting new datasets, how do you plan to collect them?
- What method, algorithm, or theoretical analysis are you proposing? If there are existing implementations, will you use them, and how? How do you plan to improve or modify such implementations? If you are addressing a theoretical question, how do you plan to make progress?
- What literature have you already surveyed or will be examining to provide context and background?
- How will you evaluate your results? Qualitatively, what kind of results do you expect (e.g. plots or figures)? Quantitatively, what kind of analysis will you use to evaluate and compare your results (e.g. what performance metrics or statistical tests)?

## Final Report
Your final report should be between 10-18 pages using the [Springer template](https://no.overleaf.com/latex/templates/springer-nature-latex-template/gsvvftmrppwq). This excludes the front page, references, and supplementary content. You should include a brief statement on the contributions of different members of the team in the report. Finally, as an appendix, you should include a 1.5-3 page peer-review of another student group's report/paper.

**Report.** The following is a suggested structure for the report:
-   Title, Author(s).
-   **Abstract:** It should not be more than 300 words.
-   **Introduction:** This section introduces your problem and the overall plan for approaching your problem.
-   **Background/Related Work:** This section discusses relevant literature for your project.
-   **Approach:** Algorithms used or developed.
-   **Theoretical results (if relevant):** Include assumptions and proof sketches.
-   **Experiment results (if relevant):** Details on experiments done. The goal is to describe in enough detail that the results are reproducible.
-   **Conclusion:** What have you learned? Suggest future ideas.
-   **References:** This is absolutely necessary. We recommend you use Mendeley or Zotero, or similar tools to organize references.
-   **Supplementary Material** is not counted towards your 6-8 page limit.

### Examples of things to put in your supplementary material:
-   Full proof details (if doing a project with theoretical results).
-   Cool videos, interactive visualizations, demos, etc. (optional)

### Examples of things to not put in your supplementary material:
-   All used submodules (Tensorflow, Theano, Caffe, CoreNLP) source code.
-   Any code that is larger than 1MB.
-   Model checkpoints.

# Course Lectures
## [[IKT460 Lecture 1]]
## [[IKT460 Lecture 2]]