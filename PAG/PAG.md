# PAG (BE4M35PAG)

## Questions

- Describe basic communication operations used in parallel algorithms. Show cost analysis of one-to-all broadcast, all-to-all-broadcast, scatter, and all-to-all personalized communication on a ring, mesh, and hypercube. Describe All-Reduce and Preﬁx-Sum operations and outline their usage.

- Describe performance metrics and scalability for parallel systems. How efficiency of a parallel algorithm depends on the problem size and the number of processors? Derive isoefficiency functions of a parallel algorithm for adding numbers (including communication between processors) and explain how it characterizes the algorithm.

- Explain and compare two parallel algorithms for matrix-vector multiplication. Describe a parallel algorithm for matrix-matrix multiplication and explain the idea of Cannon’s algorithm. Discuss the principle and properties of the DNS algorithm used for matrix-matrix multiplication.

- Outline the principle of sorting networks and describe parallel bitonic sort, including its scalability. Explain parallel enumeration sort algorithm on PRAM model, including its scalability.

- Explain all steps of a parallel algorithm for ﬁnding connected components in a graph given by the adjacency matrix. Using an example, illustrate a parallel algorithm for ﬁnding a maximal independent set in a sparse graph.

## Describe basic communication operations used in parallel algorithms. Show cost analysis of one-to-all broadcast, all-to-all-broadcast, scatter, and all-to-all personalized communication on a ring, mesh, and hypercube. Describe All-Reduce and Preﬁx-Sum operations and outline their usage.

### one-to-all

![alt text](one-to-all.png)

### all-to-all-broadcast

![alt text](a-to-a.png)
![alt text](a-to-a-2.png)
![alt text](a-to-a-cost.png)

### scatter/gatter

je to v principu one to all personalized

![alt text](scatter.png)
![alt text](scatter1.png)

### all-to-all personalized communication

![alt text](a-to-a-p-1.png)
![alt text](a-to-a-p-2.png)
![alt text](a-to-a-p-3.png)
![alt text](a-to-a-p-4.png)
![alt text](a-to-a-p-5.png)
![alt text](a-to-a-p-6.png)

### All-Reduce

![alt text](allreduce.png)

### Preﬁx-Sum

![alt text](prefixsum.png)
![alt text](prefixsum2.png)

Shrnutí vzorečků

![alt text](summary.png)


## Describe performance metrics and scalability for parallel systems. How efficiency of a parallel algorithm depends on the problem size and the number of processors? Derive isoefficiency functions of a parallel algorithm for adding numbers (including communication between processors) and explain how it characterizes the algorithm.

### Describe performance metrics and scalability for parallel systems.

Výkonnostní metrika může být speedup. Na paperu jsou další related vzorečky.

![alt text](speedup.png)
![alt text](speedup-1.png)
![alt text](amdahl.png)

### How efficiency of a parallel algorithm depends on the problem size and the number of processors?

![alt text](efectivity.png)
![alt text](efectivity-1.png)
![alt text](price.png)
![alt text](dependency.png)
![alt text](graph.png)

### Derive isoefficiency functions of a parallel algorithm for adding numbers (including communication between processors) and explain how it characterizes the algorithm.

izoefektivní funkce = Určuje snadnost, s jakou může paralelní systém udržovat konstantní účinnost, a tím dosahovat zrychlení rostoucích úměrně počtu procesorů

![alt text](izo1.png)
![alt text](izo2.png)
![alt text](izo3.png)
![alt text](izo4.png)   
![alt text](izo5.png)