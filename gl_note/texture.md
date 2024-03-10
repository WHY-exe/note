# What is the Texture?

A texture is a 2D image image in essence. It would be mapped to the triangle that shown on the screen when we doing some rendering. 

# Map the texture to a triangle using Sampling

In order to map a texture to a triangle, a vertex should contain the information about which part of the texture it belongs to. Because a texture is a 2D image , each vertex of a triangle could use 2D coordinates to represent some part of the image it wants to sample from. Fragment interpolation then do the rest automaticly for other fragments. The 2D coordinate here is called **texture coordinate,** which ranges from 0 to 1 in x and y axis (usually use (0, 0) to represent lower left corner and (1, 1) to represent the upper right corner) the process to retrive texture color(pixel) using texture coordinates is called **sampling**
