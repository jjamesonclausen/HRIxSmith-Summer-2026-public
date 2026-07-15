---
title: "ca3"
source: "https://www.simscale.com/docs/cad-preparation/"
author:
published: 2018-10-29
created: 2026-07-15
description: "Learn everything you need to know about your CAD preparation and upload it into SimScale with our documented guide. Get started today!"
tags:
  - "clippings"
---
Documentation

## CAD Preparation and Upload

Preparing, uploading, and adapting your CAD model for simulation is the first step in setting up a simulation. CAD models cannot be created in SimScale but they can certainly be uploaded, cleaned, and prepared to begin the simulation. Some tips for CAD preparation and its proper upload are outlined below:

## CAD Upload/Import

To upload a CAD file onto the SimScale Workbench:

1. Open an existing project or create a new one.
2. To open the upload dialog, click the **‘+’** button next to *Geometries* in the simulation setup tree.
3. Drag and drop your CAD file or click to open the file selection dialog.

![how to import directly from onshape to simscale ](https://frontend-assets.simscale.com/media/2025/07/image-39.png)

Figure 1: SimScale CAD upload dialog. Either upload files directly from your machine or import via Onshape.

Another option is to use the ***‘from Onshape’*** button to directly pull a design from your Onshape library. Additionally, sample CAD models are available by selecting the ***‘from Sample Library’*** button.

The maximum size limit for uploading CAD models in the SimScale platform is **3 GB** (gigabytes).

Important

When importing zip files to SimScale, the *File format* needs to be selected. For example, in the case of a [Pack and Go](https://www.simscale.com/docs/cad-preparation/#pack-and-go) file from SolidWorks, select *SolidWorks (.sldprt /.sldasm)* from the drop-down menu.

![pack and go file warning zip during import format](https://frontend-assets.simscale.com/media/2022/07/importing-solidworks-pack-and-go.png)

Figure 2: For zip files, please select the correct file format from the drop-down menu.

Did you know?

SimScale also supports simulation using uploaded meshes. So if you already have a meshed geometry and simply want to get going with the setup we refer you to [this page](https://www.simscale.com/docs/simulation-setup/meshing/mesh-upload/).

## Supported CAD Formats

SimScale supports the following CAD formats:

- Native formats:
	- Parasolid (.x\_t,.x\_b)
		- SolidWorks (.sldprt,.sldasm)
		- Autodesk Inventor (.iam,.ipt)
		- Rhino 4, 5, 6, 7, and 8 (.3dm)
		- CATIA (.CATPart,.CATProduct)
		- PTC Creo (.prt,.asm)
		- Siemens NX (.prt)
		- Solid Edge (.par,.asm,.psm)
		- REVIT (.rvt)
		- nTop (.implicit)
- Neutral formats:
	- ACIS (.sat,.sab)
		- STEP (.stp,.step)
		- IGES (.igs,.iges)
		- STL (.stl)

Generally, it is recommended to upload the model in the native format of the tool it was created with (e.g. as.sldprt if modeled in SolidWorks). SimScale natively uses the Parasolid CAD kernel. In order to have all CAD manipulation functionality available within SimScale, the CAD model needs to be successfully translatable into the Parasolid format.

## CAD Upload Options

While uploading the CAD model, it undergoes optimization steps automatically to best suit the simulation. These steps are explained in detail below. Although not advisable, the user can turn these off if needed or desired.

![CAD optimization options](https://frontend-assets.simscale.com/media/2022/07/import-options.png)

Figure 3: CAD model upload optimization options recommended for simulations

**Facet-Split on Import**

Facet models contain geometry that is not described by parametric functions but by a surface mesh consisting usually of triangles. Often the whole faceted geometry is stored in one big surface part and can not be easily accessed to define e.g. boundary conditions on separate faces. In order to do that you can split the faceted parts of the models by a surface angle. For all angles that are higher than the given value, the algorithm tries to separate the geometry by introducing separate faces. Some formats contain only faceted data, for e.g., \*.stl files; others like Parasolid, Step or Rhino can contain mixed parametric and faceted parts. For parametric geometry, this setting doesn’t take any effect.

To control the facets fully…

To control the facets fully, toggle off *Facet split on import* and split the STL outside of SimScale by putting it to different STL files and upload everything as a zip file. The files will be translated as solids and the STL-solids will be translated as faces.

**Automatic Sewing**

Automatic sewing tries to connect parts of the model that are stored separately but touch exactly. In case a closed shell can be achieved, it additionally creates a solid body bound by the original faces. As most simulations are carried out on three-dimensional domains and require solid regions as input it is recommended to use this option on import.

**Improve Data on Import**

This option tries to improve the topology (e.g. edges, vertices) and geometry of the model by adjusting tolerances, simplifying entities, etc. As this option should improve CAD operations and data handling for all downstream applications it is recommended to use it on import. For very complex models it can take a considerable amount of time though, therefore you can also opt-out and reconsider in case you face issues in geometry handling or meshing.

**Optimize for LBM / PWC**

This option allows you to import a \*.stl file that is optimized for the Incompressible LBM and Wind Comfort analysis types. It leaves out complex import steps like sewing and cleanup that are not required by the LBM solver and therefore also allows to import big and complex models fast.

To upload an assembly file from a particular CAD tool please collect all the related parts and sub-assembly files along with the assembly file and create a \***.zip** file. Then upload this **\*.zip** file using the upload dialog. Find a detailed guide on assembly upload [here](https://www.simscale.com/knowledge-base/solidworks-autodesk-assembly-upload/). Currently, SimScale supports the assembly upload feature for the following formats:

| **CAD Tool** | **Native Part format** | **Native Assembly format** |
| --- | --- | --- |
| CATIA | .CATPart | .CATProduct |
| Fusion 360 / Inventor | .ipt | .iam |
| SolidWorks | .sldprt | .sldasm |
| PTC Creo | .prt | .asm |
| Siemens NX | .prt | .prt |

Table 1: CAD Tools and their respective part and assembly formats

Keep in mind!

If sub-assemblies exist, the software first checks if the archive name matches any assembly name in the archive – and we use this assembly as a root assembly of the import.  
If not, it then checks the first assembly file alphabetically and uses this file as a root (parent) assembly of the import.

![example of cad model being shown within simscale platform ](https://frontend-assets.simscale.com/media/2020/09/geometry-in-workbench.png)

Figure 4: Once uploaded and converted successfully, the model will be shown in the viewer and listed in the Geometries section of the navigation tree. Renaming the model is facilitated.

Note

In case round parts of your geometry appear to have corners, don’t worry: SimScale will automatically simplify your geometry for display purposes to make sure that you can fluently interact with the model. Internally, especially for the meshing process, SimScale uses the fully featured geometry.

Some CAD tools, such as SolidWorks and Autodesk Inventor, have a Pack and Go functionality, which saves together all files related to a model design with correct references. This workflow is helpful when exporting complex assemblies (parent and child assembly) since it handles the structure of the export file automatically.

The image below shows the steps to use the Pack and Go functionality on SolidWorks:

![solidworks pack and go export for assemblies](https://frontend-assets.simscale.com/media/2021/07/SolidWorks-pack-and-go-workflow-1-e1625583559686.jpg)

Figure 5: Once the SolidWorks model is ready to export, you can navigate to File and select Pack and Go.

After navigating to *Pack and Go*, a second window opens with more options. Here, enabling the *Save to Zip file* option is important:

![exporting a pack and go geometry as a zip file](https://frontend-assets.simscale.com/media/2021/07/solidworks-saving-pack-and-go-as-zip.jpg)

Figure 6: Pack and Go setup window, showing different options

After saving, the Pack and Go zip file can be directly imported to the SimScale platform. Don’t forget to select the proper file format for the zip file to upload.

Importing implicit geometries from nTop works similarly to the assembly upload workflow, but requires an additional preparation step for entity assignments in the simulation workflow.

1. Export all implicit bodies required for the simulation from nTop as implicit files using the ***‘Export implicit body’*** block.
2. Export additional auxiliary bodies that enclose relevant faces for the simulation setup, e.g., to define boundary conditions or result controls. Those auxiliary bodies need to be named with a prefix **‘NS\_’** for named selection.

To import the prepared model, add all bodies to a compressed archive (zip, tar.gz) and upload it to SimScale. All subsequent workflow steps work exactly as for parametric or faceted models.

## Import Plugins

To enable a seamless design workflow, SimScale offers direct integration with a couple of CAD modeling tools. These integrations allow the direct import (via push/pull) of your designs into SimScale.

The SimScale Connector App for [Onshape](https://www.onshape.com/) allows you to quickly import your CAD models directly from your Onshape account into the SimScale simulation platform without the need of exporting and uploading files.

![onshape importer widget](https://frontend-assets.simscale.com/media/2020/07/onshape-importer.jpg)

Figure 7: To import a model directly from Onshape, click ‘ Import from Onshape ‘ in the CAD upload widget (see above). A new window will open in which the model to be imported can be selected (shown here for Pump ).

Create your model on Autodesk Fusion 360 and with a few clicks push your geometry to an existing project on SimScale without having to leave the application or do cumbersome format conversions when saving the models you want to use in your simulations.

To download, visit the Fusion 360 app store:

> [How to Import Geometries From Fusion 360?](https://www.simscale.com/knowledge-base/how-to-import-geometries-from-fusion-360/)

## Supported CAD Operations: CAD Edit

After CAD upload, some additional preparation might be required. SimScale offers a dedicated environment to interact with your model called **‘CAD Edit’** that helps you optimize the model within SimScale without having to switch to other CAD software. [Try this feature today](https://www.simscale.com/docs/cad-preparation/cad-mode/).

> [CAD Editing](https://www.simscale.com/docs/cad-preparation/cad-mode/)

The CAD Edit supports many operations like scaling, extrude, body and face delete, surface splitting, flow volume extraction, etc. Users can access the CAD Edit from the workbench itself by clicking on the CAD in the Geometry tree. This brings up the CAD tool bar allowing editing in place. The modified geometry can be seamlessly updated in simulations with only one click.

![meeting room geometry being edited in the cad editing tool](https://frontend-assets.simscale.com/media/2026/06/cad-editing-tool-overview-with-meeting-room-geometry-2048x1116.png)

Figure 8: Access CAD Edit from the SimScale Workbench by clicking on the imported geometry and start editing it.

## CAD Preparation

Depending on the complexity and quality of your CAD model, some preparation and cleanup work might be required. Most of this cleanup work can be done within SimScale using the available CAD operations. The following general guidelines might help get you to the first successful iteration of your simulation.

- **Start simple and iterate**  
	A proven strategy for the simulation setup is to create it for a very simple version of the problem in order to see whether or not the simulation approach is viable.
- **Think the complete workflow through  
	**Having an idea about the mesh and the application of boundary conditions can help with CAD preparation.
- **Have a clear understanding of the problem**  
	This helps to decide whether certain effects can be neglected or not.

Diving deeper, keep in mind the following requirements for a successful and accurate simulation:

The dimension of the model is very important for the simulation. If there are any discrepancies between the model units and the SimScale units this can lead to unrealistic geometrical dimensions. In this case, it is crucial to perform a scaling operation.

![selecting units accordingly before uploading the cad model](https://frontend-assets.simscale.com/media/2022/07/adjusting-stl-model-dimensions-during-import.png)

Figure 9: While uploading a \*.stl file, the model dimension can be selected.

The default dimension used within the Workbench is *Meter*. The user can change it to other units from the dropdown as shown above although this option is only available for.stl files that do not contain unit information in the file.

Very often the CAD model can be simplified to get more accurate simulation results in a shorter time. A few cases for potential optimization are listed below:

CAD models often contain many detailed features because of manufacturing constraints or the installation. Good examples are small holes or windings. These detailed features might be relevant for the final manufacturing but they do not affect simulation results, rather only increase the meshing and computing time significantly. Therefore, such features should be removed.

Small entities can be a problem when it comes to meshing. If there are very small faces with sharp angles the surface meshing might fail. An example is demonstrated below, where faces had to be merged before a surface mesh could be generated. Such small entities should also be removed during CAD preparation.

![example of small features that should be cleaned up before import](https://frontend-assets.simscale.com/media/2019/12/small-feature-removal-example.jpg)

Figure 10: Left: Very small face with very sharp angles. Causes the surface mesher to fail. Right: Problematic face was removed, meshing works fine.

If the problem is symmetric, computation time can be significantly reduced by using [symmetry boundary conditions](https://www.simscale.com/docs/simulation-setup/boundary-conditions/symmetry/) and performing simulations on just a part of the whole CAD model. In such a case only one instance of the symmetric parts of the model should be imported.

Analyzing smaller parts of the CAD one by one, rather than analyzing the entire CAD in a single simulation, can help reduce the complexity of the problem and speed up the simulation.

When performing a simulation with rotating parts, such as pumps and turbines, rotating zones need to be created as a part of CAD preparation. This requires some additional steps including [CAD Edit](https://www.simscale.com/docs/cad-preparation/cad-mode/) before using the model for simulation. You can find a detailed approach to CAD preparation in the following article:

> [How to Prepare the CAD for Simulating Rotating Zones?](https://www.simscale.com/knowledge-base/how-to-prepare-cad-for-simulating-rotating-zones/)

## CAD Faults

In case your model could not be successfully translated into the SimScale-specific internal format, all entities that failed translation will be exposed after upload. In order to progress further, try fixing all faulty parts and upload the model once more.

![cad faults interface shown within the simscale platform ](https://frontend-assets.simscale.com/media/2019/12/cad-faults-example.jpg)

Figure 11: Faulty topological entities will be listed in the scene tree (top right). Click on a fault to visualize it in the viewer. To progress further, all faults need to be resolved first and another instance of the cleaned geometry needs to be uploaded.

Refer to our knowledge base article on [how to find faults in your CAD model](https://www.simscale.com/knowledge-base/how-to-find-faults-in-the-cad-model-2/).

> [How to Find Faults in the CAD Model?](https://www.simscale.com/knowledge-base/how-to-find-faults-in-the-cad-model-2/)

## CAD Topology

In general, a CAD model consists of different types of topological entities such as solids, faces, edges, and vertices. It’ is important to be aware of this topology as it will have an impact on mesh generation and simulation setup. Find an introduction to CAD topology [here](https://www.simscale.com/docs/simwiki/preprocessing/cad-topology/).

Still not satisfied? Looking for case-specific information? Visit the **CAD PREPARATION** section of our [Knowledge Base articles](https://www.simscale.com/docs/knowledge-base/#cad-preparation).

Last updated: June 12th, 2026

What's Next

part of: [Simulation Setup](https://www.simscale.com/docs/simulation-setup/)

Product

What is SimScale?

Technology

Solutions

Use cases

Applications

Industries