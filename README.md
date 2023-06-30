# A Numerically Exact Algorithm for the Bin Packing Problem

This page contains the online material of the paper entitled "A Numerically Exact Algorithm for the Bin Packing Problem" by R. Baldacci, S. Coniglio, J.F. Cordeau, and F. Furin. From it, the user can download the algorithm proposed in the paper and run it on the instances on which the experiments were conducted.

It also reports certified dual solutions to the linear-programming (LP) relaxation of the set-partitioning formulation of the Bin Packing Problem  (BPP)---to so-called Fractional Bin Packing Problem (FBPP)---for the instances of the Augmented Non-IRUP (ANI) class.

## BCCP algorithm

In order to compile the code (we used gcc version 13.1.0), access to the following packages is requered:
- CPLEX version 12.9
- Gurobi version 9.5.1
- SOPLEX 5.0.1

The code is compiled by
1. running the command unzip BCCF.zip
2. setting in Makefile_link CPX_LIB, GRB_LIB, and SOPLEXLIB to the local path of the three aforementioned packages
3. running the command make -f Makefile_link

One can test whether the code is running correctly by executing the script run_example.sh, which will run the BCCF algorithm on the (included) ANI instance 201_2500_NR_0.txt, using the included parameter file param_test_BPP-non-IRUP-2exp44.txt, which is the one that was used to run the algorithm in its best-performing configuration according to the paper.

The included parameter file corresponds to the description of the algorithm given in the paper, and is suitable for the solution of the ANI instances proposed in
Delorme, M., Iori, M. and Martello, S., 2016. Bin packing and cutting stock problems: Mathematical models and exact algorithms. European Journal of Operational Research, 255(1), pp.1-20.

More instances can be downloaded from the BPPLIB page at the url: https://site.unibo.it/operations-research/en/research/bpplib-a-bin-packing-problem-library.

Detailed instance-by-instance results obtained with the BCCF run with the configuration used in the paper are contained in the file results.ods.


# Rational infinite-precision dual solutions to the Fractional Bin Packing Problem (FBPP)

In the following, we report the names of the instances for which a certified dual solution has been found, the number of columns (patterns) generated by the extended-precision LP solver (SOPLEX) and its computing time (in seconds). We solve a total of:
- 50/50 instances with 201 items
- 50/50 instances with 402 items
- 50/50 instances with 600 items
- 24/50 instances with 801 items
- 15/50 instances with 1002 items.

The results are obtained by setting:
- K1 = 1E-13 (K1  corresponds to the precision that is used in the label-setting algorithm that solves the pricing problem as well as in the solver---SOPLEX---that is used for reoptimizing each LP relaxation)
- K2 = 1E-03 for the instances with 201, 402, and 800 items and K2 = 1E-05 for the instances with 600 and 1002 items (K2 coincides with the reduced cost value after which the code swithces from using Gurobi as LP solver to SOPLEX)
						
![image](https://user-images.githubusercontent.com/33290924/123983007-6e71de00-d9bb-11eb-82d6-0c6a3188819c.png)
			
![image](https://user-images.githubusercontent.com/33290924/123983038-76318280-d9bb-11eb-9047-822303b73c54.png)





