```mermaid
flowchart LR
  Plan --> Source --> Vet --> Onboard --> Reflect
  Reflect -.->|adjust the rubric| Plan
  classDef current stroke-width:3px,fill:#fff4d6
{%- if include.phase == 1 %}
  class Plan current
{%- elsif include.phase == 2 %}
  class Source current
{%- elsif include.phase == 3 %}
  class Vet current
{%- elsif include.phase == 4 %}
  class Onboard current
{%- elsif include.phase == 5 %}
  class Reflect current
{%- endif %}
```
