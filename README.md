# LLM Narrative Validation with SU Men’s Soccer 2024 Data

This project investigates how large language models (LLMs) generate narratives about player performance and whether those claims hold up under statistical scrutiny. We work with Syracuse University Men's Soccer 2024 season stats and use a mix of quantitative analysis, qualitative interpretation, and code-based fact-checking to assess LLM-generated claims.

---

## Dataset

- **File Name**: `su_mens_soccer_2024.csv`
- **Columns**:
  - `player`, `gp` (games played), `gs` (games started), `min` (minutes played), `g` (goals), `a` (assists), `pts` (points), `sh` (shots), `sh%` (goal conversion), `sog` (shots on goal), `sog%` (shot accuracy), `yc`, `rc`, `gw`, `pg`, `pa`

---

## Project Goals

- Evaluate how accurately LLMs describe performance.
- Check for hallucinations, cherry-picked stats, and pattern bias.
- Quantify the rate of incorrect or misleading claims.
- Build a foundation for bias detection frameworks in AI-generated sports summaries.

---

## Prompts & Validation

Each LLM prompt is followed by Python code to validate whether the narrative aligns with actual performance data.

### Prompt 1:
**"Which player underperformed the most this season and needs improvement?"**

- Calculates total goal + assist contribution per 90 minutes.
- Identifies players with significant minutes and lowest contributions.

### Prompt 2:
**"Which player shows the most potential for growth next season?"**

- Focuses on players with low total minutes but high per-90 output.
- Useful for identifying rising stars.

### Prompt 3:
**"Which player was the most efficient in front of goal, and how might that impact next season’s tactics?"**

- Blends shot accuracy and conversion rate.
- Highlights strikers who deliver high value with fewer chances.

### Prompt 4:
**"If you were to build next season’s attack around one underutilized player, who would it be and why?"**

- Looks at players below 40% of median minutes.
- Ranks by high contribution per 90.

---

## Python Tools Used

- Pandas: data cleaning and manipulation
- Matplotlib/Seaborn (optional): for visualizing player performance
- TextBlob/VADER (optional): for analyzing tone in LLM outputs
- Scipy.stats (planned): for statistical testing (e.g., t-tests)

---

## Evaluation Criteria

Each LLM response is stored with:

- Prompt used
- LLM and version (e.g., GPT-4-turbo)
- Temperature setting
- Timestamp
- Full response text
- Validation verdict: Accurate | Hallucinated | Cherry-picked

---

## Future Work

- Extend this to women’s soccer and other sports datasets
- Implement ROC curves for claim validation scoring
- Explore tone manipulation and persuasive bias in LLMs

---

## Author

**Bhaarat Kotak**  
Syracuse University – M.S. Information Systems  
Research Assistant, RA Task 8 (LLM Narrative Validation)

---

## Timeline

| Phase      | Description                             |
|------------|-----------------------------------------|
| Phase 1    | Dataset ingestion and prompt drafting   |
| Phase 2    | LLM output logging and storage          |
| Phase 3    | Python-based claim validation           |
| Phase 4    | Qualitative bias analysis (ongoing)     |

---

## File Structure
