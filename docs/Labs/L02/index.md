Lab Class participation:
Question:
What is one design rule or guideline specific to Design for Additive Manufacturing (DfAM), what does it mean, and why does it matter?

Answer:
Proper support structure management is a critical DfAM guideline where designers must plan whether a part uses automated supports, custom manual supports, or is engineered to self-support without any added material.

Question:
What is infill strategy in FDM 3D printing, and how does a designer use it to optimize a part?

Answer:
Infill strategy determines the internal structure and density of a 3D printed part, directly controlling its stiffness, weight, and overall pressure tolerance. Designers work around this by customizing both the infill percentage and geometric pattern (such as grid or gyroid) based on the specific mechanical requirements and intended use of the part.

Group Share Info:
They are focusing on the overhang supports. 


# Lab 2: Print Something Small

## Download

For this project, I chose to print the [Bird Door Stopper](https://www.printables.com/model/624315-bird-door-stopper/files) from Printables.

### Why I Selected This Model

* It has a flat base, which makes it stable on the build plate without needing complex support structures.
* The dimensions fit well within the assignment constraints (under 0.25 inches tall, max 2 X 2 inches).
* The design is simple and practical for a quick FDM print test.


---

## Preprocessor

I imported the STL file into PrusaSlicer to prepare the model for printing with PLA.

### Slicer Configuration & Settings

* **Material:** PLA
* **Layer Height:** 0.20 mm
* **Infill:** 15% (Grid)
* **Build Orientation:** Placed flat on its largest bottom surface to ensure good bed adhesion and prevent slipping.
* **Supports:** None needed due to the low profile and flat geometry.
* **Scaling:** Scaled down slightly in PrusaSlicer to guarantee it stayed strictly under the 2x2 inch footprint limits.

(docs/Labs/L02/Gcode Slice.png)

(docs/Labs/L02/Print Settings.png)

---

## Print

* **Printer Used:** UNCC Print Farm Printer #[18]
* **Print Partner(s):** Worked with [Partner Name(s) (forgot)] to combine our models on a single build plate to save time and share printer access.
* **Material Used:** PLA



(docs/Labs/L02/Lab 2 FDM footage.mp4)

(docs/Labs/L02/IMG_9393.JPG)

---

## Lessons Learned

1. **Combining Builds Saves Time:** Printing multiple small parts with a partner on one build plate freed up machines for other students and reduced setup overhead.
2. **Double-Check Scaling Units:** Inspecting dimensions in the slicer beforehand is critical to staying within exact constraints (under 0.25 inches tall).
3. **Flat Surfaces Simplify Slicing:** Selecting a model with a flat bottom surface eliminates the need for supports and significantly improves bed adhesion.
4. **Print Time Management:** Preparing g-code efficiently ahead of time ensured our overall print time stayed well under the 1.5-hour limit.

* **Total Time Taken:** Approximately [13] minutes from downloading the file to holding the finished print.
* **Acknowledgments:** Thanks to [Profesor Fagan] for coordinating on the build plate layout and the lab staff for printer access.

---

## Resources

* [Bird Door Stopper on Printables](https://www.printables.com/model/624315-bird-door-stopper/files)
* [PrusaSlicer Documentation](https://help.prusa3d.com/)
