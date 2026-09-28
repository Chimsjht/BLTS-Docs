# Manuscript Review: *Bugasong Legislative Tracking System* (BLTS)

**Capstone Project, BSIT, College of Computer Studies, University of Antique – Tario-Lim Memorial Campus (March 2025)**
Files reviewed: `part1.docx` (preliminary pages), `part2.docx` (Chapters 1–5 and References), `part3.docx` (Appendices A–M)

Review date: September 28, 2026

---

## 1. Overall verdict

| Area | Rating | Comment |
|---|---|---|
| Completeness of parts | **Good** | All standard parts are present: preliminary pages, Chapters 1–5, references and Appendices A–M. |
| Alignment (problems → objectives → method → results → conclusions) | **Fair** | The 5 problems match the 5 specific objectives one to one. The results only report an ISO 25010 survey, so objectives 4 (OCR) and 5 (sentiment analysis) are never measured directly. |
| Connection across the 3 files | **Fair** | Front matter lists, figure/table numbers and names do not match Chapters 1–5 and the appendices (see Section 3). |
| Conformity to research standards | **Needs revision** | Errors in the "Entire Group" statistics, a significance claim with no statistical test, citation and reference errors, a thin literature base for sentiment analysis, and no ethics or data-privacy statement. |

**Bottom line:** the study is a coherent, complete developmental capstone. The system was evaluated and accepted by the LGU, and its conclusions ("Very Satisfactory" in every characteristic) **still hold after correction**. Before it is turned over to the Extension Program, fix the **Critical** items in Section 2. The other items are editorial fixes.

---

## 2. Critical issues (fix before turnover)

### 2.1 The adviser is also listed as a researcher
**Jessie H. Tacuyan** appears as the 6th proponent on the Title Page, Panel's Approval Sheet and both recommendation sheets. The same name also signs as **Adviser**, and the Acknowledgement thanks "their adviser, Mr. Jessie H. Tacuyan." Appendix M has resumes for only the other five proponents.
**Fix:** remove the name from the list of proponents, unless the college's policy specifically allows it and that is intended. As written, it looks like a conflict of interest to anyone reading the turnover copy.

### 2.2 The "Entire Group" statistics are computed incorrectly (Tables 6–15; Appendix I)
Appendix I shows that each "Entire Group" mean is the **plain average of the three group means**, for example (4.67 + 4.88 + 4.86) / 3. The "Entire Group SD" is the **SD of those three means**. The groups are different sizes (15 / 8 / 7), so:

- The Entire Group mean should be **weighted by n** (or computed from all 30 individual responses). Some examples:

| Indicator | Reported | Correct (weighted, n = 30) |
|---|---|---|
| Functional completeness | 4.83 | **4.77** |
| Functional accurateness/correctness | 4.73 | **4.67** |
| Maturity | 4.64 | **4.57** |
| User error protection | 4.57 | **4.53** |
| Replaceability | 4.55 | **4.47** |
| Grand mean (Table 15) | 4.72 | **≈ 4.70** |

- The Entire Group **SD must describe the spread of the 30 responses**. Values such as 0.01–0.06 are the spread of three means, which makes the ratings look far more uniform than they are. Recompute the SD from all 30 responses.
- Appendix I divides by **n** for some groups (IT: √(3.6/15)) and by **n − 1** for others (SB: √(0.86/7)). Choose one formula (sample SD, n − 1, is conventional) and state it in *Statistical Treatment of Data*.

All interpretations stay "Very Satisfactory", so the conclusions stand, but the numbers should be corrected in Tables 6–15, the discussion text and Appendix I.

### 2.3 A "no significant difference" claim with no significance test
Chapter 3 (*Statistical Treatment*) says the scales determine whether the groups' perceptions "differed significantly." Chapter 4 concludes "there is **no significant difference** among the perception of the IT Experts, Sangguniang Bayan Staff, and people from the Community." Means alone cannot establish significance.
**Fix (choose one):**
- (a) Delete the significance claim and say that the three groups' ratings "were consistently within the Very Satisfactory range"; **or**
- (b) Run a **Kruskal–Wallis H test** (suited to ordinal Likert data and small, unequal groups) or a one-way ANOVA, and report the test statistic, df and p-value. Add the test to *Statistical Treatment of Data*.

### 2.4 Objectives 4 (OCR) and 5 (Sentiment Analysis) are not directly evaluated
The only evidence reported is the perception survey (ISO 25010). The two core technical features are never measured:
- **OCR:** no accuracy result such as character or word error rate on a sample of scanned ordinances. The OCR engine and library (e.g., Tesseract) are also never named.
- **Sentiment analysis:** the algorithm, library, lexicon or model is never named. The manuscript also does not say which languages it handles (English? Kinaray-a? Hiligaynon?) or how accurately it classifies posts (e.g., a confusion matrix on sample posts).

**Fix:** at minimum, add a short subsection to Chapter 3 (*Project Description* or *Development Process*) naming the OCR engine and the sentiment-analysis method. Ideally, also add a small accuracy test to Chapter 4. Otherwise, reword the Conclusion so it does not claim that the system "ensures that only appropriate content is shared." The study offers no evidence for that claim, and Scope and Limitations already admits the method has weaknesses (sarcasm, dialects).

### 2.5 No ethics or data-privacy statement
The study collected responses from 30 people and processes citizens' emails and forum posts, yet it never mentions **informed consent** or the **Data Privacy Act of 2012 (RA 10173)**.
**Fix:** add an *Ethical Considerations* paragraph to Chapter 3 covering consent, voluntary participation, confidentiality of responses and the system's handling of personal data.
**For turnover copies:** Appendix M (resumes) includes dates of birth, parents' names, home addresses and mobile numbers. Redact these in any copy that will be shared publicly or with outside offices.

---

## 3. Consistency between the three files

### 3.1 Part 1 (preliminary pages) vs Part 2 (Chapters)
| Item | Part 1 says | Part 2 / Part 3 actually has |
|---|---|---|
| List of Figures | 21 figures; Fig. 9 = Log-in Panel, Fig. 21 = List of Legislatives | **27 figures**. Fig. 9 = **Gantt Chart**, Figs. 10–27 = UI screens (Registration Form, Manage Documents, Add Resolution, Log History, etc. are missing from the list) |
| Fig. 3 caption | "Use Case Diagram" | "Use Case Diagram of Bugasong Legislative Tracking System" |
| Chapter 4 TOC entries | "User Interface" p. 43 | No "User Interface" heading exists in Chapter 4 |
| Chapter 2 TOC | No "Foreign Studies / Local Studies / Prior Arts" subheadings | Chapter 2 uses these subheadings |
| Chapter 3 TOC | "Data Gathering Instruments" | Heading reads "**Evaluation Instruments**" |
| Scope and Limitation | "Scope and Limitation" | "Scope and **Limitations**" |
| Preliminary pages | TOC lists "Instructor's Recommendation Sheet" | The page is titled "**ADVISER'S** RECOMMENDATION SHEET" a second time. Retitle it "Instructor's Recommendation Sheet" |
| Research Committee Contract | Listed in TOC (p. v) | Only a heading/image. Confirm the signed page is included |
| TOC formatting | Page numbers aligned with spaces | Use Word's automatic TOC with dot leaders, then **update fields** after all edits |

### 3.2 Table numbers cited wrongly in the text
- Chapter 3, *Evaluation Procedure*: "descriptive rating in **Table 4**" should be **Table 5** (Likert scale).
- Chapter 4: compatibility discussion says "**Table 8** shows…" → **Table 13**; Perception-as-a-whole says "**Table 9** shows…" → **Table 14**; Grand mean says "As shown in **table 10**…" → **Table 15**.
- Table 12's caption is placed **below** the table, while all other captions are above it. Make them consistent (APA: table number and title above the table).

### 3.3 Numbers that disagree within Chapter 4
- Maturity (SB staff): Table 7 = **4.88**, text = **4.87**.
- Non-repudiation (entire group): Table 12 = **4.54**, text = **4.53**.
- Functional SD: Table 6 = **0.05**, Table 15 = **0.04**. Maintainability SD: Table 10 = **0.04**, Table 15 = **0.09**.
- Table 4 column "PERCENTAGE (%)" shows **0.23 / 0.27 / 0.50 / 1.0**. Show 23.33 / 26.67 / 50.00 / 100.00, or rename the column "Proportion".
- Functional-suitability text: "the rate of accurateness and **completeness** in every group… is completely the same". You mean accurateness and **correctness**.

### 3.4 Part 2 vs Part 3 (Appendices)
- **Appendix I** calculations produce the incorrect values described in 2.2. Update them together with the tables.
- **Appendix F (Use Case)** has an "Adding User Account" use case in which the admin registers citizens, while Chapter 4 (Fig. 11) and the User Manual describe **citizen self-registration**. State both flows or make them agree.
- **Appendix H (User Manual)**, forum paragraph, ends mid-sentence: "…if not it will not appear to". Finish the sentence.
- The Background mentions an "**interview and survey**", but no interview guide or survey form from the problem-identification stage is in the appendices. Add it (e.g., as part of Appendix A or D) or remove "survey".
- The Chapter 3 sprint list has **9 sprints**. Check that the Gantt Chart (Fig. 9 / Appendix B) shows the same sprints.

---

## 4. Chapter-by-chapter notes

### Preliminary pages
- **Abstract:** add the **key numerical result** (overall mean, e.g., "an overall mean of 4.70, 'Very Satisfactory'"), the number and type of respondents, and **keywords** (e.g., legislative tracking, OCR, sentiment analysis, e-governance, ISO 25010).
- Acknowledgement: "Mr. Levi John A. Bernisto" is missing his "MIS" (it appears on the approval sheet). Make panel names and titles identical everywhere.

### Chapter 1 – Introduction
- Cite sources for the **population (36,447)**, e.g., PSA 2020 Census, and for "**127 resolutions and ordinances in 2024**", e.g., SB Office records.
- "Microsoft database" is vague. Specify it (e.g., MS Access or Excel).
- "The researcher propose a system that aimed…" → "The researchers proposed a system that aims…".
- The **legal basis** is missing and would strengthen the rationale: RA 7160 (Local Government Code) Sec. 59 on posting and publication of ordinances, and **EO No. 2, s. 2016 (Freedom of Information)** and/or the **Ease of Doing Business Act (RA 11032)** for digital access.
- *Conceptual Framework:* the figure's Input/Process/Output labels sit on a separate line under the diagram. Label them in the diagram and make sure the "Evaluation ISO 25010" box appears under Output.
- *Definition of Terms:* sort alphabetically (already mostly done). Use the same term everywhere, e.g., "Sentiment**s** Analysis" vs "Sentiment Analysis", and "Scanned Documents." (period) vs colon.
- *Significance of the Study:* written in past tense ("benefited", "helped"). Significance is normally in the present or future tense ("will benefit"). Grammar: "helped the municipal mayor **enhanced**", "presiding officer to **improves**", "cited as **a references**".
- Add the **Sangguniang Bayan Secretary/Staff** and the **University/Extension Program** as beneficiaries. This ties the study to the turnover.

### Chapter 2 – Review of Related Literature
- **Only 8 sources, and none on sentiment analysis**, even though it is one of the 5 objectives. Add 3–5 sources on sentiment analysis/content moderation (preferably Filipino/Tagalog/Hiligaynon text) and 2–3 on e-governance/transparency in Philippine LGUs, preferably 2020–2025.
- **Table 1** labels all three patents as "**Journal Article**". Change to "**Patent**". Also correct: "Digitizations" → "Digitization", "managrement" → "management". The EP3611664A1 origin "Europe" should be **European Patent Office**.
- The Summary compares BLTS with "**EP2821934A1**", but that patent is never reviewed. The third patent reviewed is **US2023065934A1**.
- Author forms vary: "Pandes (2018)" vs "Pandes et al. (2018)"; "Rattana-umnuaychai" vs "Rattanaumnuaychai"; "Perbangsa et al., (2018)" has a stray comma; "Mendis et. al." → "Mendis et al.". Use **Pandes et al. (2018)** throughout.
- "Department of Social **Worker** and Development" → **Social Welfare** and Development.
- The last Summary paragraph is incomplete: "…BLTS can upload files and track the text by using OCR" has no period and no closing synthesis. End with a clear **research gap** statement, e.g., "None of the reviewed systems combines OCR-based digitization, public access and sentiment-moderated citizen feedback for a Philippine municipal SB."
- **Table 2** check marks are images. Check that they display correctly in the final PDF.

### Chapter 3 – Methodology
- It claims a "**mixed-method approach**", but no qualitative analysis is described. Either describe how interview and suggestion data were analyzed (e.g., thematic analysis) or call the design **descriptive-developmental**.
- **Tense:** "will be used", "will evaluate" → past tense ("was used", "evaluated"). Some passages overuse past perfect ("had aimed", "had been designed") and should use simple past.
- **Respondents:** purposive selection based on "willingness, availability, ease of access" is **convenience sampling**. Describe it accurately and give the **inclusion criteria** for IT experts (e.g., ≥ 2 years in IT work) and community members.
- **Instrument:** having **community members** rate *modularity, testability, reusability, non-repudiation, co-existence* is questionable, because they cannot observe those qualities. Either explain why all groups rated all characteristics, or note it as a limitation. Also state whether the questionnaire was **validated** (e.g., by the statistician or experts) and cite the ISO/IEC 25010:2011 standard in the References.
- **Sub-characteristic names:** ISO/IEC 25010:2011 names the functional-suitability sub-characteristics *completeness, correctness, **appropriateness***. The manuscript uses "**accurateness**" and "correctness". Rename "accurateness" to "appropriateness", or explain the change.
- The Likert scale table is titled "5-point Likert Scale" but only shows interpretation ranges. Add the **response labels** (5 = Very Satisfactory … 1 = Very Unsatisfactory).
- "Statistical Microsoft Excel application" → "Microsoft Excel".
- **Hardware requirements** "16–64 GB RAM" looks like the development machine. Give **minimum deployment/server requirements** and **client (browser) requirements**. The Extension Program and LGU need these.
- Name the **frameworks and libraries** used (the Appendix C code shows PHP + Bootstrap/SB-Admin), plus the OCR engine and sentiment method (see 2.4).
- Sprint 8 says "admin should check first the post submitted by the users", but elsewhere sentiment analysis auto-approves posts. Say clearly whether posts are **auto-published or held for admin approval**. The Chapter 4 text for Figs. 19 and 26 differs on this too.

### Chapter 4 – Results and Discussion
- Chapter 4 opens by restating the whole background and method. Cut this to 2–3 sentences.
- The "aspects" list has **4 items** but there are **5 objectives**. The search-function objective is merged into item 1. Map results to **each objective** explicitly, even with a short heading per objective.
- Fig. 27 is captioned "**List of Legislators**" but shows the list of legislative *documents*. Retitle it "List of Legislative Documents". Also fix the "**Fgure** 11" typo.
- Interpretations overreach. For example, "Maturity… has reached optimal functionality", "Fault tolerance… operates despite hardware or software faults" and "Reliability… operates without failures" are claims made from perception scores. Phrase them as "respondents perceived the system as…".
- Figure/table numbers in the text do not match (Section 3.2). Every table and figure should be **introduced before it appears**.
- **Hinkley (2023)** is cited but missing from the References.
- Good practice: the section summarizing respondents' suggestions is valuable. Say **which suggestions were implemented** (e.g., log history was added in Fig. 23).

### Chapter 5 – Summary, Findings, Conclusions, Recommendations
- **Findings** only repeat "very satisfactory" for each ISO characteristic. Add the **numbers** (mean, SD) and add findings for objectives 1–5, e.g., "The system stored X ordinances and Y resolutions during testing" and "OCR extracted text from scanned PDFs, with manual correction for low-quality scans."
- **Conclusions** should answer the 5 objectives one by one. Remove unsupported claims (see 2.3 and 2.4).
- **Recommendations:** "Based on the result of the system tests" does not fit, because none of the 4 recommendations comes from the test results. Add recommendations that come from the findings and are useful for **turnover and sustainability**:
  - an **LGU adoption and training** plan for SB staff,
  - **hosting, domain, backup and maintenance** responsibility,
  - a **data-privacy** notice and policy for citizen accounts,
  - the lowest-rated items (fault tolerance, user error protection, replaceability),
  - the respondents' unimplemented suggestions (Ch. 4),
  - future research: OCR and sentiment-accuracy testing, and a larger community sample.

### References
Use **APA 7th edition** consistently, in alphabetical order:
- **Perbangsa et al. (2018)** uses full first names and "*Binus E-Thesis*". It is an IEEE ICIMTech 2018 paper: *Perbangsa, A. S., Hariawan, M., & Pardamean, B. (2018). Legislation information system. In 2018 International Conference on Information Management and Technology (ICIMTech) (pp. …). IEEE.*
- **Patents** need APA patent format with country/office and number, e.g., *Srinivas, L. (2023). Extract data from a true PDF page (U.S. Patent Application No. US2023065934A1). U.S. Patent and Trademark Office.* Remove "Dr" and the all-caps from "LINGINENI SRINIVAS" and "Dr Schreiber Gerald". Change the Table 1 names to match (Schreiber et al. rather than "Gerald et al.").
- **Mendis et al. (2022):** the author list is broken ("Silva, Haddela, P. S., & Dimuth Adeepa Gunarathne"). Copy it from IEEE Xplore.
- **Jayoma et al. (2020):** the DOI ending in "…**9400000**" looks like a placeholder. Verify it on IEEE Xplore.
- **Donato (2023):** remove the "#:~:text=…" text-fragment from the URL and the "Www." prefix in the site name.
- **Mino (2021)** is in the References but **not cited** in the text. Cite it or remove it. The title also has a typo ("Resons").
- Add missing sources: **Hinkley (2023)**, **ISO/IEC 25010:2011**, and the laws and census data cited (if added).
- Delete the doubled heading "REFERENCES / References" (the second one is redundant), and delete the trailing lone "REFERENCES" at the end of Part 3.

---

## 5. Appendices checklist (Part 3)

| Appendix | Present | Note |
|---|---|---|
| A – Letters | ✅ | Include the SB Office permission/endorsement letter |
| B – Schedule / Timeline | ✅ | Check that it matches the 9 sprints |
| C – Sample Source Code | ✅ | Good. Add a short caption for each file shown (e.g., *add_ordinance.php – OCR upload form*). Add the OCR and sentiment-analysis code, which are the study's core contribution |
| D – Evaluation Instrument | ✅ | Add the validation certificate if one exists |
| E – Sample Filled-in Form | ✅ | Blur respondent names or signatures if published |
| F – Use Case | ✅ | Registration flow inconsistency (Section 3.4) |
| G – User Interface | ✅ | Names differ from Chapter 4 figure names. Match them |
| H – User Manual | ✅ | Finish the cut-off sentence. Add admin log-in and publish/unpublish steps |
| I – Test Result | ✅ | Recompute (Section 2.2) |
| J – Sample Output | ✅ | |
| K – Certificate of Acceptance | ✅ | Important for the Extension Program. Make sure it is signed and dated by the LGU |
| L – Documentation (photos) | ✅ | |
| M – Resumes | ✅ (5) | Redact personal data for turnover copies (Section 2.5). If the 6th listed proponent is a real student, their resume is missing |

---

## 6. For the Extension Program turnover (not required by the research standard, but recommended)

1. A signed **MOA/MOU** or turnover agreement between the University and the LGU of Bugasong.
2. **Deployment details:** server/hosting, domain, admin credentials handed over securely (not in the manuscript).
3. A **training record** for SB staff, with an attendance sheet and photos.
4. A **maintenance and support plan** (who fixes bugs, for how long).
5. A **Data Privacy** notice in the system (for the citizen registration form).
6. A post-implementation **monitoring or impact evaluation** tool for the Extension Program's own reporting.

---

## 7. Priority summary

**Must fix (research validity):** 2.1 author/adviser listing · 2.2 weighted means and SD · 2.3 remove or test the significance claim · 2.4 describe the OCR and sentiment methods and qualify the claims · 2.5 ethics and data privacy.
**Should fix (consistency):** List of Figures and TOC · wrong table references · number mismatches · missing or extra references · patent labels in Table 1.
**Nice to fix (editorial):** tense consistency, grammar, APA formatting, abstract keywords and results.
