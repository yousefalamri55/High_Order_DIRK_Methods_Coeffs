# High_Order_DIRK_Methods_Coeffs

This repository accompanies the manuscript "VERY HIGH-ORDER A-STABLE STIFFLY ACCURATE DIAGONALLY
IMPLICIT RUNGE-KUTTA METHODS WITH ERROR ESTIMATORS" available here
https://arxiv.org/abs/2211.14574

It contains the coefficients (A,b) for a 6th, 7th, and 8th order DIRK-type methods and their embedded error estimators. The notation used is 
 $$\text{TYPE}(s,p)[r]X-[(\widehat{s},\widehat{p})Y]$$
where 

* TYPE: is the structure of the DIRK-type method, that is DIRK, EDIRK, SDIRK, or ESDIRK.
  
* $s$: number of stages for the advancing method.

* $p$: order of convergence for the advancing method.
* $r$: stage order of the advancing method.
* $X$: stability property of the advancing method; i.e., $A$ for A-stable, $L$ for L-stable, $SA$ for stiffly accurate, or $SAL$ if both stiffly accurate and L-stable.
* $\widehat{s}$: number of stages for the embedded error estimator.
* $\widehat{p}$: order of convergence for the embedded error estimator.
* $Y$: stability property of the embedded error estimator, if any.
 
Note that in some methods $$\widehat{s} = s + 1 > s$$ for which we may take $$b_{s+1} = 0$$ in the embedded pair. Using the above notation, the new schemes in this work are:

 
* Sixth-order methods
  
    * $\texttt{DIRK(6,6)[1]A-[(7,5)A]}$
    \2 \texttt{DIRK(8,6)[1]SAL-[(8,5)A]} 
    \2\texttt{ESDIRK(8,6)[2]SA-[(8,4)]}
    \2 \texttt{SDIRK(9,6)[1]SAL-[(9,5)A]}

    \1 Seventh-order methods
    \2 \texttt{DIRK(9,7)[1]A-[(9,5)A]} 
    \2 \texttt{DIRK(10,7)[1]SAL-[(10,5)A]} 
    \2\texttt{ESDIRK(10,7)[2]SA-[(10,5)]} 
    \2 \texttt{SDIRK(11,7)[1]SAL-[(11,5)A]}

    \1 Eighth-order methods
    \2 \texttt{DIRK(13,8)[1]A-[(14,6)A]} 
    \2 \texttt{DIRK(15,8)[1]SAL-[(16,6)A]} 
    \2\texttt{ESDIRK(16,8)[2]SAL-[(16,5)]} 
 
 


They are organaized for each order in a folder. Each set of Coeffs is named as Xsp, where X is either the matrix A or vector b, s is the number of stages, and p is the order of the method. Each error estimator is added as a subfolder. If the same function evaluation is used (i.e., same matrix A) for the error estimator, the pertaining folder only includes \hat{b}, Otherwise it includes the modified A with an additional stage. We name the error estimators as Xsp_Ezq, where Xsp is the original method, and Ezq denote the embedding's number of stages (z) and order (q).

The folder "(E)SDIRK_Methods" contains additional methods with high stage order and identical diagonal elements. They work better with newton-type solvers and are useful for highly stiff problems and differntial algebraic system.
