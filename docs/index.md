---
Title: IDAES UI
Creator: Dan Gunter
Author: The IDAES Project
Date: 2023-03-28
---
<span id="top" />

# IDAES UI

The Institute for the Design of Advanced Energy Systems Integrated Platform (IDAES-IP) consists of high-level capabilities that solve complex design and optimization problems with the core IDAES software framework, which makes use of state of the art equation-oriented optimization  solvers. For more details on these components, see the [IDAES documentation](https://idaes-pse.readthedocs.io/en/stable/). 

This documentation is for *user interface* components that build on top of the IDAES core Python library and applications. This documentation is for all users; additional information relevant for software developers of the IDAES platform will be prefixed with "💻Developers".

Sections:

* [Getting started](#getting-started) - Install the software
* [Flowsheet Visualizer](#fv) - Visualize flowsheet layout and properties.

<span id="getting-started" />

## Getting Started

The IDAES UI components are distributed as a Python package using the Conda package management system from [Anaconda](https://docs.anaconda.com). They are normally installed with the IDAES software. For details, see the [IDAES installation instructions](https://idaes-pse.readthedocs.io/en/latest/tutorials/getting_started/index.html). 

💻Developers: To install the UI components from GitHub, follow the procedures outlined in the IDAES-IP [Advanced User Installation](https://idaes-pse.readthedocs.io/en/latest/tutorials/advanced_install/index.html) section to set up your environment. Then you should fork and clone the [idaes/idaes-ui](https://github.com/IDAES/idaes-ui.git) repository and install it with: `pip install -e .`

<span id="fv" />

----

## Flowsheet Visualizer

Screenshot of the Flowsheet Visualizer:

<img src="sample_fv.png" />

The IDAES-IP [Flowsheet Visualizer](#flowsheet-visualizer) (FV) is a graphical user interface that displays complex *flowsheets* (connected components representing a system or sub-system to be optimized) created with the IDAES-IP Python core software. The FV uses web technologies (HTML, CSS, JavaScript) so is cross-platform and has identical functionality on computers running Windows, Mac, and UNIX.

**FV Sections:** [Tutorials](#fv-tutorials) | [How-to](#fv-howto) | [Reference](#fv-reference)

<span id="fv-tutorials" />

### Tutorials

#### Example flowsheet

A simple example flowsheet is included and can be viewed with:

 `python -m idaes_ui.fv.example`

This will open the system's default web browser to show the flowsheet and its controls.

<span id="fv-howto" />

### How-to

#### Start the visualizer
Assuming your flowsheet object is called `flowsheet`:
* From within a Jupyter Notebook, `flowsheet.visualize("Flowsheet Name")`
* From within a Python script, add a keyword argument if you want the visualizer to keep running: `flowsheet.visualize("Flowsheet Name", loop_forever=True)`

#### Save the visualization
* Export &rarr; Flowsheet to save the flowsheet as an image
* Export &rarr; Stream table to save the stream table as comma-separated values

#### Basic controls in the diagram

Unit models (shapes)
* Click and drag unit models to move them 
  * Right-click on a unit model to rotate it 90 degrees
  * Drag in an open area to create a rectangle that selects multiple unit models at once

Streams (lines)
* Drag streams to change their routing 
  * Click on the line to create a new segment for routing, and eliminate that segment by clicking the dot that appears on mouseover


<span id="fv-reference" />

### Reference

See the [visualize()](https://github.com/IDAES/idaes-ui/blob/main/idaes_ui/fsvis/fsvis.py) function code for documentation on its options and behavior. 



