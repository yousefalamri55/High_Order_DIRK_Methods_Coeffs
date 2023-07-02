# High_Order_DIRK_Methods_Coeffs

This repository accompanies the manuscript "Very High-Order A-stable Stiffly Accurate Diagonally Implicit Runge-Kutta Methods" available here
https://arxiv.org/abs/2211.14574

It contains the coefficients (A,b) for DIRK methods and their error estimators. They are organaized for each order in a folder. Each set of Coeffs is named as Xsp, where X is either the matrix A or vector b, s is the number of stages, and p is the order of the method. Each error estimator is added as a subfolder. If the same function evaluation is used (i.e., same matrix A) for the error estimator, the pertaining folder only include \hat{b}, Otherwise it includes the modified A with an additional stage. We name the error estimators as Xsp_Ezq, where Xsp is the original method, and Ezq denote the embedding's number of stages (z) and order (q).

The folder "(E)SDIRK_Methods" contains additional methods with high stage order and identical diagonal elements. They useful for highly stiff problems and differntial algebraic system.
