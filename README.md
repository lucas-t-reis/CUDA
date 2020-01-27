# CUDA - C/C++

Testing and profiling code with the CUDA API

## Cheat sheet

 * Useful abstraction: threads live on blocks, blocks exist on grids. No thread from different block may interact

 * CUDA programming model has coordinates variables such as
 
 * Nvidia defines uint3 type - essentialy a struct with 3 members: x,y,z - which is returned by most of it's pre-initialized variables

```cpp
// Acessing thread index
threadIdx.x
threadIdx.y
threadIdx.z

// Acessing block index
blockId.x
blockId.y
blockId.z
 
```

 * There is also the type dim3, returned by the following methods

```cpp
// Block dimension (measured in threads)
blockDim.x
blockDim.y
blockDim.z

// Grid dimension (measured in blocks)
gridDim.x
gridDim.y
gridDim.z
```

### DEBUGGING
 * The following macro is useful from wrapping CUDA API calls

 ```cpp
#define CHECK(call) {
 const cudaError_t error = call;
	 if(error != cudaSuccess) {
		 printf("Error: %s:%d, ", __FILE__, __LINE__);
		 printf("code:%d, reason: %s\n", error, cudaGetErrorString(error));
		 exit(1);
	 }
}
```
