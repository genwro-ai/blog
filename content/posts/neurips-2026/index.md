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

They cover a good part of what we work on: counterfactual explanations, rare-event simulation, film and image restoration, the geometry of learned representations, medical imaging and LLMs in clinical triage. Below is the full list with abstracts. Names in bold are genwro.AI members.

## Main Track

### CounterFlowNet: From Minimal Changes to Meaningful Counterfactual Explanations

**Oleksii Furman**, Patryk Marszałek, Jan Masłowski, Piotr Gaiński, **Maciej Zięba**, Marek Śmieja · [arXiv](https://arxiv.org/abs/2602.17244)

Counterfactual explanations (CFs) provide human-interpretable insights into model's predictions by identifying minimal changes to input features that would alter the model's output. However, existing methods struggle to generate multiple high-quality explanations that (1) affect only a small portion of the features, (2) can be applied to tabular data with heterogeneous features, and (3) are consistent with the user-defined constraints. We propose CounterFlowNet, a generative approach that formulates CF generation as sequential feature modification using conditional Generative Flow Networks (GFlowNet). CounterFlowNet is trained to sample CFs proportionally to a user-specified reward function that can encode key CF desiderata: validity, sparsity, proximity and plausibility, encouraging high-quality explanations. The sequential formulation yields highly sparse edits, while a unified action space seamlessly supports continuous and categorical features. Moreover, actionability constraints, such as immutability and monotonicity of features, can be enforced at inference time via action masking, without retraining. Experiments on eight datasets under two evaluation protocols demonstrate that CounterFlowNet achieves superior trade-offs between validity, sparsity, plausibility, and diversity with full satisfaction of the given constraints.

### Robust Importance Sampling for Rare Events via Constrained Gaussian Mixtures

Paweł Lorek, Rafał Nowak, Rafał Topolnicki, Tomasz Trzciński, **Maciej Zięba** · [arXiv](https://arxiv.org/abs/2610.07485)

We study estimating rare-event probabilities $I = \mathbb{P}(g(\mathbf{X}) > γ)$ with $\mathbf{X} \sim \mathcal{N}(\boldsymbol{\mu}, \boldsymbol{\Sigma})$ and general $g : \mathbb{R}^d \to \mathbb{R}$. We address this problem through importance sampling, and propose a framework that substantially improves efficiency and robustness over baselines such as crude Monte Carlo, adaptive cross-entropy, variational-inference-based methods (including reverse- and forward-KL approaches), as well as Safe-ICE, Subset Simulation, and Sequential Monte Carlo, drawing on ideas from both rare-event estimation and cross-entropy optimization. The key contribution has two parts: first, we separate the problem into coverage, to overcome the cold-start barrier, and fitting, to refine proposals once a meaningful signal is available; second, we constrain the final GMM proposal so that it has finite importance-sampling variance (since coverage alone is not sufficient -- without safeguards, importance sampling may still suffer from infinite variance). Together, these ingredients yield expressive proposals; finite variance does not by itself guarantee practical stability at a fixed sampling budget. Extensive experiments demonstrate substantial variance reduction, strong robustness across diverse benchmarks, and favorable cost--efficiency trade-offs, with the proposed approach often outperforming these baselines, particularly in high-dimensional and multimodal settings where competing methods frequently become unstable or fail. Our code is available at https://github.com/lorek/robust-cfi-is.

## Datasets & Benchmarks

### AbsoluteDegradation: A Physics-Inspired Synthetic Film-Degradation Pipeline and Archival Film Restoration Benchmark

Mikołaj Jastrzębski, Dawid Glinkowski, Dawid Zieliński, Daniel Borkowski, **Wojciech Kozłowski**, **Kamil Adamczewski** · [arXiv](https://arxiv.org/abs/2607.02131)

Restoring archival film remains a fundamentally challenging problem due to the absence of paired training data and the lack of standardized evaluation benchmarks. Pristine versions of deteriorated footage are physically unrecoverable, requiring supervised methods to rely on synthetic data that often fail to capture the complex, temporally coherent nature of real film degradation. At the same time, existing real-world datasets are limited in scale, quality, and accessibility, hindering reliable evaluation and fair comparison across methods. We address both limitations with AbsoluteDegradation, a physics-inspired, modular pipeline for synthesizing realistic film degradations, and a new large-scale archival benchmark. The proposed pipeline models the analog-to-digital process as a structured composition of artifact families, incorporating signal-dependent grain, parametric scratches, and temporally coherent camera motion, enabling controlled generation of diverse degradation regimes. In parallel, we introduce a curated dataset of 81,576 high-resolution frames sourced from real archival footage, designed for consistent evaluation under real-world conditions. Together, these contributions provide a unified framework for training and benchmarking restoration models. Extensive experiments across multiple architectures show that models trained with AbsoluteDegradation generalize better to real-world footage, while the proposed benchmark reveals systematic failure modes of current methods. We hope this work establishes a foundation for reproducible and domain-authentic evaluation in archival film restoration.

## Workshops

### Robust to Which Model Change? A Unified Evaluation of Robust Counterfactual Explanations

{{< venue "Trust-AI-Eval workshop" >}}

**Marcin Kostrzewa**, **Maciej Zięba** · [arXiv](https://arxiv.org/abs/2609.30918)

Robust counterfactual explanations promise recourse that still works after the model behind it changes. Whether they keep that promise depends on what the change is. A small perturbation of the parameters, retraining on new data, and a new architecture are different events, and each existing method is evaluated against the one it was built for. Reported robustness scores, therefore, answer different questions and cannot be compared. We propose a unified cross-family evaluation protocol that holds factual instances and generated counterfactuals fixed while testing every method against the same eight types of model change. The benchmark compares six robust methods and two standard baselines on four tabular datasets. It characterizes every changed classifier through its outputs and reports empirical robustness together with coverage, base validity, and proximity. We find that relative performance and failure modes vary across change families. Bounded parameter perturbations change 0.95% of test predictions on average, compared with 4.9% for bootstrap retraining. Methods with guarantees for these perturbations do not necessarily transfer to other changes. RobX transfers most consistently in our experiments, although greater stability can require larger interventions. We argue that robust CFE methods should be evaluated through a common protocol that specifies the model changes, measures their realized behavioral magnitude, and keeps generation performance separate from robustness.

### Beyond Local Linearity: Scale-Resolved Geometry of Learned Image Encoders

{{< venue "NeurReps workshop" >}}

Jakub Szymkowiak, Wojtek Pałubicki, **Kamil Adamczewski** · [arXiv](https://arxiv.org/abs/2609.39115)

Understanding how learned representations respond to finite input changes is important for characterizing their sensitivity, invariances, and robustness. Yet existing geometric analyses are predominantly local and describe only infinitesimal perturbations. We introduce a scale-resolved statistic that compares an encoder's measured feature displacement with its local linear prediction as the perturbation magnitude increases. Across diverse image encoders, we discover a characteristic plateau-rise-peak-decay profile, which we call the bump. The bump is absent at initialization, emerges early during standard training, and does not form under randomized labels or random-noise inputs. Its shape also varies with the training distribution and robustness objective. These results establish departures from local geometry as a signature of how encoder representations are shaped by learning.

### CyFM: Cylindrical Optimal Transport for Few-Step Complex-Valued Flow Matching

{{< venue "GDDL workshop" >}}

Marcel Musiałek, Iga Wolanin, Damian Ryczko, Anna Grelewska, **Oleksii Furman** · [arXiv](https://arxiv.org/abs/2609.14171)

Complex-valued signals like MRI and audio spectrograms are typically modelled as flat two-channel Euclidean data. The inherited Euclidean metric $dA^2 + A^2 dθ^2$ vanishes at the origin, leaving phase unpenalised exactly where the signal is weakest. We replace it with the decoupled product metric $dA^2 + dθ^2$ on the cylindrical closure $[0, \infty) \times S^1$, which stays non-degenerate at $A = 0$. We measure what this substitution costs and buys. Exact analytical bridges across synthetic fields, fastMRI knee data, and LibriSpeech spectrograms show Cartesian paths induce a heavy-tailed angular velocity distribution (Pareto index $\approx 1$). Under independent coupling, 43%-49% of signal energy falls on paths turning faster than $π$ rad per unit time. Cylindrical paths never reach this speed. We formulate Cylindrical Flow Matching (CyFM) to strictly bound the angular regression target, coupling noise and data via exact minibatch Optimal Transport jointly over whole fields. This coupling reduces few-step generation error by 3%-60%. CyFM achieves lower generative error than the best Cartesian baseline at every step up to $k = 8$ on synthetic fields and speech spectrograms, with all seeds separated. On knee MRI, the single-step advantage is 1.8x. At convergence ($k = 100$), the two geometries show no significant difference. Finally, a prior-only control exposes the cost of flat parametrisation: on synthetic fields, a single Cartesian Euler step performs worse than the unintegrated noise prior (0.376 vs. 0.150).

### SADGE: Spatially-Adaptive Diffusion Guided by Estimated Degradation for Image Restoration

{{< venue "AI for Stochastic Dynamics workshop" >}}

Dominik Galus, Michał Furgała, Piotr Ryszko, **Wojciech Kozłowski**

A diffusion restoration method that concentrates on damaged regions and reduces hallucinations. It was developed with the Solvro student research club.

### ALLMTS: Automated LLM-based Medical Triage System

{{< venue "GenAI4Health workshop" >}}

Michał Remigiusz Janiszewski, Artur Stopa, **Łukasz Lenkiewicz**, Wojciech Achtelik, Bartosz Adam Gonczarek

A triage system in which an LLM executes clinical guidelines rather than guessing. It reaches 95% accuracy, compared with 47% for a raw LLM.
