# Lab 3: Design Something Small

## Design
For this lab assignment, I designed a compact, custom **Cable Organizer** using parametric CAD software. The design features tailored slots to secure desktop cables cleanly while adhering strictly to all assignment geometric constraints.

- **Dimensions:** 1.5 in x 1.5 in x 0.5 in ($38.1\text{ mm} \times 38.1\text{ mm} \times 12.7\text{ mm}$)
- **Overhangs:** None (designed with 0° overhang angles to eliminate the need for print supports)
- **CAD File Link:** [Lab 3 Mohammad Hasan.SLDPRT](https://github.com/MHasan-27/Mohammad-Hasan/blob/main/docs/Labs/L03/Lab%203%20Mohammad%20Hasan.SLDPRT)
- **STL File Link:** [Lab 3 Mohammad Hasan.STL](https://github.com/MHasan-27/Mohammad-Hasan/blob/main/docs/Labs/L03/Lab%203%20Mohammad%20Hasan.STL)

*Insert CAD design process screenshots here*

---

## Research
### Three Infill Types & Uses
1. **Gyroid:**
   - *Geometry:* A continuous, 3D wave pattern that provides balanced isotropic strength.
   - *Uses:* Best for parts subjected to multi-directional mechanical stress or liquid flow applications, as it has no internal flat planes and prevents shear failure along layer boundaries.
2. **Cubic:**
   - *Geometry:* A 3D pattern composed of stacked, tilted cubes forming internal pyramids.
   - *Uses:* Ideal for structural functional components that require equal load resistance across all three axes ($X$, $Y$, and $Z$) while minimizing total filament mass.
3. **Honeycombed (Hexagonal):**
   - *Geometry:* A repeating 2D hexagonal cell structure mimicking natural honeycomb.
   - *Uses:* Excellent for lightweight parts requiring high strength-to-weight ratios along the vertical axis, commonly used in drone frames and aerospace brackets.

### Core Questions Addressed
- **How does percentage infill affect mechanical properties?**
  Increasing the infill percentage directly increases part density, overall weight, tensile strength, and impact resistance. However, strength gains plateau around 50–60% infill, beyond which material consumption increases drastically with marginal mechanical improvement.
- **How do different infill patterns affect mechanical properties?**
  Patterns dictate stress distribution. 2D patterns like **Grid** or **Rectilinear** offer high strength along specific principal axes, whereas 3D patterns like **Gyroid** distribute forces evenly across all spatial planes.
- **Why use different wall thicknesses?**
  Wall thickness (perimeters) contributes significantly more to overall bending and structural stiffness than internal infill. Adding more wall shells increases outer layer strength, prevents infill show-through, and improves waterproofing without filling the entire inner core solid.

---

## Preprocessor and Printing
Models were arranged in PrusaSlicer to combine multiple parts on a single platform for efficient batch execution on the UNCC print farm.

- **Printer Used:** Prusa CORE One ($0.4\text{ mm}$ nozzle)
- **Material:** Generic PLA
- **Infill Percentage:** 20% (modified from the default 15%)
- **Infill Pattern:** Grid (chosen for rapid printing and rigid vertical load support)
- **Wall Thickness / Perimeters:** 3 perimeters (modified from standard 2 for enhanced outer rigidity)
- **Layer Height:** $0.20\text{ mm}$ SPEED
- **Build Orientation:** Placed flat on its largest bottom face to ensure maximum bed contact and stability.
- **Scaling:** None required (designed natively to meet size limits).
- **G-Code File Link:** [Lab 3 Gcode Slice](https://github.com/MHasan-27/Mohammad-Hasan/blob/main/docs/Labs/L03/Lab%203%20Mohammad%20Brayan%20Ameer%20Noah_0.4n_0.2mm_PLA_COREONE_22m.bgcode)

![Lab 3 Slice](Lab%203%20Slice.png)

![Lab 3 Print Settings](Lab%203%20Print%20Settings.png)

---

## Print
- **Group Execution:** Worked in a team of 4 (Mohammad, Brayan, Ameer, and Noah) to batch print our individual parts on a single build bed.
- **Estimated & Actual Print Time:** **22 minutes** total for all 4 parts combined (well under the 1.5-hour maximum constraint).
- **Stipulation Verification:** Verified dimensions ($1.5'' \times 1.5'' \times 0.5''$), zero overhangs, PLA material, and modified wall parameters.
<video src="Printing%20Video.mp4" controls width="100%"></video>

![Infill, Type, and Wall Layer](Infill,%20type,%20and%20Wall%20Layer%20.png)

![Final Print](Final%20Print.png)

---

## Lessons Learned
1. **Batch Printing Efficiency:** Combining four separate models onto one build platform reduced setup time and overall energy consumption while keeping total print duration down to 22 minutes.
2. **Perimeter vs. Infill Balance:** Increasing wall thickness to 3 perimeters provided greater shell stiffness than simply cranking up the infill percentage, optimizing print speed and structural integrity simultaneously.
3. **Flat Base Geometry Benefits:** Designing the cable organizer with a flat bottom ensured superior bed adhesion on the Prusa CORE One bed without requiring additional brim or support enforcers.


### Reflection & Critical Analysis
- **Scaling Up Consequences:** Scaling low infill and thin walls to load-bearing parts (e.g., auto brackets) risks sudden shear failure from poor internal stress distribution.
- **Mistakes Caught & Prevented:** Visually checking the G-code preview ensured safe spacing and prevented toolhead collisions between all four team members' models.
- **Real-World Parallel:** Commercial electronics enclosures use specific wall thicknesses and internal ribbing (like infill) for impact strength and lower costs.

---

## Resources
- SolidWorks CAD Software
- [PrusaSlicer Manual & Documentation](https://help.prusa3d.com/)
- UNCC Print Farm Facilities & Equipment Guidance
- AI Assistance (Gemini) was used to format the lab documentation into GitHub-flavored Markdown, organize image/video file links, and refine structural technical explanations.
