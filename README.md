# CUDA - C/C++

Testing and profiling code with the CUDA API

## Cheat sheet

 * Useful abstraction: threads live on blocks, blocks exist on grids. No thread from different block may interact

 * CUDA programming model has coordinates variables such as
 
 * Nvidia defines uint3 type - essentialy a struct with 3 members: x,y,z - which is returned by most of it's pre-initialized variables

### Thread Id's
 ```
 threadIdx.x
 threadIdx.y
 threadIdx.z
 ```

### Block Id's
```
blockId.x
blockId.y
blockId.z
```

 * There is also the type dim3, returned by the following methods

### Block dimension (measured in threads)
```
blockDim.x
blockDim.y
blockDim.z

```
### Grid dimension (measured in blocks)
```
gridDim.x
gridDim.y
gridDim.z
```
