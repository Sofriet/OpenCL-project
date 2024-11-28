# OpenCL project from Parallel Computing 2023 (at Radboud)
Optimized heat diffusion code with OpenCL
<br>with Daan Smeets, Daniel Schenk and Anaïs Otting
<br>Feedback:
- Creating a kernel is not expensive, but the simple.h functions for executing them (launch and runKernel) copy the input to the device (and run copies it back too). That is what is expensive.
As you swap after each iteration, in_dev will always have the output, so you should store than into out. There is no need to copy out_dev back.
- Speedup is present, but not nicely presented in a graph. Bandwidth calculations and the roofplot discussion are missing.
- Discussion: Your efficiency numbers seem to suggest something different than what you conclude.

Note: no record of other two projects (optimized code with OpenMP and MPI) from Parallel Computing as I switched groups
