---
date: '2026-10-09T14:00:00+02:00'
author: "genwro.AI"
draft: false
title: 'genwro.AI at NeurIPS 2026'
description: "Eight papers at NeurIPS 2026: two in the Main Track, one in Datasets & Benchmarks and five at workshops."
categories: ["news"]
tags: ["NeurIPS", "conferences", "counterfactual explanations", "generative models", "medical AI"]
ShowToc: false
cover:
  image: "cover.png"
  alt: "genwro.AI at NeurIPS 2026: 2 Main Track papers, 1 Datasets & Benchmarks paper and 5 workshop papers"
  relative: true
---

We'll be presenting eight papers at NeurIPS 2026. Two are in the Main Track, one is in the Datasets & Benchmarks track and five are at workshops.

They cover a good part of what we work on: counterfactual explanations, rare-event simulation, film and image restoration, the geometry of learned representations, medical imaging and LLMs in clinical triage. Below is the full list with a short note on each paper. Names in bold are genwro.AI members.

## Main Track

### CounterFlowNet: From Minimal Changes to Meaningful Counterfactual Explanations

**Oleksii Furman**, Patryk Marszałek, Jan Masłowski, Piotr Gaiński, **Maciej Zięba**, Marek Śmieja · [arXiv](https://arxiv.org/abs/2602.17244)

A counterfactual explanation should change as little as possible about the input and still make sense. CounterFlowNet produces explanations that do both.

### Robust Importance Sampling for Rare Events via Constrained Gaussian Mixtures

Paweł Lorek, Rafał Nowak, Rafał Topolnicki, Tomasz Trzciński, **Maciej Zięba**

An importance sampling method for rare events that gives stable estimates with provably finite variance, also in high dimensions.

## Datasets & Benchmarks

### AbsoluteDegradation: A Physics-Inspired Synthetic Film-Degradation Pipeline and Archival Film Restoration Benchmark

Mikołaj Jastrzębski, Dawid Glinkowski, Dawid Zieliński, Daniel Borkowski, **Wojciech Kozłowski**, **Kamil Adamczewski** · [arXiv](https://arxiv.org/abs/2607.02131)

A pipeline that applies realistic, physics-inspired damage to film footage, together with a benchmark for restoring archival film.

## Workshops

### Robust to Which Model Change? A Unified Evaluation of Robust Counterfactual Explanations

{{< venue "Trust-AI-Eval workshop" >}}

**Marcin Kostrzewa**, **Maciej Zięba** · [arXiv](https://arxiv.org/abs/2609.30918)

One evaluation protocol for robust counterfactual explanations, covering eight types of model change.

### Beyond Local Linearity: Scale-Resolved Geometry of Learned Image Encoders

{{< venue "NeurReps workshop" >}}

Jakub Szymkowiak, Wojtek Palubicki, **Kamil Adamczewski**

Image encoders carry a geometric signature that only emerges through learning.

### CyFM: Cylindrical Optimal Transport for Few-Step Complex-Valued Flow Matching

{{< venue "GDDL workshop" >}}

Marcel Musiałek, Iga Wolanin, Damian Ryczko, Anna Grelewska, **Oleksii Furman** · [arXiv](https://arxiv.org/abs/2609.14171)

Flow matching for complex-valued signals such as MRI, modelled in amplitude-phase coordinates. In single-step generation the error is up to 2.1× lower.

### SADGE: Spatially-Adaptive Diffusion Guided by Estimated Degradation for Image Restoration

{{< venue "STODY workshop" >}}

Dominik Galus, Michał Furgała, Piotr Ryszko, **Wojciech Kozłowski**

A diffusion-based restoration method that concentrates on the damaged regions of an image and hallucinates less. We built it together with the Solvro student research club.

### ALLMTS: Automated LLM-based Medical Triage System

{{< venue "GenAI4Health workshop" >}}

Michał Remigiusz Janiszewski, Artur Stopa, **Łukasz Lenkiewicz**, Wojciech Achtelik, Bartosz Adam Gonczarek

A triage system where the LLM executes clinical guidelines instead of guessing the answer. It reaches 95% accuracy; a raw LLM gets 47%.
