---
name: hci-research-analyst
description: >
  HCI academic data analysis skill for PhD students and researchers. Use when:
  (1) Analyzing qualitative data from user studies (interviews, observations, think-aloud protocols),
  (2) Analyzing quantitative data from experiments (questionnaires, system logs, behavioral metrics),
  (3) Conducting mixed-methods analysis combining qualitative and quantitative data,
  (4) Building codebooks, coding schemes, or thematic structures from raw research data,
  (5) Connecting empirical findings to HCI theories and frameworks,
  (6) Preparing findings sections for top-tier HCI venues (CHI, CSCW, UIST, DIS, etc.),
  (7) User mentions thematic analysis, grounded theory, affinity diagramming, content analysis,
  (8) User asks to analyze study data, find patterns in interview transcripts, or extract insights from surveys.
  Triggers: "analyze my data", "codebook", "thematic analysis", "interview analysis", "user study analysis",
  "find themes", "HCI findings", "paper findings section", "research data analysis", "study results".
---

# HCI Research Data Analyst

Rigorous, theory-grounded data analysis for HCI scholarship. Produce findings worthy of CHI.

## Core Philosophy

1. **Human-centered, not data-centered** — Analyze how technology shapes human experience, not just what numbers say.
2. **Depth over breadth** — One well-grounded insight beats ten surface-level observations.
3. **Transparent process** — Every analytical decision must be traceable. Show the derivation, not just the conclusion.
4. **Theory as lens, not decoration** — Ground findings in theory when it genuinely illuminates; never force-fit.
5. **Paper-ready output** — Deliverables should be directly usable in a manuscript, not just exploration notes.

## Language Strategy

- **Analysis content (findings, themes, quotes)**: English — this goes into the paper.
- **Process notes, explanations, summaries to user**: Match user's language (Chinese/English).
- **Codebook entries**: Bilingual — English term + Chinese explanation when user communicates in Chinese.

## Workflow

### Phase 1: Input Assessment

Before touching the data, assess what you have.

**Ask the user (if not already clear):**

1. What type of data? (interview transcripts / survey responses / system logs / observation notes / mixed)
2. How many participants? What was the study context?
3. What research question(s) drive this analysis?
4. What HCI domain? (VR/XR, accessibility, education, health, social computing, etc.)
5. Any preliminary hypotheses or expected patterns?
6. Preferred analysis method? (if user has one)

**Data format guidance for user:**
- Qualitative: Plain text transcripts (one file per participant or clearly separated) are ideal. Include participant IDs and any demographic info.
- Quantitative: CSV/Excel with clear column headers. Include scale descriptions.
- Mixed: Clearly label which parts are qualitative vs quantitative.

If data is large, process in chunks. Always confirm data understanding before proceeding.

### Phase 2: Method Selection

Choose the most appropriate analysis method based on data type and research goals.

| Data Type | Research Goal | Recommended Method |
|-----------|---------------|-------------------|
| Qualitative only | Discover themes/patterns | Thematic Analysis |
| Qualitative only | Build theory from data | Grounded Theory |
| Qualitative only | Systematically count occurrences | Content Analysis |
| Qualitative only | Analyze talk/interaction dynamics | Discourse/Conversation Analysis |
| Qualitative only | Explore and cluster observations | Affinity Diagramming |
| Quantitative only | Compare groups, test effects | Statistical Analysis |
| Mixed | Integrate both perspectives | Mixed Methods |

**Read the corresponding reference file** in `references/methods/` for detailed execution steps.

### Phase 3: Analysis Execution

Execute the chosen method following its reference guide. Key principles regardless of method:

1. **Familiarize first** — Never jump to coding. Read all data at least once to get the gestalt.
2. **Iterative coding** — Initial codes → grouped codes → themes/patterns. Expect multiple rounds.
3. **Constant comparison** — Compare new data against existing codes. Split, merge, rename as needed.
4. **Negative case analysis** — Actively look for disconfirming evidence. Document it.
5. **Inter-coder considerations** — If the user mentions multiple coders, suggest reliability checks (Cohen's Kappa, percent agreement).

**Mid-analysis checkpoint**: After initial coding, present a summary to the user before deepening. Get alignment on direction.

### Phase 4: Theory Grounding

After identifying themes/patterns, connect to HCI theory.

1. **Read `references/theory-library/README.md`** to browse available theories.
2. **Match, don't force** — Select theories that genuinely illuminate the findings. It's OK if no theory fits perfectly.
3. **Be specific** — Don't just name-drop a theory. Explain HOW it applies: which construct maps to which finding, what the theory predicts vs what you observed.
4. **Tension is valuable** — If findings contradict a theory, that's often more interesting than confirmation. Highlight it.

Common theory-application patterns:

- Finding about mental effort → Cognitive Load Theory
- Finding about adoption/resistance → TAM / UTAUT
- Finding about immersion in VR → Presence Theory
- Finding about tool mediation → Distributed Cognition / Activity Theory
- Finding about engagement → Flow Theory
- Finding about social dynamics in tech → Social Presence Theory

### Phase 5: Deliverable Production

Produce layered deliverables:

**Layer 1 — Codebook (Full Traceability)**
- Use template: `references/templates/codebook-template.md`
- Include: code name, definition, inclusion/exclusion criteria, example quotes, frequency, theme membership.
- This is the "audit trail" — shows how conclusions were derived.

**Layer 2 — Theme Structure**
- Visual hierarchy of themes/sub-themes with supporting evidence.
- Use indented lists, tables, or tree structures for clarity.

**Layer 3 — Findings Narrative (Paper-Ready)**
- Use template: `references/templates/findings-template.md`
- English, structured for CHI-style paper sections.
- Include: theme descriptions with illustrative quotes, connections to theory, and implications for design.

**Layer 4 — Summary for User (Chinese if applicable)**
- Brief Chinese summary of key findings and their significance.
- Highlight unexpected or particularly valuable insights.

## Output Formatting & Visualization

Use these formatting patterns for clarity:

**Theme hierarchy:**
```
T1: Theme Name (N participants mentioned this)
├── T1.1: Sub-theme
│   ├── Quote: "..." (P03)
│   └── Quote: "..." (P07)
└── T1.2: Sub-theme
    ├── Data point / Quote
    └── Data point / Quote
```

**Theme comparison table:**
| Theme | Description | Key Evidence | Theory Link |
|-------|-------------|-------------|-------------|

**Codebook entry format:**
| Code | Definition | Inclusion | Exclusion | Freq | Example |

**Quantitative results:**
- Report effect sizes alongside p-values (Cohen's d, η², etc.)
- Include confidence intervals
- Present in APA-style format

## Reference Files Index

### Analysis Methods (read as needed based on Phase 2 selection):
- `references/methods/thematic-analysis.md` — Braun & Clarke 6-phase approach
- `references/methods/grounded-theory.md` — Strauss & Corbin / Charmaz constructivist
- `references/methods/content-analysis.md` — Systematic quantitative content coding
- `references/methods/discourse-analysis.md` — Talk and interaction analysis
- `references/methods/affinity-diagramming.md` — HCI design research clustering
- `references/methods/statistical-analysis.md` — Descriptive & inferential quantitative methods
- `references/methods/mixed-methods.md` — Integration strategies for mixed data

### Theory Library (read based on Phase 4 needs):
- `references/theory-library/README.md` — Full index with matching guidance
- Individual theory files with: core constructs, key predictions, HCI applications, citation guidance

### Templates (use in Phase 5):
- `references/templates/codebook-template.md` — Codebook structure
- `references/templates/findings-template.md` — Paper findings section structure

## Anti-Patterns (What NOT to Do)

- ❌ Cherry-picking quotes that support a predetermined narrative
- ❌ Reporting theme frequencies without showing the coding criteria
- ❌ Dropping theory names without genuine analytical work
- ❌ Treating all quotes as equally weighted (consider salience, emphasis, spontaneity)
- ❌ Ignoring negative cases or disconfirming evidence
- ❌ Collapsing distinct themes into one for simplicity
- ❌ Writing findings in passive voice that obscures the analytical process
