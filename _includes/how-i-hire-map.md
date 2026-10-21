```mermaid
flowchart LR
  subgraph P1["Part 1: Before the first interview"]
    Plan --> Source
  end
  subgraph P2["Part 2: Hire engineers, not coders"]
    Vet --> Hire
  end
  subgraph P3["Part 3: Raise the water line"]
    Onboard["Onboard & Probation"] --> Grow --> Reflect
  end
  Source --> Vet
  Hire --> Onboard
  Reflect -.->|adjust the rubric| Plan
  classDef current stroke-width:3px,fill:#fff4d6
{%- if include.part == 1 %}
  class Plan,Source current
{%- elsif include.part == 2 %}
  class Vet,Hire current
{%- elsif include.part == 3 %}
  class Onboard,Grow,Reflect current
{%- endif %}
```
