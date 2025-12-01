# Interaction Logic — Harry Houdini

This document describes how user input affects the shader.

## Mouse Input Processing

The script `PivotController.cs` performs:
1. `Input.mousePosition` → converted to viewport space.
2. Calculation of movement delta:
> delta = currentPos - previousPos
> speed = delta.magnitude / Time.deltaTime
3. Normalization of speed for shader:
> normalizedSpeed = Mathf.Clamp(speed / maxExpectedSpeed, 0, 1)


## Shader Communication

The script sends:
- `_CursorDirection` (Vector2)
- `_CursorSpeed` (Float)
- `_RippleIntensity` (Float)

Parameters are updated every frame.

## Visual Result

- When the cursor moves quickly → stronger ripple amplitude.
- When cursor stops → ripples decay.
- Waterline bends opposite the direction of movement.
- Character appears to interact with the water passively as surface shifts around them.

## Design Philosophy

The viewer becomes a “gravitational disturbance,”  
and their presence is expressed visually through water behavior.

Interaction is intentionally limited to amplify subtlety and focus on aesthetics.
