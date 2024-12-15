---
layout: post
title:  Research Interests
date:   2024-03-21 10:51:21
description: description
---

Recent years have seen rapid advances in music generative models. They are capable of generating high-fidelity outputs but, at the same time, are unusable as practical tools. I aim to improve music generative models into helpful, interactive tools by 1) enabling generalizable forms of controls, 2) better understanding and leveraging the human creative process behind music production, and 3) devising reliable and holistic evaluation methods. I gained rich research experience under the supervision of Professors Gus Xia, Timothy Baldwin, and Chris Donahue. To further grow as a researcher and contribute to this promising field, I intend to pursue a PhD.

# Past and Ongoing Research
## Taming Music Generative Models
I have been working on generalizable methods to enable such models to take on more tasks. In a project supervised by Professor Gus Xia, I attempted to enable Jukebox, an optionally lyrics-conditioned model, to handle various forms of conditions. Models like Jukebox can generate reasonably realistic music, but in practical use, users may want to apply different conditions (e.g., MIDI, chord, or melody controls). These conditions take different formats, and developing specific methods for each type of control can be impractical. I proposed audio-to-audio generation as a general setup of conditional generation. The advantage of this setup lies in its versatility, as many forms of control signals can be recast into the audio-to-audio format. For instance, MIDI-to-audio synthesis can be recast by synthesizing the input condition using simple sine waves. To accommodate this setup, I modified the transformer prior model of Jukebox with an adaptor module following ControlNet such that it can take in audio as an additional condition. Small-scale experiments show that this method can handle tasks such as MIDI-conditioned synthesis and accompaniment generation. Under the supervision of Professor Chris Donahue, I later extended this line of ideas to music information retrieval (MIR) tasks by recasting temporally varying MIR labels as audio supervision signals (e.g., beat detection can be formulated as predicting a sequence of audio clicks). I explored approaches (e.g., weight-tying, attention biases, and input patterns) to enforce locality correspondence between the input and output sequence and benchmarked our method against other methods based on generative models. While the audio-to-audio approach somewhat falls behind finetuned baselines, I believe audio-to-audio control is a unifying approach that will allow generative models a deeper understanding of music and enable more versatile applications.

## Automatic Evaluation for Music Generation
Effective evaluation is crucial for understanding and informing the development of systems and methods, and automatic evaluation has been commonly used as a practical proxy for human judgements. During my master’s studies, I developed robust automatic metrics for evaluating machine translation and text simplification systems. By contrast, evaluation appears underexplored in music AI, where practitioners have only recently started to move on from using the dated VGGish model as evaluation backbones. This is particularly concerning considering the rapid advancement in music foundation models and applications. In an ongoing project supervised by Professors Chris Donahue and John Thickstun, we proposed a new metric for open-ended music generation based on generative models and divergence frontiers and synthesized sets of meta-evaluation data targeting fidelity, musicality, context, and diversity, where our metric overall outperforms the widely used Fréchet Audio Distance. Currently, we are conducting a listening study to verify our results and inform future research. 

# Future Research
## Better Evaluation for Music Generation
Evaluation is underexplored for music generation, and an immediate effort to alleviate this is to set up protocols to scalably collect ratings on music generated through one-round interactions (e.g., arena-style evaluation). In the long run, I am interested in evaluating music generation more holistically and under setups that may realistically occur during interactions. Ideally, human users interact with models in a multi-round, collaborative fashion (e.g., The user writes a melody, the model generates the accompaniment, and the user edits the generated music and writes a new melody as a continuation, repeating the process). This process involves many aspects that cannot be easily assessed by examining the end product (e.g., can the model infer the key I play in? Can it anticipate when I want to move on to the next section of the song?). This necessitates something akin to a musical Turing Test. One way to cheaply approximate this setup would be to study LM-LM collaboration and use grounded downstream metrics for fine-grained evaluation.

## Understanding and Leveraging the Creative Process
Unlike language models, humans do not use a sequential, autoregressive process to create music. By using the autoregressive formulation, we are missing out on an opportunity to make models more compatible with interactive applications. I am interested in collecting and leveraging data regarding the creative process. For instance, we can collect traces of digital audio workstation (DAW) uses from processing tutorial videos or song-writing hackathons. This sort of data can be tremendously useful. Aside from building models that factorize music creation in a more human-like way, I am interested in the locality aspect of music listening (during the creative process). The free lunch of the music domain is that we do not need an eye tracker to know which part of the song the user is listening to. This provides a scalable way to collect human “attention maps”, which can then be used for distantly supervised applications (e.g., concept discovery, dynamic inference time compute allocation, etc.).

## Universal Control Interfaces
Collaborative music creation with generative models involves diverse forms of control, many of which are difficult to account for beforehand (e.g., novel physical interfaces). I am interested in formulating and enabling a general way of conditioning generative models. Concretely, suppose we have a distribution of temporally varying control signals (e.g., sequences of keyboard presses corresponding to unaligned real music), can we learn a control mapping such that an acoustic music generative model’s decisions can be best explained by the key presses? One way to implement this would be to quantize the intermediate states of the acoustic model and decouple them such that one branch can maximize the sequence-level probability given by the control distribution.