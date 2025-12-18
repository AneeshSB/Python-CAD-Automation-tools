Siemens NX Composite Curve Automation

A Python-based engineering tool that automates the extraction of composite curves from Siemens NX CAD models, reducing manual pre-processing time by ~90%

🎥 Demo
*The tool in action: Selecting a feature group and automatically generating composite curves.*



---

## 🧐 Problem Statement
In aerospace and automotive composite workflows, engineers must prepare CAD geometry for downstream manufacturing (Layup planning, Laser projection, etc.).

**The Manual Process:**
1.  Engineers manually identify curve boundaries on complex surfaces.
2.  They use point-and-click operations to extract curves one by one.
3.  **Result:** This takes **15–20 minutes per part** and is prone to human selection errors.

## 💡 The Solution
I developed a Python script utilizing the **NXOpen API** to programmatically traverse the geometry. By inputting a single Feature Group, the algorithm detects, filters, and extracts the necessary composite curves automatically.

### Key Benefits
* ✅ **Efficiency:** Reduces extraction time from minutes to seconds.
* ✅ **Repeatability:** Removes human variability; the output is standard every time.
* ✅ **Scalability:** Capable of processing complex assemblies that would be tedious to handle manually.

---

## 🏗️ Architecture & Logic

The script follows a modular extraction pipeline:

```mermaid
graph LR
    A[Start: User Selects Feature Group] --> B{Validation};
    B -- Invalid --> C[Error: Invalid Selection];
    B -- Valid --> D[Traverse Geometry];
    D --> E[Filter Curves (Edge/Spline Logic)];
    E --> F[Extract to New Layer];
    F --> G[End: Report Generated];
