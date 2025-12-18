Siemens NX Composite Curve Automation

A Python-based engineering tool that automates the extraction of composite curves from Siemens NX CAD models, reducing manual pre-processing time by 90%

**Demo:**

*The tool in action: Selecting a feature group and automatically generating composite curves.*

<div align="center">
  <img src="demo/Python Gif.gif" alt="Demo" width="700">
</div>

**Problem Statement:**
In Aerospace,Wind and automotive composite workflows, engineers must prepare CAD geometry for downstream manufacturing (Layup planning, Material Cutting and Kiting, Laser projection, etc.).

**The Manual Process:**
1.  Engineers manually identify curve boundaries on complex surfaces in 3D Model.
2.  They use point-and-click operations to extract curves one by one and save this individually.
3.  **Result:** This takes **15–20 minutes per part** and is prone to human selection errors.

**The Solution:**
I developed a Python script utilizing the **NXOpen API** to programmatically export the geometry. By inputting a single Feature Group, the algorithm detects, filters, and extracts the necessary composite curves automatically from the selected group.

**Key Benefits:**
**Efficiency:** Reduces extraction time from minutes to seconds.
**Repeatability:** Removes human variability; the output is standard every time.
**Scalability:** Capable of processing complex assemblies that would be tedious to handle manually.

**Architecture & Logic:**
The script follows a modular extraction pipeline:

```mermaid
graph LR
graph TD
    Start([User Clicks 'Custom Python Tool']) --> GUI[GUI Opens];
    
    subgraph User_Inputs [User Configuration]
        GUI --> SelectModel[/Select 3D Model/];
        SelectModel --> SelectFolder[/Select Output Folder/];
        SelectFolder --> TypeName[/Enter Feature Group Name/];
        TypeName --> Run[Click 'Start Batch IGES Export'];
    end
    
    Run --> Open[System Opens 3D Model];
    Open --> Search{Feature Group Found?};
    
    Search -- No --> Error[Log Error & Stop];
    Search -- Yes --> Iterate[Iterate Curves in Sequence];
    
    Iterate --> Export[Export IGES to Output Folder];
    Export --> Finish([Process Complete]);
