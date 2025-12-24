BLP SECTION
This section contains the algorithms and benchmark instances for the disjointly constrained bilinear programs.
Algorithms
- PEA: This code implements the Polyhedra Expansion Algorithm(PEA). It solves the disjoint bilinear program using an iterative exploration of optimality polyhedrons. PEA treats the y variables as free and does not require bounds on them.
- Gurobi_Module: Python code that solves the BLP problems using the Gurobi Optimizer as a nonconvex optimization problem. A lower bound on the y variables is required for Gurobi to run.
Instances: The BLP instances are stored inside BLP.zip. They consist of 160 benchmark problems organized into 16 folders numbered 1 through 16. Each folder contains the following for every instance:
		An input file containing the full problem specificationas follows:
		Line 1: m = number of constraints in the x variables; Line 2: n = number of x variables; Line 3: p = number of y variables; Line 4: l = number of constraints in the y variables
		The next line contains the vector c. It has n entries separated by commas. This corresponds to the linear term c^T x.
		The next line contains the vector d. It has p entries separated by commas. This corresponds to the linear term d^T y.
		The next block contains the matrix Q. It is an n by p matrix written row by row. This defines the bilinear term x^T Q y.
		The next block contains the matrix A. It is an m by n matrix that defines the constraints A x = b.
		The next block contains the matrix E. It is an l by p matrix that defines the constraints E y >= f.
		The next line contains the vector b. It has m entries.
		The next line contains the vector f. It has l entries.
		The final line contains a lower bound for all y variables. This bound is used only when solving with Gurobi. It is not used by PEA, since PEA treats y as a free variable. The bound was added because Gurobi cannot solve these instances without at least one finite bound on the y variables.
		This ordering is the same for all instance files.
		An info file containing metadata about the instance. This includes the number of Kernel Problem 1 and Kernel Problem 2 components, the class selections for KP 1, the number of KP 1 problems in each class, the number of local minima, the number of global minima, and lists of global optimal points before and after transformation.
BIMATRIX SECTION
This section contains the algorithms and instances for the bimatrix game problems.
Algorithms
- PEA_BMX: Python code implementing the PEA algorithm for bimatrix games. This includes both a driver file and a solver file.
- R4b_bmx: Code for running the algorithm described by Zhen et al. on the bimatrix instances.
Instances: The bimatrix instances are stored inside Bimatrix.zip. This archive contains:
- Bimatrix instances: The bimatrix game instances used in the work of Zhen et al., provided in plain text format. These include the payoff matrices and any additional data needed to run the algorithms.
These bimatrix instances allow direct comparison between PEA, the Zhen et al. algorithm, and other methods for solving bimatrix games.

REQUIREMENTS
Python 3 NumPy Gurobi and the Gurobi Python interface. Any additional packages are listed in the code headers

CITATION
If you use these instances or algorithms in academic work, please cite the associated paper once it is accepted.
