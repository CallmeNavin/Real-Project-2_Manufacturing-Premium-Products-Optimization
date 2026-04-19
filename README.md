# Real-Project-2_Manufacturing-Premium-Products-Optimization

**What This Case Actually Felt Like**

**1. Problem**

In an industrial production system, output quality (represented by protein content) is a key factor directly linked to product value. However, achieving higher quality levels is not straightforward. Production teams must balance multiple competing objectives:
- Product quality
- Production capacity
- Machine constraints
→ → This naturally creates trade-offs between stability and quality performance, highlighting the need to re-evaluate existing operating preferences based on data
The challenge is further complicated by the fact that output quality is not directly controlled by a single parameter, but emerges from a combination of upstream conditions and process interactions.
- **Business question:** How can we define practical operating guidance to improve output quality while respecting real production constraints?

**2. Challenges**

- Output quality is measured after production, not controlled in real-time
- Final output is influenced by multiple upstream stages (material → intermediate → final output)
- Many-to-many relationships between stages: A single output batch may originate from multiple upstream batches, direct 1–1 traceability is not possible
- Different data sources with inconsistent granularity
- Operational constraints:
  + Production capacity
  + Machine constraints
  + Product quality

**3. Approach**

**Key principles**
- Map upstream factors to final output level using database queries, accept many-to-many relationships and handle them through aggregation
- Focus on stable operational patterns rather than isolated correlations
- Quantify trade-offs to support decision-making

**Details**
- Step 1 - Define analysis level: All data was normalized to the final output level (batch-level representation). Due to many-to-many relationships, aggregation was used to reflect real production behavior
- Step 2 - Identify operational patterns: Instead of relying purely on statistical correlation, the analysis focused on observed patterns across different operating ranges, consistent signals within noisy real-world data & performance comparison across grouped conditions
- Step 3 - Evaluate trade-offs: Certain upstream conditions have traditionally been favored in operations due to their stability benefits. However, the analysis reveals that these same conditions can limit the probability of achieving higher quality outcomes. This creates a fundamental trade-off between operational stability and quality performance. The goal of this analysis is not to override existing practices, but to quantify this trade-off, allowing stakeholders to make decisions based on clear visibility of gains and compromises

**4. Key Insights**

- Contamination is the primary driver:
  + Lower contamination → higher probability of achieving premium quality
  + Higher contamination → significantly reduced performance
- Moisture acts as a trade-off lever, influences the balance between operational stability on upstream stage & probability of achieving high-end quality
  + Lower moisture → higher quality potential, but reduced stability
  + Higher moisture → stable operation, but lower premium probability
- Decision can be structured into:
  + Optimal zone: Highest quality potential → Requires stricter control on contam, moisture
  + Operational zone: Stable production conditions → Moderate quality performance
→ Not all variables contribute equally — contamination consistently dominates outcome, while moisture acts as a trade-off variable.
- Decision Perspective: This analysis is not intended to provide fixed thresholds. Instead, it enables production teams to answer:
  + What do we gain, what do we sacrifice if we push for higher quality?
  + Which levers are most effective to control?
→ The goal is not certainty, but **clarity for decision-making**
![  esult_framework](https://github.com/CallmeNavin/Real-Project-2_Manufacturing-Premium-Products-Optimization/blob/main/result.png)

**5. Engineer Diary**

_5.1. First wrong assumption_
- At first, I expected:
  + Clear mapping between stages
  + Clean relationships between variables
- This quickly proved incorrect:
  + One output batch could originate from multiple upstream sources
  + Data relationships were many-to-many
  + Direct traceability became impractical
→ Difficult to demonstrate to the production, QA/QC team
- I just need to find the optimal point for Production & QA/QC team to control. This quickly proved incorrect due to the trade-off between operational stability and quality performance
→ My problem changed from: "What predicts quality?" to "Given how the system actually behaves, what decisions are realistic?

_5.2. What actually worked_
- Accepting imperfect structure
- Using aggregation instead of forcing precision
- Focusing on patterns rather than exact causation

_5.3. The most important insight_
- The key challenge was not technical, but organizational: How to present the trade-off clearly enough for stakeholders to reconsider existing operational preferences
**→ The role of this analysis is not to define what is "right", but to clarify what each decision costs**

**6. Notes on Confidentiality**
- To respect company confidentiality:
  + Company identity is not disclosed
  + Exact process parameters are omitted
  + Internal dataset structures are not shown
  + Numerical thresholds are generalized → This case focuses on methodology and thinking rather than proprietary information
- The analysis was independently conducted, from data extraction to insight development. However, the problem itself was defined within a real operational context, where:
  + Production teams provided perspective on process constraints
  + QA/QC teams validated quality-related observations

**7. Personal Takeaway**
- Technical skills help. But what mattered more here was:
  + Understanding process reality
  + Accepting data limitations
  + Framing **trade-off** instead of forcing conclusions
  + Translating messy data into operational guidance
**Still: The biggest learning was simple: Real data work is not about clean datasets. It is about staying useful when data & reality is messy**
