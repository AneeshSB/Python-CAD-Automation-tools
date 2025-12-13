# Python-CAD-Automation-tools
Python based Siemens NX CAD automation tool for composite engineering workflows, including automatic extraction of composite curves and feature group selection option to reduce manual effort and improve repeatability.

Overview
Manual Extraction of composite curves from CAD or geometric data is often repetitive, time-consuming, and prone to inconsistency.
This project is a Python-based automation tool that extracts composite curves automatically, reducing manual effort and improving repeatability in engineering workflows.This tool is currently a prototype / research implementation developed as part of my exploration into engineering CAD automation for composite design and manufacturing.

Problem Statement
In composite design and manufacturing workflows, engineers often need to:
• Identify and extract curves from geometry
• Use these curves for downstream tasks such as layout planning, inspection, or automation

These steps are frequently performed manually inside CAD tools, which:
• Takes significant time
• Depends heavily on user experience
• Is difficult to automate or standardize

Solution
This tool automates the extraction of composite curves using Python-based geometry processing.
Key features:
• Automatic detection and extraction of curves from input geometry
• Minimal user input required
• Output suitable for further processing or analysis

Demo
Demo video showing:
• Input geometry
• Execution of the extraction process
• Extracted curve output
(Demo available in the /demo folder)

How It Works (High-Level)
1. Input geometric data is loaded
2. Curve detection logic processes the geometry and allows you to choose feature group from where the curves should be extracted, since you can have multiple groups within an CAD model.
3. Relevant composite curves are extracted
4. Results are exported for further use

This design keeps the logic modular so that individual steps can be improved or replaced.

Tech Stack
• Python
• NumPy
• Nxopen
• Nxopen.Features
• Nxopen.Selection

Current Limitations
• Tested on limited geometry types
• Not optimized for very large or complex CAD models
These are known limitations and areas for future improvement.

Future Improvements
• Support for additional geometry formats
• Improved robustness for complex composite surfaces
• Integration with CAD or PLM workflows
• Performance optimization

Disclaimer
This project is intended for learning, experimentation, and portfolio demonstration.
It is not production-ready and has not been validated for industrial deployment.

About the Author
Developed by an engineer with experience in:
• Composite design
• CAD (CATIA and Siemens NX)
• Industry 4.0
• Engineering automation using Python

Composite-curve-extraction
├── demo/
│   └── demo_video.mp4
├── examples/
│   └── sample_input_output.png
├── src/
│   └── main.py
├── requirements.txt
├── README.md
└── LICENSE

Feedback
Feedback, suggestions, and technical discussions are welcome.
Contributions, bug reports, and feature requests are welcome.  
Please open an issue or submit a pull request if you’d like to collaborate.

