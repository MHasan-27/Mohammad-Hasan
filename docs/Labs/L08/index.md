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

## Design 

### 1. Initial Concept & Sketching
* The initial concept for the tabletop laptop holder started with hand-drawn concept sketches outlining an inclined, low-profile cradle that elevates the computer screen while maximizing airflow underneath the chassis. These sketches were exported to a PDF and included in the portfolio workspace.

### 2. CAD Modeling Stages
The 3D model was built step-by-step in SolidWorks (`Table Top Laptop Holder.SLDPRT`), following a structured parametric design workflow:

* **Step 1: Base Profile Sketch**  
  Started with a side-profile sketch establishing the 65° incline angle, 150.00 mm base length, 100.00 mm height, and an initial fillet radius of R11.00 mm for the front laptop stop.
  ![Design Step 1](Design%20Step%201.png)

* **Step 2: Extrusion & Width Definition**  
  Extruded the side profile sketch using a blind extrusion set to 160.00 mm width to create the primary structural arm and connect the support base.
  ![Design Step 2](Design%20Step%202.png)

* **Step 3: Reference Plane Creation**  
  Created an offset reference plane (`Plane1`) positioned at an exact distance of 80.00 mm from the outer face to prepare for mirroring the structural arm.
  ![Design Step 3](Design%20Step%203.png)

* **Step 4: Mirror Operation**  
  Used the Mirror feature across `Plane1` to replicate the left-side support arm and base structure symmetrically, ensuring a balanced dual-rail cradle configuration.
  ![Design Step 4](Design%20Step%204.png)

* **Step 5: Final Assembly & Fillets**  
  Completed the model by adding structural fillets (e.g., `Fillet15`) to eliminate sharp stress concentration corners and ensure smooth transitions.
  ![Design Step 5](Design%20Step%205.png)

### 3. Decision Making Along the Way
* **Angle Optimization:** Selected a **65° incline angle** because it provides an ideal ergonomic viewing height for standard desk use while keeping the laptop securely cradled against gravity without slipping.
* **Open Frame Architecture:** Designed the stand with two parallel support rails rather than a solid block. This drastically reduces print time, saves filament weight, and leaves the entire bottom surface of the laptop open to ambient air, preventing thermal throttling.
* **Stress Reduction:** Integrated generous fillets (R5.00 mm and R11.00 mm) at all high-stress corners and bending joints to eliminate sharp edges where layer lines might otherwise crack under heavy typing pressure.

### 4. Engineered Allowances & Tolerances
* **FDM Shrinkage & Tolerances:** Designed with a nominal structural wall thickness of **10.00 mm** to ensure rigid resistance against downward bending loads.
* **Surface Clearances:** Maintained strict geometric constraints in the front lip slot (radius R11.00 mm) to ensure standard laptop edge thicknesses (ranging from 15mm to 20mm) fit snugly without requiring post-processing sanding or risking loose movement.

### 5. Design Limitations & Proposed Improvements
* **Sizing & Compatibility Constraints:** Due to physical build volume limitations of the 3D printer and the single-part design, the current stand cannot accommodate larger 15-inch laptops and is currently limited to smaller devices such as the MacBook Air and iPad.
* **Friction & Stability Additions:** 
  * **Base Anti-Slip Pads:** The bottom base requires the addition of stick-on rubber pads to create necessary friction against smooth desk surfaces and ensure overall stability during typing.
  * **Arm Grip Pads:** Rubber contact pads can also be placed on the upper surface of the holder arms to increase friction, which would help securely grip larger devices and prevent slipping.

### Final Design Dimensions & Engineering Drawing

![Table Top Laptop Holder Drawing](Table%20Top%20Laptop%20Holder.JPG)

* **SolidWorks Drawing & Part Files:** You can download the native files directly from your repository directory:
  * [Download SolidWorks Drawing (`Table Top Laptop Holder.SLDDRW`)](Table%20Top%20Laptop%20Holder.SLDDRW)
  * [Download SolidWorks Part (`Table Top Laptop Holder.SLDPRT`)](Table%20Top%20Laptop%20Holder.SLDPRT)

  ## 3D Print
  

* **Video the process of the 3D print:**  
    A video recording of the print run is embedded below:
  
  <video controls width="100%">
    <source src="Printing%20Videos.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>

1. **What number machine did you use?**  
   Prusa CORE One (Machine #15).
   ![Printing Machine](Printing%203.jpeg)
   

2. **Did you use a raft? If so, what were the settings?**  
   No raft was used. A **5 mm brim** was enabled instead, along with an **Elephant foot compensation of 0.25 mm** to ensure stable bed adhesion along the sharp corners, prevent warping, and maintain precise first-layer dimensions without wasting excessive material.
   ![Elephant foot Compensation](Elephant%20foot%20Compensation.png)
  

3. **What was the wall thickness?**  
   Set to **3 perimeters** (minimum vertical shell thickness) for structural rigidity and load support.
   ![Slice Perimeters Settings](Slice%20Perimeters%20Settings.png)

4. **What infill did you use and why?**  
   **15% Gyroid infill pattern** was used because it provides isotropic strength properties (equal resistance to loads in all directions) and an optimal strength-to-weight ratio.
   ![Infill Pattern](Infill%20Pattern.png)

5. **Did you use supports? Why or why not? If you did, explain the technical process you used to support the print.**  
   Supports were enabled to support the overhangs under the front lip cradle. A support interface gap of 0.2 mm was used to allow clean separation.
 ![Automatic Support](Automatic%20Support%20.png)

6. **What did you use to remove the supports?**  
   Removed manually using flush cutters, needle-nose pliers, and a flat scraper tool.
  

7. **How many layers are used in the print?**  
   Total layer count from the slicer preview: **1300 layers**.

8. **What is the layer thickness?**  
   **0.2 mm** standard resolution profile.

9. **What is the build volume of your print?**  
   Prusa CORE One build volume: **160 x 97.14 x 180 mm^3**.

10. **Comment on the surface finish of the supports:**  
    Slightly textured where support interfaces contacted the underside surfaces, which was easily smoothed out with fine-grit sandpaper.

11. **Outline reasons for the layout:**  
    Positioned flat in the center of the print bed to maximize thermal bed adhesion and ensure the print stayed secure throughout the run.

12. **Outline reasons for build orientation:**  
    Oriented horizontally flat so that primary mechanical bending stresses run parallel to continuous layers rather than across layer interfaces, maximizing shear strength.

13. **Outline slicer settings and reasons for the settings:**  
    Printed in **PLA** with a 0.4 mm nozzle. Configured advanced settings including a **Seam gap distance of 20%** and **Scarf joint placement set to "Everywhere"** to optimize outer perimeter blending and minimize visible layer lines.
    ![Slice Seam Gap distance and Scarf Joint placement](Slice%20Seam%20Gap%20distance%20and%20Scarf%20Joint%20placement%20.png)

14. **Note the slice information on Prusa Slicer:**  
    `Table Top Laptop Holder_0.4n_0.2mm_PLA_COREONE_5h4m.bgcode` — Estimated print time: **5 hours and 4 minutes**.

---

## Lessons Learned

* **Process Reflection:** Throughout this lab, I learned how critical proper part orientation is for FDM printing. Initially, printing components vertically risked layer delamination under the downward bending forces of typing. Orienting the dual-rail laptop stand flat on the bed significantly improved its load-bearing capacity. 
* **Mistakes & Trial and Error:** During my first test slice, support structures fused too tightly to the overhangs because the interface gap was set too narrow. Adjusting the gap to 0.2 mm in PrusaSlicer resolved this issue and made manual support clean-up much smoother.
* **Actual Time & Resources:** The entire process—from initial concept sketching and parametric SolidWorks modeling to slicing, post-processing support removal, and final validation—took approximately **6.5 hours** total. Resources utilized included SolidWorks, PrusaSlicer, a Prusa CORE One 3D printer, and roughly **120 grams of PLA filament**.

  ---

## Demonstration

Here is the physical demonstration of the 3D printed tabletop laptop holder in use, showcasing its compatibility with devices like the iPad and the final printed parts setup:

* **iPad Setup Demonstration:**  
  The stand securely holds and elevates smaller devices like an iPad at an optimal ergonomic viewing angle.
  ![Demonstration with iPad](docs/Labs/L08/Demonstration%20with%20ipad.jpeg)

* **Printed Parts Overview (View 1):**  
  Overview of the finished structural dual-rail components right after print completion.
  ![Printed Parts 1](docs/Labs/L08/Printed%20parts.jpeg)

* **Printed Parts Overview (View 2):**  
  Alternate angle showing the clean surface finish, geometric profile, and overall quality of the final printed parts.
  ![Printed Parts 2](docs/Labs/L08/Printed%20parts%202.jpeg)
