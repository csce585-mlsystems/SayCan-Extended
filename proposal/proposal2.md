# Project Proposal: Improving SayCan's Robotic Planning Through Enhanced Language-Action Grounding

## Problem Statement
We aim to enhance the open-source tabletop implementation of SayCan to better ground language instructions to robotic actions. The current implementation relies on simple object detection for affordances rather than learned value functions, and uses a basic prompt template for language model planning. This leads to potential misalignments between what the language model thinks is possible and what the robot can actually accomplish.

This is an interesting problem because:
1. It bridges the gap between large language models and robotic control
2. It explores how to ground abstract language in concrete robotic capabilities
3. It has practical applications for more intuitive human-robot interaction
4. The open-source implementation provides a controlled environment for systematic improvements

## Background Reading
Our primary sources will include:
- "Do As I Can, Not As I Say: Grounding Language in Robotic Affordances" (Ahn et al., 2022)
- "Language Models as Zero-Shot Planners" (Huang et al., 2022) 
- "CLIPort: What and Where Pathways for Robotic Manipulation" (Shridhar et al., 2022)
- "Inner Monologue: Embodied Reasoning through Planning with Language Models" (Huang et al., 2022)

## Data
We will use the existing tabletop simulation environment with:
- Synthetic data generated through the PyBullet simulator
- A dataset of language instructions and corresponding action sequences
- Training data for CLIPort-style manipulation policies

We plan to expand the dataset with:
- Additional language instruction templates
- More complex multi-step manipulation sequences
- Diverse object configurations and relationships

## Proposed Method
We will improve the current implementation in several ways:
1. Replace the ViLD object detection affordance scoring with a learned value function:
   - Train a CLIPort-style policy with a value head
   - Use reinforcement learning to learn affordances directly from interaction
   
2. Enhance the language model prompting:
   - Implement chain-of-thought reasoning for complex tasks
   - Add structured reasoning about physical constraints
   - Incorporate feedback from failed attempts

3. Add closed-loop execution:
   - Monitor task progress and detect failures
   - Enable recovery and replanning
   - Implement interactive clarification dialogues

## Evaluation
Qualitative evaluation:
- Visualizations of affordance predictions
- Analysis of generated plans and reasoning steps
- Videos demonstrating complex multi-step tasks
- Examples of failure recovery and replanning

Quantitative metrics:
- Success rate on standard pick-and-place tasks
- Success rate on novel compositional tasks
- Planning time and execution efficiency 
- Accuracy of affordance predictions
- Language-action alignment scores

We will evaluate on both:
- A test set of standard tasks from the original paper
- Novel tasks requiring composition of learned skills
- Edge cases that test generalization and robustness

Our goal is to demonstrate improved performance particularly on:
1. Multi-step tasks requiring precise ordering
2. Recovery from failures or unexpected situations
