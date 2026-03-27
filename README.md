# IIRF-EVRP

This repository contains experimental results for the paper:

**"Solving Electric Vehicle Routing by Iterative Instance Refinement Framework"**

The repository provides processed solution outputs and statistics for EVRP benchmark instances.


---

## How to Read the Results

Each instance has a JSON file containing multiple independent runs and aggregated statistics.

Example:

```
solutions/E-X/E-n29-k4-s7/processed.json
```

---

## JSON Format

Each file follows this structure:

```json
{
  "runs": [...],
  "stats": {...},
  "global_best_*": ...
}
```

---

### Runs

`runs` contains results from multiple independent executions (typically 20 runs):

```json
{
  "run": 1,
  "best_true_total": 378.44,
  "inserted_routes": [...],
  "base_routes": [...]
}
```

* `best_true_total`: objective value of the best EV-feasible solution in this run
* `inserted_routes`: final EV-feasible routes (with charging stations inserted)
* `base_routes`: original routes before energy feasibility adjustments

---

### Global Best

* `global_best_true_total`: best solution across all runs
* `global_best_inserted_routes`: corresponding EV-feasible routes

---

### Statistics

```json
"stats": {
  "n_runs": 20,
  "min": 378.44,
  "mean": 378.44,
  "std": 0.0
}
```

* `min`: best objective value across runs
* `mean`: average performance
* `std`: stability of the algorithm

----------

## Use

Please cite

> Lin, T.-H., & Chen, Y.-p. (2026). Solving Electric Vehicle Routing by Iterative Instance Refinement Framework. In <i>Proceedings of 2026 IEEE Congress on Evolutionary Computation (CEC 2026)</i>.
