# Lab #8: Design and Print Something Useful

## Reading and Writing
Asking smart questions matters because it stops us from rushing blindly into a solution before we truly understand what needs to be fixed. In design thinking, taking the time to investigate the core problem helps uncover hidden constraints, user needs, and root causes instead of just treating surface-level symptoms. Good questions challenge our initial assumptions, open up new creative perspectives, and make sure we spend our time solving the right problem rather than moving fast in the wrong direction.

## Problem Statement
1. **Purpose of your design & Research:**  
   The purpose of this design is to create a simple, compact tabletop laptop holder that elevates the computer screen to a more ergonomic viewing height while improving airflow underneath the chassis to prevent overheating. *(Research reference: [Great Questions Lead to Great Design: A Guide to the Design-thinking Process](https://www.toptal.com/designers/product-design/design-thinking-great-questions)).*

2. **How you noticed the problem:**  
   I noticed this problem during daily study and work sessions when looking down at a flat laptop screen caused neck strain, and the bottom of the laptop became noticeably warm due to blocked air vents resting directly against the desk.

3. **Target User / Ideal User:**  
   The ideal user is a student, remote worker, or professional who spends long hours at a desk using a laptop and wants an inexpensive, lightweight, and clutter-free ergonomic setup.

4. **Approach to Design:**  
   The design approach focuses on a minimalist, angle-optimized profile modeled in CAD. It uses a stable base design that can be sliced efficiently in PrusaSlicer and 3D printed quickly out of standard rigid filament without needing complex assembly or permanent hardware.

## Design (40%)

### 1. Initial Concept & Sketching
* The initial concept for the tabletop laptop holder started with hand-drawn concept sketches outlining an inclined, low-profile cradle that elevates the computer screen while maximizing airflow underneath the chassis. These sketches were exported to a PDF and included in the portfolio workspace.

### 2. CAD Modeling Stages
The 3D model was built step-by-step in SolidWorks (`Table Top Laptop Holder.SLDPRT`), following a structured parametric design workflow:

* **Step 1: Base Profile Sketch**  
  Started with a side-profile sketch establishing the 65° incline angle, 180.00 mm base length, 100.00 mm height, and an initial fillet radius of R11.00 mm for the front laptop stop[cite: 3].
  ![Design Step 1](Design Step 1.jpg)

* **Step 2: Extrusion & Width Definition**  
  Extruded the side profile sketch using a blind extrusion set to 160.00 mm width to create the primary structural arm and connect the support base[cite: 4].
  ![Design Step 2](Design Step 2.jpg)

* **Step 3: Reference Plane Creation**  
  Created an offset reference plane (`Plane1`) positioned at an exact distance of 80.00 mm from the outer face to prepare for mirroring the structural arm[cite: 5].
  ![Design Step 3](Design Step 3.jpg)

* **Step 4: Mirror Operation**  
  Used the Mirror feature across `Plane1` to replicate the left-side support arm and base structure symmetrically, ensuring a balanced dual-rail cradle configuration[cite: 1].
  ![Design Step 4](Design Step 4.jpg)

* **Step 5: Final Assembly & Fillets**  
  Completed the model by adding structural fillets (e.g., `Fillet15`) to eliminate sharp stress concentration corners and ensure smooth transitions[cite: 2].
  ![Design Step 5](Design Step 5.jpg)

### 3. Decision Making Along the Way
* **Angle Optimization:** Selected a **65° incline angle** because it provides an ideal ergonomic viewing height for standard desk use while keeping the laptop securely cradled against gravity without slipping.
* **Open Frame Architecture:** Designed the stand with two parallel support rails rather than a solid block. This drastically reduces print time, saves filament weight, and leaves the entire bottom surface of the laptop open to ambient air, preventing thermal throttling.
* **Stress Reduction:** Integrated generous fillets (R5.00 mm and R11.00 mm) at all high-stress corners and bending joints to eliminate sharp edges where layer lines might otherwise crack under heavy typing pressure.

### 4. Engineered Allowances & Tolerances
* **FDM Shrinkage & Tolerances:** Designed with a nominal structural wall thickness of **10.00 mm** to ensure rigid resistance against downward bending loads.
* **Surface Clearances:** Maintained strict geometric constraints in the front lip slot (radius R11.00 mm) to ensure standard laptop edge thicknesses (ranging from 15mm to 20mm) fit snugly without requiring post-processing sanding or risking loose movement.

### Final Design Dimensions & Engineering Drawing
The complete technical drawing specifies all critical manufacturing dimensions, including the overall width (172.22 mm outer / 152.37 mm inner span), 97.15 mm vertical clearance, and 30.00 mm component spacing[cite: 6].

![Table Top Laptop Holder Drawing](Table Top Laptop Holder.jpg)

* **SolidWorks Drawing File:** You can download or view the complete engineering drawing and part files here: [Table Top Laptop Holder Drawing (`Table Top Laptop Holder.SLDDRW`)](Table%20Top%20Laptop%20Holder.SLDDRW)[cite: 6].
