# Lab 5: Design a Snap Fit

**Total Time Spent:** 10 Hours

---

## 1. Modeling Section

This section details the step-by-step CAD modeling process for both the Snap Clip and the Snap Clip Cover in SolidWorks.

### Snap Clip

#### Step 1: Base Sketch & Extrusion
Using the core dimension parameters, sketch the main flexure base profile on the Front Plane and extrude it by 15 mm.

![Snap Clip Step 1](Design%20Step%201.jpg)

#### Step 2: Wall Thickness Extrusion
Extrude both side walls by 1.5 mm so that the outer profile matches the wall thickness of the mating cover.

![Snap Clip Step 2](Design%20Step%202.jpg)

#### Step 3: Guide Extension Profile
Sketch an 8 x 15 mm profile on the mirrored side of the clip, then extrude by 45 mm to ensure a tight, guided fit when inserting the clip into the cover housing.

![Snap Clip Step 3](Design%20Step%203.jpg)

#### Step 4: Ergonomic Tab Extensions
On both the top and bottom surfaces of the base, extrude 5 mm grip features to allow for easy pushing and pulling during assembly and disassembly.

![Snap Clip Step 4](Design%20Step%204.jpg)

---

### Snap Clip Cover

#### Step 1: Cover Base
Sketch an 18.5 x 40 mm base profile and extrude it by 3 mm to form the rear structural endplate.

![Snap Clip Cover Step 1](Design%20Cover%20Step%201.jpg)

#### Step 2: Enclosure Walls
On the face of the base, sketch 2.9 mm top and bottom walls alongside 1.5 mm side walls, then extrude by 60.5 mm to create the primary sleeve profile.

![Snap Clip Cover Step 2](Design%20Cover%20Step%202.jpg)

#### Step 3: Retention Cutout
On the side wall where the snap clip flexure arm engages, cut out a pocket using the clip's retention dimensions as a direct reference.

![Snap Clip Cover Step 3](Design%20Cover%20Step%203.jpg)

---

## 2. Parametric Design & Mathematical Analysis

### Mathematical Calculations & Engineering Equations

To ensure structural integrity during engagement without exceeding the yield strain of 3D-printed PLA, cantilever flexure beam equations are applied below.

#### A. Geometrical Parameters & Cross-Section Properties
* Beam Length (L) = 50.0 mm
* Flexure Width (b) = 15.0 mm
* Base Thickness / Root Depth (h) = 3.0 mm
* Engagement Hook Height / Deflection (y) = 2.5 mm
* Yield Strain limit for 3D printed PLA (epsilon_allowable) = 0.015 (1.5%)
* Modulus of Elasticity for PLA (E) = 2300 MPa

#### B. Moment of Inertia Equation
The area moment of inertia (I) for the rectangular flexure arm cross-section is:

I = (b * h^3) / 12

I = (15.0 * (3.0)^3) / 12 = (15.0 * 27.0) / 12 = 33.75 mm^4

#### C. Maximum Mechanical Strain Equation
The maximum strain (epsilon) occurring at the root base of the cantilever flexure arm is calculated as:

epsilon = (1.5 * h * y) / (L^2)

epsilon = (1.5 * 3.0 * 2.5) / (50.0^2)
epsilon = 11.25 / 2500.0 = 0.0045 (0.45%)

**Result:** Since the calculated strain of 0.45% is significantly less than the material allowable strain of 1.5% (epsilon < epsilon_allowable), the cantilever arm deforms purely elastically without permanent yield deformation.

#### D. Maximum Bending Stress Equation
The maximum bending stress (sigma) developed at the root of the flexure arm is calculated using Hooke's Law:

sigma = E * epsilon

sigma = 2300 * 0.0045 = 10.35 MPa

#### E. Engagement Deflection Force Equation
The perpendicular force (P) required to deflect the beam tip by 2.5 mm is:

P = (3 * E * I * y) / (L^3)

P = (3 * 2300 * 33.75 * 2.5) / (50.0^3)
P = 583031.25 / 125000.0 = 4.66 N

#### F. Assembly Mating Push Force Equation
Taking into account the friction coefficient (mu = 0.3) and a lead angle (alpha = 30 degrees):

tan_alpha = 0.577

W = P * (mu + tan_alpha) / (1 - (mu * tan_alpha))

W = 4.66 * (0.3 + 0.577) / (1 - (0.3 * 0.577))
W = 4.66 * (0.877) / (1 - 0.1731)
W = 4.087 / 0.8269 = 4.94 N

---

### Parametric Design Questions & Answers

1. **What are the parameters used?**
   * Beam length (L = 50.0 mm), beam root thickness (h = 3.0 mm), beam width (b = 15.0 mm), tip deflection depth (y = 2.5 mm), and wall clearances (1.5 mm side / 2.9 mm top-bottom).

2. **Why did you choose the specific parameters?**
   * Dimensions were selected to ensure the maximum strain experienced during engagement remains under 0.5%, well below PLA's yield limit (1.5%), while maintaining a compact form factor for 3D printing.

3. **What values did you choose for the specific parameters?**
   * L = 50.0 mm, h = 3.0 mm, b = 15.0 mm, y = 2.5 mm, cover wall thickness = 1.5 mm, engagement length = 45.0 mm, and handle extension = 5.0 mm.

4. **Did the values change throughout the process? If so, why?**
   * Yes, the thickness of the beam root was initially modeled thicker, but reduced to 3.0 mm to decrease the required insertion force and lower root stress concentrations.

5. **Take many pictures of the different stages of the CAD model.**
   *(Images documented above under Section 1: Modeling)*

6. **Detail the decision-making process and how you determined the engineered allowances of the interactive parts.**
   * A nominal clearance allowance of 0.2 mm to 0.3 mm was specified between mating sliding surfaces to compensate for standard FDM printing dimensional swelling and layer line friction.

7. **Take a picture of the overall design in CAD.**

![Overall Assembly Model](Design%20Step%204.jpg)

---

## 3. 3D Printing and Testing Section

### Research & Build Orientation Analysis
In FDM 3D printing, anisotropic layer bonding dictates that parts are weakest across layer boundaries (along the Z-axis). For a cantilever flexure beam subjected to bending loads, orienting the beam flat on the print bed (XY-plane orientation) ensures that tensile stresses align parallel to continuous extruded filament strands rather than pulling layers apart.

### Slicer Configuration & Pre-Processing
* **Build Orientation:** Laid flat along the length of the beam to maximize flexural strength along the outer fibers.
* **Support Structures:** Minimal snug support added under overhang features to prevent sagging while maintaining easy post-processing removal.
* **Infill Percentage:** 20% infill with a grid pattern for the body, and 4 perimeter walls to reinforce full solid density through the flexure arm section.
* **Print Settings:** 0.20 mm layer height, nozzle temperature of 210 degrees C, and bed temperature of 60 degrees C.

### Process Video

*(Video demonstration of 3D printing the snap fit letters and functional testing will be placed here)*
