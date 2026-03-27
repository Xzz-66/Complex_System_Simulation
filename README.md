# Complex System Simulation: Prisoner's Dilemma on Networks

This repository contains a project for the course **Complex System Simulation**.  
The project studies how **cooperation emerges and persists on networks** using the **Prisoner’s Dilemma** as the interaction model.

The main goal is to understand how network structure, update rules, and control parameters affect long-run cooperation, cooperative cluster formation, and possible phase-transition-like behavior. 

## Project Overview

Agents are placed on a graph \(G=(V,E)\). Each agent chooses either:

- **C**: cooperate
- **D**: defect

At each time step, agents interact with their neighbors and update their strategies according to a chosen rule. The project investigates several research questions, including: 

- Can cooperation persist instead of collapsing to full defection?
- Which network structures promote cooperation?
- Do cooperators form small islands or large stable clusters?
- Are there threshold effects or percolation-like transitions?
- Does rewiring the network help stabilize cooperation?

## Research Questions

The project is organized around the following questions: 

### RQ0: Baseline existence
Can cooperation persist under a given network family, payoff setting, and update rule?

### RQ1: Network architecture
How do different network structures affect long-run cooperation and local assortment?

### RQ2: Cooperative clusters
When cooperation exists, does it appear as many small clusters or one large cooperative component?

### RQ3: Phase transitions
As a control parameter such as temptation or noise varies, is there a threshold where the cooperative subgraph changes sharply?

### RQ4: Endogenous rewiring
If edges are allowed to rewire, does coevolution of network structure and strategies stabilize cooperation?

## Measurements

To answer these questions, the project uses several quantitative measurements, including: 

- global cooperation fraction
- long-run average cooperation
- fixation probability of all-cooperate and all-defect states
- time to absorption or stationarity
- neighbor cooperation correlation (assortment)
- size of the largest cooperative component
- cluster size distribution
- Jaccard stability of cooperative sets
- susceptibility-like measure for cooperative clusters
- edge-type fractions such as CC, CD, and DD

## Network Models

The project compares several network families under matched settings such as network size and mean degree. Recommended network types include: 

- 2D lattice / grid
- Erdős–Rényi (ER)
- Watts–Strogatz (WS)
- Barabási–Albert (BA)
- degree-corrected stochastic block model (DC-SBM)

These networks differ in clustering, path length, heterogeneity, and modularity, which may all influence cooperation.

## Interaction Model

The main game is the **Prisoner’s Dilemma**, implemented either with canonical payoff notation \((T,R,P,S)\) or with the donation-game form using benefit \(b\) and cost \(c\). Agents play with all neighbors and accumulate payoff over the network.  

The project can compare:

- accumulated payoff
- normalized payoff

and different update schemes such as:

- imitate-best
- Fermi rule
- synchronous updates
- asynchronous updates 

## Files

### `Prison.py`
Main Python script for simulating the Prisoner’s Dilemma on networks.  
This file likely contains the core game logic, network interaction rules, and update dynamics.

### `RQ0.ipynb`
Notebook for **RQ0: Baseline existence**.  
Focuses on whether cooperation can persist under selected network and payoff settings.

### `RQ1.ipynb`
Notebook for **RQ1: Network architecture**.  
Compares how different graph structures influence long-run cooperation and assortment.

### `RQ2.ipynb`
Notebook for **RQ2: Cooperative clusters**.  
Studies the size, morphology, and temporal stability of cooperative components.

### `RQ3.ipynb`
Notebook for **RQ3: Phase transitions / percolation-like behavior**.  
Analyzes whether varying a control parameter leads to sharp transitions in cooperative structure.

### `Assumption_and_Equation.pdf`
Project summary document containing the formal research questions, hypotheses, model assumptions, measurements, and implementation plan.  

## Methods

The project combines:

- agent-based simulation on graphs
- repeated runs under different random seeds
- network comparison under matched controls
- time-series analysis of cooperation
- connected-component analysis of cooperative subgraphs
- parameter sweeps for threshold detection
- optional rewiring dynamics

## Hypotheses

The project is guided by several hypotheses, including: 

- higher clustering may support cooperation
- degree heterogeneity may help or hurt depending on payoff normalization and update rule
- stronger community structure may reinforce within-group cooperation
- high-cooperation regimes should correspond to larger cooperative components
- cooperative phase transitions may appear as sharp increases in largest-cluster size and peaks in susceptibility
- cooperator-favoring rewiring may increase long-run cooperation

## How to Run

You can run the notebooks individually depending on the research question of interest.

A typical setup is:

```bash
pip install numpy pandas matplotlib networkx scipy jupyter
jupyter notebook
