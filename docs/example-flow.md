# Example Flow

## Example: Verifying a Claim

**User Prompt:** "NASA confirms alien life on Mars."

### Step-by-Step Process:

1. **Router:** Classifies as "Science News".

2. **Crawler:** Searches NASA, Reuters, BBC Science.

3. **Knowledge Base:** Finds no NASA official report.

4. **Cross-check:** Reuters and BBC also report "No official confirmation."

5. **Fact-check API:** Snopes lists claim as **false**.

6. **Veracity Analyzer:** Trust score = 0.18 → Label = **Fake**

### Result

The claim "NASA confirms alien life on Mars" is determined to be **FAKE** with a trust score of 0.18.
