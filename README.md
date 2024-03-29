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
## line_cracker (SOP: Line Cracker)
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
* Iteration Threshold: Avoid extreme small piece.
---
## export_Maya_nParticles_cache (SOP: Export Maya nParticle cache)  
*Export Maya nParticle cache from Houdini directly.*  

REQUIREMENT:  
1. unique id attribute. 
2. [source code: nCache.py](https://github.com/chordee/mayaGeoCache)  

Attribute Mapping:  
```
v@v -> velocity
f@age -> age
f@life -> lifespanPP
f@pscale -> radiusPP
v@Cd -> rgbPP
f@Alpha -> opacityPP
v@rotation -> rotationPP
```

<img src="imgs/export_maya_nparicle_cache_node.png" alt="export Maya nParticle cache node" height="240"/>  

* Start Frame
* End Frame
* Evaluation Rate
* XML: xml file path to be written.
* Particle Name: Particle Shape name in Maya.
* Python Module Path: [nCache.py](https://github.com/chordee/mayaGeoCache/blob/master/nCache.py) filepath.

---
## export_Maya_geoCache (SOP: Export Maya geoCache)  
*Export Maya geometry point cache from Houdini directly. (Multiple objects is ok)*  

REQUIREMENT:  
1. Primitive attribute: path. 
2. [source code: nCache.py](https://github.com/chordee/mayaGeoCache)  

> path attribute is used to define the target in Maya. Therefore, the best way is using the alembic which was exported from Maya, and keep the path attribute so that can be used to export back.

<img src="imgs/export_maya_geo_cache_node.png" alt="export Maya Geo cache node" height="240"/> 

* XML: xml file path to be written.
* Start Frame
* End Frame
* Python Module Path: [nCache.py](https://github.com/chordee/mayaGeoCache/blob/master/nCache.py) 

---
## Mandelbrot3D (VOP)
[Entagma - VEX in Houdini: Mandelbrot and Mandelbulb](https://vimeo.com/176911687)  

[Zeus VFX - 3D Fractal in Houdini Tutorial](https://youtu.be/-qgtQ91oItQ)  
  
<img src="imgs/mandelbrot3d.png" alt="Mandelbrot3D" height="240"/>  

---  
## volume_texture (VOP: Volume Texture)  
Reuse the volume texture which was exported from **Labs Volume Texture Export** in Houdini.  
<img src="imgs/volume_texture_node.png" alt="Volume Texture Node" height="160"/> 
* Volume Texture: Texture filepath.
* BB_pos: bbox position.
* U_Tile
* V_Tile
* outClr: RGB color from volume texture.  

---
## create_crowd_collections_by_agent_stage_material (LOP)
Create collections by the name of material binding with source agent mesh.
<img src="imgs/crowd_collections_node.png" alt="Create Crowd Collections" height="120"/>

* Collection: collection prim path
* From Path
* Replace Path


---
## thunder_builder (SOP: Thunder Builder)



