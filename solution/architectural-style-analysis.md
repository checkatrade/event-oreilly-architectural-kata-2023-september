# Architectural Style Analysis

Here we take our primary architectural characteristics, and compare them with architectural styles in a scoring matrix. We acknowledge a bias towards event-driven microservices based on the large scale, resilient requirements combined with reasonably clear external events that on the surface appear to lend themselves to asynchronous workloads.

| Capability | Layered	| Modular Monolith	| Micro Kernel	| Microservices	| Service-Based	| Service-Oriented	| Event-Driven	| Space-Based |
|--|--|--|--|--|--|--|--|--|
|fault-tolerance	| 1	| 1	| 1	| 5	| 4	| 3	| 5	| 3 |
|interoperability	| 1	| 1	| 3	| 3	| 2	| 5	| 3	| 2 |
|scalability	| 1	| 1	| 1	| 5	| 3	| 3	| 5	| 5 |
|**Totals**	| **3**	| **3**	| **5**	| **13**| 	**9**| 	**11**| 	**13**| 	**10**|

Based on this matrix, these characteristics favour Micro-Services / Event-Driven architectures. This could be confirmation bias, but it is nevertheless an evidenced starting point to act from for sketching our solution ideas.

## References

- [Fundamentals of Software Architecture](https://learning.oreilly.com/library/view/fundamentals-of-software/9781492043447/), Richards & Ford, 2020
- [Dev Cheat Sheets](https://www.developertoarchitect.com/resources.html), developertoarchitect.com