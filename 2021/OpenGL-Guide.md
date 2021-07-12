# The CSCI 1230 Guide to OpenGL

OpenGL, the best graphics library this side of the Mississippi (which actually means the whole world, if you’re hip to geometric topology). This guide will guide you through the guiding principles of OpenGL. That’s a lot of guide. It is organized by topic, and in each topic we order each subtopic by a plausible chronology of use. If you can’t find something, use <kbd>Control</kbd>+<kbd>F</kbd> or <kbd>Command &#8984;</kbd>+<kbd>F</kbd>. If you still can’t find it, contact a TA and tell us what we missed.

## Table of Contents

- [The CSCI 1230 Guide to OpenGL](#the-csci-1230-guide-to-opengl)
  - [Table of Contents](#table-of-contents)
  - [Vertex Buffer Objects (VBOs)](#vertex-buffer-objects-vbos)
    - [Create a VBO ID](#create-a-vbo-id)
    - [Generate a VBO](#generate-a-vbo)
    - [Storing Data in a VBO](#storing-data-in-a-vbo)
      - [Binding a VBO](#binding-a-vbo)
      - [Buffering Data](#buffering-data)
      - [Unbinding a Buffer](#unbinding-a-buffer)
    - [Deleting a Vertex Buffer Object](#deleting-a-vertex-buffer-object)
    - [Full Example of Using Vertex Buffer Objects](#full-example-of-using-vertex-buffer-objects)
  - [Vertex Array Objects (VAOs)](#vertex-array-objects-vaos)
    - [Create a Vertex Array Object ID](#create-a-vertex-array-object-id)
    - [Generate a Vertex Array Object](#generate-a-vertex-array-object)
    - [Using a Vertex Array Object](#using-a-vertex-array-object)
      - [Binding a Vertex Array Object](#binding-a-vertex-array-object)
      - [Enabling Array Access](#enabling-array-access)
      - [Specifying the structure of a VBO with a VAO:](#specifying-the-structure-of-a-vbo-with-a-vao)
      - [Unbinding a Vertex Array Object](#unbinding-a-vertex-array-object)
      - [Deleting a Vertex Array Object](#deleting-a-vertex-array-object)
  - [Shaders](#shaders)
    - [How To Get a Shader Into Your Code](#how-to-get-a-shader-into-your-code)
      - [Create a Shader Object](#create-a-shader-object)
      - [Add Code To Shader Object:](#add-code-to-shader-object)
      - [Compile the Shader Object](#compile-the-shader-object)
      - [Create A Program Object](#create-a-program-object)
  - [Miscellaneous Important Calls](#miscellaneous-important-calls)
    - [Depth Culling](#depth-culling)
    - [Enabling and Disabling built-in OpenGL Features](#enabling-and-disabling-built-in-opengl-features)

## Vertex Buffer Objects (VBOs)

Vertex Buffer Objects (VBOs) are OpenGL’s way of storing geometry data. VBOs are referenced by VBO IDs that can be generated using OpenGL. Every object that you wish to render will eventually have to have its geometry stored in a VBO, so you really should spend some time getting to know these objects well.

### Create a VBO ID

In order to create a VBO, we need a way to store a reference to it. This is done using a VBO ID. All VBO IDs are of type `GLuint`, which is a GL-unsigned-int. Generally we make this GLuint a member variable so we can access it in multiple methods. This ID is the way we reference and access the VBO. Sometimes, this ID id is called the VBO name, but it is still the same GLuint.

To store a VBO ID, we need to create a variable of type `GLuint`

**Example Code**
```C++
// Create a variable to store our VBO ID
GLuint vboID;
```


### Generate a VBO

We have a variable to store the VBO ID, but that variable is currently uninitialized (which is bad). To initialize it, we need to generate a VBO and store that VBO's ID in our variable. The OpenGL function `glGenBuffers` does exactly that for us. This command will generate 1 or more VBOs and store the IDs to access them in `vboID`, which is a variable of type `GLuint` that you should have made previously.

**Function Definition**
```C++
void glGenBuffers(GLsizei n, GLuint * buffers);
```
*Parameters*  
`GLSizei n`: The number of vertex buffer objects to generate  
`GLuint * buffers`: A pointer to the `GLuint` variable in which to store the newly generated VBO's ID (or an array of `GLuint`s if generating multiple VBOs)

**Example Code**
```C++
// Create a variable to store our VBO ID
GLuint vboID;
// Generate the VBO and store the VBO's ID in vboID
glGenBuffers(1, &vboID);
```
```C++
// Create an array to hold three VBO IDs
GLuint[3] vboIDArray;
// Generate the VBOs and store one ID per position in the array
glGenBuffers(3, &vboIDArray);
```

### Storing Data in a VBO

An empty VBO doesn't do us much good, so we need to fill it with data. Storing data in a VBO takes three commands: you have to bind the buffer, buffer the data, and then finally unbind the buffer. We go over each command below.

#### Binding a VBO

In order to use the VBO, we must first bind the vertex buffer object to a *buffer binding target*. You can think of this target as a global variable inside of OpenGL that can hold a reference to a single object. By binding the VBO ID to a target, you are assigning the buffer to that specific target so that subsequent OpenGL function calls will operate on the buffer you want (the one you bound to the target). We can use the general purpose OpenGL buffer binding function to do this.

**Function Definition**
```C++
void glBindBuffer(GLenum target, GLuint buffer);
```
*Parameters*  
`GLenum target`: Specifies the buffer binding target to which the buffer object should be bound.  
`GLuint buffer`: The buffer object that we wish to bind to the specified target. This will usually be your VBO ID.

**Example Code**
```C++
// Create a variable to store our VBO ID
GLuint vboID;
// Generate the VBO and store the VBO's ID in our variable vboID
glGenBuffers(1, &vboID);
// Bind our VBO to the OpenGL Array Buffer
glBindBuffer(GL_ARRAY_BUFFER, vboID);
```

#### Buffering Data

Now that OpenGL has our buffer bound, we have to send the data over to the buffer itself. We do this using the general purpose OpenGL buffering function, `glBufferData`.  

**Function Definition**
```C++
void glBufferData(GLenum target, GLsizeiptr size, const GLvoid * data, GLenum usage);
```

*Parameters*  
`GLenum target`: Specifies the buffer binding target to which the data should be sent.  
`GLsizeiptr size`: The size in bytes of the data you whish to send to the buffer. Since you specify this, you could send as much or as little data from your source as you want. Be sure that you don't pass in a size greater than the size of your data (or else bad things will happen).  
`const GLvoid * data`: A pointer to the data you want to send to be stored in the buffer. Notice that it is marked `const` so we know that the data won't be changed.  
`GLenum usage`: Specifies the expected usage pattern of the data store. Generally should be `GL_STATIC_DRAW`. The STATIC means the data in the buffer will only be altered once, and used many times. The DRAW means the data is used as the source for GL drawing and image specification commands. See [the OpenGL docs here](https://www.opengl.org/sdk/docs/man/html/glBufferData.xhtml) for more info on other cool usage specifications, like `GL_DYNAMIC_DRAW`.  

**Example Code**
```C++
// Create some data, which in this case is a set of verticies for a triangle
float[] vertexData = {1.0, 0.0, 1.0,
                      0.5, 1.0, 1.0,
                      0.0, 0.0, 1.0}

// With a buffer already bound to GL_ARRAY_BUFFER, send the data over to the buffer
// Note that since vertexData is an array, it will be passed as a pointer to glBufferData
glBufferData(GL_ARRAY_BUFFER, 9*sizeof(float), vertexData, GL_STATIC_DRAW);
```

#### Unbinding a Buffer

It is considered good practice to leave OpenGL in it's original state when we're done working with it, so when we're done using a buffer we need to unbind it. OpenGL doesn't have an unbind buffer function, so instead we bind the buffer we were just using to `0` to indicate that nothing is bound. To do this, we use the same `glBindBuffer` function as before.

**Example Code**
```C++
// Unbind the GL_ARRAY_BUFFER that we were just using
glBindBuffer(GL_ARRAY_BUFFER, 0);
```

### Deleting a Vertex Buffer Object

Like everything else in C and C++, you have to delete a buffer object when you are done using it to avoid causing memory leaks. This is easily done using `glDeleteBuffers`, which works just like `glGenBuffers` but in reverse, deleting buffers that were previously created using `glGenBuffers`.

**Function Definition**
```C++
void glDeleteBuffers(GLsizei n, const GLuint * buffers);
```
*Parameters*  
`GLSizei n`: The number of vertex buffer objects to delete  
`GLuint * buffers`: A pointer to the `GLuint` variable that stores the VBO's ID (or an array of `GLuint`s if deleting multiple VBOs)

**Example Code**
```C++
// Delete the buffer that has its ID stored in our variable vboID
glDeleteBuffers(1, &vboID);
```
```C++
// Delete the buffers that have their IDs stored in our array vboIDArray
glDeleteBuffers(3, &vboIDArray);
```

### Full Example of Using Vertex Buffer Objects

Putting it all together, this code demonstrates the whole process of creating, using, and deleting a vertex buffer object.

```C++
// Create a variable to hold our VBO ID
GLuint vboID;

// Generate a VBO and store the ID in our variable
glGenBuffers(1, &vboID);

// Bind our VBO to the GL_ARRAY_BUFFER
glBindBuffer(GL_ARRAY_BUFFER, vboID);

// Send some data over to the GL_ARRAY_BUFFER, which currently has our VBO bound to it
float[] data = {0.5, 1.0, 0.0, 0.0, 0.5, 0.0, 0.0, 0.0, 0.0} // Made up example data
glBufferData(GL_ARRAY_BUFFER, 9*sizeof(float), data, GL_STATIC_DRAW);

// Unbind our VBO
glBindBuffer(GL_ARRAY_BUFFER, 0);

// Delete our VBO since we are done using it
glDeleteBuffers(1, &vboID);
```


## Vertex Array Objects (VAOs)

A Vertex Array Object (VAO) specifies how the data stored in a VBO is to be read by the vertex shader. Using a VAO is optional but recommended as VAOs greatly simplify your program logic. When you create and bind a VAO, that VAO will remember all of the function calls you make to describe the structure of your data to OpenGL. That way, all you have to do later is rebind the VAO and OpenGL will already know all about your data without you having to tell it twice.

### Create a Vertex Array Object ID

Just like vertex buffer objects, all vertex array objects are referenced by their ID. That ID is just a `GLuint`, again just like VBOs.

**Example Code**
```C++
// Create a variable to store our VAO ID
GLuint vaoID;
```

### Generate a Vertex Array Object

Again, just like a vertex buffer object, we need to tell OpenGL to generate a vertex array object for us. This is done using `glGenVertexArrays`.

**Function Definition**
```C++
void glGenVertexArrays(GLsizei n, GLuint * buffers);
```
*Parameters*  
`GLSizei n`: The number of vertex array objects to generate  
`GLuint * arrays`: A pointer to the `GLuint` variable in which to store the newly generated VAO's ID (or an array of `GLuint`s if generating multiple VAOs)

**Example Code**
```C++
// Create a variable to store our VAO ID
GLuint vaoID;
// Generate the vertex array object and store the VAO's ID in vaoID
glGenVertexArrays(1, &vaoID);
```
```C++
// Create an array to hold three VAO IDs
GLuint[3] vaoIDArray;
// Generate the VAOs and store one ID per position in the array
glGenVertexArrays(3, &vaoIDArray);
```


### Using a Vertex Array Object

To use a vertex array object, you need to first bind the VAO and then make a series of calls that OpenGL will remember and reapply next time you bind the VAO. Finally, when you are done describing your data, you unbind the VAO. This is what makes VAOs useful: you only have to describe your data once while the VAO is bound, and then next time you bind the VAO OpenGL will already know all about your data. First, we list some functions. Then, we will go over them in detail below.

1. `glBindVertexArray(m_vaoID);`
2. `glEnableVertexAttribArray(index);`
3. `glBindBuffer(GL_ARRAY_BUFFER, vboID);` Note: This is the same VBO command covered in the VBO section
4. `glVertexAttribPointer(index, size, type, normalized, stride, (void*) pointer);`
5. `glBindBuffer(GL_ARRAY_BUFFER, 0);` Note: This is the same VBO command covered in the VBO section
6. `glBindVertexArray(0);`


#### Binding a Vertex Array Object

To use a VAO, you first have to bind it. Note that there isn't a target parameter for VAOs like vertex buffer objects have. Thus you can only have one vertex array object bound at a time. To bind a VAO, we use `glBindVertexArray`.

**Function Definition**
```C++
void glBindVertexArray(GLuint id);
```
*Parameters*  
`GLuint id`: The ID of the vertex array object we wish to bind

**Example Code**
```C++
// Create a variable to store our VAO ID
GLuint vaoID;
// Generate the vertex array object and store the VAO's ID in vaoID
glGenVertexArrays(1, &vaoID);
// Bind the VAO
glBindVertexArray(vaoID);
```


#### Enabling Array Access

Initially array access is denied for all attributes in a newly created VAO. Access to any attributes must be manually enabled. We do this using `glEnableVertexAttribArray`.

**Function Definition**
```C++
void glEnableVertexAttribArray(GLuint index);
```
*Parameters*  
`GLuint index`: The index of the generic vertex array attribute to be enabled

**Example Code**
```C++
glEnableVertexAttribArray(0);
```
#### Specifying the structure of a VBO with a VAO:

VBOs have structure. Structure in this case means a structured ordering of data. Are all the positions stored, then all the normals, then all the texture coordinates? Is everything interleaved? To tell the program the answer, we use a VAO. 
To specify the structure of the VBO, we first must bind the VBO we went to specify to  `GL_ARRAY_BUFFER`. Then we call the following command.

**Function Definition**
```C++
void glVertexAttribPointer(GLuint index, GLint size, GLenum type, GLboolean normalized, GLsizei stride, const void *offset);
```

*Parameters*  
`GLuint index`: the index of the generic vertex attribute to be modified.  
`GLint size`: the number of components per generic vertex attribute. Must be 1, 2, 3, 4. (also the symbolic constant `GL_BGRA` is accepted)  
`GLenum type`: the data type of each component in the array. In this class we generally use `GL_FLOAT`, but you also could use `GL_BYTE`, `GL_SHORT`, `GL_INT`, or `GL_DOUBLE`. The initial value is `GL_FLOAT`.  
`GLboolean normalized`: whether fixed-point data values should be normalized (`GL_TRUE`) or converted directly as fixed-point values (`GL_FALSE`) when they are accessed.  
`GLsizei stride`: the byte offset between consecutive generic vertex attributes. If stride is 0, the generic vertex attributes are understood to be tightly packed in the array. The initial value is 0.  
`const void *pointer`: offset of the first component of the first generic vertex attribute in the array in the data store of the buffer currently bound to the `GL_ARRAY_BUFFER` target. The initial value is 0.

**Example Code** 
```C++
glVertexAttribPointer(0, 3, GL_FLOAT, GL_FALSE, 0, 0);
```

#### Unbinding a Vertex Array Object
	
After using our VAO, we want to unbind it, as a matter of good housekeeping, to prevent accidental uses of our VAO. To do this we bind a vertex array with index 0. 

**Example Code**
```C++
glBindVertexArray(0);
```

#### Deleting a Vertex Array Object

After we are sure we never want to use this VAO again, we need to delete it. The procedure to do this is quite like that for a VBO.

**Function Definition**
```C++
glDeleteVertexArrays(GLsizei n, GLuint *arrays);
```

*Parameters*
`GLsizei n`: number of VAOs to delete
`GLuint *arrays`: either the address of an ID of a single VAO to delete or the address of an array of IDs to delete.

**Example Code**
```C++
glDeleteVertexArrays(1, &vaoID);
glDeleteVertexArrays(3, &vaoIDArray);
```

## Shaders

A Shader is a user-defined program designed to run on some stage of a graphics processor. With OpenGL, shaders are written in GLSL, a C-like language. A shader is a separate file called by our program. All OpenGL programs must have at least 2 shaders: a vertex shader, and a fragment shader. Although these files can have any file extension, we use .vert and .frag in this class to keep things organized.

### How To Get a Shader Into Your Code

So say you have a neat shader and you want to use it in your project, there are a couple steps you need to go through to get everything set up. Here’s an overview.

1. Create a shader object.
2. Give that object the code inside your shader file.
3. Compile that shader object.
4. Create a program object.
5. Attach the shader object to the program object.
6. Link the program object.

That seems like a lot of stuff, but really it’s not that bad, and is a relatively conserved process between different graphics projects. So learn to do it once, be able to do it 100 times.

Now let’s look at each step in detail.

#### Create a Shader Object

This command creates a shader object and returns a GLuint that will be the ID for the created shader.

**Function Definition**
```C++
GLuint shaderID; 
glCreateShader(GLenum shaderType);
```
*Parameters*  
//yes I know this technically isn’t an argument, but it needed to be explained, and this was the most relavent section to explain it in  
`GLuint shaderID`: ID of created shader 
`GLenum shaderType`: the type of shader. Must be one of these: `GL_VERTEX_SHADER`, `GL_TESS_CONTROL_SHADER`, `GL_TESS_EVALUATION_SHADER`, `GL_GEOMETRY_SHADER`, `GL_FRAGMENT_SHADER`, or `GL_COMPUTE_SHADER`.

**Example Code**
```C++
GLuint shaderID; 
glCreateShader(GL_VERTEX_SHADER);
```
#### Add Code To Shader Object:

This command will put the GLSL code we wrote for our shader into the shader object. The code we want must be stored in a string array, and preferably null terminated. We recommend using the .c_str() command to make sure the string array is null terminated. 

**Function Definition**
```C++
void glShaderSource​(GLuint shader, GLsizei count, const GLchar **string, const GLint *length);
```

*Parameters*  
`GLuint shader`: ID of shader object  
`GLsizei count`: the number of individual strings in string  
`const GLchar **string`: array of strings that store the code to add to the shader object  
`const GLint *length`: array of lengths for each string in `string`  
**NOTE**: length can be NULL if all the strings have null endings. If length is set to null, the program will try to automatically find the length of the strings by searching for null endings.

**Example Code**
```C++
glShaderSource(vertexShader, 1, &source, NULL);
```

#### Compile the Shader Object

The `glCompileShader` function compiles the shader object. 

**Example Code**
```C++
glCompileShader(shaderID);
```

#### Create A Program Object

The `glCreateProgram` function creates a program object.
	
**Example Code**
```C++
GLuint programID = glCreateProgram();
```

## Miscellaneous Important Calls

Whew, that was a lot. All done, right? Not quite! There are still a few important calls that don’t fit exactly into any of the above categories, but still need to be explained. 

### Depth Culling
	
When rendering pixels, its a waste render pixels that are occluded, or behind other pixels. OpenGL gives you a method to not render occluded pixels, and it uses something called the depth buffer. Basically, the depth buffer records the closest pixel at each location. When a new pixel is spit out by the fragment shader, OpenGL will check to see if it’s closer than the current best. If it is, it renders it. If it’s not, it tosses it. Also, it’s simple to turn on!

**Example Code**
```C++
glDepthMask(GL_TRUE);
glEnable(GL_DEPTH_TEST);
glClear(GL_DEPTH_BUFFER_BIT);
```

So what’s going on here. The first call turns on writing to the depth buffer. The second call turns on using the depth buffer to perform depth culling, and the final call clears the default value of the depth buffer, which is stupidly intitally set to 0, which is the closest value, meaning no future values will ever be closer. If you forget to clear the buffer, the screen will be all black, and you will be confused, and it will make you unhappy.

### Enabling and Disabling built-in OpenGL Features

OpenGL has a lot of built in features that can speed-up or visually improve your work. We already saw GL_DEPTH_TEST, which helps limits the number of occluded pixels rendered, or GL_MULTISAMPLE, which uses multiple fragment samples to generate a pixel color. See here for a full list and their descriptions. 

**Function Definition**
```C++
glEnable(GLenum cap);
glDisable(GLenum cap);
```

*Parameters*
```GLenum cap```: symbolic constant representing an OpenGL capability.

**Example Code**
```C++
glEnable(GL_MULTISAMPLE);
glDisable(GL_MULTISAMPLE);
```

