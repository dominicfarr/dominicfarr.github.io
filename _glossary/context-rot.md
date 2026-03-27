---
title: Context rot
---

Context rot is the degradation of the LLMs output quality that occurs as the length of the input increases.
There are several key characteristics of context rot; Positional Bias, Attention Dilution, Distractor Interference, Universal Phenonmenon.

### Postional Bias

The "Lost in the middle" issue. Models perform best when information is at the very beginning or end of the context, but as the context grows longer struggle to access information buried in the middle.

### Attention Dilution

As the context expands, the attention mechanism distributes weight across more tokens, causing each individual token to receieve less attention, effectively burying critical instructions.

### Distractor Interference

When a LLM is given a long document containing specific piece of correct information, but also returns other incorrect information that is semantically simialar.

### Universal Phenonmenon

Every model from any provider usin transformer-based architecture exhibits context rot, regardless of its maximum context window size.
