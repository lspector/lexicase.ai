---
layout: page
title: About
permalink: /about/
---

# About Lexicase Selection

Lexicase selection is a parent selection method for evolutionary algorithms that was first introduced for genetic programming. Unlike traditional selection methods that aggregate fitness across all test cases, lexicase selection considers performance on individual test cases.

## How It Works

1. **Random Ordering**: For each selection event, the test cases are randomly shuffled
2. **Sequential Filtering**: Candidates are filtered based on performance on each test case in order
3. **Best Performance**: Only individuals with the best performance on the current test case advance
4. **Final Selection**: The process continues until one individual remains or all test cases are considered

## Advantages

- **Diversity Maintenance**: Helps maintain population diversity by considering different aspects of fitness
- **Specialist Solutions**: Allows specialists that excel on particular test cases to survive
- **No Aggregation**: Avoids the need to combine multiple objectives into a single fitness value

## Applications

Lexicase selection has been successfully applied to:
- Genetic programming
- Program synthesis
- Multi-objective optimization
- Automatic programming
- Software debugging

## Research

This selection method has been the subject of extensive research in the evolutionary computation community. It has shown particular promise in domains where maintaining diversity is crucial for finding high-quality solutions.

---

For more technical details, see the [Documentation](/docs) section.
