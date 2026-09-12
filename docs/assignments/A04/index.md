# A4 – [Motor Mount]

## Objective
![a4_1](a4_1.png)
![a4_3](a4_3.png)

The purpose of this design exercise is to construct a motor mount with an optimized structure for a Brushed 24V DC Gear Motor 3.6Kg.cm/46RPM w/ 99.5:1 Planetary Gearbox that securely mounts onto Wall A. By taking the initial approach of using a cantilever beam model based on Appendix B, the motor mount will be analyzed sequentially with respect to two different components to ensure a factor of safety of 3 with respect to material yield and to limit the displacement to 0.30 mm. Manufactured from a material of choice in order to increase rigidity and ignoring the internal mass of the motor, the final geometry consists of features that limit deflection with verified bolt holes of 3.4 mm.

### Assumptions
![a4_2](a4_2.png)

In order to apply structural mechanics in the modeling of the mount, the plates were decoupled and modeled independently as cantilever beams following the guidelines in Appendix B. The point of connection between the two and the 4-bolts fixed to the ceiling were considered to be fixed supports, while the remaining length of the support on Wall A allowed bending. When viewing feature 2 as a cantilever beam, we also assume that the connection side from features 1 and 2 acts as a rigid wall for feature 1.

Additionally, the model considers that Wall A, being very stiff, offers strong support for the mounting fixtures, and ignores the internal weight of the motor to focus only on the external loading path. It is also assumed that the strong factor of safety of 3 will take care of any stresses induced because of cutting the holes for 3.4 mm bolts and the center shaft hole.


## Feature 1

### Chosen Material
![a4_7](a4_7.png)

It was decided that PLA would be the most effective bracket material among the available materials provided in the assignment since this material has a very high stiffness (Elastic Modulus). Based on the data available in the verified databases at MatWeb, an average tensile yield strength of 45.2 MPa has been used in the design to ensure the structural safety of the material, and the average modulus of elasticity of 2,350 MPa has been used to provide proper simulation of rigidity. In this case, this high value of elasticity becomes very significant through the governing thickness, and the material’s initial stiffness should be maximized.


### Knowns and Unknowns
![a4_w1](a4_w1.png)

The vertical dimension L1 for Feature 1 has been set to a compact fit of 50 mm to accommodate the outside diameter of the motor body and still leave a solid material for additional support. A constant width of 30 mm has been specified in order to ensure that it matches up well with the geometry of the motor housing and remains compact overall. The particular combination of dimensions guarantees that there is sufficient material left around the 3.4 mm screw holes without creating interference with the motor assembly.

Known values:
- **1.** — Yield strength - 45.2 MPa (Matweb)
- **2.** — Elastic Modulus (E) - 2350 Mpa (Matweb)
- **3.** — Length (L1) - 50 mm
- **4.** — Width (w1) - 30 mm
- **5.** — P = F = 300 N
- **6.** — Delta L(max) = 0.30 mm
- **7.** — Factor of Safety (FOS) = 3


Unknown values:
- **1.** — Thickness (t1)
- **2.** — Moment (M1)



### FBD 1
![a4_w2](a4_w2.png)
![a4_4](a4_4.png)

Based on the coordinate system placed in the upper right of the FBD, the motor drive shaft will be placed directly “above” (in orientation) feature 1. The outlined portion of the FBD represents the drive shaft length (Lshaft) of the motor (as seen in Appendix A). It is also known that load P will be perpendicular to the drive shaft. 

Feature 1 of the Free Body Diagram is shown as a cantilever beam with an offset of Lshaft (18 mm) for the perpendicular force P. Using moment equilibrium and placing all reactions, M1 produces a bending moment of 5,400 N * mm. The rigid wall mount is depicted using a hatched line along the right end.


### Allowable Stress
![a4_w3](a4_w3.png)
![a4_w4](a4_w4.png)

As shown in the picture below, solving for the allowable stress using the yield and FOS given within Matweb, the allowable stress equals 15.07 MPa.

The second picture shows the cross-sectional area (hatched) of feature 1; using the orientation, we can see what the width and thickness are.

The standard moment of inertia formula for a rectangle is being used and will be implemented in the subsequent Flexure Formula.


### Flexure Formula
![a4_w5](a4_w5.png)

As seen above, the flexure formula uses both the moment from the FBD 1 and the moment of inertia for feature 1. Since the moment of inertia includes the thickness parameter, we will use that to solve for the thickness of feature 1.

Solving symbolically (eq 1) and numerically, we get a thickness of 8.47 mm based on the allowable stress.


### Beam Deflection Equation
![a4_w6](a4_w6.png)

Since we solved for thickness 1 through the allowable stress, we need to solve for the possible governing thickness using the deflection constraint given in the problem (Delta L(max)).

The deflection equation can be seen containing the moment of inertia; we use this to solve for the thickness. Solving symbolically (eq 2) and numerically, we see that based on the deflection constraint, the thickness of feature 1 needs to be a minimum of 15.65 mm (t1).

This is the governing thickness because the greater thickness represents the minimum required thickness of the feature. 


## Feature 2

![a4_ww](a4_ww.png)

### Chosen Values and Knowns and Unknowns

Using the same material throughout (PLA) and also the same width as feature 1 due to visual symmetry and assumptions.

Similar to feature 1, our knowns include:
- **1.** — Yield strength - 45.2 MPa (Matweb)
- **2.** — Elastic Modulus (E) - 2350 Mpa (Matweb)
- **3.** — Width (w1 = w2) - 30 mm
- **4.** — P = F = 300 N
- **5.** — Delta L(max) = 0.30 mm
- **6.** — Factor of Safety (FOS) = 3
- **7.** — Diameter of clearance hole (Db) = 3.4 mm


Unknowns:
- **1.** — Length (L2 total)
- **2.** — Length (L rigid)
- **3.** — Length (L free)

### Assumptions for Feature 2
![a4_5](a4_5.png)

These new unknowns are introduced based on the figure above. We will assume and divide the total length of Feature 2 into two sections: Lrigid and Lfree.

Lrigid is the length over which the clearance mounting holes are present.
Lfree is the remaining length of the total Feature 2 length. 

This will be explored more after FBD 2.


### FBD 2
![a4_w7](a4_w7.png)
![a4_2](a4_2.png)

As seen in the FBD (1)above and also in the model below, the orientation of feature 2 is horizontal, with the fixed wall (Wall A) on “top” (from the FBD).

In the FBD (2) right below my work, you see an outline of the motor; the dimensions were given in Appendix A. These dimensions listed in the outline help us solve for the total length of feature 2 another way. Feature 2 gets embedded with the thickness (t1) of feature 1. 

To solve for L2 total, we need to account for both the length dimensions of the motor (motor housing and gear body) and the thickness of feature 1. Solving for this gives us L2 total equal to around 91 mm. These lengths will be rounded due to ease of manufacturing. 

Since we solved for L2 total, we use this length alongside Lshaft to have the total moment arm to solve for the moment of feature 2 (M2).

Solving for M2 gives us a value of 32700 N * mm.


### Solving for Lrigid
![a4_w8](a4_w8.png)

To clarify, Lrigid is the length over which the mounting bolts will be placed through the clearance hole diameter (Db). Since Db is given as 3.40mm, we can use a standard structural engineering rule that determines the length from the center of Db to its respective edge. We will call this distance Loffset.

The structural engineering rule for Loffset uses twice the diameter of the hole as the distance. Solving for this gives us a distance of around 7 mm, and we round up due to the logic of having more solid material, which makes the assembly more stable.


![a4_w9](a4_w9.png)

As seen in diagram 1, we use Loffset for both the horizontal and vertical distances from each respective edge to the center of the hole. The reasoning for this is to achieve a uniform wall thickness of solid plastic surrounding the hardware and maximize space inside for a strong, moment-resistant bolt configuration.


![a4_w10](a4_w10.png)
![a4_6](a4_6.png)

As seen in diagram 2 and the reference to feature 2 given in the assignment, there are two sets of clearance holes, Db. We can use another structural engineering standard called the “Minimum Bolt Pinch Rule” or “bolt-to-bolt spacing rule”.

This rule states that fasteners need a spacing from one set to another of 1.5 * d to 2.0 * d. We will call this set distance L vertical. In this case, I will assume and bump up the distance between the sets to 4 times Db. The reasoning for this is that the bigger the distance between sets, the more leverage there is to resist motion from Wall A.
([Source for both structural engineering rules](https://industrialmonitordirect.com/de/blogs/knowledgebase/designing-bolt-patterns-rules-calculations-and-engineering-standards#section-1))

Calculating Lvertical gives 13.6 mm, but we will also bump this distance to 20 mm due to the same logic to resist motion. 



### FBD 2 (cont.)
![a4_w11](a4_w11.png)

Diagram 3 shown above shows us the setup for how we will assemble and determine Lrigid. From this orientation, Loffset will be counted twice from each respective edge and “end” of the rigid part of feature 2. 

Now we can solve for Lrigid from the diagram; this gives us a value of 34 mm for the rigid part.


![a4_w12](a4_w12.png)

Having already solved for L2 total, we can finally solve for Lfree and use that Lfree for the moment of inertia. 

Solving for Lfree is simply solving for the remaining length of feature 2; this gives us a length of 57mm


### Second FBD
![a4_ww1](a4_ww1.png)

As seen in the picture, this again shows how L2 total is divided. This includes an outline of feature 1 alongside M2 from Lfree. 


### Solving for t2
![a4_w13](a4_w13.png)

As stated before, we will use Lfree to plug into the standard moment of inertia equation. Similar to how we solved for t1, we use the flexure formula and symbolically solve for t2 (eq 1). Solving for t2 through the allowable stress gives a thickness of 20.832 mm.


![a4_w14](a4_w14.png)

Now we have to check which thickness will govern. Using the deflection equation, we also symbolically solve for t2 from the moment of inertia (eq 2). Solving for t2 gives a value of 31.12 mm.

The thickness based on the deflection constraint will be the governing thickness because the greater thickness represents the minimum required thickness of the feature due to load P.


## Summary 
![a4_w15](a4_w15.png)
![a4_w16](a4_w16.png)
Here are the summary values for each feature.


## CAD Design

### Isometric View
![a4_w17](a4_w17.png)
![a4_3](a4_3.png)

Here is the isometric view of what the model will look like. The design features I have placed on the motor mount to minimize deflection include the pocket indentation on feature 1 to use t1 effectively and also the fillet placed where features 1 and 2 connect, since this allows a better dispersion of loads.

Although some dimensions are not yet specified, they will be added later in the CAD process. All dimensions with numeric values were already calculated.


### Parametric Equations
![a4_cad0](a4_cad0.png)

As seen above in the parametric equations, there are independent and dependent variables.

Independent variables:
- **1.** — FOS
- **2.** — def (Delta L max)
- **3.** — w (width chosen)
- **4.** — P (given load)
- **5.** — E (Matweb)
- **6.** — L1
- **7.** — L_shaft
- **8.** — L_motor
- **9.** — d_B (Db)


Dependent variables:
- **1.** — M1
- **2.** — t1
- **3.** — L2_total
- **4.** — M2
- **5.** — t2


### Feature 1 CAD
![a4_cad1](a4_cad1.png)

This shows the 2D sketch of both features and their dimensions using the parametric variables.


![a4_cad2](a4_cad2.png)

This shows the width of the extruded feature using parametric variables


![a4_cad3](a4_cad3.png)

This shows the mounting holes within the same face as where the drive shaft of the motor is. The diameter of all mounting holes is the same (d_B).

Make sure the mounting holes are centered on the length and width of feature 1; this top view shows this.


![a4_cad4](a4_cad4.png)

This shows the mounting holes being extruded completely through t1.


![a4_cad5](a4_cad5.png)
![a4_3](a4_3.png)

Referencing the dimensions of the motor, this sketch shows where the pocket fits, using the diameter of the drive shaft guide.


![a4_cad6](a4_cad6.png)

This shows the sketch being extruded to a depth of 7 mm, as seen in the dimensions of the motor. The chosen value of 7 mm depth was because of using t1 effectively; this 7 mm depth is a deflection-minimizing feature while still providing enough solid material to support loads.


![a4_cad7](a4_cad7.png)

This shows the sketch of the diameter of the drive shaft diameter. 


![a4_cad8](a4_cad8.png)

This shows the extruded sketch hole entirely through feature 1.


![a4_cad9](a4_cad9.png)

This shows a sketch of another deflection-minimizing feature pocket for the gear body of the motor.


![a4_cad10](a4_cad10.png)

This shows the extrusion of the sketch to a depth of 5 mm. The reasoning for the 5 mm is the same logic as using t1 effectively while also maintaining enough solid support material for load. This support pocket has to connect to the depth of the drive shaft guide (2 mm); therefore, the 7 mm pocket alongside the 5 mm pocket achieves this 2 mm depth from the motor dimensions.


### Feature 2 CAD

![a4_cad11](a4_cad11.png)

This is the sketch including the mounting spacing calculated before and the d_B.


![a4_cad12](a4_cad12.png)

This shows the extrusion from the sketch, with the mounting holes through all of t2.


### Fillet

![a4_cad13](a4_cad13.png)
![a4_cad14](a4_cad14.png)

This shows the location of the fillet; this is another deflection-minimizing feature. A fillet had to be created right along the 90-degree internal angle where feature 1 meets feature 2. Because sharp internal corners concentrate stress, without a fillet the heavy cantilever bending would have concentrated at a single point, leading to micro-fractures and failure. A radius of 5 mm was chosen as the proportion needed to evenly distribute the internal stress load over a bigger surface area.


## CAD Model Views

![a4_cad15](a4_cad15.png)
![a4_cad16](a4_cad16.png)


## Work

[Work](a4-work.pdf)
[CAD File](A4.zip)


## Communicate
Time: 11 hours
