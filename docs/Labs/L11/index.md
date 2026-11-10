### LAB 11: Snap Fit Research and Modeling Principles

## 1. Summary of Key Design Principles

For this design, a **cantilever snap-fit** was selected. This type of snap fit uses flexible arm clips on the lid that bend slightly as you push the lid down, then spring back out to lock into slots cut into the main box.

Key design principles used from the *Snap-Fit Joints for Plastics* guide include:

- **Cantilever Arm Action:** The clips act like small diving boards. They bend out of the way during assembly and flex back to their original straight shape once fully closed, so they don't stay under constant stress.

- **Tapered Shape:** The clips are thicker at the base (where they attach to the lid) and get thinner near the hook tip. This helps distribute the bending evenly along the whole arm instead of concentrating all the strain right at the base.

- **Smart Hook Angles:**
  - The sloped front angle (entry angle) makes it easy to slide the lid into place without needing to force it.
  - The flat back ledge (retention angle) keeps the lid securely locked in place so it won't pop off accidentally.

---

## 2. Main Design Features and Visual Breakdown

The shape of the snap fit handles bending and force through three key geometric features:
![Lab 11](Lab%2011.png)

**Important Features Shown in the CAD Model:**

1. **Deflection / Push Distance (y):**  
   This is how far the hook sticks out. As you press the lid down, the wall of the box pushes the clip sideways by this exact distance until it hits the slot opening.

2. **Smooth Base Fillet (Root Radius R):**  
   Sharp inner corners break easily when bent. Adding a rounded curve (fillet) where the clip attaches to the lid spreads out the bending stress and prevents cracking.

3. **Tapered Arm Thickness:**  
   Making the arm thicker at the base and thinner near the tip keeps the bending spread out evenly, preventing the base from over-stretching.

---

## 3. How the Math and Physics Control the Fit

The performance of the snap fit comes down to a few basic rules of physics:

### Bending and Stretching (Strain epsilon)

The maximum amount the material stretches (epsilon) when the clip bends sideways is calculated by:

epsilon = 1.5 * (h * y) / L^2
  
Where:
- h = Thickness of the arm at the base
- y = How far the clip is pushed sideways (undercut depth)
- L = Length of the flexible arm

To stop the clip from bending permanently out of shape or snapping off, the stretch (epsilon) must stay below the maximum limit allowed by the material.

### Push Force (W)

The amount of hand force needed to snap the lid on depends on:

  F = (E * w * t^3 * y) / (4 * L^3) * (mu + tan(alpha)) / (1 - mu * tan(alpha))


Where:
- E = How stiff the plastic is (modulus of elasticity)
- b = Width of the clip
- alpha = Angle of the sloped hook
- mu = Friction between the sliding plastic parts

### How Geometry Affects the Fit

- **Arm Length (L):** Making the arms longer makes them much softer and easier to bend. Longer arms lower the push force and prevent cracking.
- **Arm Thickness (h):** Making the clip thicker makes it exponentially stiffer. A small increase in thickness makes the lid much harder to snap on.

---

## 4. How 3D Printing Resin (SLA) Affects the Design

Printing this design on a Form 4 SLA printer using resin requires specific design choices compared to regular molded plastics:

- **Resin is Stiffer and More Brittle:** Formlabs SLA resin is hard and rigid, but it cannot stretch as much as common flexible plastics (like polypropylene). If bent too far, SLA resin snaps instead of stretching.

- **Design Adjustments for Resin:**
  - **Longer, Slender Clips:** The arms are designed longer (L) so they bend gradually without over-stretching the material.
  - **Generous Base Curves:** Extra rounded fillets are added to the root of the arm because 3D printed resin is sensitive to sharp notches.
  - **Clearance Gap:** A small space (~0.015 to 0.025 in) is left between the clip and the box slot so the parts slide smoothly together without jamming.

---

# Snap Fit CAD Design

## 1. Mechanism Identification & Function

- **Type of Snap Fit:** Cantilever Snap-Fit Mechanism (Internal dual clips with symmetrical hooks).
- **Intended Function:** This snap-fit mechanism locks a top cover lid onto an oval box housing. It keeps the box securely closed during handling while keeping the locking clips inside for a clean, smooth outer appearance.

---

## 2. Combined SolidWorks Modeling Process

### Part A: Box Housing Modeling Steps

The lower box housing was created in SolidWorks using a 4-step process:

1. **Step 1: Main Outer Shell (Boss-Extrude1)**  
   Sketched an oval slot shape (1.00 in long by 0.75 in wide) with a 0.65 in inner boundary to set a uniform wall thickness of 0.05 in (1.27 mm). Extruded vertically to form the outer walls.
 ![Box Step 1](Box%20Step%201.png)

2. **Step 2: Base Floor Plate (Boss-Extrude2)**  
   Sketched a solid oval matching the bottom of the walls and extruded it 0.05 in upward to close the bottom of the box.
 ![Box Step 2](Box%20Step%202.png)

3. **Step 3: Snap Engagement Slots (Cut-Extrude1)**  
   Sketched a 0.25 in × 0.25 in square on both side faces and cut through both walls. These windows serve as the locking receivers for the lid's snap hooks.
![Box Step 3](Box%20Step%203.png)

4. **Step 4: Bottom Drain Holes (Cut-Extrude2)**  
   Cut six small circular holes through the bottom floor plate.
![Box Step 4](Box%20Step%204.png)

### Part B: Cover Lid Modeling Steps

The top cover plate and internal snap clips were created using an 8-step process:

1. **Step 1: Base Lid Plate (Boss-Extrude1)**  
   Sketched an oval matching the box dimensions (1.00 in × 0.75 in) and extruded it 0.05 in thick.
![Cover Snap Step 1](Cover%20Snap%20Step%201.png)

2. **Step 2: Snap Arm Block (Boss-Extrude2)**  
   Sketched a 0.25 in × 0.15 in rectangle on the underside of the lid and extruded it up by 0.47 in to create material for the clip arm.
![Cover Snap Step 2](Cover%20Snap%20Step%202.png)

3. **Step 3: Shaping the Hook Profile (Cut-Extrude1)**  
   Cut the side profile of the block to define the clip geometry: an arm length of 0.27 in, a hook overhang (undercut) of 0.05 in, and a tapered wall thickness going from 0.03 in down to 0.010 in near the tip.
![Cover Snap Step 3](Cover%20Snap%20Step%203.png)

4. **Step 4: Mirroring Second Arm (Mirror1)**  
   Mirrored the finished snap arm across the center plane to create the matching clip on the opposite side.
![Cover Snap Step 4](Cover%20Snap%20Step%204.png)

5. **Step 5: Side Thumb Tab (Boss-Extrude3)**  
   Extruded a small 0.15 in tab extending outward from the edge of the lid plate to create a finger grip for easy removal.
![Cover Snap Step 5](Cover%20Snap%20Step%205.png)

6. **Step 6: Base Fillets (Fillet1)**  
   Added a smooth R 0.05 in fillet curve at the root base where the snap arms attach to the lid.
![Cover Snap Step 6](Cover%20Snap%20Step%206.png)

7. **Step 7: Mirroring Second Thumb Tab (Mirror4)**  
   Mirrored the thumb tab to the opposite side of the lid.
![Cover Snap Step 7](Cover%20Snap%20Step%207.png)

8. **Step 8: Outer Edge Fillets (Fillet2 & Fillet3)**  
   Applied an R 0.10 in fillet to round off the sharp outer edges of the thumb tabs and top plate.
![Cover Snap Step 8](Cover%20Snap%20Step%208.png)

---

## 3. Engineering Design Intent & Mechanical Principles

### A. Controlling Stress and Deflection

- **Root Fillets (Fillet1):** Adding the R 0.05 in curve at the base of the snap arm eliminates sharp 90° inner corners. Sharp corners concentrate bending force and cause arms to snap off easily; the fillet spreads this force out safely.

- **Tapered Thickness:** The arm tapers from 0.03 in at the root down to 0.010 in near the tip. This ensures the arm bends smoothly along its whole length rather than bending only at the base.

- **Hook Angles:** The sloped outer face allows the clip to slide into the box with light hand force, while the flat 90° ledge inside holds the lid closed securely until intentionally opened.

The FEA simulation results confirm that maximum von Mises stress concentrates at the filleted root ($R = 0.05\text{ in}$) without exceeding the resin yield strength, while maximum displacement occurs at the snap hook tip during initial deflection.
![Cover Snap FEA Displacement](Cover%20snap-Static%201-Displacement-Displacement1.jpg)

![Cover Snap FEA Strain](Cover%20snap-Static%201-Strain-Strain1.jpg)

![Cover Snap FEA Stress](Cover%20snap-Static%201-Stress-Stress1.jpg)

### B. SLA Printing Adjustments & Clearances

- **Drain Holes:** The 6 floor holes (Cut-Extrude2) prevent suction forces on the Form 4 printer bed and allow uncured liquid resin to drain cleanly out during washing.

- **Clearance Gaps:** A clear space of 0.02 in was designed between the box slot and the lid clips so SLA resin parts can slide together smoothly without binding or sticking.

### C. Separable Assembly Design

The snap hooks lock directly into open window slots cut through the side walls. To separate the lid from the box, a user can press the exposed hook tips inward through the window slots while lifting up on the side thumb tabs.


![Assemble Crosssection View on Clip or snap fit location](Assemble%20Crosssection%20View%20on%20Clip%20or%20snap%20fit%20location.png)

![Assemble Distance Between clip to box slot](Assemble%20Distance%20Between%20clip%20to%20box%20slot.png)
---

# Preprocessing and 3D Printing

## 1. Machine & Material Setup

- **Printer:** Formlabs Form 4 (SLA 3D Printer)
- **Resin:** Standard Gray Resin (V5)

## 2. Print Orientation & Reasoning

- **Position:** Both parts were tilted at a 45° angle rather than printed flat.
- **Why Tilt?**
  - **Prevents Suction:** Flat hollow faces create strong suction forces that can tear or distort resin prints.
  - **Smoother Snap Clips:** Angling the snap arms lets layers build smoothly, preventing layer splits during bending.
  - **Cleaner Outer Surface:** Placed support mark nubs on non-visible bottom edges.

## 3. Plate Layout & Supports

- **Layout:** The Box and Lid were placed side-by-side with a 15–20 mm gap, allowing 2 to 3 student project sets to fit on a single shared build plate.
- **Supports:** Auto-generated light supports (0.40 mm touchpoints) placed under key overhangs and hook edges.
- **Wall Thickness:** 0.05 in (1.27 mm) to keep the box walls from bulging.
- **Layer Resolution:** 0.050 mm (50 μm).
![Printing Slide](Printing%20Slide.png)
![Printing Slide Supports](Printing%20Slide%20supports.png)

## 4. Resin Isotropy & Clearance

- **Isotropic Strength:** SLA resin cures chemically across layer lines, making the snap arms equally strong in all bending directions (unlike weaker, layer-dependent FDM prints).
- **Clearance Gap:** A gap of 0.02 in was added around the hook and slot to ensure parts slide together without sticking.

## 5. Slicer Summary Table

| Parameter     | Value                          |
|---------------|--------------------------------|
| Printer       | Formlabs Form 4                |
| Resin         | Standard Gray Resin (V5)       |
| Layer Height  | 0.050 mm (50 μm)               |
| Print Time    | 1 Hour 20 Mins                 |
| Resin Used    | ~18.5 mL (including supports)  |

<video controls width="100%">
  <source src="https://github.com/MHasan-27/Mohammad-Hasan/raw/main/docs/Labs/L11/Printing%20Video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
---

# Post-Processing

## 1. Post-Processing Steps & Timing

| Step               | Tool / Method                           | Duration          |
|--------------------|-----------------------------------------|-------------------|
| 1. Wash            | Form Wash (99% Isopropyl Alcohol - IPA) | 10 mins           |
| 2. Dry             | Air blow-dry & bench dry                | 15 mins           |
| 3. Cure            | Form Cure UV chamber (60°C)             | 15 mins at 60°C   |
| 4. Support Removal | Flush cutters & tweezers                | 5 mins            |
| 5. Finishing       | No Sanding needed                       | —                 |

## 2. Key Observations

- **Effect of Post-Curing:** Right after washing, the uncured resin clips feel soft and rubbery ("green state"). UV post-curing stiffens the plastic, giving the clips a strong spring-back action and a crisp locking snap.

- **SLA vs. PLA (FDM):** PLA filament clips often break along printed layer lines when bent. SLA resin has uniform strength throughout the arm, making it much more reliable under cyclic bending.

- **Surface Finish & Fit:** The Form 4 produced smooth, mold-like outer walls and accurate dimensions, allowing the lid clips to snap into the box slots without extra sanding or filing.

---

# Validation

## 1. Fit Performance & Engagement

- **Secure Engagement:** Yes. The internal cantilever hooks snap securely into the box window slots with a distinct, satisfying click. The lid stays firmly attached during handling.

- **Fit Quality:** Ideal fit. The snap connection is neither too tight nor too loose. The lid closes flush without needing excessive force, and it does not rattle or fall off.

- **Adjustments Needed:** None. No post-print filing, trimming, or CAD adjustments were required after printing.

## 2. Applied SLA Clearances

- **Tolerance Applied:** Using empirical tolerance findings learned from Lab 10, a clearance gap of 0.015 to 0.025 in (0.38 – 0.63 mm) was applied between the sliding snap arms and the box walls.

- **Result:** This clearance offset perfectly accounted for SLA resin light bleed and liquid swelling, allowing the parts to slide and lock together seamlessly on the first print attempt.

## 3. Assembled Artifact Proof

![Printed Parts Back](Printed%20Parts%20Back.jpeg)

![Printed Parts Front](Printed%20Parts%20Front%20.jpeg)

![Printed Parts Isometric Assemble view](Printed%20Parts%20Isometric%20Assemble%20view.jpeg)


---

# Lessons Learned

## 1. Challenges with Resin Flexibility & Clearance

- **Material Stiffness:** SLA Formlabs resin is stiffer and more brittle than standard FDM plastics (like PLA or ABS). Designing short or thick snap arms risks snapping the clips under bending load.

- **Finding the Balance:** The main design challenge was making the cantilever arms long (0.27 in) and tapered down (0.030 in → 0.010 in) so they could flex enough to clear the undercut without exceeding the resin's low strain limit.

## 2. SLA Tolerances & Print Orientation

- **Tolerance Control:** SLA printing provides high detail, but resin swelling requires an empirical offset of 0.015 in – 0.025 in for sliding fits.

- **Orientation Matters:** Printing parts at a 45° tilt prevents suction cup forces on hollow box bodies, improves surface smoothness on hooks, and places support mark nubs on hidden bottom edges.

## 3. SLA vs. FDM Snap Fits

| Feature              | SLA Snap Fits (Resin)                                                                 | FDM Snap Fits (Filament - PLA)                                                         |
|----------------------|---------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| Strength Uniformity  | Isotropic: Chemical bonds form evenly across layers, preventing clip snaps along layer lines. | Anisotropic: Weak layer adhesion makes snap arms prone to snapping along Z-axis print lines. |
| Surface Finish       | Smooth, injection-mold-like sliding surfaces with minimal friction.                   | Stepped layer lines create friction and rough sliding action.                          |
| Material Flexibility | Stiffer & more brittle; requires longer, thinner arm geometry.                        | More flexible/ductile; tolerates larger bending strain before cracking.                |

## 4. Cost, Time, and Resource Summary

- **Print Time:** Fast batch printing of 1 hour 20 minutes on the Form 4. Total 12 Hours
- **Material Efficiency:** Used only ~18.5 mL of liquid resin (including supports), making it a low-cost print.
- **Shared Platform:** Couldn’t find anyone to share the printer.

## CAD Download Files
* 📦 [Box Part File (Box.SLDPRT)](Box.SLDPRT)
* 📦 [Cover Snap Lid File (Cover snap.SLDPRT)](Cover%20snap.SLDPRT)
* ⚙️ [Assembly File (Assem1.SLDASM)](Assem1.SLDASM)
* 🖨️ [Formlabs PreForm Print File (Snap Fit.form)](Snap%20Fit.form)
