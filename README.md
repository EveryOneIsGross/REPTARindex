# REPTARindex
A command-line tool for recursive graph-based document indexing and retrieval with hierarchical cluster summaries and inverted keyword indexing.


```mermaid
graph TD
%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#ffaa00', 'primaryTextColor': '#000000', 'primaryBorderColor': '#ffaa00', 'lineColor': '#ffaa00', 'secondaryColor': '#ffaa00', 'tertiaryColor': '#ffaa00', 'clusterBkg': 'none', 'clusterBorder': 'none', 'fontSize': '20px'}}}%%

    %% Indexing Process
    A[Input Documents] --> B[Text Extraction & Chunking]
    B --> C[Embedding Generation]
    C --> D[Initial Graph Creation]
    D --> E[Recursive Clustering]
    E --> F[Cluster Summarization]
    F --> G[Update Graph Structure]
    G --> H[Build Inverted Index]
    H --> I[Final REPTAR Index]

    %% Feedback loops in indexing
    F --> |Refine Clustering|E
    G --> |Optimize Graph|D
    H --> |Update Embeddings|C

    %% Search Process
    J[User Query] --> K[Query Processing & Embedding]
    K --> L[Initial Filtering with Inverted Index]
    I --> L
    L --> M[Match Query to Cluster Hierarchy]
    M --> N[Traverse Relevant Clusters]
    N --> O[Perform Similarity Matching on Subset]
    O --> P[Rank and Return Results]

    %% Feedback loops in search
    N --> |Refine Search|M
    O --> |Adjust Relevance Criteria|N
    P --> |Update Query Representation|K

    %% Inter-process connections
    I -.-> |Index Structure|M
    I -.-> |Cluster Summaries|N
    I -.-> |Document Embeddings|O

    subgraph
    A
    B
    C
    D
    E
    F
    G
    H
    I
    end

    subgraph
    J
    K
    L
    M
    N
    O
    P
    end



```
