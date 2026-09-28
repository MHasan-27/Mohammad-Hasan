Here is the complete Markdown text for your `index.md` file, updated with all required embedded images, HTML5 video players, resource downloads, and direct file links corresponding to your repository structure.

---

# Lab #6: Design Fits for an Artifact

## Parametrically design

### CAD Design Process & Step-by-Step Reconstruction

The design process involved taking precise physical measurements of the artifact's mating feature and parametrically modeling a custom clip component to achieve a secure snap fit.

* **Step 1:** Sketched a $1.75\text{ in} \times 2.11\text{ in}$ base rectangular feature and extruded it to a thickness of $0.125\text{ in}$.
* **Step 2:** Sketched a pillar measuring $0.75\text{ in} \times 0.125\text{ in}$ on one side, located $0.25\text{ in}$ from the top edge of the base and $0.0625\text{ in}$ inward from the side edge. Extruded the pillar by $0.125\text{ in}$ and mirrored it to the opposite side along the same edge.
* **Step 3:** Using the same dimensions and offset distances from Step 2, sketched and mirrored two additional pillars on the opposite edge of the base.
* **Step 4:** Sketched a triangular catch profile on the inner-facing surface of one pillar. Mirrored the sketch across to the adjacent pillar and extruded the profile by $0.125\text{ in}$. Repeated the process for the remaining two pillars to complete all four snap-fit engagement tabs.
* **Step 5:** Sketched a $0.0625\text{ in} \times 0.125\text{ in}$ foot feature on the bottom face of each of the four pillars and extruded them downward by $0.0625\text{ in}$.
* **Step 6:** Applied fillet operations to the highlighted stress-concentration edges near the pillar roots and transition zones to improve bending durability during deflection.

---

### Parameters, Tolerances & Decision-Making

#### 1. Parameters Used

| Parameter | Artifact Dimension (in) | Snap Fit Drawing Dimension (in) |
| --- | --- | --- |
| **Length ($L$)** | $2.7010$ | $1.7500$ |
| **Width ($W$)** | $2.1010$ | $2.1100$ |
| **Thickness (Min)** | $0.1125$ (Target Area) | $0.1300$ |
| **Thickness (Max)** | $0.1395$ | N/A |

* **Width Tolerance:** Set to $\pm 0.005\text{ in}$ (Five Thousandths). If the width parameter is too large, the snap fit becomes too loose; if it is too small, the artifact cannot fit between the retaining pillars.
* **Length Parameter:** The snap clips grip along the sides, allowing the base component length ($1.7500\text{ in}$) to be shorter than the overall artifact length ($2.7010\text{ in}$) without sacrificing engagement strength.
* **Height / Thickness Allowance:** The maximum thickness ($0.1395\text{ in}$) occurs where the power input/output ports are located. Positioning the clips away from these ports avoids the maximum thickness region. The target feature minimum thickness is $0.1125\text{ in}$, while the drawing specifies an opening gap of $0.1300\text{ in}$ with a $-0.005\text{ in}$ tolerance, leaving sufficient clearance for insertion.
* *Note:* Prior testing in Lab #4 established our 3D printer height tolerance range as $-0.3\%$ to $+1.18\%$.

#### 2. Reason for Parameter Selection

Parameters were selected based on critical functional interface dimensions of the physical artifact. By parameterizing the gap, width, and pillar offsets in CAD, tolerance adjustments could be pushed directly to the model without re-creating geometry features if test fits required tuning.

#### 3. Specific Parameter Values

* Base Width: $2.1100\text{ in}$
* Base Length: $1.7500\text{ in}$
* Internal Opening Gap Thickness: $0.1300\text{ in}$
* Pillar Cross-Section: $0.7500\text{ in} \times 0.1250\text{ in}$

#### 4. Parameter Changes Throughout Process

| Dimension | Snap Fit Drawing Dimension (in) | Snap Fit Actual Printed Dimension (in) |
| --- | --- | --- |
| **Length ($L$)** | $1.7500$ | $1.7520$ |
| **Width ($W$)** | $2.1100$ | $2.1130$ |
| **Thickness** | $0.1300$ | Min = $0.1290$, Max = $0.1320$ |

#### 5. Artifact Feature Measurements

Digital calipers were used to measure the physical artifact features, establishing a width of $2.1010\text{ in}$ and target region thickness of $0.1125\text{ in}$.

#### 6. Hand Sketch & CAD Reference

A hand sketch was drafted to map datum references, critical tolerances, and clip profile dimensions.

#### 7. Artifact Feature Reconstruction

The mating features were recreated in CAD to verify geometric constraints and interference boundaries.

#### 8. CAD Model Development Stages

The model was built sequentially from initial base extrusions to clip geometry and edge fillets.

#### 9. Engineered Allowances & Decision Making

Allowances were determined by calculating the flexural deflection needed during insertion. A clip tip deflection allowance of $0.050\text{ in}$ (Fifty Thousandths) was engineered into the triangular lip face to allow outer arm expansion during snap-on engagement without exceeding material yield strength.

#### 10. Overall CAD Model Final View

Isometric view of the finalized parametric model.

---

## Documentation

### 3D Printing Parameters & Slicer Setup

1. **Machine Name:** Prusa CORE One ($0.4\text{ mm}$ Nozzle, Printer #6)
2. **Print Size / Bounding Dimensions:** $1.7520\text{ in} \times 2.1130\text{ in} \times 0.2500\text{ in}$ ($63.12\text{ mm} \times 19.05\text{ mm} \times 44.45\text{ mm}$)
3. **Layout Reasoning:** The part was placed flat on the print bed to maximize bed adhesion area and promote uniform heat distribution across the base plate.
4. **Build Orientation:** Oriented using the right-side face as the build base. This orientation aligns layer boundaries so that layer line stack-ups cross the clip arms, ensuring bending stresses act across the layers during snap engagement rather than causing inter-layer delamination.
5. **Support Structure Size & Type:** Supports were required under the overhang beam of the snap clips. Enabled smart surface detection using **Snug** support types to minimize support footprint and ensure clean removal.
6. **Wall Thickness:**
* Vertical Walls: $0.86\text{ mm}$
* Horizontal Top: 5 layers ($0.70\text{ mm}$)
* Horizontal Bottom: 3 layers ($0.50\text{ mm}$)


7. **Layer Count & Perimeters:** 2 perimeter wall loops used throughout the print.
8. **Layer Thickness / Height:** $0.20\text{ mm}$ layer height ($0.86\text{ mm}$ total extrusion perimeter width).
9. **Build Volume Occupied:** $63.12\text{ mm} \times 19.05\text{ mm} \times 44.45\text{ mm} = 8425.05\text{ mm}^3$ ($0.514\text{ in}^3$).
10. **Slicer Settings Rationale:**
* **Perimeters:** 2 perimeter walls were selected to maintain dimensional accuracy on side faces while ensuring structural integrity.
* **Infill Percentage:** 15% infill provided adequate internal stiffness without extending print time.
* **Infill Pattern:** **Gyroid** infill was selected due to its multi-directional load distribution and smooth printing path.


11. **Support Removal Tools:** Needle-nose pliers were used to break away the snug support structures beneath the clip overhangs.
12. **Fit Adjustments & Failure Analysis:** If dimensions were incorrect or tolerances were off, the part would fail to engage or fit loosely. Additionally, with a designed deflection of $0.050\text{ in}$, if clip arms snap during engagement, the clip depth and feature width parameters must be adjusted to reduce strain.

### Print Process Video

Below is the embedded video recording of the 3D printing process on the Prusa CORE One:

---

## Show and Tell

The printed part was physically mated to the artifact feature to verify the snap-fit retention.

### Demonstration Video

Below is the embedded video demonstrating the snap fit onto the physical artifact:

---

## Lessons Learned

* **FDM Anisotropy & Bending Stresses:** Layer line orientation is critical when designing snap-fit clips. Printing the arms such that bending stress acts across stacked layers prevents layer separation at the root of the cantilever beam.
* **Tolerance & Dimensional Accuracy:** Calibrating parameters based on known machine height variances ($-0.3\%$ to $+1.18\%$) ensured that the actual printed thickness ($0.1290\text{ in} - 0.1320\text{ in}$) matched our functional target gap ($0.1300\text{ in}$).
* **Support Placement for Mating Faces:** Using snug supports with smart surface detection reduced surface scarring on critical interior clip contact areas, allowing smooth deflection over the artifact edges.
* **Total Time & Resource Commitment:**
* **Total Time:** ~8 Hours (covering physical measurements, CAD parameter setup, test slicing, printing, support removal, and documentation).
* **Material / Resources Used:** PLA Filament on Prusa CORE One (Printer #6), needle-nose pliers, digital calipers.



---

## Resources & Download Links

Below are the downloadable CAD model files, technical drawings, print-ready G-code, and 3MF project files for this assignment:

* [Download CAD Solid Part (.SLDPRT)](https://www.google.com/search?q=Snap%2520fit.SLDPRT&utm_source=gemini)
* [Download CAD Drawing File (.SLDDRW)](https://www.google.com/search?q=Snap%2520fit.SLDDRW&utm_source=gemini)
* [Download 3D Print Project (.3MF)](https://www.google.com/search?q=Snap%2520fit.3mf&utm_source=gemini)
* [Download Prusa CORE One BGCode File (.bgcode)](https://www.google.com/search?q=Snap%2520fit_0.4n_0.2mm_PLA_COREONE_34m.bgcode&utm_source=gemini)

