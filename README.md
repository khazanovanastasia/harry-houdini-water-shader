# HARRY HOUDINI - Interactive Water Shader Sketch

**Interactive digital art piece exploring motion, gravity simulation, and shader-driven visual storytelling.**

This repository is a **public showcase** of the technical and artistic elements behind *Harry Houdini*, a realâ€‘time interactive scene rendered in Unity.  
The full development repository remains private; this repo contains curated assets demonstrating the core idea.

---

## 🎨 Project Overview

*Harry Houdini* is an interactive art sketch where the viewer influences the behavior of a simulated water surface.

Inside a transparent cube “half‑filled” with water sits a stylized 3D character.  
The liquid is not real geometryâ€”its illusion is generated entirely through a **Shader Graph–based water shader** that reacts to mouse movement.


### Interaction
- The user moves the mouse.
- The shader receives input about cursor direction and speed.
- The water surface bends perpendicularly to the cursor vector.
- Ripples appear based on cursor velocity and gradually fade.

The result: the viewer becomes a kind of “gravitational force,” disturbing the water simply by looking and moving.

---

## 🧩 Contents of This Repository

```
/Shaders
    Water.shadergraph     # Core water shader

/Scripts
    PivotController.cs    # Script handling mouse input and communication with the shader

/Models
    Character.fbx         # 3D model created in Blender (showcase version)
    CubeContainer.fbx     # Container geometry

/Media
    screenshots/
    gifs/
```

> Full Unity project remains private.  
> This repo is for demonstration and review only.

---

## 🛠 Technical Highlights

### 🌊 Water Shader (Shader Graph)
- Mask-based split between transparent and opaque region  
- Direction distortion driven by cursor-to-center vector  
- Ripple amplitude influenced by cursor speed  
- Ripple decay over time  
- Exposed parameters for customization  

### 🖱 Pivot Controller Script
- Tracks cursor position relative to cube center  
- Computes velocity + direction  
- Feeds normalized data into shader parameters  
- Produces interactive waterline deformation  

### 👤 Art & Assets
- Character model sculpted and textured in Blender  
- Simple rig for posing  
- Clean cube geometry to highlight distortion  

---

## 🌐 Demo

A **WebGL build** is available on the project page of my portfolio:  
*(link)*

Additional GIFs and screenshots are in the `Media/` folder.

---

## 🧪 Requirements

- Unity 2021+ (URP recommended)  
- Shader Graph package  
- Mouse input support  

---

## 📬 Contact

email / website / portfolio

