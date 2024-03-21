OpenGL Shader Pipeline and Implementation
=========================================

This repository contains the implementation of an OpenGL shader pipeline consisting of a vertex shader and a pixel shader. The shaders are designed to handle texture mapping and blending for rendering 2D & 2.5D graphics.

Shader Files
------------

### Vertex Shader (VertexShaderTex.txt)

The vertex shader (`VertexShaderTex.txt`) performs the following tasks:
- Takes input attributes for vertex position, texture coordinates, and vertex color.
- Calculates the final vertex position in screen space using transformation matrices (world, projection, and view).
- Transforms texture coordinates with a texture matrix for texture mapping.
- Outputs interpolated texture coordinates, vertex color, and blend ratio for the pixel shader.

### Pixel Shader (PixelShaderTex.txt)

The pixel shader (`PixelShaderTex.txt`) performs the following tasks:
- Takes interpolated texture coordinates, vertex color, and blend ratio from the vertex shader.
- Samples the input texture using the interpolated texture coordinates.
- Discards fragments with low alpha values (transparency) to optimize rendering.
- Blends between the sampled texture color and a specified blend color based on the blend ratio.

Pipeline Overview
-----------------

1. **Vertex Shader Input**: 
   - Vertex position (`inPosition`)
   - Texture coordinates (`inTexCoord`)
   - Vertex color (`inColor`)

2. **Vertex Shader Output**:
   - Interpolated texture coordinates (`TexCoord`)
   - Interpolated vertex color (`Color`)
   - Interpolated blend ratio (`blendRatio`)

3. **Pixel Shader Input**:
   - Interpolated texture coordinates (`TexCoord`)
   - Interpolated vertex color (`Color`)
   - Interpolated blend ratio (`blendRatio`)

4. **Pixel Shader Output**:
   - Final pixel color (`pixelColor`)

Usage
-----

To use these shaders in an OpenGL application, follow these steps:

1. Compile and link the shaders with your OpenGL program.
2. Set the necessary uniforms (matrices, textures, blend factors) before rendering.
3. Bind the vertex and pixel shaders during the rendering process.
4. Render your geometry to see the texture mapping and blending effects.

Notes
-----

- Ensure that your OpenGL context supports at least version 3.30 (`#version 330 core`) to use these shaders.
- Adjust the blend factor and blend color uniforms (`blend` and `blendColor`) to achieve desired color blending effects.
- Customize the shaders as needed for specific rendering requirements.

Feel free to explore and modify the shaders to suit your graphics rendering needs.
