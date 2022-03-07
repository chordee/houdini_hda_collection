# houdini_hda_collection
Houdni Digital Assets Collection

---
## fake_window (VOP: Fake Window)
Something like Fake Window shader in Unity. Output simple color from perspective camera.
|<img src="imgs/fake_window_node.png" alt="fake window node" height="160"/>|<img src="imgs/fake_window_setting.png" alt="fake window example" height="160"/>|
|:---:|:---:|
|Vop in MatNetwork|pre-setting: UV and Normal|
* Depth: Max depth value when output inDepth.
* Outputs: 
    |<img src="imgs/wall_outUV.png" alt="outUV" height="160"/>|<img src="imgs/wall_id.png" alt="id" height="160"/>|<img src="imgs/out_nor.png" alt="drawing" height="160"/>|<img src="imgs/in_depth.png" alt="inDepth" height="160"/>|
    |:---:|:---:|:---:|:---:|
    |outUV|id|outNor|inDepth|
---
## grid_cutter (SOP: Grid Cutter)
|<img src="imgs/grid_cutter_node.png" alt="grid cutter node" height="160"/>|<img src="imgs/grid_cutter.png" alt="grid cutter example" height="160"/>|
|---|---|
* Auto Align: Align the face to X/Z before cutting. 
  (Useful when using grid_cutter in For-Each Primitive)
  <img src="imgs/grid_cutter_auto.png" alt="auto align" width="160"/>
* Force Cut Long Side: Cut the long side at each iteration.  
  <img src="imgs/grid_cutter_force.png" alt="force cut long side" width="160"/>
* Half Ratio: How close to half everytime cutting.
  | <img src="imgs/grid_cutter_h05.png" alt="half ratio 05" width="160"/>|  <img src="imgs/grid_cutter_h1.png" alt="half ratio 1" width="160"/> |
  |:----:|:----:|
  | Half Ratio: 0.5 | Half Ratio: 1 |
* Min Size: Limit the size of smallest piece.
---
## line_creacker (SOP: Line Cracker)
Fracture base on polyline projection. (X/Z plane)  
|<img src="imgs/line_cracker_node.png" alt="line creacker node" height="160"/>|<img src="imgs/line_cracker_45.png" alt="line crack example" height="160"/>|
|---|---|
> Input 1: polyline.  
> Input 2: Ground plane (Don't need to be flatten)  
> Output: Fractured poly with attributes.

|<img src="imgs/line_cracker_circle.png" alt="close line example" height="160"/>|<img src="imgs/line_cracker_straight.png" alt="open line example" height="160"/>|
|:---:|:---:|
|Close Line|Open Line|
* Iterations: Increase to match the input line. (Maybe can not be perfect match.)
* Iteration Threshold: Avoid really small piece.
---
## export_Maya_nParticles_cache (SOP: Export Maya nParticle cache)  
#####REQUIREMENT:  
1. unique id attribute. 
2. [source code: nCache.py](https://github.com/chordee/mayaGeoCache)  

> Attribute Mapping:  
> + v@v -> velocity
> + f@age -> age
> + f@life -> lifespanPP
> + f@pscale -> radiusPP
> + v@Cd -> rgbPP
> + f@Alpha -> opacityPP
> + v@rotation -> rotationPP.

<img src="imgs/export_maya_nparicle_cache_node.png" alt="close line example" height="160"/>  

* Start Frame
* End Frame
* Evaluation Rate
* XML: xml file path to be written.
* Particle Name: Particle Shape name in Maya.
* Python Module Path: nCache.py filepath.
---
## Mandelbrot3D (VOP)

