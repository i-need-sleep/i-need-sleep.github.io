---
layout: post
title:  Research Interest & Works in Progress
date:   2024-03-21 10:51:21
description: description
---

My research interest is to find better ways to use and understand acoustic and symbolic music LMs. In the long run, this includes in-context learning, interaction via prompting, etc. Currently, I am working on smaller-scale projects also involving making use of music LMs.

**Music LMs as regularization/search constraints**. Consider the case of unsupervised music transcription with only audio data and a pretrained, frozen symbolic music LM. We apply a VQ-VAE to encode the audio data and design a way to regularize the quantized codes such that they maximize the sequence-level probability given by the symbolic LM. Going further, this can have implications for building interactive systems: Consider optimizing an instrument/synthesizer/audio edit model such that the audio output is most likely. In general, can we use pretrained language models to convey musicality/world models to upstream/downstream modules?

**Multi-agent collaborative evaluation for music LMs**. Human users interact with acoustic/symbolic music LMs in a multi-round, collaborative fashion (e.g. The user writes a melody, the model generates the accompaniment, and the user edits the generated music and writes a new melody as a continuation, repeating the process). We study LM-LM collaboration as a proxy of the Human-LM setup and use grounded downstream metrics (e.g. beat-tracking) for fine-grained evaluation.