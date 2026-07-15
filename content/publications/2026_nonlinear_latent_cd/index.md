---
title: "Nonlinear Causal Discovery in the Presence of Unobserved Variables"
date: 2026-01-01
<!-- publishDate: 2013-01-01 -->
authors: ["Stella Huang", "Qing Zhou"]
publication_types: ["2"]

featured: true
publication: "(Initial work published in dissertation, full paper in preparation)"
links:
  - icon_pack: fas
    icon: scroll
    name: Link
    url: 'https://escholarship.org/content/qt5w5539pc/qt5w5539pc.pdf'
---

## Abstract

We propose a framework for learning the ADMG under the nonlinear SEM in this work. Given the PAG, our method aims to infer the edge marks of all undetermined marks by evaluating and orienting edges sequentially. Our framework differentiates between edges that can be correctly oriented and those that cannot. To orient such edges, we employ a constraint-based strategy that first tests for potential latent confounding and then applies the likelihood ratio test to distinguish the causal direction.

For other edges, we compare the graph structure under different edge directions using estimated log-likelihood values obtained through an iterative parameter fitting procedure. The key to this procedure is to accurately capture the covariance term, which indicates the presence of a bidirected edge. Through this orientation framework, our method is able to infer substantially more edge marks in the PAG, thereby moving beyond standard equivalence-class information. Extensive numerical experiments demonstrate that our framework produces more accurate graph estimates than competing nonlinear ADMG and DAG learning methods across a wide range of functional forms, network sizes, and extent of latent confounding. Moreover, our approach consistently yields more informative graphs than both the exact PAG and estimated PAG alone, showing a substantial ability to refine partially identified structures and infer additional causal relations.

## Summary

- Learning (nonlinear) causal relations amongst observed variables when there are hidden/latent variables present

- Objective: learn the maximal ancestral graph (MAG), where variables are connected by directed edges (X -> Y) or bi-directed edges (X <-> Y) that indicate causal relations and confounding relations, respectively

- Involves residual independence testing, log-likelihood estimation, and model selection methods to determine (1) the existence of confounders and (2) causal relations, when possible

## Methodology

To determine the orientatation of undirected edges (->, <-, <->), either having causal or confounding relations, we employ two strategies
	
1. Graphical criterion to orient edges by conditional independence tests
    - Orientation by conditional independence tests typically requiring iterative testing, which is computationally inefficient and subject to inflated Type I errors
    - Utilized graphical properties to determine whether any observed, neighboring nodes are confounders between two variables
    - If no confounders exist among observed variables relative to a pair of variables, then we can determine their causal/confounding relation in one pass

2. Orientation by nonlinear likelihood estimation for mixed graphs
    - Mixed graphs contain both directed and bidirected edges, with the latter indicating the presence of a latent variable, so the likelihood estimation is more complex
    - Implemented a joint regression of two variables (X,Y) in PyTorch to estimate their residual terms and covariance to compute the likelihood
    - Determines the edge orientation of two nodes using the log-likelihood only given their observed parent nodes, opposed to using the entire graph

