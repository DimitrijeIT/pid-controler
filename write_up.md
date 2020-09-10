# PID Controller 

PID Controller is made of tri components:

- Proportional
- Integral
- Derivative 
Each component is taken into account with its weight

Componets have different
- Proportional component takes into account only the error to the wanted trajectory 
- Integral component takes into account the sum of all errors to the wanted trajectory 
- Derivative component takes into account delta from the previous position (error).

If Kp, Ki, Kd are weighted for Proportional, Integral, Derivative component respectively, and CTE current error to the wanted trajectory, CTE_prev previous cte, and Sum(CTEs) sum of all cte then the output of PID filter for current position is:

PID = - Kp * CTE - Kd * (CTE - CTE_prev) - Ki * Sum(CTEs)

To get the final hyperparameters (weights) I have started with once that are used in video lectures and then manually tune them. 
To start off with tunning I have used the algorithm of increasing or decreasing each hyperparameter by a large coefficient (find soon that integral hyperparameters need to be really small, and derivative hyperparameters can have larger values). 
After a couple of interactions, I have switched to using the concepts from Twiddle algorithm and finding the final parameters. 
