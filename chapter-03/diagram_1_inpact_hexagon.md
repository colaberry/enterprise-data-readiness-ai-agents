```mermaid
%%{init: {'theme':'base', 'themeVariables': { 'primaryColor':'#e0f2f1','primaryTextColor':'#004d40','primaryBorderColor':'#00897b','lineColor':'#00897b','secondaryColor':'#f0fff0','tertiaryColor':'#fff'}}}%%

graph TB
    subgraph INPACT["<b>INPACTâ„¢ Framework</b><br/>Six Agent Needs for User Trust"]
        I["<b>I - Instant</b><br/>Speed Builds Confidence<br/>&lt;2s response time"]
        N["<b>N - Natural</b><br/>Understanding Builds Connection<br/>75-85% NLU accuracy"]
        P["<b>P - Permitted</b><br/>Security Builds Safety<br/>ABAC + HITL authorization"]
        A["<b>A - Adaptive</b><br/>Improvement Builds Reliability<br/>Continuous learning loops"]
        C["<b>C - Contextual</b><br/>Completeness Builds Accuracy<br/>5-8+ system integration"]
        T["<b>T - Trusted</b><br/>Transparency Builds Confidence<br/>100% audit trails + citations"]
    end
    
    I --- N
    N --- P
    P --- A
    A --- C
    C --- T
    T --- I
    
    I -.-> C
    N -.-> A
    P -.-> T
    
    Note1["All six needs are REQUIRED<br/>Missing even one increases failure risk to 95%"]
    
    INPACT -.-> Note1
    
    classDef needBox fill:#e0f2f1,stroke:#00897b,stroke-width:2px,color:#004d40
    classDef framework fill:#00695c,stroke:#004d40,stroke-width:3px,color:#ffffff
    classDef note fill:#fff9e6,stroke:#f57c00,stroke-width:2px,color:#e65100
    
    class I,N,P,A,C,T needBox
    class INPACT framework
    class Note1 note
```

**Figure B.1: INPACTâ„¢ Six Agent Needs Framework**

The INPACTâ„¢ framework identifies six architectural requirements agents must fulfill to earn user trust. All six needs are interdependentâ€”missing even one significantly increases the risk of joining the 95% of AI pilots that fail to achieve ROI.

---

Â© 2025 Colaberry Inc.
