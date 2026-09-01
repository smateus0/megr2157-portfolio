# A2 – Truss Stress Analysis

## Objective

In this project, the aim was to develop and optimize a safe and lightweight truss of seven members that can resist a certain load by applying A500 Structural steel or equivalent and high-strength tool steel pins.

## Design of Truss

The truss structure presented is a 7-member, 5-pin truss with a roller support at B and a pin support at A.  The truss has a total length of 3a, which equals 1.2 m.  The total width of the truss is b, which equals 0.3 m. The truss has an external load of force P at both joint C and joint D. Joint C has a force P pointing upward, while joint D has a force P pointing downward. The force P I decided to exert on the truss is 20kN. 

### Reasoning of Truss Design

The Truss configuration shows the equilibrium and how the design of the system, through symmetry of the external loads, leads to a clean distribution of the vertical reaction forces. With the loads experienced, the internal forces in the members act along the exact geometric axes determined by the geometry of the truss, with the maximum stress acting along the optimized diagonal and chord axes. The chosen structure geometry is an optimized Pratt truss configuration.

![truss FBD](truss_whole.png)

Throughout the truss, each joint experiences different forces. To calculate these forces, we need to examine each joint individually. We first need to determine the external forces needed to be in equilibrium. 


### External FBD
![truss external](truss_external1.png)

As seen in the picture above, the roller support (B) experiences a vertical force from the support, and the pin support (A) experiences both a vertical and horizontal force. Using moment equilibrium on the pin support, due to the two unknowns, this allows us to solve the unknown vertical force, By.

Since there are no external horizontal forces other than the Ax force, we can determine that Ax is 0kN. 

After solving for the unknown force By and noting that Ax is 0, we can take the moment equilibrium of B to solve for the vertical force Ay.


## Joint Analysis


### Truss Angle Theta

![truss angle theta](truss_angle_theta.png)

After solving for all external forces, we move on to solving for one of the two angles in this truss. The first angle (theta) is calculated by taking the inverse tangent of the right triangle formed by the outer diagonal of the truss: opposite over adjacent. Due to similar angles, this is the same angle as the horizontal angle at supports B and A. We now know that angle theta is 36.87 degrees from the horizontal. 


### Solving for each Joint

![truss 2/11](truss_2_11.png)

Now we need to analyse each individual joint and determine the internal forces each joint is experiencing. We assume tension for all unknown internal forces. Starting at joint B, due to the already known external force By and angle theta. We take the summation of the vertical forces at equilibrium,  maintaining correct sign usage and the correct trig function, sin, due to the horizontal angle theta of the internal force F(BC) pointing downward. We then solve for force F(BC) by moving the unknown to the left side and all knowns to the right side. 

After solving for force F(BC), we then take the summation of the horizontal forces at equilibrium. Using the correct trig function, cos for the horizontal forces and the angle theta, we now only have one unknown force, F(BC). Now move the unknown to the left side and the knowns to the right side. 

Using these formats for each joint, make sure the proper trig function is used for either horizontal (cos) or vertical (sin) if the angle used is from the horizontal. Move the unknown internal force to the left side and the known forces to the right, and solve for the unknown. After solving for the unknown, the sign of the force will dictate whether the force is indeed tension, which was assumed first, or compression. It is important to follow the sign rule: a negative force answer is compressive, and a positive force answer is tension.


### Truss Angle Phi

![truss 3/11 angle phi](truss_angle_phi.png)

After using joint analysis of joints B and A, since it allows us to use the known values of the already calculated external forces, we move to joint D. Joint D introduces the second angle, phi. Phi is calculated by drawing a vertical line from joint E to the lower member CD; this allows us to use a right triangle and use the inverse tan to solve for the horizontal angle phi. Using the opposite side (b) and the adjacent side (a/2), we get phi to be 56.31 degrees from the horizontal. Using similar angles as well, this gives the angle of member ED from the horizontal. 


### Joint Analysis Check 

![truss 3/11](truss_3_11_1.png)

Joint D also allows you to “check” your final forces, as seen in force F(CD). Given the structure of the truss, member CD does not experience any force; this is proven to be correct through the joint analysis of D. 

Using this angle phi for the joint analysis of E, with the correct trig functions and the sign convention for each internal force, whether it be compression or tension. 


![truss 4/11](truss_4_11.png)

As seen in joint D, you can “check” the joint analysis on E and C since they are the last two joints in the truss. Following the same procedure, make sure to use the correct angle (theta or phi), the correct trig functions, and the sign convention. Since this truss is at equilibrium, all forces in joint E and C are equal to each other in magnitude and opposite in direction. 


## Summary Joint Analysis

![truss 4.5/11](truss_4.5_11.png)

Above is a summary of the joint analysis for the truss.


## Stress Calculations (Members)


### Material Selection due to Knowns and Unknowns 

![truss 5/11](truss_5_11.png)

From the joint analysis, internal force F(CE) has a value of 16.07kN. This internal force is the maximum and is needed to determine the minimum cross-sectional area for the members, given a square cross-section. Given the parameters of the assignment, A500 structural steel is needed or a material equivalent. SolidWorks materials library contains ASTM A36 steel; this material has the same density as A500 steel and will be used as an equivalent. 


### Minimum Area for Members

![truss area 5/11](truss_5a_11.png)

Focusing on the member dimensions, solving for the minimum cross-sectional area is shown. With the yield stress of ASTM A36 steel being 250Mpa from SolidWorks, we use this value alongside the equation (Eq 1): allowable axial stress equals force divided by cross-sectional area. Using an equivalent equation, allowable axial stress is equal to the factor of safety divided by the yield stress (Eq 2); set the two equations equal and solve for the cross-sectional area. Now, knowing the cross-sectional area and assuming it's square, we can solve for the side dimension. 


### Pin Offset Description

![truss 6/11 description](truss_6_11_1.png)

Due to the assumed cross-sectional area being a square, we need to take into account the offset distance of each pin slot from its closest edge of the member. This is important to determine since we need to ensure enough solid material for the pin slot so the member does not fail under load. 

The distance from the center of the pin slot to its closest edge of the member will be known as the Pin Slot Offset. 
In order to find the Pin Slot Offset, we need to first find the cross-sectional area of the pin.

Continuing on member dimensions, we will calculate the center-to-center lengths from the dimensions a and b from the truss structure. It is important to distinguish this length type from another; this will be important later on in the CAD model. 


### Solving Lengths (L)

![truss length values 6/11](truss_6_11_2.png)

Starting with calculating the center-to-center length(L) from the given dimensions a and b. Length (L) represents the length from one pin slot center to another. Solving for L on each member depends on the member's orientation, since each member is at different angles (theta and phi). We need to use the Pythagorean Theorem to solve for each member length.

Starting with the top horizontal members (BE and EA):
The lengths of these members are simply a + (a/2)

The bottom horizontal members (CD):
The length of CD is just length a

Solving for the outer diagonal members (BC and AD):
The lengths of members BC and AD are calculated by using the Pythagorean theorem and solving for the magnitude of the x-distance component (a) and the y-distance component (b).

Solving for the inner diagonal members (CE and DE):
The lengths of members CE and DE are calculated using the Pythagorean theorem by solving for the horizontal x-component and the y-component, taking note that the horizontal x-component is a/2. Then, take the magnitude of both components.


![truss 7/11 finish lengths value](truss_7_11_1.png)

Solving for the total length (L) by adding all member lengths (L)


## Length (L) vs. Length (L0)

![truss 7/11 description](truss_7_11_2.png)

Then, introduce the two distinct lengths (L) and (L0). 

As a reminder, length (L) represents the length from one pin slot center to another.

Length (L0) represents the length of each member from edge-to-edge. This length (L0) will be used in the CAD model later and to determine the weight of the truss.

To find the length (L0), we need to determine the diameter of the pin. We need to determine the diameter of the pin due to a Structural Engineering Standard stating, “the AISC Specification (2016), the horizontal edge distance, leh, must be greater than or equal to 2d, where d is the bolt diameter” [(ideastatica)](https://www.ideastatica.com/support-center/verification-examples/single-plate-shear-connections-aisc)


## Stress Calculations (Pin)

### Knowns and Unknowns

![truss 7/11 known and unknown](truss_7_11_3.png)

Listing all the information the assignment gives
We can solve for the allowable shear stress of the pin and the weight

The plan:

- **a.** — To solve for the pin diameter.
- **b.** — Then to solve for the length (L0). 
- **c.** — After solving for L0, we then solve for the volume using the minimum cross-sectional area of the member (this was solved in 5/11).
- **d.** —We can solve for the volume
- **e.** —Then we can solve for the mass, which can be converted to the weight
- **f.** —Starting with solving for the cross-sectional area of the pin


### FBD Pin

![truss 8/11 pin FBD](truss_8_11_1.png)

From the FBD of the pin at joint C, the forces are compressive. The largest force to determine the minimum area will be the same 16.07kN force from the members

My reasoning for choosing 16.07kN:

An external load of 20 kN is a point load coming from the environment straight down to a particular joint. But the 20 kN is not concentrated at one point. As soon as it comes into the joint, the angular truss members behave like a geometric path and spread out the load across the entire structure. The pin joint does not know anything about the external load. It only knows what forces are applied to it by the metal rods that are attached directly to it. If you exert an internal axial load of 16.07 kN on a truss member, then the truss member exerts this load on the side of the pin joint.


### Solving Minimum Pin Area

![truss 8/11 area of pin](truss_8_11_a.png)

Similar to solving for the minimum cross-sectional area of the member, the given yield shear and the factor of safety (FOS) allow us to use the equation (Eq 1): allowable shear stress equals shear force (F) divided by area. We also use an equivalent equation (Eq 2): allowable shear stress equals the yield shear stress divided by FOS. 

After solving for the minimum cross-sectional area of the pin, we can find the diameter using the area of a circle.


### Using Bearing Stress

![truss 8/11 length of pin](truss_8_11_3.png)

If a pin enters a hole in the truss members, the force acts on pushing firmly into the inner walls of this hole. That is bearing stress on the pins and inner member wall; the formula for bearing stress is shown below as Eq 1. Hard tool steel is much stronger and harder than ASTM A36 steel, and it can resist wear better too. The less durable material will deform first. Therefore, we need to consider the values of ASTM A36 Steel in order to calculate the safety limit, which is done according to Eq 2. Eq 2 is consistent with the previous equivalent formulas; Eq 3 is equivalent to bearing stress; Eq 2 is equivalent to bearing stress. From Eq 2 and Eq 3 solve for length from Eq 3. 


Because the cross section is assumed to be square and the side is 15mm long, it means that the pins should extend beyond the 15mm outline to connect to the mounting brackets or clevis tabs in a realistic mechanical structure.


### Solving Pin Slot Offset

### Using Structural Engineering Standard

![truss 9/11 description](truss_9_11_1.png)

Now that we have solved for the diameter of the pin, we can use the structural engineering standard stated before (Length (L) vs. Length (L0)). The offset of the pin slots should be a distance of twice the diameter of the pin from the closest edge of the member. 


### Solving for Length (L0)

![truss 9/11 length values](truss_9_11_2.png)

Using the logic of each member having two pin slots (one on each edge), the length we calculated before (L) from center-to-center needs to be increased by the two offsets from the pin slots. In doing so, we now get the length (L0) for all members. 


## Summary Stress Values 

![truss 9.5/11](truss_9_5_11.png)

Above is a summary of the values we currently have


## Solving for Weight 

### Solving for Weight of Truss

![truss 10/11 finish L0](truss_10_11_1.png)

Now, solving for the total L0 length from all members from the summation, we can then begin to solve for the weight of the truss as a whole. 


### Solving for Weight of Pins

![truss 10/11 member mass](truss_10_11_2.png)

The plan to solve for the weight of the truss is the same as for the weight of the pins:

- **1.** — After solving for L0, we can get the volume using the minimum cross-sectional area of the members
- **2.** — Using volume, we can find mass using the density of ASTM A36 steel
- **3.** — We then convert the mass into weight


![truss 11/11 FBD](truss_11_11_1.png)

To solve for the weight of the pins, in a similar format, we multiply the minimum cross-sectional area of the pin by the length of the pin and the density of the material given.

We then multiply by the number of pins


## Theoretical vs Assembly Percentage Error

![truss 11/11 end](truss_11_11_2.png)

From the CAD model, all the calculated values are included. The theoretical (calculated) weight of the truss with the pins came out to be 13.973lbs. The CAD model gave a weight of 13.1lbs.

Using the percentage error formula, this calculated value only gave a 6.7% error. The theoretical calculated weight of the truss frame was found to be 13.973 lbs, but after the design of the 3D CAD model using the validated ASTM A36 steel, its weight was found to be 13.100 lbs, making for a slight variation of 6.7%. The reason why this variation is acceptable from a structural perspective is due to the interpretation of volumes that takes place at the intersection of joints in the CAD model. Since the required cross-sectional area of 224.98 mm^2 has been met in the members, this means that weight optimization has been achieved successfully.


## Summary of Lengths (L0) and Volumes
![truss 11.5](truss_11_5.png)

Above is a summary of the rest of the values of members and pins


## Summary Total
![truss 4.5/11](truss_4.5_11.png)
![truss 9.5/11](truss_9_5_11.png)
![truss 11.5](truss_11_5.png)


## Member CAD

### Construction Lines

![cad_truss1](cad_truss1.png) ![cad_truss5](cad_truss5.png) ![cad_truss2](cad_truss2.png) ![cad_truss3](cad_truss3.png) ![cad_truss4](cad_truss4.png) ![cad_truss6](cad_truss6.png)

Using construction lines (dashed lines), I made sure to create the center-to-center lengths first and ensure they are constrained using the length (L).
The pictures show the progression of aligning the center-to-center length (L) first, then building the calculated angles. 


### Overlapping Beams

![cad_truss7](cad_truss7.png) ![cad_truss9](cad_truss9.png) ![cad_truss8](cad_truss8.png) ![cad_truss10](cad_truss10.png) ![cad_truss11](cad_truss11.png)

Then I moved to the width of the beam; due to the cross-sectional area of the member being a square, the side is simply the square root of the area. I used that value as both the width and the depth of the model.
As seen in the picture, I overlapped where the beam members would lie; this allowed for a more accurate placement of the members. 


### Ensuring Constraints and Dimensions

![cad_truss12](cad_truss12.png) ![cad_truss13](cad_truss13.png)

Using all the construction lines to align all members from the center-to-center lengths and have them perpendicular to the edge-to-edge lengths (L0), I used the line tool and traced all construction lines. 
Ensuring that the pin slot offset is the same for all members and that the angles from each member matched the FBD of the truss. 
Also ensuring that each line is parallel to its pair and making them perpendicular to the width for all members. 


### Eliminating Overlap and Reasoning

![cad_truss14](cad_truss14.png) ![cad_truss15](cad_truss15.png)

After using the line tool, followed through all the construction lines, eliminating the overlapping lines within the structure. I kept the outside overlapping lines to keep the members rectangular in shape and allow for the possibility of gusset plates to get integrated into these member edges. 


## Final Sketch Overview

![truss_sketchview](truss_sketchview.png)

After creating the construction lines, tracing the line tool over them, and deleting the inner overlapping lines, this is the final result. It is important to make sure that each beam has its parallel and perpendicular constraints to ensure the beams are where they need to be. 


### Extruding Sketch

![truss_extruded](truss_extruded.png)

Orienting the truss from 2-D first, then extruding using the square cross-sectional area of 15mm for the depth and the width 


## Material Values Member

![cad_creosolid_truss](cad_creosolid_truss.png)

Due to preference, I gathered the material values for ASTM A36 steel from SolidWorks and implemented them into Creo Parametric. 


## Pin CAD

### Pin Part

![pin_truss1](pin_truss1.png) ![pin_truss2](pin_truss2.png)

Due to rounding, the area was maintained relative to the calculated value,

![pin_truss3](pin_truss3.png)

Pin calculated length used in part file. 


## Material Value Pin

![cad_creosolid_pin](cad_creosolid_pin.png)

Since the pin material was classified as hardened tool steel with given parameters, I placed them in the material information table in Creo with their respective units from the SolidWorks values



## CAD Assembly

![truss_asym1](truss_asym1.png)

7-member, 5-pin truss as shown in the FBD and the assembly file.


![truss_asym2](truss_asym2.png)

The calculated minimum length of the connecting pins minimum length of was used in the assembly. 1.06 inches (26.92 mm) was determined by the allowable bearing stress criteria for the ASTM A36 steel holes and the difference in strength between the pin material and the member material. Even though each truss frame cross-section is a uniform extrusion thickness of 15.00 mm, this pin length is mechanically justified and kept intentionally in the final CAD model. In any mechanical engineering practice, this pin has to go beyond the internal frame length so that it can fit into some external mounting brackets or double-gaged clevis plates. Additionally, this length is needed to give a clear space for fastener retainer elements like clips or hex nuts. This makes a realistic assembly possible that checks the required 4.0 safety factor against shear and bearing failure.


### Mass Assembly

![cad_mass1](cad_mass1.png)

Here are the masses in the assembly file.


## Errors

### Cylinder Members
![top_cylinder_cad_error](top_cylinder_cad_error.png)

(Picture is taken viewing the truss from the top)
Originally wanted the cross-sectional area of the members to be cylindrical since this was what came to mind when thinking about trusses. This allowed me to find the minimum cross-sectional area, and the rest followed. 

When building the truss as individual part files for each member, the members were not aligning at the same distance from one another. The members had the correct values, but the CAD geometry did not add up. What I had to do was change the cross-sectional area to a square and, with the CAD file, orient the truss from the 2-D view and extrude it outward.


### Indeterminate Truss Structure

![truss_error2](truss_error2.png)

Due to the problem of the CAD geometry not aligning with the calculated values, I did not think of the square cross-section; instead, I decided to create another truss structure. What I did not know was that the truss structure seen above is statically indeterminate, so I could not explain the joint analysis process correctly.

## CAD and Work Downloads

### All Work
[All work](CamScanner%209-1-26%2009.51.pdf)

### CAD Models 
[Member](whole_truss_asym.prt.13)

[Pin](truss_pin.prt.10)


