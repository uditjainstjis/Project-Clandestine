# Trust Score Table / Rishik Research

## Dynamic Trust Score System

Assign each source a **dynamic trust score** between 0 and 1 based on measurable criteria:

| Factor | Description | Example Scoring Rule |
|--------|-------------|----------------------|
| Domain Reputation | Is it recognized and authoritative? | 0.9 for .edu, .gov; 0.8 for .org |
| Source Verification | Is it referenced by other reliable entities? | Add +0.05 per cross-citation |
| Fact-Check Record | Has it been flagged for misinformation? | Subtract 0.2 for known false reports |
| Recency | Is the data up to date? | Subtract 0.1 for >2 years old |
| Consistency | Matches other trusted sources? | Add up to +0.2 for high similarity |

## Cross-Verification Process

Whenever system finds a fact from a "trusted" source:

* Search 3–5 other trusted outlets for the same claim.
* Compare named entities, dates, and numbers.
* Compute similarity scores (Cosine/BERT embedding distance).

## NLP-Based Verification

Use NLP-based techniques to measure logical alignment between claim and reference:

* **Textual Entailment Models** (e.g., roberta-large-mnli)
  * Predicts if one statement entails, contradicts, or is neutral to another.
  
**Example:**
* Claim: "COVID-19 originated in 2020 in China."
* Verified Source: "COVID-19 was first detected in Wuhan, China, in late 2019."
* Result: Contradiction → Trust Score -0.3

## Final Trust Score Formula

```
FinalScore = 0.4D + 0.3C + 0.2R + 0.1F
```

where:
* D = Domain trust
* C = Cross-source consistency
* R = Recency
* F = Fact-check verification

### Trust Level Classification

* If FinalScore ≥ 0.75 → "Trusted"
* 0.5–0.75 → "Partially Trusted"
* < 0.5 → "Untrusted"
