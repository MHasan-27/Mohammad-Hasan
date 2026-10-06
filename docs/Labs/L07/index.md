# Lab #7: Linkage Mechanisms

## Research

### Linkage / Mechanism 1: Compliant Slider-Crank Mechanism
* **How it Works:** Instead of using traditional pin joints that can wear out, this mechanism relies on flexible plastic hinges that bend to create movement. As the crank turns, these flexible parts bend back and forth to push and pull a slider without any rubbing parts.
* **Industrial Applications:**
  1. *Medical Devices:* Great for small surgical tools and sterile pumps because there are no joint gaps where dirt or bacteria can hide.
  2. *Precision Electronics:* Useful in optical alignment tools and sensors where traditional joints would have too much extra play or slop.

### Linkage / Mechanism 2: Reconfigurable & Transformable Planar Linkages
* **How it Works:** This system uses adjustable pivot points or transformable wheel linkages on its frame so you can change the length or position of the arms. By shifting where the pins sit, you can alter the path the output arm follows without having to 3D print a brand-new part.
* **Industrial Applications:**
  1. *Automotive & Manufacturing:* Used in robotic assembly lines and transformable wheel systems so the same arm or wheel can adapt to different box sizes or obstacles.
  2. *Agricultural & Rehabilitation Equipment:* Applied in farming machinery and finger rehabilitation devices to adjust arm sweep or grip motion based on different user needs or uneven ground.

> **Credible Sources:**
> 1. [IEEE Transactions on Robotics (IEEE T-RO 2024) — Transformable Wheel Mechanisms](https://ideaocean.ai/technology/publications/)
> 2. [Patsnap Patent Landscape — Slider-Crank & Force Transmission Systems](https://www.patsnap.com/resources/blog/rd-blog/slider-crank-mechanism-force-transmission-design-patent-landscape-patent-landscape/)
> 3. [ASME Journal of Mechanical Design (JMD)](https://ideaocean.ai/technology/publications/)

---

## Design

### Purpose
* **What it does:** The mechanism converts continuous 360° rotational motion into linear reciprocating (back-and-forth) motion.
* **Why I chose to design it:** I chose the Piston (Slider-Crank) mechanism because it is a fundamental mechanical linkage used everywhere in modern engineering—from internal combustion engines to pumps. It provides a simple, highly reliable demonstration of mechanical energy conversion with a low part count, making it straightforward to model, print, and debug.

### Components Table

| Component Name | Function | Type |
| :--- | :--- | :--- |
| **Base Frame & Cylinder Guide (Base)** | Holds the crank ground pivot pin and provides a linear U-channel bore to guide the sliding piston. | 3D Printed |
| **Input Crank (Wheel)** | Rotates on the fixed base pin to drive the mechanism. | 3D Printed |
| **Connecting Rod (Coupler / Linkage)** | Transfers rotational movement from the crank pin to the slider pin. | 3D Printed |
| **Piston / Slider** | Reciprocates linearly back and forth inside the base guide channel. | 3D Printed |

### Tolerances & Clearances

To ensure smooth motion without binding or excessive wobble, targeted clearances were designed into each interface based on test coupon prints and close running fit guidelines (RC4/RC5) from *Machinery's Handbook*.

| Moving Interface | Nominal Dimensions | Designed Clearance | Purpose / Reason Needed |
| :--- | :--- | :--- | :--- |
| **Slider to Base Channel** *(Sliding Fit)* | Channel width vs. Slider body width | **0.015"** (15 thousandths) | Prevents the slider from jamming inside the channel due to wall friction or slight FDM layer swelling. |
| **Slider Pin to Linkage Hole** *(Revolute Joint)* | Pin OD: 0.200"<br>Hole OD: 0.210" | **0.010"** (10 thousandths) | Allows the coupler link to rotate smoothly around the slider pin without rotational resistance. |
| **Base Pin to Wheel Hole** *(Main Crank Pivot)* | Pin OD: 0.250"<br>Hole OD: 0.262" | **0.012"** (12 thousandths) | Accounts for internal hole shrinkage on the wheel so it spins freely around the base shaft without seizing. |
| **Wheel Pin to Linkage Hole** *(Crank Pin Joint)* | Pin OD: 0.125"<br>Hole OD: 0.140" | **0.015"** (15 thousandths) | Provides extra play on the smaller pin to ensure smooth continuous rotation at high speeds without binding. |

### Key Design Decisions

1. **Fully 3D-Printed Pins vs. Metal Fasteners:**
   * *Alternatives Considered:* Using standard M3 or M4 steel bolts with locknuts.
   * *Selection & Rationale:* I chose to design and 3D print integrated cylindrical pins directly onto the Base, Wheel, and Slider components. This eliminated the need for external hardware, keeping the assembly fully self-contained and easy to assemble directly off the print bed.

2. **Open U-Channel Guide vs. Fully Enclosed Cylinder:**
   * *Alternatives Considered:* A fully enclosed tubular cylinder body for the slider.
   * *Selection & Rationale:* I opted for an open-top rectangular guide track on the base frame. An open channel allows clear visual verification during movement, avoids internal overhang printing issues, and makes it much easier to clear out any small surface imperfections.

3. **Step Offset on Linkage Arm:**
   * *Alternatives Considered:* A flat, single-plane connecting rod.
   * *Selection & Rationale:* I added a small vertical clearance offset at the connecting rod ends. This elevates the linkage body slightly off the base floor and wheel face, preventing surface friction and link collisions during full 360° rotation.

### CAD Model Images

* **Base Frame:**
  ![Base 2](Base%202.png)
  *Figure 1: Base plate CAD layout showing the main pivot pin and guide rails.*

  ![Base 3](Base%203.png)
  *Figure 2: Completed Base model with optimized wall thickness and mounting features.*

* **Input Crank / Wheel:**
  ![Wheel 1](Wheel%201.png)
  *Figure 3: Initial sketch and drive pin placement on the Wheel model.*

  ![Wheel 2](Wheel%202.png)
  *Figure 4: Final CAD view of the Wheel with central shaft bore.*

* **Connecting Rod / Linkage:**
  ![Linkage 1](Linkage%201.png)
  *Figure 5: CAD model of the Linkage arm showing pin-hole spacing and revolute joint eyes.*

* **Piston / Slider:**
  ![Slider 1](Slider%201.png)
  *Figure 6: CAD design of the Slider body and guide contact faces.*

  ![Slider 2](Slider%202.png)
  *Figure 7: Detail view of the Slider top pin interface.*

* **Final CAD Assembly:**
  ![Assemble](Assemble%20.png)
  *Figure 8: Complete CAD assembly showing all mated components.*

---

## 3D Print

### Slicing & Printing Details
* **Slicer Setup:** The complete assembly was sliced together (`The Piston (crank-slider)..3mf` / `.bgcode`) using PLA filament with a 0.4 mm nozzle and 0.20 mm layer height.
* **Key Slicer Settings:** Applied a horizontal expansion offset ([Elephant's foot compensation](https://help.prusa3d.com/article/elephant-foot-compensation_114487)) to prevent bottom-layer mushrooming from tightening the slider track. Seams were placed away from sliding faces using [Seam position tuning](https://help.prusa3d.com/article/seam-position_151069).

### Slicer Configuration Images

- **Elephant Foot Compensation on Slice:**
  ![Elephant Foot Compensation on Slice](Elephant%20Foot%20Compensation%20on%20Slice.png)
  *Figure 9: Toolpath preview displaying elephant foot compensation on sliced layers.*

- **Elephant Foot Compensation Settings:**
  ![Elephant Foot Compensation](Elephant%20Foot%20Compensation.png)
  *Figure 10: Slicer parameters for initial layer elephant foot compensation.*

- **Seam Position Settings:**
  ![Seam Position](Seam%20Position%20.png)
  *Figure 11: Z-seam alignment settings configured to prevent binding along sliding surfaces.*

### Slicer & Printed Part Measurements Table

| Component / Interface | Slicer / CAD Dimension | Printed Measured Dimension | Deviation / Notes |
| :--- | :--- | :--- | :--- |
| **Base Channel Height** | 0.1270" | **0.1120"** | -0.0150" deviation; slight first-layer squish reduced effective channel height, but retained sufficient clearance. |
| **Slider Body Height** | 0.1160" | **0.1010"** | -0.0150" deviation; matches channel height reduction proportionally, ensuring a smooth sliding clearance fit (~0.0110"). |
| **Slider Pin OD (Linkage Joint)** | 0.2000" | **0.1965"** | -0.0035" deviation; minor FDM perimeter shrinkage on pin outer diameter. |
| **Base Pin OD (Main Axis)** | 0.2500" | **0.2400"** | -0.0100" deviation; thermal contraction reduced shaft diameter slightly. |
| **Wheel Hole ID (Main Axis)** | 0.2620" | **0.2540"** | -0.0080" deviation; internal hole shrinkage, yielding a smooth 0.0140" running clearance over the 0.2400" base pin. |
| **Wheel Pin OD (Drive Pin)** | 0.1250" | **0.1265"** | +0.0015" deviation; slight material bulge near pin root. |
| **Linkage Hole ID (Wheel Joint)** | 0.1400" | **0.1165"** | -0.0235" deviation; significant FDM internal hole wall expansion, requiring light reaming for free rotation over the 0.1265" wheel pin. |
| **Linkage Hole ID (Slider Joint)** | 0.2100" | **0.1965"** | -0.0135" deviation; internal hole shrinkage created an exact zero-clearance press/snug fit with the 0.1965" slider pin. |

### 3D Printed Assembly Images

- **Print Bed View:**
  ![Print Complete](Print%20Complete.jpg)
  *Figure 12: Fully printed assembly on the print bed.*

- **Printing Process:**
  ![Printing Picture](Printing%20Picture.jpg)
  *Figure 13: In-progress printing of mechanism components.*

---

## Demonstrations & Physical Assembly

### Demonstration Videos

- **Assembly Demonstration Video:**
  <video width="100%" controls preload="metadata">
    <source src="Demonstration.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>

- **Low-Res Assembly Video:**
  <video width="100%" controls preload="metadata">
    <source src="Assemble%20Low%20Resu.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>

- **In-Progress Printing Video:**
  <video width="100%" controls preload="metadata">
    <source src="Printing.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>

### Motion GIF
![Assembly GIF](Assem%20GIF.gif)

### Physical Assembly Views
- **Isometric View:**
  ![Assemble Isometric View](Assemble%20Isometric%20View.jpg)

- **Front View:**
  ![Assemble Front View](Assemble%20Front%20View.jpg)

- **Top View:**
  ![Assemb Top View](Assemb%20Top%20View.jpg)

- **Bottom View:**
  ![Assemb Bottom View](Assemb%20Bottom%20View.jpg)

- **Slide Channel Detail:**
  ![Assemble Slide channel](Assemble%20Slide%20channel.jpg)

---

## Lessons Learned

1. **Time Breakdown:**
   * **Research:** 2.5 hours
   * **CAD Modeling:** 4.5 hours
   * **Slicing & Print Prep:** 0.5 hours
   * **3D Printing:** 1.0 hour
   * **Post-Processing & Assembly:** 1.5 hours
   * **Total Time:** **10.0 hours**
   * *Comparison:* The total time took longer than my initial expectations primarily due to the extensive CAD modeling iterations required to ensure pin-and-hole clearances were dialed in properly before sending files to the slicer.

2. **Biggest Mistake:**
   * *Failure & Cause:* My initial slider bound up slightly inside the base guide channel due to small surface layer-start "zits" along the inner track wall.
   * *Discovery & Fix:* I identified the issue by manually moving the slider and feeling where it caught on the wall. I fixed it by lightly sanding the inner track walls with fine sandpaper and aligning the slicer seam locations away from the contact surfaces.

3. **Tolerances:**
   * *Performance:* The designed 0.010" – 0.015" clearances worked well overall straight off the print bed without requiring major reprints.
   * *Future Adjustments:* If I re-printed this mechanism, I would increase the Wheel-to-Base pin clearance from 0.012" to 0.016" to give the main rotating shaft a slightly looser, lower-friction spin without needing any post-sanding.

---

## Downloads & Resources

### Part & Assembly CAD Files
* 📄 [Base Part (`Base.SLDPRT`)](Base.SLDPRT)
* 📄 [Wheel Part (`Wheel.SLDPRT`)](Wheel.SLDPRT)
* 📄 [Linkage Part (`Linkage.SLDPRT`)](Linkage.SLDPRT)
* 📄 [Slider Part (`Slide.SLDPRT`)](Slide.SLDPRT)
* 🧩 [Full CAD Assembly (`Assem crank-slider.SLDASM`)](Assem%20crank-slider.SLDASM)

### Print & G-Code Files
* 📦 [3MF Project File (`The Piston (crank-slider)..3mf`)](The%20Piston%20(crank-slider)..3mf)
* 🖨️ [G-Code File (`The Piston (crank-slider)._0.4n_0.2mm_PLA_COREONE_21m.bgcode`)](The%20Piston%20(crank-slider).%20_0.4n_0.2mm_PLA_COREONE_21m.bgcode)

### External Resources & References
* 🎥 [12 Crank Mechanisms Visualized Beautifully (YouTube)](https://www.youtube.com/watch?v=N2TcOHkQaJw) — Mechanism reference and animation motion profiles.
* 📖 [Prusa Knowledge Base — Elephant Foot Compensation](https://help.prusa3d.com/article/elephant-foot-compensation_114487) — Slicer dimensional calibration guidelines.
* 📖 [Prusa Knowledge Base — Seam Position Settings](https://help.prusa3d.com/article/seam-position_151069) — Layer seam optimization for revolute pin and sliding fit joints.
* 📘 *Machinery's Handbook (31st Edition)* — Standard fit tables (RC4/RC5 close running fits).
