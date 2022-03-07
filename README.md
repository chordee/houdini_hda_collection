# houdini_hda_collection
Houdni Digital Assets Collection

---
## fake_window (VOP)
Something like Fake Window shader in Unity. Output simple color from perspective camera.
|<img src="imgs/fake_window_node.png" alt="drawing" height="160"/>|<img src="imgs/fake_window_setting.png" alt="drawing" height="160"/>|
|:---:|:---:|
|Vop in MatNetwork|pre-setting: UV and Normal|
* Depth: Max depth value when output inDepth.
* Outputs: 
    |<img src="imgs/wall_outUV.png" alt="drawing" height="160"/>|<img src="imgs/wall_id.png" alt="drawing" height="160"/>|<img src="imgs/out_nor.png" alt="drawing" height="160"/>|<img src="imgs/in_depth.png" alt="drawing" height="160"/>|
    |:---:|:---:|:---:|:---:|
    |outUV|id|outNor|inDepth|
---
## grid_cutter (SOP: Grid Cutter)
|<img src="imgs/grid_cutter_node.png" alt="drawing" height="160"/>|<img src="imgs/grid_cutter.png" alt="drawing" height="160"/>|
|---|---|
* Auto Align: Align the face to X/Z before cutting. 
  (Useful when using grid_cutter in For-Each Primitive)
  <img src="imgs/grid_cutter_auto.png" alt="drawing" width="160"/>
* Force Cut Long Side: Cut the long side at each iteration.  
  <img src="imgs/grid_cutter_force.png" alt="drawing" width="160"/>
* Half Ratio: How close to half everytime cutting.
  | <img src="imgs/grid_cutter_h05.png" alt="drawing" width="160"/>|  <img src="imgs/grid_cutter_h1.png" alt="drawing" width="160"/> |
  |:----:|:----:|
  | Half Ratio: 0.5 | Half Ratio: 1 |
* Min Size: Limit the size of smallest piece.
---
### line_creacker (SOP)
Fracture base on polyline projection. (X/Z plane)  
|<img src="imgs/line_cracker_node.png" alt="drawing" height="160"/>|<img src="imgs/line_cracker_45.png" alt="drawing" height="160"/>|
|---|---|
> Input 1: polyline.
> Input 2: Ground plane (Don't need to be flatten)  
> Output: Fractured poly with attributes.

|<img src="imgs/line_cracker_circle.png" alt="drawing" height="160"/>|<img src="imgs/line_cracker_straight.png" alt="drawing" height="160"/>|
|:---:|:---:|
|Close Line|Open Line|
* Iterations: Increase to match the input line. (Maybe can not be perfect match.)
* Iteration Threshold: Avoid really small piece.
---
### Mandelbrot3D (VOP)

