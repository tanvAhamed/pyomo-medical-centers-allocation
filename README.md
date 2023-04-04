# pyomo-medical-centers-allocation
Optimizing Medical Support Center Allocation During Natural Disasters

Natural disasters such as earthquakes can have devastating effects on communities, and providing efficient aid and support is crucial. One way to achieve this is through the application of optimization techniques, which can help allocate resources such as manpower, food, shelter, and medical supplies to the areas that need them the most. Medical support center allocation is also critical during natural disasters, and optimization can be used to allocate a limited number of centers based on factors such as population and travel time constraints. By maximizing the effective reachable population, optimization can ensure that medical assistance reaches those in need in a timely manner, ultimately saving lives and minimizing the impact of these disasters on affected communities.

We can formulate the problem as a Mixed Integer Linear Programming (MILP) problem to allocate a limited number of medical support centers in a way that maximizes the effective reachable population while satisfying certain constraints. Specifically, the problem requires that each point on a map should be reachable within t2 minutes and that a point is effectively reachable when it can be accessed by at least two medical centers within t1 minutes (where t1 is less than t2). We will use the CBC (Coin-or branch and cut) solver to solve the MILP problem. Additionally, we will exploit the Pyomo modeling language to formulate the optimization problem, which is a Python-based optimization modeling language.

Objective - To maximize the effective reachable population

Decision variables - Binary, which indicate whether or not a medical center is allocated at a particular location. Let x_i = 1 if a medical center is allocated at location i, and x_i = 0 otherwise.

Constraints -

Suppose there is a finite number of medical support centers (Nc) available, and we aim to allocate them while satisfying two constraints. 
  Firstly, a maximum number of medical support centers can be opened
  Secondly, every point on the map should be reachable within a given time limit t2. 
  Lastly, a point is considered effectively reachable only if it can be accessed by at least two medical centers within a shorter time limit t1 (t1<t2).
