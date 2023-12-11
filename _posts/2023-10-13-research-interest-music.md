---
layout: post
title:  Research Interest (Music AI)
date:   2023-10-13 10:51:21
description: description
---

Broadly interested in music AI and NLP, my research goal is to draw parallels between music and language processing and 1) devise methods for better understanding music and language models, 2) devise generalizable methods for music AI, and 3) develop effective, useful music AI applications. I have gained rich research experience under the supervision of Professors Gus Xia and Timothy Baldwin. To further grow as a researcher and contribute to these promising fields, I intend to pursue a PhD.

# Past Research
## Generalizable Methods for Music AI
Music AI encompasses a plethora of understanding and generation tasks, each with its own characteristics. I am interested in unifying them into a shared, general framework, taking inspiration from generalizable methods in NLP. In a research project supervised by Professor Gus Xia, I noted that many autoregressive music generation models are slow at inference time, prohibiting them from being used as interactive tools in music creation. However, certain generation tasks, such as harmonic style transfer, can be approximated with rule-based operations, with the transformed output refined with only minor edits. Following this intuition, I devised an edit-based model (commonly used in NLP tasks such as grammatical error correction), augmented it with a rule-based approximation step and experimented with having it learn from an autoregressive style transfer model in a distillation setup. While there exists a gap in the output’s quality, the semi-autoregressive edit model leads to a 4x improvement in inference speed, and I believe using learned rule-based transformations can make it useful for many more tasks.

In a separate course project, I have attempted to unify a series of music information extraction (MIR) tasks under an audio-to-audio format. To accommodate this setup, I modified the transformer prior model of Jukebox with an adaptor module following ControlNet such that it can take in audio as additional condition. The advantage of this setup lies in its versatility, as many MIR tasks that involve symbolic inputs and outputs can be recast into the audio-to-audio format. For instance, MIDI-to-audio synthesis can be recast by synthesizing the input condition using simple sine waves, and music transcription can be recast by synthesizing the output. Small-scale experiments show that this method can handle tasks such as vocal source separation and MIDI-conditioned synthesis.

## Emergent Concepts
It is a common belief that certain innate priors are behind the human understanding of concepts across different modalities. In <a href="http://www.yichenwilliamhuang.com/#sps">(Liu et al., 2023)</a>, published at NeurIPS 2023, we examined physical symmetry as one such high-level inductive bias. We showed that by enforcing a prior model regularized by equivariance constraints, a VAE can learn concepts such as music pitch and 3D coordinates from unlabeled perceptual data. I investigated the applicability of the approach under a more realistic setup. Specifically, I designed and conducted experiments learning from natural melodies from the Nottingham dataset and with time-invariant timber. This project helped demonstrate the commonality across models in different modalities.

# Future Research
## Understanding Music Models and Language Models
In (Liu et al., 2023), we investigated a common mechanism behind different modalities, but the method cannot be easily adapted to more complex data such as polyphonic music. As it has been established that pretrained transformers are universal compute engines, I believe an alternative way to understand models and, ultimately, human concepts is to study the parallels between uni-modal models of different modalities. Music and language can serve as an ideal subject since they both involve structures and syntax. I am interested in examining the structural understanding of music and language models through methods such as probing and mechanistic interpretability methods and identifying commonalities. Findings along this line may lead to more data-efficient ways to fuse music and language models without using web-scaled data.

## Generalizable Methods for Music AI
I have experimented with unifying certain MIR tasks as audio-to-audio by modifying Jukebox, which is akin to sequence-to-sequence in NLP. A natural extension is to apply multi-task training. To go even further, I am interested in investigating in-context learning (ICL) and other advanced prompting methods in generative music models. Large music audio models have recently been introduced following the success of textual LLMs, but characteristic LLM features such as ICL and prompting are under-studied. I intend to start with simple setups, such as framing iterative score reduction as a chain-of-thought problem. Going further, I am interested in instructional finetuning for music audio models through adaptors.

## Applications in Music AI
A strong appeal of music AI to me is that it can be directly applied to practical problems in music-making. As an amateur guitarist, a common frustration for me during recording is the laborious process of splicing and editing multiple flawed takes to produce a refined track. This complex task of recording refinement involves both performance-level (timing and techniques) and score-level (wrong notes) flaws and is under-explored in the context of music AI. An intuitive solution is to use feature fusion, where we combine the latent representations of the multiple takes and feed it into a quality-aware decoder, which may be trained with a denoising objective. However, real-world use cases may require more controllability as users may want to specify the notes or audio segments to edit. Therefore, I am also interested in applying partial re-synthesis (where we explicitly model notes, performance and timber as intermediate representations) and program synthesis (where a controller model utilises a set of pre-defined or learned edit operations). As an additional use case, such a system can be used in music tutoring by informing students of the flaws in their performance and providing demonstrations.



<!-- How does this relate to all the fun research I've done? See <a href="../how-i-got-here">How I Got Here</a>. -->