---
title: "ca4"
source: "https://www.simscale.com/docs/cad-preparation/cad-mode/"
author:
published: 2026-02-25
created: 2026-07-15
description: "SimScale offers an environment to perform CAD editing operations as a part of preprocessing and in the middle of a simulation setup."
tags:
  - "clippings"
---
Documentation

## CAD Editing

SimScale offers an integrated environment to interact with your CAD model and perform CAD-related operations.

Within the Workbench, users can execute CAD operations to generate features such as flow volume extraction, deletion, extrusion, scaling CAD parts, amongst others. SimScale saves each CAD modification automatically. To edit a CAD model from the Workbench, select the imported geometry and start editing it as shown in the next figure:

![Access CAD Edit](https://frontend-assets.simscale.com/media/2026/04/figure-1-Access-CAD-Edit-1.png)

Figure 1: Access CAD editing in the Workbench by selecting the imported geometry to start editing it.

## CAD Editing Interface

The interface for CAD editing opens in the CAD context. If a user is editing simulations, then CAD editing interface will be hidden. The next figure shows the interface:

![CAD Workbench Editing interface](https://frontend-assets.simscale.com/media/2026/04/figure-2-CAD-Edit-Interface.png)

Figure 2: CAD editing has three sections: 1. CAD Operations Toolbar, 2. CAD Feature List, 3 CAD Scene Tree.

1. **CAD** **Operations Toolbar**: Contains all supported CAD operations. All the operations are further explained in this document.
2. **CAD Feature List**: Displays the history of the features applied to the CAD (features are results of a CAD operation).
3. **Scene Tree**: Lists the original geometry with its solid bodies and faces. Toggle *Show faces* to see and keep track of all the faces of each solid body present in the geometry.

## Updating a CAD model in a simulation

A user can modify a CAD model that is assigned to a simulation and manually update the edited CAD model in the simulation. Let’s see this workflow with an example.

A user assigns a CAD model to a simulation:

![Assigning a geometry to a simulation](https://frontend-assets.simscale.com/media/2026/04/figure-3-Simulation-with-no-Flow-region.png)

Figure 3: The user assigned a CAD model to a simulation

The user realizes that the CAD model has no flow volume; therefore, the user creates one by clicking on the CAD model in the GEOMETRIES tree and editing it.

![Changes detected in the simulation Geometry ](https://frontend-assets.simscale.com/media/2026/04/figure-4-flow-region-created-CAD-shows-update.png)

Figure 4: The user created an external flow volume and now the CAD model in the simulation is outdated.

Upon CAD modifications, SimScale indicates that the CAD model in the simulation is outdated by displaying a circular arrows and a yellow warning icon. SimScale does not automatically update the geometry in the simulation to the latest state. It must be done manually.

![Update the CAD model in the simulation](https://frontend-assets.simscale.com/media/2026/04/figure-5-update-CAD-in-simulation.png)

Figure 5: The user clicked on the geometry in the simulation to Update the CAD model.

When the user clicks on the geometry in the simulation, SimScale shows the CAD model without the latest CAD modifications (the CAD is the same as the last time when the user edited simulation setup). The user then has two options:

1. **Use the geometry without the CAD modifications:** If the user would like to simulate the geometry without the CAD modifications (i.e., without the flow volume), the user doesn’t need to do anything besides setting up the simulation and running it.
2. **Accept the changes and update the simulation geometry:** If the user would like to simulate the geometry with the CAD modifications (i.e., with the flow volume), then the user clicks **Update** button in the Geometry panel (which opens after clicking on the Geometry item in the simulation tree as shown in the above figure) and confirms the update (using the blue checkmark on the top right, as shown in the figure below). SimScale will then swap the CAD geometry and provide feedback about the mapped entities in the simulation assignments.

![Accept the geometry update by clicking on the blue checkmark](https://frontend-assets.simscale.com/media/2026/04/figure-6-accept-changes.png)

Figure 6: The user accepts the update of the CAD model by clicking on the blue checkmark.

## CAD Operations

The following operations are supported with more coming soon. The operations are categorized based on their application.

## Face

The *Delete* operation helps you to delete a face from the CAD model by selecting **‘Delete’** from the operations toolbar and then assigning one or multiple faces to be deleted.

![Delete face operation in CAD mode with healing methods](https://frontend-assets.simscale.com/media/2023/09/Heal.png)

Figure 7: Delete face operation with healing methods: Heal and Cap. More than one face can be assigned.

The settings panel also allows choosing between the available healing methods, viz. Heal and cap while the face delete operation is being performed. Choose Leave Open to opt out.

In the following section, all the healing methods are described using simple geometry as follows:

![reference geometry to demonstrate healing methods](https://frontend-assets.simscale.com/media/2021/03/image-29.png)

Figure 8: Reference geometry used to demonstrate the healing methods for the face delete operation is a cylinder with an extra curved face.

The reference geometry is a cylinder with one of its edges rounded to produce 1 curved and 3 planar faces.

**Heal**

The *Heal* method will try to fill up the surface lost to the delete operation by trying to either expand or contract the adjacent faces until they intersect.

![shrink healing method in face delete cad mode](https://frontend-assets.simscale.com/media/2021/03/image-33.png)

Figure 9: The Heal method. Deleting the top face should return the exact same result as if the operation wasn’t performed. Deleting the curved face should raise the side face and expand the top face until they intersect.

**Cap**

The *Cap* healing method will try to fill up the surface lost to the delete operation by connecting the adjacent faces without changing them.

![cap healing method in face delete cad mode](https://frontend-assets.simscale.com/media/2021/03/cap-cad-mode.jpg)

Figure 10: The Cap healing method. Deleting the top face should return the exact same result as if the operation wasn’t performed. Deleting the curved face should create a face that connects the previously connecting faces without changing them.

**Leave Open**

This healing method will leave a void as a result of the face delete operation and no additional efforts will be taken to heal the connecting faces.

![no healing method in face delete cad mode](https://frontend-assets.simscale.com/media/2021/03/no-healing-cad-mode.jpg)

Figure 11: The Leave Open method. Deleting the top face and the curved face should just remove it, creating a sheet body. In case there survive faces that are not in contact with any of the remaining faces they will still be part of the same sheet body.

With the *Move* operation, you can move a face in the direction of its normal. Select **‘Move’** from the operations toolbar to open the settings panel for this operation. There are two methods to move faces. For illustration let’s consider the highlighted heat sink face:

![cad mode move operation on heat sink ](https://frontend-assets.simscale.com/media/2021/10/cad-mode-move-1.jpg)

Figure 12: Selecting a face for performing the Move operation. More than one face can be selected.

First, select the face and then choose one of the following methods:

**Distance**

Specify the distance up to which the selected faces need to be moved/extruded.

![cad mode move operation with distance method](https://frontend-assets.simscale.com/media/2021/10/cad-mode-move-distance-1.jpg)

Figure 13: Selecting the Move method to Distance will extrude that face up to the desired value.

**Up to Entity**

Specify the entity face up to which the selected faces need to be moved.

![cad mode move operation with up to entity method](https://frontend-assets.simscale.com/media/2021/10/cad-mode-move-entity-1.jpg)

Figure 14: Selecting the Move method to Up to entity will extrude that face up to the plane of the entity face.

Important

The move operation will fail if it causes intersections of the same body. In such case use the *Extrude > Merge > Up to entity* option.

With the *Extrude* operation, you can extrude a face in the direction of its normal by specifying the distance or the face of an entity up to which it should extrude. Select **‘Extrude’** from the operations toolbar to open the settings panel for this operation. There are three methods to extrude faces. For illustration let’s consider the highlighted-blue face:

![extrude operation simscale](https://frontend-assets.simscale.com/media/2023/09/Screen-Shot-2023-09-29-at-04.55.23-e1719597624120.png)

Figure 15: Settings panel for Extrude operation.

First, select the face and then choose one of the following methods:

**Add New**

Add a new face to the existing one, while it is extruded in the normal direction. This operation creates an additional part.

![Selecting the Add new method to Distance will extrude that face up to the desired value.](https://frontend-assets.simscale.com/media/2023/09/addnew.png)

Figure 16: Selecting the Add new method will add a part to the geometry.

Did you know?

Using a negative value in the *Add new* type extrusion would result in the removal of a part of the geometry dividing it into two parts instead of adding a new part.

**Merge**

Extrude the face, merging it with the previous one. Thus, the number of parts remains the same.

![Selecting the Merge method to Distance will extrude that face up to the desired value.](https://frontend-assets.simscale.com/media/2023/09/merge.png)

Figure 17: Selecting the Merge method will extrude the face maintaining the same number of parts.

**Remove**

Extrudes the face in the normal opposite direction, giving a removal operation.

![Selecting the Remove method to Distance will extrude that face up to the desired value.](https://frontend-assets.simscale.com/media/2023/09/remove.png)

Figure 18: Selecting the Remove method will subtract a part of the geometry.

Important

To perform extrude operation on multiple faces at the same time, ensure that all selected faces have the same normal.

**Distance**

Specify the distance up to which the selected faces need to be extruded. All those Extruded operations in this section were made using the distance extrusion method.

![Selecting the Extrude method to Distance will drive that face up to the desired value.](https://frontend-assets.simscale.com/media/2023/09/Screen-Shot-2023-09-29-at-04.50.17-1.png)

Figure 19: Selecting the Extrude method to Distance will drive that face up to the desired value.

**Up to Entity**

Specify the entity face up to which the selected faces need to be extruded.

![Selecting the Extrude method to Up to entity will drive that face up to the desired value.](https://frontend-assets.simscale.com/media/2023/09/Screen-Shot-2023-09-29-at-04.50.33.png)

Figure 20: Selecting the Extrude method to Up to entity will drive that face up to the desired value.

## Body

The *Delete* operation will delete the solid bodies present in the CAD model. Click on **‘Delete’** under *Body* in the operations toolbar and assign one or more volumes from your CAD model before hitting **‘Apply’**.

![Delete bodies in CAD Mode](https://frontend-assets.simscale.com/media/2023/12/delete-body-operation.png)

Figure 21: Assign bodies to be deleted. More than one body can be assigned at once.

There are instances where the CAD is missing one or more faces (these CAD models are called sheet bodies) and you are unable to proceed in the simulation process. In such cases the *Close Sheet* operation for bodies (volumes) is helpful. In the settings panel, select the bodies with missing faces to close and choose a closing method.

![settings panel close sheet cad mode simscale](https://frontend-assets.simscale.com/media/2021/03/cad-mode-close-sheet.jpg)

Figure 22: Settings panel for the Close Sheet operation requires you to select sheet bodies and a closing method to apply.

**Closing Method**

*The Closing method* defines how to close the sheet body using either the *Cap* or the *Grow* method. These methods are described below using an example of Crystal Towers:

![crystal towers](https://frontend-assets.simscale.com/media/2021/03/crystal-towers.jpg)

Figure 23: A CAD model of Crystal Towers used as a reference for the Close Sheet operation. The middle tower is missing a face on the top.

The tower in the middle has a missing face on the top. Hence, the close sheet operation is perfect for this CAD model.

**Cap**

The *Cap* method looks for the minimum possible surface path to close the sheet body and is the default closing method.

![cap closing sheet method](https://frontend-assets.simscale.com/media/2021/03/cap-closing-sheet.jpg)

Figure 24: The missing top face for the middle tower is now closed with a face with a minimum possible surface area

Applying this method to the middle tower closes the top face with minimum possible surface area.

**Grow**

The *Grow* method will try to extend the connecting faces to the missing face until they meet at a vertex.

![grow closing sheet method](https://frontend-assets.simscale.com/media/2021/03/grow-closing-sheet-1.jpg)

Figure 25: The middle tower is extended up to a point where the connecting faces meet.

Applying this method by picking up the middle tower extends the connecting faces of the missing face elongating the middle tower until they all meet at a point.

*Facet Split* allows users to split the CAD model into multiple faces based on the defined maximum split angle. This operation comes in handy when dealing with.stl files as they often consist of only a single face.

![facet split cad mode](https://frontend-assets.simscale.com/media/2021/01/facet-split-cad-mode.jpg)

Figure 26: Use the Facet Split operation to split your CAD model into multiple faces based on the maximum split angle.

The angle can be added in degrees between 0 and 180 and is by default 30.

In order to detect interfaces between two solids or a solid and a fluid, we need to perform an imprint. This action cuts the interface between two bodies that are in physical contact into recognizable surfaces. Please refer to our article where a detailed explanation of [what an imprint does](https://www.simscale.com/knowledge-base/what-does-imprint-do/) is well mentioned.

In the CAD mode, click on **‘Imprint’**, then assign all the parts that need to be imprinted, and hit **‘Apply’**.

![body operation imprint](https://frontend-assets.simscale.com/media/2023/12/imprint-operation.png)

Figure 27: Detect interfaces between bodies by performing an imprint operation on them.

In case the uploaded model does not match the original dimensions or the dimensions of your choice, the *Scaling* operation can be used to adapt the model size accordingly. With scaling, the simulation setup parameters might also change and care should be taken to avoid unreliable results.

![Scale bodies within the CAD Edit mode](https://frontend-assets.simscale.com/media/2023/12/scale-operation.png)

Figure 28: Scaling operation can be used to adapt the model size accordingly using a scaling factor.

Assign all the bodies that need to be scaled. The settings panel also contains a slider to set a scaling factor while also allowing direct entry of the value.

The *Split* operation allows users to cut individual CAD bodies into two parts based on the position and the orientation of the plane defined.

![split operation in CAD mode](https://frontend-assets.simscale.com/media/2023/12/CAD-split-operation.png)

Figure 29: Split operation in CAD edit where the model can be split into two parts

The orientation of the splitting plane is defined by specifying the normal to the plane. The part lying on the side where the normal vector points is retained, while the other part is removed. The user has the option to keep parts from both sides of the plane as well.

You might run into situations where your CAD model has multiple overlapping parts. This might pose a hindrance to the simulation physics causing the simulation setup to fail. If this is the case try our set of Boolean operations. These operations allow you to perform union, subtraction, and intersection operations between different parts. These are described below:

Important

To perform the boolean operations the user must select two or more bodies that share overlapping volumes. If there are assigned bodies that don’t overlap they will be excluded from the operation. Even if no parts overlap, the operation will still show as successful but no changes will be shown in the viewer and in the scene tree.

#### Union

The *Union* operation is used to merge two overlapping entities into a single entity. The resulting body encloses the volume of both overlapping entities. This is shown below:

![union operation in cad mode](https://frontend-assets.simscale.com/media/2021/03/cad-mode-boolean.jpg)

Figure 30: Union boolean operation is used to merge two or more bodies into a single body.

The CAD geometry consists of two overlapping bodies, *Part 1* (cube) and *Part 2* (sphere). Their different colors represent two separate entities. These two bodies are separately identified in the scene tree. To perform the *Union* operation select the two bodies and hit **‘Apply’**.

![result of union operation simscale](https://frontend-assets.simscale.com/media/2021/03/cad-mode-boolean-2.jpg)

Figure 31: A successful union operation of two bodies resulting in a single body, shown in the scene tree by listing only one part.

On success, the CAD geometry shows a single body identified with the name *Part 2* in the scene tree and the same color. This signifies that the two bodies are united into one single body.

#### Intersect

The *Intersect* operation is used to create a new entity out of the common volume between the overlapping entities. You just need to select the involved entities. Using the same example as in Figure 27 the intersection operation results in the following CAD model:

![intersect boolean operation](https://frontend-assets.simscale.com/media/2021/03/cad-mode-intersection.jpg)

Figure 28: Intersect boolean operation between overlapping bodies results in a new body whose surfaces are enclosed by their common volume.

The result is a quarter of a sphere.

#### Subtract

The *Subtract* operation can be used for the following operations:

- To remove the common volume from one of the entities while keeping it intact in the other
- To remove the common volume along with one of the entities

The settings panel for this operation is shown below:

![subtract operation cad mode](https://frontend-assets.simscale.com/media/2021/03/cad-mode-subtract.jpg)

Figure 32: Subtract operation can remove the common volume and the tool body or the common volume from the target body only.

The settings panel asks the user to select target bodies and tool bodies. A target body is a body to subtract from while a tool body is a body to be subtracted. In this example, we choose to subtract the sphere (in pink) from the cube (in blue).

One more important step is to choose whether to keep the tool bodies or not. If *Keep tools* is selected then the common volume gets subtracted only from the target body. The final result still has two separate bodies.

If *Discard tools* is selected then both the common volume and the tool body gets subtracted. The final result now has a single body. Both the results are shown in the figure below:

![keep tools versus discard tools in subtract boolean cad mode](https://frontend-assets.simscale.com/media/2021/03/cad-mode-subtract-2.jpg)

Figure 33: Difference between Keep tools and Discard tools feature for the subtract boolean operation. The former results in the same number of bodies while the latter removes the tool bodies.

Under this section, there are operations that allow users to move the part volumes within their geometry by either translating them whole up to a certain distance or rotating them by a specified angle.

#### Translate

As the name suggests, the *Translate* feature aids in translating the body or bodies up to a certain specified distance in the specified directions. Similar to the *Move* operation, there are two methods to proceed:

**X, Y, Z**

With this method, you can specify the distance up to which the selected volume needs to be translated in each direction. A negative value would translate in the opposite direction. Kindly follow the orientation cube at the bottom right to avoid confusion.

Following the same example from Figure 9, this time instead of moving the face of the heat sink we will move the whole heat sink body in the positive y-axis by a distance of 0.025 $m$.

![translate xyz cad mode](https://frontend-assets.simscale.com/media/2021/12/translate-xyz-cad-mode.png)

Figure 34: Selecting the Translate method to X, Y, Z will translate that body to the desired coordinates.

**Up to Entity**

In this method, you just have to assign the face of the entity up to which the assigned volume needs to be translated. This time we assigned a face of the chip for the algorithm to translate the heat sink such that its foremost face is coplanar with that of the chip.

![translate up to entity cad mode](https://frontend-assets.simscale.com/media/2021/12/translate-up-to-entity.png)

Figure 35: Selecting the Up to entity method will translate that body up to the plane of the entity face.

The following schematic perfectly represents the possibilities of a successful *up to entity* translate operation:

![translate operation schematic to represent possibilities in cad mode](https://frontend-assets.simscale.com/media/2021/12/translate-operation-cad-mode-1.png)

Figure 36: The possibilities of success and failure using the up to entity translate operation

#### Rotate

As the name suggests, the *Rotate* feature aids in rotating a body or multiple bodies about a specified axis. This axis of rotation passes through the center of an imaginary bounding box whose dimensions represent the minimum and maximum coordinates of that body (or bodies combined) in the x-, y-, and z-direction.

Let’s look at the following example:

![rotate operation settings](https://frontend-assets.simscale.com/media/2021/07/cad-mode-rotate-2.jpg)

Figure 37: Rotate feature allows rotation of one or more bodies about a specified axis.

Here, different parts of the airplane wing are being rotated about the positive y-axis. This means that all these parts will rotate, in the anti-clockwise direction, at the same time about the central axis of the bounding box pointing in the positive y-direction. It is advised to refer to the orientation cube while assigning the rotation axis. Clicking on the inverse button will result in the reversal of the axis assigned (negative y-axis in this example).

![result of rotate operation](https://frontend-assets.simscale.com/media/2021/07/cad-mode-rotate-2-1.jpg)

Figure 38: Result of the Rotate operation above

Often there are instances where the CAD model has too much detailing that is insignificant from the simulation point of view. This may include threads on a bolt or pattern imprint on a tire. These fine details can cause simulation overhead by requiring a fine mesh and subsequently a high consumption of [core hours](https://www.simscale.com/knowledge-base/what-is-core-hours/).

With the *Simplify* feature, these fine details can be replaced with primitive shapes like cylinders or boxes that occupy minimum bounding dimensions.

![simplify settings panel cad mode](https://frontend-assets.simscale.com/media/2021/06/cadmode_simplify.jpg)

Figure 39: Simplify feature allows replacement of a detailed body with a box or cylinder primitive

![replacement with box and cylinder test](https://frontend-assets.simscale.com/media/2021/06/cadmode_simplify_1-1024x317.jpg)

Figure 40: Examples showing the difference between replacement with a box against a cylinder

Multiple bodies can be replaced in a single operation either with a cylinder or a box. By default each body is replaced separately however this can be toggled off to generate a single resultant body.

![different replacement options in simplify](https://frontend-assets.simscale.com/media/2021/06/image-4-2.png)

Figure 41: Multiple bodies can be selected at once for replacement and can be replaced individually or as a group.

The *Wrap Surface* operation is intended to generate a simulation-ready CAD model in situations where it contains a lot of artifacts like self-intersections, holes, cracks, overlaps, unimportant features, etc. Cleanup of such CAD can be very complex and extremely time-consuming, often even impossible, making it unsuitable for meshing.

The settings look as follows:

![wrap feature in cad mode](https://frontend-assets.simscale.com/media/2023/03/wrap.png)

Figure 42: Settings panel for the Wrap feature. Select the whole model or parts to be wrapped.

- *Bodies to be wrapped:* Whole CAD model or a part of the model to be used as an input to the wrapping procedure.
- *Wrap Type:*
	- *Fit to surface:* This will try to make a wrap closest to the original body, however, it will not make any attempts to preserve any features like sharp edges. This operation is more robust and stable.
		- *Snap to edges:* This will try to fit the resulting surface to sharp edges in the model. Sharp edges are currently defined as edges on the geometry where the angle between adjacent surfaces is larger than 30°.
- *Resolution:* This controls the wrap precision. Values between 1 and 10 are accepted. Higher values produce geometry that closely represents the input surface. Lower values result in a faster, but coarser representation.
- *Allow Tunnels:* If toggled on, it will allow the result to be topologically more complex than a sphere. This means tunnels or even multiple disconnected surfaces.
- *Cap Tunnels:* If toggled on, the algorithm will try to close all detected tunnels, pockets, and gaps, simplify the model, and create an outside envelope while still maintaining other significant features.
- *Tunnel Detection:*
	- *Automatic:* Detects the tunnels automatically.
		- *Manual:* Requires the minimum tunnel diameter that is needed to be recognized.
- *Wrap each body individually:* An option to wrap all selected bodies at once as a group or wrap each selected body individually.

![wrap surface result for car](https://frontend-assets.simscale.com/media/2022/06/wrap-surface-result.png)

Figure 43: Car model containing a number of features and a lot of self-intersections (left). Car model after wrapping – simplified and ready for meshing (right).

## Model

*Fix interferences* should be your option when trying to fix the interfering bodies in your CAD model automatically. Just click on the icon and hit **‘Apply’**. It should get rid of all the interfering parts. Users should note that, in this automatic operation, the smaller body is subtracted from the larger body.

Don’t forget to run an interference check again just to be certain (see *[Interferences](https://www.simscale.com/docs/cad-preparation/cad-mode/#interferences)* below). You should see a **“No Interferences found in your CAD Model”** message.

The *Add CAD* operation allows you to add parts to an existing CAD model in SimScale. As an example, the *Electronics Box* geometry below is missing one *Large Capacitor*:

![two cad models in simscale add cad mode](https://frontend-assets.simscale.com/media/2022/04/add-cad-operation-cad-mode.png)

Figure 44: Before performing an Add CAD operation, make sure that both models are uploaded to SimScale.

In CAD mode, you can create a new **‘Add CAD’** operation to have both CAD models combined:

![add cad configuration in CAD mode](https://frontend-assets.simscale.com/media/2022/04/add-cad-operation-e1719597923683-1024x667.png)

Figure 45: Setting up a new Add CAD operation in CAD mode

As a result of the operation, the capacitor is added to the electronics box geometry:

![result of the add CAD operation](https://frontend-assets.simscale.com/media/2024/07/image.png)

Figure 46: Result of the Add CAD operation

It is worth noting that the new CAD part is added respecting its original coordinates. If the new part needs to be re-positioned, please consider using a [translate](https://www.simscale.com/docs/cad-preparation/cad-mode/#translate) CAD edit operation.

## Create

A CFD simulation is performed on the actual fluid volume. For an internal flow problem, this means that the fluid volume needs to be extracted from the CAD geometry or, be created around the CAD geometry for an external flow problem.

This can be performed in the CAD editor using the *Flow volume* operation. More information on flow volume extraction can be found [here](https://www.simscale.com/knowledge-base/flow-volume-extraction/).

#### External Flow Volume

To create an external flow volume, you need to enter the minimum and maximum dimensions for the volume in the x-, y-, and z-direction. Optionally, select a [seed face](https://www.simscale.com/knowledge-base/what-is-a-seed-face/) that corresponds to any face on the CAD geometry.

![external flow volume cad mode](https://frontend-assets.simscale.com/media/2021/01/external-flow-volume-cad-mode-1024x464.jpg)

Figure 47: External flow volume extraction requires minimum and maximum dimensions, and an optional seed face.

By default, this operation retains all the CAD parts. You can specifically exclude them by selecting them under *Excluded parts*. If unsure, the parts can also be deleted later using the delete operation for the body (discussed above).

#### Internal Flow Volume

To create an internal flow volume you need to specify a [seed face](https://www.simscale.com/knowledge-base/what-is-a-seed-face/) and one or more boundary faces ( lies between the external environment and the internal).

![internal flow volume cad mode](https://frontend-assets.simscale.com/media/2021/01/internal-flow-volume.jpg)

Figure 48: Internal flow volume extraction requires a seed face and one or more boundary faces.

Similar to external FVE internal FVE also retains all the CAD parts. You can exclude them under *Exclude parts* option.

Important

Users should note that faces selected for operation in a flow volume extraction process, such as seed face and boundary face, cannot belong to the excluded parts (volumes) of the CAD model.

#### Internal Caps

The *Internal caps* operation creates cap faces for the inlets and outlets of the internal flow domain and groups them into a sheet body. The operation can currently only be used with the Immersed Boundary analysis type. Internal caps operation creates faces (caps) that cover the inlets and outlets of the internal flow volume. The faces can later be used for the definition of boundary conditions. Read more about this operation [here](https://www.simscale.com/docs/analysis-types/immersed-boundary-analysis/#internal-caps).

By clicking *Box,* the user is allowed to create a box shape within CAD Edit. This is particularly helpful in manually creating internal or external flow volumes by a subsequent [*Boolean Subtraction*](https://www.simscale.com/docs/cad-preparation/cad-mode/#subtract), if the *Create* **→** *Flow Volume* option does not work.

There are two methods to create boxes: *Custom* and *From faces*.

When using the *Custom* method, the box’s X, Y and Z min/max coordinates need to be specified by the user.

![cad mode custom box](https://frontend-assets.simscale.com/media/2024/09/image-1.png)

Figure 49: A preview of the box is visible in the viewer before accepting the cylinder settings

As this might be a cumbersome process when one does not know the exact global coordinates to be applied, another option is to select faces which will be covered by the box, as shown in the picture below.

![cylinder operation cad mode from faces](https://frontend-assets.simscale.com/media/2024/09/image-2.png)

Figure 50: The box selection tool, highlighted by the blue arrow, can help to quickly select the faces of interest for the generation of the box

A *Scaling factor* may also be used in case one wants a box to envelop a higher volume than the one delimited by the chosen faces. The result of this operation is depicted in the picture below.

![additional cylinder created rotating zone](https://frontend-assets.simscale.com/media/2024/09/image-3.png)

Figure 51: A new volume named Box will be visible after running the operation

This operation allows the creation of a cylinder, which is especially useful in simulations involving [rotating zones](https://www.simscale.com/knowledge-base/how-to-prepare-cad-for-simulating-rotating-zones/). There are two methods to create cylinders: *Custom* and *From faces*.

When using the *Custom* method, the center of rotation, axis of rotation, radius, and height of the cylinder need to be specified by the user.

![cad mode custom cylinder](https://frontend-assets.simscale.com/media/2022/07/custom-cylinder-operation-cad-mode.png)

Figure 52: A preview of the cylinder is visible in the viewer before accepting the cylinder settings

The *Custom* approach requires global coordinates to be provided for the creation of the cylinder. In case you don’t have those readily available, the *From faces* approach might be preferred.

When using the *From faces* approach to create a cylinder, the user needs to select the *Faces* which should be covered by the cylinder:

![cylinder operation cad mode from faces](https://frontend-assets.simscale.com/media/2022/07/cylinder-from-faces-cad-mode-1.png)

Figure 53: The box selection tool, highlighted by the blue arrow, can help to quickly select the faces of interest for the generation of the cylinder

With this approach, a cylinder that envelops all selected faces is created. Furthermore, a *Clearance factor* is applied, ensuring that the cylinder is slightly larger than the assigned faces. For simulations involving rotating machinery, a *Clearance factor* of **1.1** is recommended.

As a result of the *Cylinder* operation, a brand new volume is created:

![additional cylinder created rotating zone](https://frontend-assets.simscale.com/media/2022/07/additional-cylinder-created.png)

Figure 54: A new volume named Cylinder will be visible after running the operation

## Tools

Your CAD model is not ready for the simulation setup if it has interfering solid parts. Interfering/Overlapping solid parts can result in the [failure of geometry operations](https://www.simscale.com/knowledge-base/why-do-geometry-operations-fail/) performed while editing the geometry and more importantly cause the meshing algorithm to fail. Hence, it should be avoided at all costs.

To check for interfering parts click on the **‘Interference’** icon and wait for a message while the operation runs in the background. A valid CAD model with no interfering parts should display the message on the left as shown below:

![cad mode interference check ](https://frontend-assets.simscale.com/media/2021/06/cad-mode-interference-1.jpg)

Figure 55: If you have a CAD model with multiple solid parts don’t forget to run an interference check.

To fix interferences manually use boolean or delete-body operations described above. Additionally, for automatic fixing of interferences use the *[Fix interferences](https://www.simscale.com/docs/cad-preparation/cad-mode/#fix-interferences)* feature discussed under *Models*.

When preparing your CAD model there are often undesired gaps that are not visible or overseen and can lead to mesh quality issues or prolonged run times. These gaps need to be identified and fixed at an early stage. For example, in a CHT case, all the components must be in contact with each other to capture the heat transfer correctly. The below geometry has thin gaps because of which contact cannot be generated between the mainboard and the chip.

![Small undesired gaps in the geometry which is usually overseen leading to missing contacts.](https://frontend-assets.simscale.com/media/2022/03/small-undesired-gaps-in-the-geometry-which-is-usally-overseen-leading-to-missing-contacts.-4-2048x655.png)

Figure: Small undesired gaps in the geometry which are usually overseen leading to missing contacts.

To detect these small gaps click on the ****‘Gaps’**** icon and then specify the **‘Maximum distance’** to define a gap tolerance and then hit **‘Detect gaps’**. All gaps that are equal to or less than the maximum distance will be detected. Depending on the CAD model this can take a while and will display a message as shown in the below figure.

![Specify a maximum distance upto which gaps in the CAD model should be detected.](https://frontend-assets.simscale.com/media/2022/03/detect-gaps-2.png)

Figure 56: Specify a maximum distance up to which gaps in the CAD model should be detected.

After running the operation, the following results can occur, depending on the *Maximum distance*:

![Find gaps in the CAD model up to a specified tolerance (Maximum distance) by clicking on Detect gaps](https://frontend-assets.simscale.com/media/2022/03/Detect-gaps-in-CAD-model-upto-a-specified-tolerance-2-1.png)

Figure 57: Find gaps in the CAD model up to a specified tolerance ( Maximum distance ) by clicking on Detect gaps.

Upon expanding the detected gaps and selecting a face, the corresponding face will be highlighted in red color on the model. These gaps can be fixed either via *Move>Face* or *Translate* operations.

Last updated: May 19th, 2026

Product

What is SimScale?

Technology

Solutions

Use cases

Applications

Industries