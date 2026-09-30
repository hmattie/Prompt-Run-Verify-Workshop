# Prompt, Run, Verify: Using LLMs for Data Analysis in Public Health

Materials for Workshop 3 of an AI workshop series for graduate students at the Harvard T.H. Chan School of Public Health (September 30, 2026). Presented by Heather Mattie, PhD, Department of Biostatistics.

## About the workshop

Large language models (LLMs) can write analysis code in seconds. This 90-minute workshop shows what that looks like in practice and why you still need to check everything they produce. Using a public dataset of 1,000 US adults, we ask an LLM for descriptive statistics, visualizations, a Table 1, and linear and logistic regression, then run and verify the results in R.

The workshop covers:

- **Text vs. numbers.** LLMs predict numbers rather than calculate them, so numbers typed in a chat reply need checking.
- **A framework for coding with an LLM:** Plan, Protect, Prompt, Run, Verify, Own.
- **Working with an uploaded file**, with a verification checkpoint after each step.
- **Working without uploading data**, for restricted data such as PHI or data covered by a data use agreement: describe the structure, build on fake data, and run on the real data in an approved environment.
- **Debugging:** LLMs fix errors that stop your code, but you have to find the errors that don't.
- **Exporting** one analysis to HTML, Word, PowerPoint, figures, and CSV.
- **Dos and don'ts** for using LLMs responsibly.

The goal is to show what's possible without replacing domain expertise. You still need to learn to do the analysis yourself, and you are responsible for every number you report.

## Files

| File | What it is |
|---|---|
| `Prompt_Run_Verify.pptx` | The workshop slides. |
| `student_guide.html` | The Student Guide, to use during the session. It has the prompts (P1–P12), the codebook, the Spot the bug exercise, a verification checklist, dos and don'ts, and answers. Download it and open it in a web browser. |
| `student_guide.docx` | The same Student Guide as a Word document. |
| `student_guide.Rmd` | The R Markdown source for the Student Guide. |
| `nhanes_workshop.csv` | The workshop dataset: 1,000 adults from the public NHANES R package. This is the file you upload to the LLM during the demos. |
| `workshop3_analysis.Rmd` | The analysis walkthrough to run in RStudio: import, cleaning, descriptive statistics, plots, Table 1, regression models, and exporting. Verification checkpoints are written between the code chunks. |
| `workshop3_analysis.html` | The knitted analysis walkthrough, with all code and output. Read it here if you don't want to run the code. |

## Getting started

**No R experience?** Download `student_guide.html` and `nhanes_workshop.csv`. You can do every exercise in your LLM chat window and use the verification checklist in section 6 of the guide.

**Using R?** Download `nhanes_workshop.csv` and `workshop3_analysis.Rmd` into the **same folder**, open the `.Rmd` file in RStudio, and install the packages once:

```r
install.packages(c("tidyverse", "gtsummary", "flextable", "broom", "rmarkdown"))
```

Then run the chunks one at a time and read the output, or click **Knit** to make the full report.

## About the data

`nhanes_workshop.csv` is a random sample of 1,000 adults aged 20 and older from the [`NHANES` R package](https://cran.r-project.org/package=NHANES) (National Health and Nutrition Examination Survey, 2009–2012). It is public data and safe to upload to an LLM.

For teaching, the data were changed in two ways that an LLM won't notice unless you tell it:

- Missing BMI values are coded as `999`.
- Race/ethnicity is stored as the numbers 1–5 (1 = White, 2 = Black, 3 = Mexican American, 4 = Other Hispanic, 5 = Other/Multiracial).

The full codebook is in section 4 of the Student Guide. These are teaching data; don't use them for research or population estimates.

## Reference

Della Vedova C. Four best practices for using ChatGPT/Claude as an effective R assistant. *Bull Dial Domic.* 2026;9(2). [doi:10.25796/bdd.v9i2.87112](https://doi.org/10.25796/bdd.v9i2.87112)
