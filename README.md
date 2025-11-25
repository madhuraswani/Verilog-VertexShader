# Verilog-VertexShader

A vertex shader is a programmable unit in the graphics pipeline that processes each vertex individually. It performs operations such as transforming vertex coordinates from object space to screen space using model-view-projection matrices. Additionally, it can calculate per-vertex attributes like color, normals, and texture coordinates.

In hardware design, implementing a vertex shader involves designing a module that takes vertex data as input and applies mathematical transformations to prepare it for the subsequent stages of the pipeline, like rasterization and fragment shading. This Verilog-based vertex shader demonstrates how these computations can be realized in hardware for graphics acceleration.

The top-level module diagram illustrates the structure and data flow within the vertex shader, showing how inputs are processed to produce transformed vertex attributes for rendering. 

## FP16 (16-bit Floating Point)

FP16 (Half-Precision Floating Point) is a 16-bit computer number format that occupies half the space of the standard 32-bit floating point (FP32). It is widely used in applications requiring lower memory bandwidth and faster computations with acceptable precision loss, such as machine learning, graphics, and embedded systems.

The FP16 format typically consists of:
- 1 sign bit
- 5 exponent bits
- 10 fraction (mantissa) bits

FP16 allows representation of a wide range of values but with less precision and dynamic range compared to FP32. It helps reduce storage and computation requirements while maintaining reasonable numeric accuracy for many use cases.

In hardware design and digital signal processing, using FP16 can significantly improve throughput and power efficiency, especially in AI accelerators and GPUs.

## Top-View
![Top-level Diagram of Vertex Shader](.\Images\Architecture_VertexShader.png)

### Basic Blocks
#### FP Multiplier (FP-M)

The FP (Floating Point) Multiplier block performs multiplication of two floating-point numbers according to the IEEE 754 standard (commonly FP16 or FP32 formats).  
Key operations include:
- Multiplying the mantissas (fractional parts)
- Adding the exponents
- Determining the sign of the result
- Normalizing and rounding the final product  
This block is crucial for operations requiring floating-point arithmetic with precision and speed, commonly used in graphics, machine learning, and digital signal processing.

#### FP Adder (FPA)

The FP (Floating Point) Adder block performs addition or subtraction of two floating-point numbers by aligning their exponents first.  
Key steps include:
- Comparing and aligning the exponents
- Adding or subtracting the mantissas based on the sign bits
- Normalizing and rounding the result  
FP adders are essential components for accurate and efficient floating-point arithmetic, widely used in computational hardware blocks and scientific calculations.


