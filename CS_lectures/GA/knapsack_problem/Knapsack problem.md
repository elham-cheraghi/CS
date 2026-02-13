
<!-- .slide: data-vertical-align="top" -->

### Genetic Algorithms
<div align="center">solving optimization problem inspired by nature</div>

---
The problem
let's say you want to go on a trip and all you can bring with you is 3 kilograms of hand luggage so yo wanna make best out of it you can choose between a laptop ,headphones, coffee mug, notepad and water bottle 

---

![[k2.png]]

---
### What is the correct solution?
---
![[k1.png]]

for total value of 740
and the weight of 2.9 kilograms

---
that was not so hard our brain is good at finding a good solution or with the small number of items finding the best solution relatively quick.

---
### let's add some more items shall we?

---
![[k3.png]]

---
### What do you think the answer is ?
---

----

![[k4.png]]

---
>| ITEMS        | COMB. | SECONDS        |
|-------------|----------|--------------|
|5    | 32        | 0.000003   |
|10    | 1.024       | 0.000807        |

---
Genetic Algorithms 
GA can be used to generate solutions for problems for which we have no way to calculate a solution and that is what we need right now .
genetic algorithm are part of a bigger group of algorithm called **Evolutionary Algorithms**  and they use natural selection to approximate solutions for a given problem you can use it to generate pack list for your backpack. But  another way is to use it generate form of an antenna  as done by NASA in 2006.This is called an Evolve antenna. Which a genetic algorithm generate to find the best radiation pattern.

---
genetic algorithm uses a population of possible solutions in our case there would be combination of items in our backpack .

---
![[k6.png]]

---
Each specimen in our population has a genome that encode solution it's a binary encoding of the content.
In a **genetic algorithm (GA)**:

- A **population** = a group of possible solutions
    
- Each **specimen (individual)** = one candidate solution
    
- The **genome (or chromosome)** = the way we _encode_ that solution so the algorithm can modify it
    

Think of the genome as a **list of values that describes the solution**.

---
![[k7.png]]

---
1 says that this item is inside the backpack and when there is 0 its left out.

---
the sets of all current solution at a given point during the algorithm is called the generation .generation 0 the starting generation is just random mess of possible solution. so we start our evolutionary process with complete chaos.

---
![[k8.png]]

---
### Natural Selection 

---
we use a fitness function to determine how good a given solution is. in our case the fitness function returns a value of the packet items as long as it fits into the weight limit.

---
![[k10.png]]

---
If the weight limit succeeded the fitness of specimen is 0.

---
![[k11.png]]

---
after that we are selecting parent for the next generation we use the high fitness core.

---
![[k12.png]]

---
we choose  2 parents and cut their gnome at the random spot in half and switch the  ending this is called SINGLE POINT CROSSOVER FUNCTION.
and select 2 new solutions for the next generation

---
![[k13.png]]

---

![[k14.png]]

---
we repeat the process as long as we don't have enough specimen for the next generation how by crossing 2 solutions we got a better one .the selection and cross over function is governed by randomness and no way to guarantee that we won't destroy our best solution that's where a process called elitism comes in 
In **genetic algorithms**, _elitism_ means:

> Always keep the **best solutions** from one generation so they are NOT lost.
> we select top solution and just copy them into the next generation we will just keep our top 2
---
the next step in evolution is mutation .mutation helps to discover new solution 
during mutation we simply change random bit of the gnome with a certain probability 
that's it here are new generation
---
![[k16.png]]
---
![[k17.png]]
---
![[k19.png]]

---
### what happen after we produce new generation?
---

We repeat the same steps:

### Evaluate them again

For every solution in the new generation:

- calculate fitness
    
- check weight limits (for knapsack)
    
- see which ones are good / bad
    

So we ask again:
How good is each solution now?

---
### Select the best again

We choose parents **from this new generation**.

Better fitness → higher chance to be chosen.

Bad ones usually disappear.


----
### Crossover again

We mix parents again to create children:

`Parent + Parent → Child`

We hope to combine good parts.

---
### Mutation again

Sometimes:

- flip a bit
    
- change a value
    
- create something new
    

Just a _tiny_ amount of randomness.

---
### Build another new generation

Old population is replaced, and now:

> **Generation 2 → Generation 3 → Generation 4…**

Each time, solutions (on average) become **better**.

---
# When do we STOP?

### We don’t loop forever.

### We stop when one of these happens:

 we reach a set number of generations  
 best fitness doesn’t improve anymore  
 time runs out  
we find a solution that is “good enough”

Then we say:
This is the best solution the GA found

---
<!-- .slide: data-vertical-align="top" -->
#### What is a genetic algorithm?
A genetic algorithm is a search method inspired by biological evolution.
It finds good(not always perfect) solutions to difficult problems.

Try many solutions → keep the best → improve them step by step.

---
Why Do We Need GAs?
Some problems have:

- Enormous search spaces
    
- No fast exact algorithm
    
- Many constraints
    

GAs help us find **good answers quickly** when trying everything is impossible.

---
Main Concepts
- **Population** — group of possible solutions
    
- **Chromosome** — one solution
    
- **Gene** — part of a solution
    
- **Fitness** — how good a solution is

---
Evolution Idea
GAs mimic nature:

1. Selection — choose better solutions
    
2. Crossover — mix parents
    
3. Mutation — small random change
    
4. Repeat over generations
    

Better solutions survive and spread.

---
Representation (Chromosomes)

We must encode a solution as data.

Examples:

- Binary string: `1 0 1 1`
    
- Sequence / order of items
    
- Real numbers
    

The representation must match the problem.

---
Fitness Function

The **fitness function** measures quality:

> Higher fitness = better solution.

Examples:

- Maximize profit
    
- Minimize distance
    
- Balance constraints
    

Bad or invalid solutions get **low fitness**.

---
Selection
We prefer better individuals to reproduce.

Common methods:

- Roulette wheel
    
- Tournament
    
- Rank-based
    

Goal: give high-fitness solutions more chance to continue.

---
Crossover (Recombination)

Combine two parents to create children.

Example (cut and swap):

Parent A: `1 1 | 0 0`  
Parent B: `0 0 | 1 1`

Child: `1 1 1 1`

It mixes good traits from each parent.

---
Mutation

Occasionally flip or change a gene:

`1 0 1 0` → `1 1 1 0`

Why?

- Prevents getting stuck
    
- Explores new possibilities
    
- Adds diversity
    

Mutation is **small and rare**.

---
GA Cycle (Overview)

1. Initialize population  
2. Evaluate fitness  
3. Select parents  
4. Apply crossover  
5. Apply mutation  
6. Form new population  
7. Repeat until stopping condition

---
Stopping Conditions

Stop when:

- Max generations reached
    
- No improvement
    
- Time limit exceeded
    
- Solution is “good enough”
---
# Knapsack Problem (Intro)

ou have:

- A bag with **limited capacity**
    
- Items with weight + value
    

Goal:

> Choose items to maximize value without exceeding capacity.

---

Chromosome representation (binary):

`1` = take item  
`0` = skip item

Example:  
`1 0 1 1` → take items 1, 3, and 4.

Fitness:

- Sum values
    
- Penalize overweight solutions
---
