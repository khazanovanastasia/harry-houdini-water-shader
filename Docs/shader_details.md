# Shader Details — Water Simulation (Shader Graph)

This document explains how the waterline and ripple simulation are constructed.

## Core Concepts

### Waterline Mask
A height-based mask splits the cube into:
- transparent upper region,
- opaque tinted lower region.

This creates the illusion of a water surface without additional geometry.

### Distortion Logic
The shader receives:
- cursor direction (normalized),
- cursor movement velocity.

Using these values:
- the waterline rotates perpendicular to the cursor vector,
- the mask boundary shifts slightly,
- UV distortion simulates bending of the surface.

### Ripples
Ripples are generated using:
- time-based sine functions,
- velocity-dependent amplitude,
- smooth damped decay.

The shader stores a ripple intensity value that decreases over time.

## Graph Structure

**Nodes used:**
- Vector Math (Normalize, Subtract, Multiply)
- UV Distortion
- Smoothstep
- Lerp
- Add, Multiply, Sin
- Time

**Master Stack outputs:**
- Base Color (distorted)
- Alpha (driven by waterline mask)

The shader is lightweight and runs efficiently on WebGL.
