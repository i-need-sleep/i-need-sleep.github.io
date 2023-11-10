---
layout: post
title:  Research Interest
date:   2023-10-13 10:51:21
description: description
---
I am recently intrigued by these two topics: functional alignment and emergent concepts.

# Functional Alignment

Pretrained transformers are universal computation engines, and much of the internal reasoning/computation performed by pretrained models is agonistic to domains, tasks, languages and modalities. This is evidenced by the success of PEFT and, in particular, reprogramming methods where the same model (function) can be applied to different tasks with minor modifications in the inputs and outputs. In other words, profound commonalities exist between uni-modal functions, and these commonalities can be leveraged for functional alignment to improve data efficiency and enhance cross-modal interactions.

Current multi-modal models are mostly trained by feature alignment (i.e. with parallel data) and are characteristically data-hungry due to the dimensionality of the feature space. Functional alignment (with similar uni-modal functions) can be an efficient alternative or complement. As a simple, unimodal example, consider the classic approaches to aligning cross-lingual word embeddings [FIG], where the alignment is based on small sets of word pairs and the “shapes” of monolingual embedding spaces. If we can leverage the edges between the words (i.e. have access to mono-lingual functions), alignment could be done with better accuracy and data efficiency.

An additional benefit is finer and more principled cross-modal conditioning. Mappings between features of different modalities are lossy. [Show two shades of red and suggest they would both be mapped to the word “red”]. Current multi-modal LMs (e.g. GILL and Next-GPT) and diffusion models (e.g. CoDi) either use text LMs as backbones (trained on, e.g.image-caption pairs) or use text as the bridging modality. The intermediate modality (text) causes a bottleneck and prevents fine-grained multimodal control (e.g. preserving the exact colour of an object). Functional alignment offers an avenue to solve this issue (we can describe the second picture to be relatively darker). Of course, not all parts of the two functions can be exactly aligned. It would be ideal to extract, for instance, a “common language” between the textual and visual languages, which brings us to…

# Emergent Concepts

By this, I mean extracting from self-supervised models series of intermediate representations or “concepts” that follow certain principles (e.g. being interpretable or interfaceable). Such principles are enforced by predefined priors (e.g. inductive biases or bottlenecks). Some priors, such as environments (multi-agent communication) and physical symmetry (a higher order inductive bias we have previously experimented with), tend to under-define the principles when handling high-dimensional, real-world data. Others, such as domain knowledge, tend to over-define it. Another issue with domain knowledge is that we do not always have well-defined internal structures. For instance, we do not have an intuitive, concise language for music beyond chord progressions and instrumentations. The learned internal concepts should be allowed to go beyond human knowledge but still be somewhat principled.

Functional alignment offers a promising middle ground. It allows us to ask the question, “What are the parts of modality A that follow the principles of (are alignable with) modality B?”. By using a uni-modal function as a prior, we avoid using rigid human knowledge while still ensuring that the extracted representations have principles. This can then be used as an interpretable control interface where we know what can be controlled and what cannot. On a further note, this opens up possibilities for co-adaptative interfaces where human users learn to speak in emergent concepts and models learn to be aligned with human concepts.

Note: How does using part-whole relationships (capsule networks) as a prior fit on the spectrum?

# Where to Start

idontknowlol

Easy case: nested modalities

Post-hoc swapping of model components

Merits: explicit(-ish) control, plug-and-play

# Going Further

Immediately: growing trees! Adding width (audio -> note + loudness) and adding depth (speech -> text -> emotion)

Sequence alignment (diffusion, not ARLM)

Layer alignment (need architectural work. How to feed probed reps back?)

It’s too late I need to sleep

How does this relate to all the fun research I've done? See <a href=./blog/2023/research-interest>How I Got Here</a>.
