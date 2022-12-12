 # csi_csc770_final-project
csc770 parallel computing final project

-	Ashton.Granata Ashton.Granata@cix.csi.cuny.edu
-	Rifat.Abuelenin@cix.csi.cuny.edu
-	Jia.Lu2@cix.csi.cuny.edu


# This project is built with CSI HPC
- gcc/7.3.0
- openmpi/4.0.1_gnu

# Project Structure


summary :

This paper aims to provide a means for users to efficiently perform FFT of a polynomial over a finite field, 
and discusses ways of parallelizing FFT to reduce the communication overhead.
One of the approaches to parallelize FFT is to perform all butterfly computations in parallel, and to gather the results at the end
of each stage. The issue with this approach is the communication
overhead because at the end of each stage all the processors have
to communicate with each other, and the system will not proceed
to the next stage until all the output from the earlier stage is produced. This is a very good candidate to be implemented in a shared
memory system.
Another approach is to increase the scope of parallelization with
stages, in the first stage only one processor will be active while all
the other available processors are idle. However, the number of
processors used will be increased in the following stages.
In order to reduce the communication overhead, the “Communicate twice” algorithm is used. Since the next processor is aware
of the data that it is waiting for from the earlier processor, it could
perform the same computation that the previous processor is performing and then use the result for its stage computation. Some
processors could be performing similar and repeated computations, but this approach is efficient for fast processor nodes.
This can be implemented using any number of processors. When
we cannot divide the data elements at any stage, then the processor
that was supposed to divide the data set will continue to perform
computations on the entire data set from the previous stage. In this
approach, we map out the entire communication for each stage for
all the processors before beginning to compute the FFT.
Blocking MPI communication was used instead of non-blocking
communication as it will not make any difference in performance

-----------------------------------------------------------------------------------------------------------------------------------

|Parallel |Cooley–Tukey  algorithm For divide and conquer|
|Parallel FFT algorithms include Radix-2,Radix-4, and Split Radix algorithms

| Create skelton project using Fast fourier transform 
| parall performing one subtractionoperation and two adding operations Using Fast fourier transform using signals and frequency .
 

 
6.Basic fast fourier transform Writen with Complex datatype and vector with 2 dimensional array

*Incomplete C
 
 
