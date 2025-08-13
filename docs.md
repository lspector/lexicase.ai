---
layout: page
title: Documentation
permalink: /docs/
---

# Documentation

This section provides technical documentation for implementing and using lexicase selection.

## Algorithm Pseudocode

```
function lexicase_selection(population, test_cases):
    shuffle(test_cases)  // Random ordering of test cases
    candidates = copy(population)
    
    for each test_case in test_cases:
        if length(candidates) <= 1:
            break
            
        best_performance = find_best_performance(candidates, test_case)
        candidates = filter_by_performance(candidates, test_case, best_performance)
    
    return random_choice(candidates)
```

## Implementation Notes

### Performance Evaluation
- Each individual must be evaluated on all test cases
- Performance can be measured as fitness, error, or any other metric
- Lower values typically indicate better performance (minimization)

### Test Case Management
- Test cases should be diverse and representative
- The number of test cases affects selection pressure
- Dynamic test case generation can be beneficial

### Variants

#### Epsilon Lexicase
Allows individuals within an epsilon threshold to be considered equivalent:

```
best_performance = find_best_performance(candidates, test_case)
threshold = best_performance + epsilon
candidates = filter_by_threshold(candidates, test_case, threshold)
```

#### Down-sampled Lexicase
Uses a subset of test cases for each selection event to reduce computational cost.

## Parameters

| Parameter | Description | Typical Values |
|-----------|-------------|----------------|
| Population Size | Number of individuals | 100-1000 |
| Test Cases | Number of evaluation cases | 10-100+ |
| Epsilon | Tolerance threshold | 0.0-1.0 |
| Sample Rate | Fraction of test cases used | 0.1-1.0 |

## Performance Considerations

- **Time Complexity**: O(n × m) where n is population size and m is number of test cases
- **Memory**: Requires storing performance on all test cases
- **Parallelization**: Test case evaluation can be parallelized

## Example Use Cases

### Program Synthesis
```python
# Test cases for sorting function
test_cases = [
    ([3, 1, 4], [1, 3, 4]),
    ([5, 2], [2, 5]),
    ([], []),
    ([1], [1])
]
```

### Symbolic Regression
```python
# Test cases for mathematical function
test_cases = [
    (x=0, expected=1),
    (x=1, expected=2),
    (x=2, expected=5),
    (x=3, expected=10)
]
```

## References

- Spector, L. (2012). Assessment of problem modality by differential performance of lexicase selection in genetic programming
- Helmuth, T., Spector, L., & Matheson, J. (2015). Solving uncompromising problems with lexicase selection
- La Cava, W., Spector, L., & Danai, K. (2016). Epsilon-lexicase selection for regression

---

*For implementation examples and code samples, visit our [GitHub repository](https://github.com/nlorant-s/lexicase.github.io).*
