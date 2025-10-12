graph TB
    subgraph "Pillar Interdependencies"
        OBS[Pillar 5: Observability<br/>Monitors & Improves All Pillars]
        
        ACC[Pillar 1: Accessibility<br/>Data at Conversational Speed]
        SEM[Pillar 2: Semantic Richness<br/>Business Language Understanding]
        QUA[Pillar 3: Quality & Trust<br/>Data Reliability]
        GOV[Pillar 4: Governance & Security<br/>Dynamic Protection]
        
        OBS -->|Monitors latency,<br/>freshness, cache| ACC
        OBS -->|Detects semantic<br/>drift, new terms| SEM
        OBS -->|Validates completeness,<br/>accuracy, freshness| QUA
        OBS -->|Audits policy<br/>violations, access| GOV
        
        SEM -->|Query understanding<br/>improves retrieval| ACC
        SEM -->|Defines validation<br/>rules & metrics| QUA
        SEM -->|Provides data<br/>classification| GOV
        
        QUA -->|Reliable data<br/>enables trust| ACC
        
        GOV -->|ABAC must be fast<br/>to not slow retrieval| ACC
        GOV -->|Requires semantic<br/>definitions| SEM
        
        ACC -->|Fast access needs<br/>secure boundaries| GOV
        
        OBS -.->|Feedback loops drive<br/>continuous improvement| ACC
        OBS -.->|Feedback loops drive<br/>continuous improvement| SEM
        OBS -.->|Feedback loops drive<br/>continuous improvement| QUA
        OBS -.->|Feedback loops drive<br/>continuous improvement| GOV
    end
    
    style OBS fill:#e8f4f8,stroke:#0066cc,stroke-width:3px
    style ACC fill:#fff4e6,stroke:#ff9800,stroke-width:2px
    style SEM fill:#f3e5f5,stroke:#9c27b0,stroke-width:2px
    style QUA fill:#e8f5e9,stroke:#4caf50,stroke-width:2px
    style GOV fill:#fce4ec,stroke:#e91e63,stroke-width:2px
    
    classDef observability fill:#e8f4f8,stroke:#0066cc,stroke-width:3px
    classDef pillar fill:#f5f5f5,stroke:#666,stroke-width:2px