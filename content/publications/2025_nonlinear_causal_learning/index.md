---
title: "Nonlinear Causal Discovery through a Sequential Edge Orientation Approach"
date: 2025-06-04
<!-- publishDate: 2013-01-01 -->
authors: ["Stella Huang", "Qing Zhou"]
publication_types: ["2"]
abstract: "Recent advances have established the identifiability of a directed acyclic graph (DAG) under additive noise models (ANMs), spurring the development of various causal discovery methods. However, most existing methods make restrictive model assumptions, rely heavily on general independence tests, or require substantial computational time. To address these limitations, we propose a sequential procedure to orient undirected edges in a completed partial DAG (CPDAG), representing an equivalence class of DAGs, by leveraging the pairwise additive noise model (PANM) to identify their causal directions. We prove that this procedure can recover the true causal DAG assuming a restricted ANM. Building on this result, we develop a novel constraint-based algorithm for learning causal DAGs under nonlinear ANMs. Given an estimated CPDAG, we develop a ranking procedure that sorts undirected edges by their adherence to the PANM, which defines an evaluation order of the edges. To determine the edge direction, we devise a statistical test that compares the log-likelihood values, evaluated with respect to the competing directions, of a sub-graph comprising just the candidate nodes and their identified parents in the partial DAG. We further establish the structural learning consistency of our algorithm in the large-sample limit. Extensive experiments on synthetic and real-world datasets demonstrate that our method is computationally efficient, robust to model misspecification, and consistently outperforms many existing nonlinear DAG learning methods."

featured: true
publication: "(Under review at the Journal of Machine Learning Research)"
links:
  - icon_pack: fas
    icon: scroll
    name: Link
    url: 'https://arxiv.org/abs/2506.05590'
  - icon_pack: fas
    icon: laptop-code
    name: R Package
    url: 'https://github.com/stehuang/snoe'
  - icon_pack: fas
    icon: image
    name: Poster
    url: '/files/acic_poster.png'

---

## Abstract

Recent advances have established the identifiability of a directed acyclic graph (DAG) under additive noise models (ANMs), spurring the development of various causal discovery methods. However, most existing methods make restrictive model assumptions, rely heavily on general independence tests, or require substantial computational time. To address these limitations, we propose a sequential procedure to orient undirected edges in a completed partial DAG (CPDAG), representing an equivalence class of DAGs, by leveraging the pairwise additive noise model (PANM) to identify their causal directions. We prove that this procedure can recover the true causal DAG assuming a restricted ANM. Building on this result, we develop a novel constraint-based algorithm for learning causal DAGs under nonlinear ANMs. Given an estimated CPDAG, we develop a ranking procedure that sorts undirected edges by their adherence to the PANM, which defines an evaluation order of the edges. To determine the edge direction, we devise a statistical test that compares the log-likelihood values, evaluated with respect to the competing directions, of a sub-graph comprising just the candidate nodes and their identified parents in the partial DAG. We further establish the structural learning consistency of our algorithm in the large-sample limit. Extensive experiments on synthetic and real-world datasets demonstrate that our method is computationally efficient, robust to model misspecification, and consistently outperforms many existing nonlinear DAG learning methods.


## Summary

- Developed a scalable algorithm to determine (nonlinear) causal relations given the Markov Equivalence Class, or from any partially directed graph

- Algorithm consists of 4 steps:
	1. Learn the Markov Equivalence Class
	2. Orient all undirected edges in a sequential, ordered manner using a likelihood-based test to determine the causal direction
	3. Prune the learned graph to remove false positives
	4. Orient remaining undirected edges by applying the sequential orientation procedure again

- Shows (1) consistent performance across linear/invertible/non-invertible functions types, (2) higher F1 scores against competing methods, and (3) near 10-fold reduction in algorithm runtime

## Methodology

To determine the causal direction of undirected edges (pairs of variables in graph with no edge direction), we created the two original components:
	
1. Ranking procedure for undirected edges (undetermined causal directions): 
  - Ranking undirected edges based on metric that measures adherence to model assumptions (need independence between residual term and covariate)
  - Naturally produces an evaluation order that allows for correct inference, avoiding possible latent variables

2. Likelihood-ratio test for causality: 
  - Employing a likelihood-ratio test to compare and determine the competing directions X -> Y and Y -> X
  - Accounts for statistical significance in addition to the magnitude of the log-likelihood values




















