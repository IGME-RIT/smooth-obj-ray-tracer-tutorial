Documentation Author: Niko Procopi 2019

This tutorial was designed for Visual Studio 2017 / 2019
If the solution does not compile, retarget the solution
to a different version of the Windows SDK. If you do not
have any version of the Windows SDK, it can be installed
from the Visual Studio Installer Tool

Welcome to the Ray Tracing Vertex Normals Tutorial!
Prerequesites: 
	Ray Tracing OBJ Loader, 
	3D Normal Mapping ("More Graphics" section)

In previous OpenGL tutorials, we have the normals interpolated by the
rasterizer, but we cannot use the rasterizer to interpolate our values when
we are using Ray Tracing, because the entire scene is rendered with our
fragment shader. We use the point on the triangle that we are rendering,
(which we get from our hit info), then we use the triangle that the point is
in (which is also from our hit info). With that triangle, we get the points
of the triangle, and the vertex normals of the triangle. Then, we use the 
function GetInterpolatedNormal to get the per-pixel normal. The per-pixel
normal is calculated by using a "Barycentric Coordinates" algorithm. It takes
the 3 points on the triangle, the 3 vertex normals, and the 1 per-pixel point being 
processed, to get the 1 per-pixel normal that we want to use
