# Technical Breakdown — Harry Houdini

This document describes the technical components of the interactive scene.

## Unity Version
- Unity 2021+  
- URP  
- Shader Graph enabled

## Project Components

### 1. Water Shader
Created entirely in **Shader Graph**, the shader simulates:
- a distinct surface line between transparent and opaque areas,
- distortion of the surface based on input values,
- ripple generation influenced by mouse speed,
- ripple decay over time.

Exposed shader properties allow further tuning:
- _DistortionStrength_
- _RippleAmplitude_
- _RippleDecaySpeed_
- _MouseInfluence_

### 2. PivotController Script
This C# script:
1. Reads mouse position and converts it to viewport space.
2. Computes movement delta and velocity.
3. Normalizes values and sends them to shader properties via `Material.SetFloat` and `SetVector`.
4. Produces real-time deformation of the water surface.

### 3. Models
Created in Blender:
- **Character** — sculpted, retopologized, and textured manually.
- **Cube Container** — simple geometry designed for clean visual distortion.

### 4. Scene Setup
- Orthographic or perspective camera facing the cube.
- Single directional light or HDRI for soft visuals.
- Character placed inside cube; cube material replaced by shader.

## Build
A WebGL build is used for demonstration and portfolio embedding.
