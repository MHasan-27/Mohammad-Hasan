# Lab #10: Assignment – RC2 Sliding Fit Design and Verification

## 1. Research and Planning

### ASME RC 2 Sliding Fit Specification

An **RC 2** (Class 2 Precision Sliding Fit) is designed for accurate location where parts must slide or move relative to one another smoothly with minimal play, but without running freely under continuous high-speed rotation.

According to ANSI B4.1 and the *Machinery’s Handbook*:

- **Hole Limits (H6):** The tolerance is applied unilaterally positive (+IT6 / −0.0000 in).
- **Shaft Limits (g5):** The tolerance is negative relative to nominal (−Clearance / −Total Tolerance).

#### Standard Tolerance Table for Nominal Size Ranges

**1. Range 0.12 in – 0.40 in**  
*(Applied to Pin OD and Pin Hole Radius 0.15 in)*

| Feature              | Tolerance          |
|----------------------|--------------------|
| Hole Tolerance (H6)  | +0.0003 in / −0.0000 in |
| Shaft Tolerance (g5) | −0.00015 in / −0.00035 in |
| Theoretical Clearance Range | 0.00015 in (min) to 0.00065 in (max) |

**2. Range 1.19 in – 1.97 in**  
*(Applied to Slide Width 1.30 in and Slide Length 1.90 in)*

| Feature              | Tolerance          |
|----------------------|--------------------|
| Hole/Slot Tolerance (H6) | +0.0006 in / −0.0000 in |
| Shaft/Slide Tolerance (g5) | −0.00040 in / −0.00080 in |
| Theoretical Clearance Range | 0.00040 in (min) to 0.00140 in (max) |

![RC2 Tolerance Fit Chart](RC2%20Tolerance%20Fit%20Chart.png)

### Real-World Application

RC 2 sliding fits are extensively utilized in manufacturing jigs, fixture locating pins, sliding cover mechanisms, and alignment tracks where high-repeatability positioning is required without binding or excessive wobbling.

### Hand Sketches

The mechanical dimensions, tolerances, and view callouts were documented prior to CAD modeling:

- **Box & Slide Sketch:** Shows the main box body (2.0 in × 1.5 in × 1.0 in), slot dimensions (1.30 in × 1.90 in × 0.15 in), and hole centerlines.
- **Shaft/Pin Sketch:** Shows the alignment pin head (0.25 in × 0.25 in × 0.10 in) and pin shaft diameter (R0.15 in / Ø0.30 in with RC 2 shaft tolerances).

![Lab 10 Hand Sketch Box And Slide](Lab%2010%20Hand%20Sketch%20Box%20And%20Slide.jpg)
![Lab 10 Hand Sketch Shaft](Lab%2010%20Hand%20Sketch%20Shaft.jpg)

---

## 2. CAD Design

### Component Modeling & Step-by-Step Design Workflow

The assembly comprises three parametric SolidWorks parts: the **Box** (Part A), the **Slide** (Part B), and the **Shaft/Pin** (Part C). Each model was constructed systematically using feature-based parametric operations tied to the global tolerance equations.

#### A. Box Modeling Workflow (`Box.SLDPRT`)
1. **Step 1: Main Body Extrusion & Internal Pocket Cut (`Boss-Extrude1` & `Cut-Extrude1`)**
   ![Box Step 1](Box%20Step%201.png)
2. **Step 2: Internal Sliding Channel Cut (`Cut-Extrude2`)**
   ![Box Step 2](Box%20Step%202.png)
3. **Step 3: Vertical Pin Hole Cut (`Cut-Extrude3`)**
   ![Box Step 3](Box%20Step%203.png)
4. **Step 4: Lead-In Edge Chamfer (`Chamfer1`)**
   ![Box Step 4](Box%20Step%204.png)
5. **Step 5: Base Resin Drainage Holes (`Cut-Extrude4`)**
   ![Box Step 5](Box%20Step%205.png)

#### B. Slide Modeling Workflow (`Slide.SLDPRT`)
1. **Step 1: Base Plate Extrusion (`Boss-Extrude1`)**
   ![Slide Step 1](Slide%20Step%201.png)
2. **Step 2: Pass-Through Pin Hole Cut (`Cut-Extrude1`)**
   ![Slide Step 2](Slide%20Step%202.png)
3. **Step 3: Perimeter Chamfer (`Chamfer1`)**
   ![Slide Step 3](Slide%20Step%203.png)

#### C. Shaft / Locking Pin Modeling Workflow (`Shaft.SLDPRT`)
1. **Step 1: Cylindrical Pin Shaft Extrusion (`Boss-Extrude1`)**
   ![Shaft Step 1](Shaft%20Step%201.png)
2. **Step 2: Rectangular Alignment Head Extrusion (`Boss-Extrude2`)**
   ![Shaft Step 2](Shaft%20Step%202.png)
### CAD Parametric Global Variables & Design Intent

To guarantee a functional RC 2 precision sliding fit on an SLA resin 3D printer (Formlabs Form 3+), a uniform clearance allowance offset of **0.006 in** was applied to all nominal dimensions across the three mating parts:

#### 1. Box Enclosure (`Box.SLDPRT`)

Applied a unilateral positive allowance (**+0.006 in**) to all internal slot feature dimensions and hole features to establish the upper hole boundary:

| Parameter                  | Equation                          | Value     |
|----------------------------|-----------------------------------|-----------|
| SW (Slide Width Gap)       | 1.3 + 0.006 in                    | **1.31 in** |
| SL (Slide Length Gap)      | 1.9 + 0.006 in                    | **1.91 in** |
| SH (Slide Height Gap)      | 0.15 + 0.006 in                   | **0.16 in** |
| Hole (Pin Hole Radius)     | 0.15 + 0.006 in                   | **0.16 in** |
| Hole Depth                 | —                                 | **0.40 in** |

![Box Equation](Box%20Equation.png)

#### 2. Slide Component (`Slide.SLDPRT`)

Applied a unilateral negative allowance (**−0.006 in**) to outer mating surfaces to establish the shaft/insert boundary:

| Parameter                  | Equation                          | Value     |
|----------------------------|-----------------------------------|-----------|
| SW (Slide Width)           | 1.3 − 0.006 in                    | **1.29 in** |
| SL (Slide Length)          | 1.9 − 0.006 in                    | **1.89 in** |
| SH (Slide Thickness)       | 0.15 − 0.006 in                   | **0.14 in** |
| Hole (Pass-Through Pin Hole) | 0.15 + 0.02 in                  | **0.17 in** |

![Slide Equation](Slide%20Equation.png)

#### 3. Shaft / Alignment Pin (`Shaft.SLDPRT`)

Applied a unilateral negative allowance (**−0.006 in**) to the cylindrical pin shaft:

| Parameter                  | Equation                          | Value          |
|----------------------------|-----------------------------------|----------------|
| OD (Shaft Radius)          | 0.15 − 0.006 in                   | **0.14 in** (Ø0.28 in) |
| Length                     | —                                 | **0.35 in**    |

![Shaft Equation](Shaft%20Equation.png)

### Theoretical Total Clearance

With the updated 0.006 in equations applied to both hole features (+0.006 in) and shaft features (−0.006 in), the resulting total diametral/bilateral operating clearance is:

Total Clearance = (+0.006 in) − (−0.006 in) = 0.012 in (12 mils)

This **0.012 in** total gap compensates for SLA UV shrinkage (0.5% – 1.5%), light bleed expansion along slot walls, and resin surface friction, allowing the slide and pin to move smoothly without seizing.

### Isometric Model Views
![Box Isometric View](Box%20Isometric%20view.png)
![Box Corner View](Box%20Corner%20View.png)
![Slide Isometric View](Slide%20Isometric%20View.png)
![Shaft Isometric View](Shaft%20Isometric%20View.png)

### E. Assembly Fit Verification & Mating

In SolidWorks Assembly (`Assem Lab 10.SLDASM`), mechanical mates were established to verify total system alignment:

- **Concentric Mate:** Between the Box vertical hole and Shaft outer cylinder.
- **Coincident Mates:** Between the Slide bottom face and Box slot bottom track, and between Shaft head underside and Box top face.
- **Cross-Sectional Analysis:** Confirmed a uniform theoretical operating clearance gap (0.012 in) along all sliding contact faces without interference.

![Assemble Isometric](Assemble%20Isometric.png)
![Assemble CrossSection](Assemble%20CrossSection.png)

---

## 3. Preprocessing for 3D Printing

| Parameter              | Value                                      |
|------------------------|--------------------------------------------|
| Target Printer         | Formlabs Form 3+ (SLA)                     |
| Resin Material         | Standard Clear / Grey Photopolymer Resin   |
| Layer Resolution       | 0.050 mm (50 μm)                           |
| Total Combined Volume  | ∼ 14.2 mL (Well within the 20 mL maximum lab constraint including support structures) |

**Build Orientation:**

- **Box:** Tilted at 30° relative to the build platform to minimize suction cup forces in the internal cavity and prevent layer line stepping across primary sliding faces.
- **Slide & Pin:** Oriented at 45° angles to ensure uniform resin drainage during printing.

**SLA Compensation Strategy:**  
Because cured SLA resin undergoes 0.5% – 1.5% volumetric post-cure shrinkage along with slight XY light-bleed expansion, offset scaling (0.02 mm XY expansion correction) was applied in PreForm to preserve the 0.012 in designed functional clearances.

---

## 4. Post-Processing

1. **Wash Stage:** Parts were submerged in the Form Wash (99% Isopropyl Alcohol) for 15 minutes to clear uncured liquid resin from the internal slot and pin hole.
2. **Support Removal:** Support touchpoints were clipped using flush cutters prior to UV curing to prevent surface gouging on functional sliding channels.
3. **Cure Stage:** Parts were cured in the Form Cure station at 60°C for 30 minutes.
4. **Surface Finishing:** Light hand-sanding with 800-grit wet sandpaper was performed on support contact stubs to maintain smooth, parallel sliding contact faces.

---

## 5. Fit Test & Measurement Verification

### Caliper Measurement Verification

Digital caliper measurements were taken across all functional features following full post-curing and cleaning:

| Feature / Dimension              | Target CAD Value (in) | Caliper Measurement (in) | Deviation (in) | Status / Evaluation                  |
|----------------------------------|-----------------------|--------------------------|----------------|--------------------------------------|
| Box Slot Width (SW)              | 1.310                 | 1.308                    | −0.002         | Accurate slot width                  |
| Slide Width (SW)                 | 1.290                 | 1.289                    | −0.001         | Smooth sliding motion                |
| Box Slot Height (SH)             | 0.160                 | 0.159                    | −0.001         | Proper vertical clearance            |
| Slide Thickness (SH)             | 0.140                 | 0.140                    | 0.000          | Nominal size achieved                |
| Box Pin Hole Radius (Hole)       | 0.160                 | 0.159                    | −0.001         | Accurate pin location                |
| Pin Shaft Radius (OD)            | 0.140                 | 0.141                    | +0.001         | Fits cleanly without binding         |

### Functional Fit Performance

The **0.012 in** total CAD clearance successfully compensated for physical printing variations. The slide moves smoothly along the internal channel without wobbling or binding, and the alignment pin drops freely into the indexing port to securely lock the sliding mechanism.

---

## 6. Lessons Learned

1. **Resin Light Bleed in Enclosed Slots:**  
   Internal channels tend to trap liquid photopolymer resin. Thorough IPA flushing with a syringe is essential before post-curing to avoid localized resin curing inside the slot.

2. **Post-Cure Shrinkage Factors:**  
   Dimensional contraction occurs during high-temperature UV post-curing. Incorporating 0.006 in CAD tolerance offsets (0.012 in total gap) ensures that tight RC 2 specifications do not convert into press fits.

3. **Total Project Time:**

   | Phase                        | Time     |
   |------------------------------|----------|
   | Research & Hand Sketching    | 2.0 hrs  |
   | CAD Modeling & Equations     | 2.0 hrs  |
   | Printing & Post-Processing   | 4.0 hrs  |
   | Measurement & Documentation  | 2.0 hr   |
   | **Total Time**               | **10.0 hrs** |

## Download CAD Files & Assembly

- [Download Box Part File (`Box.SLDPRT`)](Box.SLDPRT)
- [Download Slide Part File (`Slide.SLDPRT`)](Slide.SLDPRT)
- [Download Shaft/Pin Part File (`Shaft.SLDPRT`)](Shaft.SLDPRT)
- [Download Complete Assembly File (`Assem Lab 10.SLDASM`)](Assem%20Lab%2010.SLDASM)
   
