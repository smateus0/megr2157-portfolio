# A7 – [FEA on Bracket]

## Objective
![a7_cad69](a7_cad69.png)

![a7_cad70](a7_cad70.png)

(Figure 2)


The purpose of this assignment is to optimize the geometrical design, material of the bracket, Factor of Safety (FOS), maximum deflection, and weight using Finite Element Analysis (FEA). Beginning with the stress-driven design from A5, the assignment requires a workflow, as seen above, of a two-loop approach: an Inner Loop dedicated to the validation of the model through the evaluation of mesh levels and convergence of each mesh level, and an Outer Loop dedicated to design optimization. In order to validate the model, individual geometrical iterations need to be simulated with static loading in terms of coarse, medium, and fine meshes until the maximum value of maximum stress, maximum displacement, and FOS converges within a 7% threshold comparison with respect to their corresponding mesh levels. In order to optimize the design, the geometry of the component needs to be optimized in three distinct ways to enable it to resist a symmetric load of 500 lbf safely with the target safety factor of 4 and with the maximum deflection of 0.005 inches. Through FEA analysis, we can detect stress concentrations and singularities.


![a7_1](a7_1.png)
![a7_2](a7_2.png)

The above shows the workflow for how each design will be evaluated. Starting at Design 1 (from A5 and A6), this design was based on my stress-calculated values and assumptions. Design 1 will be analyzed at three different mesh levels: coarse, medium, and fine. The values that will be seen in each mesh level include the max stress, max displacement, and minimum FOS. To determine the error in the coarse mesh, I will compare the coarse mesh values with the medium mesh values and take a percentage of convergence. If this percentage is below 7%, then this will be classified as "properly/satisfactory converged"; if these values are not below 7%, the fine mesh will be evaluated and given priority. 


### Chosen/Given Values (from A5)

Material: Aluminum 6061-T6 (chosen)

Yield Stress: 40000 psi ([Matweb](https://www.matweb.com/search/datasheet.aspx?matguid=1b8c06d0ca7c456694c7777d9e10be5b&ckck=1](https://www.matweb.com/search/DataSheet.aspx?MatGUID=b8d536e0b9b54bd7b69e4124d8f1d20a))

Maximum Deflection: 0.005 inches (given)

Load: 500 lbf (chosen)

FOS: 4 (given)

As seen in the first two figures, the bracket (Figure 2) will slide in the rigid beam (Figure 1).

### Material Values based on Matweb

![a7_cad2](a7_cad2.png)

As seen above, material values for Aluminum 6061-T6 will be taken from Matweb.


![a7_cad1](a7_cad1.png)

As seen above, the custom material created contains the values from Matweb and is implemented in SolidWorks.


## FEA Constraints
![a7_cad68](a7_cad68.png)

As mentioned in A5, Figure 1 shows the overall geometry of the rigid beam. We will use this outline as our fixed geometry on our bracket for all FEA studies. The fixed geometry will be on the top surface of Feature C and the inner bottom surface of both sides of Feature D.


![a7_cad3](a7_cad3.png)

The above shows the load of 500 lbf being applied directly downward on Feature A. 

## Design 1 (Stress-driven calculations)

### Coarse Mesh
![a7_cad16](a7_cad16.png)

Here we will start with the stress-driven design. Starting with a coarse mesh, as seen above.


#### Stress Values
![a7_cad5](a7_cad5.png)

As seen above, the FEA on the coarse mesh gave a max stress of 100 ksi. This value is not appropriate because the yield stress with an FOS of 4 of aluminum 6061-T6 being 40 ksi; the bracket will fail under this load.


![a7_cad11](a7_cad11.png)

This shows the location of the maximum stress being on Feature B. This is due to the thickness along the z-axis of Feature B being 0.13 inches, based on the stress calculations on A5.


#### Displacement Values
![a7_cad6](a7_cad6.png)

This shows the displacement of the coarse mesh. The maximum displacement is seen to be 0.08326 inches. Since the maximum displacement was set to 0.005 inches in assignment 5, this shows that this design will also fail due to displacement. 


![a7_cad12](a7_cad12.png)

This shows the location where the displacement is maximized. Since the fixed geometry was on the inner sides of Features C, D, and E, these areas are not affected. Feature A is the direct region where the load of 500 lbf is set. The bottom of Feature A  gets elongated the most due to the cantilever beam analysis that Feature A acts as.


#### FOS Value
![a7_cad13](a7_cad13.png)

Here is the FOS plot of Design 1. The minimum FOS is rounded to 0.4, and this also shows how Design 1 will fail due to the lack of material on all features, as it does not meet the minimum FOS of A5, which is 4.


#### Design 1 Weight
![a7_cad37](a7_cad37.png)

The advantage that Design 1 has is the weight, as shown above, being 0.65 lbs. Due to the light weight of this design, lots of failures occur. 


#### Coarse Mesh Values
![a7_w1](a7_w1.png)

Here are the values for Design 1, coarse mesh.


### Medium Mesh
![a7_cad17](a7_cad17.png)

As seen above, the number of elements has increased compared to the coarse mesh (increased to 7807 elements). This is important because it yields more accurate results from the FEA analysis. 


#### Stress Values
![a7_cad8](a7_cad8.png)

From the medium mesh, the max stress is 107.5 ksi; this value is similar to that of the coarse mesh.


![a7_w2](a7_w2.png)

This shows the convergence percentage between the medium and coarse meshes. Both values result in 6.98%, which converges.


![a7_cad18](a7_cad18.png)

This shows the location of the max stress value. This is the same as the coarse mesh.


#### Displacement Values
![a7_cad9](a7_cad9.png)

Here is the displacement plot of the medium mesh. The displacement value increased because the elements inside that round cylinder were likely too square and large to accurately capture the curvature and bending strain. Increasing the number of elements (Medium Mesh) around Feature A allows it to flex more realistically.


![a7_w3](a7_w3.png)

This shows that the percentage of convergence is above 7%, which defines both medium and coarse mesh analyses as not converging.


![a7_cad71](a7_cad71.png)

This shows the location where the max displacement value occurs. This location is the same as the coarse mesh. 


#### FOS Values
![a7_cad20](a7_cad20.png)

Here is the FOS plot. The value of minimum FOS is 0.37, which is similar to the coarse mesh analysis.


![a7_w4](a7_w4.png)

Here is the percentage of convergence; this gives 7.5%, which still classifies as a non-converged value. 


Since the majority of the values between coarse and medium mesh levels do not converge, we will move to the fine-mesh analysis.


### Fine Mesh
![a7_cad19](a7_cad19.png)

This shows the fine mesh. The number of elements increased to 65287.


#### Stress Values
![a7_cad21](a7_cad21.png)

Here is the max stress value of 127.9 ksi. This value has increased from the medium mesh due to the same logic stated before: the number of elements present and the element of Feature B being too square to analyze realistically, causing a big difference in values.


![a7_w5](a7_w5.png)

This shows the percentage of convergence. This 15.95% is above the 7% baseline; therefore, the values do not converge from medium to fine mesh levels.


![a7_cad22](a7_cad22.png)

This shows the location of the max stress. This has not changed across the different mesh levels.


#### Displacement Values
![a7_cad23](a7_cad23.png)

Here are the values of displacement. The maximum displacement value of 0.1019 inches has also increased from the medium mesh analysis due to the same logic of the number of elements stated before.


![a7_w6](a7_w6.png)

This shows the percentage of convergence for displacement. The value of 6.28% is less than the baseline; therefore, these values have converged.


![a7_cad24](a7_cad24.png)

This shows that the location of the maximum displacement has not changed.


#### FOS Values
![a7_cad25](a7_cad25.png)

This shows the FOS plot. The minimum FOS has decreased to 0.31 due to the number of elements more accurately showing how the bracket would react to the 500 lbf.


![a7_w7](a7_w7.png)

As seen above, the percentage of convergence was calculated to be 19.35%, which classifies as not converging. 
Throughout Design1, the majority of the values have not converged across the different mesh levels. Even if they did converge, Design 1 still would have failed due to the constraints of the assignment given.

#### Design 1 Values
![a7_w12](a7_w12.png)

The above shows the tabulated values between the coarse, medium, and fine mesh levels.


## Design 2

### Design Optimization
![a7_cad43](a7_cad43.png)

Due to the failure values of Design 1, I decided to focus my attention first on the max stress values. Since the stress plot showed Feature B being affected by stress the most, I increased the thickness along the z-axis. I changed the depth from 0.13 inches to 0.20 inches. I did not want to thicken this too much due to the width of the strap that Feature A will hold being 0.75 inches ([resource 1](https://www.uline.com/Product/Detail/S-12925/Poly-Cord-Strapping/Heavy-Duty-Polyester-Cord-Strapping-3-4-x-2500?pricode=WA9239&gadtype=pla&id=S-12925)) I needed to make sure there would be sufficient clearance between Feature A and the embedded depth of Feature B.


![a7_cad26](a7_cad26.png)

Since Feature B was experiencing stress across the width as well, I decided to use a generous fillet to spread the stress concentration over a bigger area between Features A and B.


![a7_cad28](a7_cad28.png)

Here is the increase in the linear depth of Feature A from 1 inch to 1.15 inches to compensate for the space taken up by the fillet.


![a7_cad27](a7_cad27.png)

This confirms the clearance of the strap width alongside the linear depth of Feature A. Assuming the strap can be held only linearly on Feature A, the distance between the inner edge of the fillet on both Feature A and B and the outer edge of Feature A is .75 inches; the strap still clears.


![a7_cad29](a7_cad29.png)

Here is the overview of the changes and completed Design 2.


### Coarse Mesh
![a7_cad30](a7_cad30.png)

This shows the start of the FEA analysis for Design 2. Starting with a coarse mesh, includes 1874 elements.


#### Stress Values
![a7_cad31](a7_cad31.png)

This shows the stress plot of Design 2. The fillet and increased depth of feature A have improved the design. The max stress has decreased to 62.63 ksi. Compared to Design 1, this decreased by 51%. Although the max stress is still above the yield stress, with an FOS of 40 ksi included, this is still a big improvement.


![a7_cad32](a7_cad32.png)

This shows the location where the max stress occurs. The location has now moved up to the corners of Features B and C. This is an improvement from Design 1 since the stress concentration area has decreased as expected.


#### Displacement Values
![a7_cad33](a7_cad33.png)

Here is the displacement plot. The maximum displacement has also decreased to 0.02521 inches. Compared to Design 1, this decreased by 75.26%. Although this max displacement value is still greater than 0.005 inches, it is still a big improvement from Design 1.


![a7_cad34](a7_cad34.png)

This shows the location of the max displacement. This has not changed from Design 1 and will be reevaluated in the next design.


#### FOS Values
![a7_cad35](a7_cad35.png)

Here is the FOS plot. This gives a minimum value of approximately 0.64. This value increased by 106.5%. Although this is not near the minimum value of 4, this is still a big improvement.


#### Design 2 Weight
![a7_cad36](a7_cad36.png)

From the improvements Design 2 had compared to Design 1, only increasing the weight of the bracket by .01 lbs is another big improvement.


#### Coarse Mesh Values
![a7_w17](a7_w17.png)

Here are the values for Design 2, coarse mesh.


### Medium Mesh
![a7_cad38](a7_cad38.png)

As shown above, moving to the medium mesh analysis, the number of elements containing the bracket has increased to 8390, resulting in more accurate values.


#### Stress Values
![a7_cad39](a7_cad39.png)

As shown above, the stress plot shows a slight decrease in the maximum stress value.


![a7_w8](a7_w8.png)

This shows the percentage of convergence between coarse and medium mesh levels. Both values are very similar and show a 2.605% convergence, which is satisfactory.


![a7_cad40](a7_cad40.png)

This shows the location of the max stress, the same as in the coarse mesh.


#### Displacement Values
![a7_cad41](a7_cad41.png)

Here is the displacement plot. The maximum displacement has increased compared to the coarse mesh. This is due to the increase in the number of elements. The location where the maximum displacement occurs remains the same as in the coarse mesh.


![a7_w9](a7_w9.png)

Here is the percentage of convergence between the medium and coarse meshes for displacement. Both values are similar and converge by 6.213%, which is satisfactory.


#### FOS Values
![a7_cad42](a7_cad42.png)

Here is the FOS plot of Design 2. The FOS has increased slightly from the coarse mesh.


![a7_w10](a7_w10.png)

The above shows the percentage of convergence between the medium and coarse mesh FOS values. Both values are similar and converge to 3.03%, which is satisfactory.


#### Design 2 Values 
![a7_w11](a7_w11.png)

Here are the tabulated values between the coarse and medium mesh analyses. Since all values converge between the coarse and medium mesh analyses, this is also a big improvement, since this means that the geometry remains constant and simplified.


## Design 3

### Design Optimization
![a7_cad44](a7_cad44.png)

Because of the max stress concentrations from Design 2, I added more surface area to distribute stress at the corners of Feature B. I applied a generous fillet since there was no clearance restraint in that region of Feature B.


![a7_cad48](a7_cad48.png)

From my stress-driven design (Design 1), I assumed a uniform depth along the z-axis on all features. I decided to reuse that assumption due to my plan to reduce the displacement and to help reduce the max displacement region on Feature A. To reduce and add more material to withstand the 500 lbf load, I needed to add “another” Feature B on the free end of Feature A. Since the strap referenced from A5 has a width of 0.75 inches, I needed to ensure that applying the “other” Feature B with the same fillets allows for a linear clearance of 0.75 inches. 

I planned to increase all features to a uniform depth of 1.55 inches. The reason I chose this value was because of the linear space the fillets take up, and to ensure that having both fillets on either side still holds a clearance equal to the width of the strap.


![a7_cad45](a7_cad45.png)

As seen above, I increased Feature C to ensure that it sits directly in the middle of Feature A with a depth of 1.55 inches.


![a7_cad46](a7_cad46.png)

Another feature I decided to add more material to was Feature D. I did this in order to help improve the FOS value to reach the minimum value of 4. I changed the length (x-axis) from 0.55 inches to 1.05 inches.


![a7_cad47.png](a7_cad47.png)

I calculated each increased dimension to make sure it still fit the rigid beam dimensions from Figure 1. As seen above, the dimension with the most accuracy from Figure 1 is still within tolerance.


![a7_cad49](a7_cad49.png)

The above shows the addition of the “other” Feature B on the free end of Feature A. I made this feature with the same dimensions as Feature B.


![a7_cad50](a7_cad50.png)

Here are the fillets on the new feature to ensure symmetry.


![a7_cad51](a7_cad51.png)

Here is the confirmation that the linear clearance still holds at 0.75 inches.


![a7_cad52](a7_cad52.png)

Here I applied the same upper fillet to ensure symmetry.


![a7_cad53](a7_cad53.png)

Here is the overview of my design changes. Thickening Features C and D to help reach the FOS value of 4, and adding another Feature B to help reach the deflection value of 0.005 inches.


![a7_cad54](a7_cad54.png)

Here is another overview of the changes for Design 3.


#### Design 3 Weight
![a7_cad67](a7_cad67.png)

From these modifications to Design 3, the weight increased to 1.44 lbs. This is almost 1 lb more than what Design 1 and Design 2 had. These modifications are needed to reach these minimum values of FOS and deflection, and to decrease the max stress value below the yield stress.


### Coarse Mesh
![a7_cad55](a7_cad55.png)

Here we start with the coarse mesh as seen above; the number of elements is 1388.


#### Stress Values
![a7_cad56](a7_cad56.png)

As seen above, the modifications were successful in achieving a max stress below the yield stress of Aluminum 6061-T6 (40 ksi). The max stress dropped to 3.261 ksi, which is 94.66% less than the value Design 2 had.


![a7_cad57](a7_cad57.png)

The above shows that the maximum stress location is still on Feature B but at a significantly lower value.


#### Displacement Values
![a7_cad58](a7_cad58.png)

The above shows the displacement plot. Design 3 lowered the maximum displacement to 0.0002102 inches. This value decreased by 99.21% from Design 2. This displacement is safely deflected and smaller than the maximum displacement given in the assignment.


![a7_cad59](a7_cad59.png)

The maximum displacement location changed; instead of being on the bottom free end of Feature A, it is now in a very predictable position: in the middle of Feature A. Feature A is now modeled as a cantilever fixed on both ends with a point load in the middle.


#### FOS Values
![a7_cad60](a7_cad60.png)

As seen above, the FOS plot now has a value of 12.27. This exceeds the minimum FOS value of 4 given in the assignment. This new FOS value is an increase of 1759.1% from Design 2.


#### Coarse Mesh Values
![a7_w18](a7_w18.png)

Here are the values for Design 3, coarse mesh.


### Medium Mesh
![a7_cad61](a7_cad61.png)

As seen above, the medium mesh level increased the number of elements to 3547, allowing for a more realistic analysis.


#### Stress Values
![a7_cad62](a7_cad62.png)

As shown above, the stress plot shows a maximum value of 3.335 ksi. This value is very similar to that of the coarse mesh.


![a7_w13](a7_w13.png)

The above shows the percentage of convergence between the coarse and medium mesh levels based on the stress values. These values converge at 2.22%, which is satisfactory.


![a7_cad63](a7_cad63.png)

This shows the location of the max stress. This location remained the same throughout all 3 designs, which is predictable due to the location of the load being on Feature A.


#### Deflection Values
![a7_cad64](a7_cad64.png)

Here is the displacement plot. Design 3 has a maximum displacement of 0.0002118 inches. This value is also very similar to the coarse mesh analysis. This value again clears the 0.005-inch max displacement. 


![a7_w14](a7_w14.png)

The above shows the percentage of convergence between the coarse and medium mesh values based on max displacement. Both values have 0.755% convergence; this is satisfactory.


![a7_cad65](a7_cad65.png)

This shows the location of the maximum displacement. This is a very predictable location due to the bracket having two Feature Bs.


#### FOS Values
![a7_cad66](a7_cad66.png)

The above shows the FOS plot for design 3. The minimum FOS value is 11.99, which is also very similar to the coarse mesh FOS value. This exceeds the minimum FOS value of 4.


![a7_w15](a7_w15.png)

This shows the percentage of convergence based on the FOS values from both the coarse and medium mesh analyses. Both values converge at 2.34%, which is satisfactory.


#### Design 3 Values
![a7_w16](a7_w16.png)

Since all values from the coarse mesh and medium mesh analyses successfully converge below 7% and meet all requirements from the bracket, this redesign is successful.
With a slight increase in weight, the design exceeded all requirements, which justifies the small disadvantage in the design.


## Tabulated Values
![a7_w19](a7_w19.png)

Above shows the full tabulated values from each design, taking the most accurate mesh level at which values converged for each design.


## Reflections
Following the workflow based on Appendices A and B, I found that the presence of structural transitions having zero-radius corners creates stress singularities, which have decreasing localized stress levels as the FEA mesh elements increase. To address this, the use of an asymmetric fillet ensures that the critical load paths are moved away from the rigid boundary constraints, which eliminates stress concentrations while ensuring that there is enough clearance for the loading strap. The inverse relationship between geometric stiffness and material reduction ensured that deflection remained below the 0.005 inch limit.


## Work
[Work](A7WORK.pdf)


[CAD](A7.zip)

## Communicate
Time: 10 hours
