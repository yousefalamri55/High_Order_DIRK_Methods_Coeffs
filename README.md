# High_Order_DIRK_Methods_Coeffs
Very High-Order A-stable Stiffly Accurate Diagonally Implicit Runge-Kutta Methods with Error Estimators

This repository contains the coefficients (A,b) for DIRK methods and their error estimators. They are organaized for each order in a folder. Each set of Coeffs is named as Xsp, where X is either the matrix A or vector b, s is the number of stages, and p is the order of the method. In the case of error estimator, if the same function evaluation is used (i.e., same matrix A), we name the error estimator as Xsp_Ezq, where Xsp is the original method, and Ezq denote the embedding's number of stages (z) and order (q).
