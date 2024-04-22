# Metashape
Agisoft Metashape processes digital images and generates 3D spatial data through a process called photogrammetry. Photogrammetry is increasingly used in cultural heritage contexts to document, share, and recontextualize historical artifacts. Depending on the quality of the images and use of calibrated scale bars, it's possible to generate 3D models with measurement data with sub-millimeter accuracy. 
Metashape is a proprietary and commonly used program for photogrammetry. There are both Standard and Pro versions of Metashape, with Metashape Pro needed to add scale bar or geospatial data. This guide will focus on the basic process of generating a 3D model without measurement data and can therefore be used for Metashape Standard or Metashape Pro. 

Visit Agisoft Metashape's [website](https://www.agisoft.com/), [documentation](https://agisoft.freshdesk.com/support/solutions), [user manuals](https://www.agisoft.com/downloads/user-manuals/) and [downloads page](https://www.agisoft.com/downloads/installer/) for more information.

## Digital Photographs
To use Metashape, you need a series of clear, overlapping photographs. The software will triangulate the images to determine spatial data and generate a 3D model. Your photographs are your raw data and it's important to keep them organized in a folder for later use or reprocessing.

This guide will not cover how to take photographs for a photogrammetry project or how to process more complex scenarios using different cameras or distances from the object of interest. [Cultural Heritage Imaging](https://culturalheritageimaging.org/Technologies/Photogrammetry/) provides a guide on how to take good photographs for a photogrammetry project.

## Interface Overview
This guide was created using Metashape Pro 2.1.1 for Mac; while there are small differences between the user interfaces for different operating systems, the general workflow is the same. 

![Screenshot of Metashape window](/img/metashape1.png)

Metashape has multiple window tabs that you can add, hide, resize, move around, or break out from the main Metashape window while working. You can toggle these tabs on and off using the View dropdown menu. While there are many tabs for specialized purposes, the following views are commonly used for all projects: 
- Toolbar: Shows options to save, move, zoom, hide, or show elements of your model.
- Workspace: Shows all components of your project, including images and any processed components, such as tie points, depth maps, or 3D models.
- Model View: Displays 3D data and allows for some editing. Selection in the Toolbar and in the Workspace will determine what is displayed.
- Photos View: Shows thumbnails of all photos and depth maps used in the project.

## General Workflow

### Add Photos
This guide assumes all photographs are taken by the same camera and from the same distance. To add photographs to Metashape, select 'Workflow > Add Photos...'. Navigate to the folder where your images are and select all images you plan to use. Be sure to save your project after each processing step.

### Align Photos
When you align images, Metashape begins to compare and match features between the images to triangulate where in space the photographs were taken. This process allows Metashape to then determine where in space individual features of your object of interest are. To align images, select 'Workflow > Align Images...'. 

![Screenshot showing 'align photos' option in the View dropdown menu](/img/metashape2.png)

A pop-up window will appear with some general and advanced parameters. The default settings should be fine for most projects. Grayed out selections cannot be selected.
- Accuracy: Determines the size of the photograph used to compare and match features; 'High' accuracy uses the photos at their original size. Lower accuracy settings downscale the images and accuracy but can decrease processing time. 'Highest' accuracy increases processing time and should only be used on very sharp images.
- Generic Preselection: Helps to speed up processing time when using a lot of photographs. When checked, Metashape aligns photos at a lower accuracy to find overlapping pairs before comparing those overlapping images at a higher accuracy.
- Reference Preselection: Helps to speed up processing time when using a lot of photographs based on the metadata of the photographs. When checked, 'Source' identifies overlapping pairs by measured camera locations if this was collected, 'Estimated' uses any orientation data that may have already been generated by a previous alignment, and 'Sequential' uses the order of the images by sequence number (including the first and last images). 'Sequential' can be helpful for images taken in the round or using a turntable.
- Reset Current Alignment: Removes any previously generated alignment data you may have run.

Select your preferred settings and click 'Ok'. A 'processing in progress...' box and status bar will appear. Depending on the amount and size of your photos, as well as your selected settings and computer hardware, this may take some time. You can minimize, pause, or cancel the alignment process at any time. 

When the processing is done, you will see in the Model View a representation of your object as points in space (tie points Metashape identified between images) and squares representing where the camera was when each image was taken. Be sure to save your project. If your object and camera positions don't look correct, you may need to reassess the quality of your images or manually identify overlapping points. 

![Screenshot of Model View showing tie points and camera positions](/img/metashape3.png)

Your project now has vital spatial data that will be used to make different outputs, such as a dense point cloud, 3D model, or digital elevation model. We will cover the first in this guide.

### Build Model
When you build the model, you are generating a digital object consisting of a mesh of spatial data. You can export these in a variety of formats for further analysis, modeling, or use in other digital or immersive contexts. To build a model in Metashape, select 'Workflow > Build Model...'. A pop-up window will appear with some general and advanced parameters. The default settings should be fine for most projects.
- Source data: Determines what data is used to create the 3D model. Available options depend on previously processed or external data. 'Depth Maps' and 'Tie Points' are available after the alignment process. Using 'Tie Points' is quicker, but less accurate as they use the points generated during the alignment process. Using 'Depth Maps,'' consisting of distance data between points, uses all information from the input images. 
- Surface type: 'Arbitrary (3D)' is appropriate for any 3D objects; 'Height Field' is optimized for flat surfaces (such as with aerial photography).
- Quality: Determines the quality of depth map used (if selected). Higher quality will result in a more accurate model but will take more time to process.
- Face count: Determines how many polygons the 3D mesh will have; lower polygons result in a less detailed model, while higher polygons can inhibit how efficiently you can show, share, and interact with your model, especially online. You can later decimate or reduce the number of polygons for your model if needed. 

Select your preferred settings and click 'Ok'. A 'processing in progress...'. box and status bar will appear. Based on your parameters and hardware, this may take some time. You can minimize, pause, or cancel the process at any time. When it's complete, you'll see a shaded 3D model of your object of interest in Metashape.

![Screenshot of Model View showing generated 3D model](/img/metashape4.png)

### Build Texture
Texture is like a wrapper that goes around a model's 3D polygon mesh. Using photographs in Metashape, this creates a photorealistic 3D model. To build a texture in Metashape, select 'Workflow > Build Texture...'. A pop-up window will appear with some general and advanced parameters. The default settings should be fine for most projects. Select your preferred settings and click 'Ok'.

![Screenshot of Model View showing generated 3D model with texture](/img/metashape5.png)

### Export Model
To export your model to share or use in another application, select the 3D model in the Workspace tab and right click. A new menu will appear; select 'Export Model...'. You'll have the option to save the model in a variety of file formats on your local computer.