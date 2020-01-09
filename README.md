 MTO——Multi-physics Topology Optimization
=========================================
Description
-----------
The code presented is a parallel solver for multi-physics topology optimization on structured grids. Density-based method is adopted for solving 2D or 3D thermal-fluid-structural topology optimization problems based on OpenFOAM.  

Installation
------------
Before running this solver, following softwares are needed.  
(a) **OpenFOAM 5.0**  
(b) **PETSc 3.12**  
(c) **swak4Foam**  

Parallel version of MMA written by Aage is also needed for updating the design variables (https://github.com/topopt/TopOpt_in_PETSc). We have changed this code to apply it in our solver. For simplicity, the C++ script have been compiled into a dynamic library (**libMMA_yu.so**), users should put this file in **FOAM_USER_LIBBIN** after installing OpenFOAM.  

Run the solver
--------------
 After finishing above works, users should run **wmake** in the src folder, and then run **blockMesh** and **decomposePar** in the app folder. Finally, the multi-physics topology optimization solver can run in the app folder by **mpirun –n 20 MTO_solid –parallel**, where 20 is the default number of cores for parallel computing.
 
Postplot
--------
After the optimization, users should run **reconstructPar** in the app folder and then run **paraFoam** to view the results with Paraview.  

Solid displacement problem-2D  
-----------------------------
![image](https://github.com/Yuminghao-DLUT/MTO/blob/master/MTO/beam_2D.gif)  
Solid displacement problem-3D  
-----------------------------
![image](https://github.com/Yuminghao-DLUT/MTO/blob/master/MTO/beam_3D.gif)  
Thermal-fluid problem-2D  
------------------------
![image](https://github.com/Yuminghao-DLUT/MTO/blob/master/MTO/heatsink_2D.gif)  
Thermal-fluid problem-3D  
------------------------
![image](https://github.com/Yuminghao-DLUT/MTO/blob/master/MTO/heatsink_3D.gif)  
