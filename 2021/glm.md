GLM Reference Doc
=================

GLM (OpenGL Mathematics) is a C++ library that replicates much of the mathematics functionality of GLSL. Nearly all types and functions in the GLM core are identical to their equivalents in GLSL in terms of naming conventions and behavior (although there are a few differences), making it particularly easy to use alongside GLSL.


GLM Headers
-----------
The header file `glm/glm.hpp` includes the entire GLM core. If you only need certain features, they can be found in the following headers.

* **glm/vec2.hpp**, **glm/vec3.hpp**, **glm/vec4.hpp**: GLSL's vector types.

* **glm/mat2x2.hpp**, **glm/mat2x3.hpp**, **glm/mat2x4.hpp**, **glm/mat3x2.hpp**, **glm/mat3x3.hpp**, **glm/mat3x4.hpp**, **glm/mat4x2.hpp**, **glm/mat4x3.hpp**, **glm/mat4x4.hpp**: GLSL's matrix types. Note that while the GLSL type for a square 2x2 matrix (for example) is `mat2`, the corresponding GLM header name is `mat2x2.hpp`. Once the type has been included, however, `glm::mat2` can still be used as an alias.

* **glm/common.hpp**: GLSL's common functions, including `min()`, `max()`, `abs()`, `mod()`, `floor()`, `ceil()`, `clamp()`, etc. These functions operate component-wise on vectors.

* **glm/exponential.hpp**: GLSL's exponential functions, including `exp()`, `log()`, `sqrt()`, `pow()`, etc. These functions operate component-wise on vectors.

* **glm/integer.hpp**: GLSL's integer functions.

* **glm/matrix.hpp**: GLSL's matrix functions, including `transpose()`, `inverse()`, and `determinant()`.

* **glm/packing.hpp**: GLSL's packing functions, which can convert between vectors and numeric types.

* **glm/trigonometric.hpp**: GLSL's trig functions, including `sin()`, `asin()`, `sinh()`, and the equivalents for cos and tan, as well as the conversion functions `degrees()` and `radians()`. These functions operate component-wise on vectors, and all except `radians()` expect their arguments to be in radians.

* **glm/vector_relational.hpp**: GLSL's vector comparison functions. Most of these, such as `lessThan()` and `greaterThanEqual()`, take two vectors of the same length and return a boolean vector (`bvec`) of the same length containing the results of each comparison. `not()` inverts a `bvec`, and `any()` and `all()` are used to obtain bools from `bvec`s.

Full GLM core documentation can be found here: http://glm.g-truc.net/0.9.7/api/a00162.html

GTC and GTX
-----------
GTC and GTX contain stable (GTC) and experimental (GTX) extensions to GLM that add functionality beyond what exists in GLSL. There are a number of extensions, but some of the most useful for this course are:

* **glm/gtx/transform.hpp**: Contains the functions `translate()`, `rotate()`, and `scale()`, for constructing standard 4x4 transformation matrices. `translate()` and `scale()` each accept a `vec3` containing the amount of translation/scaling in all three dimensions, while `rotate()` accepts an angle in radians and a `vec3` to use as the axis of rotation.

* **glm/gtc/constants.hpp**: Contains a number of useful mathematical constants, such as `pi()` and `root_two()`.

* **glm/gtc/type_ptr.hpp**: Contains the `value_ptr()` function, which returns a pointer to the start of a vector or matrix’s data (see the “Passing GLM Types to GLSL” section below). Also contains a number of functions such as `make_mat2x4()` that construct the specified type from a value pointer.

Documentation for all extensions can be found here: http://glm.g-truc.net/0.9.7/api/a00160.html (GTC) and here: http://glm.g-truc.net/0.9.7/api/a00161.html (GTX)

Swizzle Functions
-----------
GLM supports vector swizzling, as in GLSL, but the behavior here is slightly different. In GLSL, both of the following lines accomplish the same thing (switching the x and y components), where v1 and v2 are `vec2`s:

    v2 = v1.yx;
    v2.yx = v1;
In GLM, swizzling is handled by functions, so you must make sure to include the parentheses. The functions return a new vector without modifying the old one, so they will not work on the left-hand side of assignments:

    v2 = v1.yx(); //same result as in GLSL
    v2.yx() = v1; //does nothing
To enable swizzle functions, you must `#define GLM_SWIZZLE` before any GLM includes.


Passing GLM Types to GLSL
-----------
GLM vectors and matrices can easily be passed to shaders via the corresponding glUniform function: `glUniform4fv()` for a `vec4`, `glUniformMatrix2x3fv()` for a `mat2x3`, etc. For the value pointer parameter, you need a pointer to the start of the vector or matrix data, which can be obtained by dereferencing the first element of the vector or matrix, like so:

    glUniformMatrix3fv(location, 1, GL_FALSE, &matrix[0][0]);

Alternatively, you can use `value_ptr()`, found in `glm/gtc/type_ptr.hpp`, which accomplishes the same thing:

    glUniformMatrix3fv(location, 1, GL_FALSE, glm::value_ptr(matrix));