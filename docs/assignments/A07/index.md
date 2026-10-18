# A7 – [Topic]

## Objective
![a7_cad69](a7_cad69.png)

![a7_cad70](a7_cad70.png)
(Figure 2)

The purpose of this assignment is to optimize the geometrical design, material of the bracket, Factor of Safety (FOS), maximum deflection, and weight using Finite Element Analysis (FEA). Beginning with the stress-driven design from A5, the assignment requires a workflow, as seen above, of a two-loop approach: an Inner Loop dedicated to the validation of the model through the evaluation of mesh levels and convergence of each mesh level, and an Outer Loop dedicated to design optimization. In order to validate the model, individual geometrical iterations need to be simulated with static loading in terms of coarse, medium, and fine meshes until the maximum value of maximum stress, maximum displacement, and FOS converges within a 7% threshold comparison with respect to their corresponding mesh levels. In order to optimize the design, the geometry of the component needs to be optimized in three distinct ways to enable it to resist a symmetric load of 500 lbf safely with the target safety factor of 4 and with the maximum deflection of 0.005 inches. Through FEA analysis, we can detect stress concentrations and singularities.


### Chosen/Given Values (from A5)

Material: Aluminum 6061-T6 (chosen)

Yield Stress: 40000 psi ([Matweb](https://www.matweb.com/search/datasheet.aspx?matguid=1b8c06d0ca7c456694c7777d9e10be5b&ckck=1))

Maximum Deflection: 0.005 inches (given)

Load: 500 lbf (chosen)

FOS: 4 (given)

As seen above in Figure 1, the bracket (Figure 2) will slide in the rigid beam.


## Communicate

