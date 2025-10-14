graph LR
    subgraph Pillars["Five Pillars"]
        P1[Pillar 1:<br/>Accessibility]
        P2[Pillar 2:<br/>Semantic Richness]
        P3[Pillar 3:<br/>Quality & Trust]
        P4[Pillar 4:<br/>Governance]
        P5[Pillar 5:<br/>Observability]
    end
    
    subgraph Layers["Seven Layers"]
        L1[Layer 1:<br/>Real-Time Fabric]
        L2[Layer 2:<br/>Semantic Layer]
        L3[Layer 3:<br/>Multi-Modal Storage]
        L4[Layer 4:<br/>RAG Infrastructure]
        L5[Layer 5:<br/>Governance]
        L6[Layer 6:<br/>Observability]
        L7[Layer 7:<br/>Data Products]
    end
    
    %% Accessibility (P1) connections
    P1 ===|PRIMARY<br/>Freshness| L1
    P1 ===|PRIMARY<br/>Fast retrieval| L3
    P1 ===|PRIMARY<br/>Caching, parallel| L4
    P1 -.->|SECONDARY<br/>Self-service| L7
    
    %% Semantic Richness (P2) connections
    P2 ===|PRIMARY<br/>Definitions| L2
    P2 ===|PRIMARY<br/>NL understanding| L4
    P2 -.->|SECONDARY<br/>Drift detection| L6
    
    %% Quality & Trust (P3) connections
    P3 -.->|SECONDARY<br/>Pipeline reliability| L1
    P3 -.->|SECONDARY<br/>Validation rules| L2
    P3 ===|PRIMARY<br/>Quality monitoring| L6
    P3 -.->|SECONDARY<br/>Audit trails| L5
    
    %% Governance (P4) connections
    P4 -.->|SECONDARY<br/>Classification| L2
    P4 ===|PRIMARY<br/>ABAC, masking| L5
    P4 -.->|SECONDARY<br/>Monitoring| L6
    
    %% Observability (P5) connections
    P5 -.->|SECONDARY<br/>Pipeline health| L1
    P5 -.->|SECONDARY<br/>Semantic drift| L2
    P5 -.->|SECONDARY<br/>Storage metrics| L3
    P5 -.->|SECONDARY<br/>Retrieval quality| L4
    P5 -.->|SECONDARY<br/>Policy metrics| L5
    P5 ===|PRIMARY<br/>All monitoring| L6
    P5 -.->|SECONDARY<br/>Usage tracking| L7
    
    style P1 fill:#fff4e6,stroke:#ff9800,stroke-width:2px
    style P2 fill:#f3e5f5,stroke:#9c27b0,stroke-width:2px
    style P3 fill:#e8f5e9,stroke:#4caf50,stroke-width:2px
    style P4 fill:#fce4ec,stroke:#e91e63,stroke-width:2px
    style P5 fill:#e8f4f8,stroke:#0066cc,stroke-width:2px
    
    style L1 fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    style L2 fill:#f1f8e9,stroke:#689f38,stroke-width:2px
    style L3 fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    style L4 fill:#fce4ec,stroke:#c2185b,stroke-width:2px
    style L5 fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    style L6 fill:#e0f2f1,stroke:#00897b,stroke-width:2px
    style L7 fill:#ede7f6,stroke:#5e35b1,stroke-width:2px
    
    linkStyle 0,1,2 stroke:#ff9800,stroke-width:3px
    linkStyle 4,5 stroke:#9c27b0,stroke-width:3px
    linkStyle 8 stroke:#4caf50,stroke-width:3px
    linkStyle 11 stroke:#e91e63,stroke-width:3px
    linkStyle 14 stroke:#0066cc,stroke-width:3px