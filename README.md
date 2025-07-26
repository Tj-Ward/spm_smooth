# SPM based smoothing function

 Ported spm_smooth into Python3!
 
 Credit goes to the SPM team for their design.

 WHY? scipy has a gaussian smooth implementation which works well but that implementation is different, it does not use 1st degree B-spline interpolation. When I discovered the difference, I could not find python implementations so I ported the matlab ode. 

 Identical to SPM12 spm_smooth as of 10-21-2021 except the addition of edge-preservation option and you can return the nibabel image rather than having to save the output to a file.

 Method for edge preservation inspired by https://stackoverflow.com/a/36307291/7128154
 
 Quoting the author of the edge preservation method: 
 
> '''A Gaussian filter which ignores NaNs in a given array U can be easily obtained by applying a standard Gaussian filter to two auxiliary arrays V and W and by taking the ratio of the two to get the result Z.

> Here, V is copy of the original U with NaNs replaced by zeros and W is an array of ones with zeros indicating the positions of NaNs in the original U.
 
> The idea is that replacing the NaNs by zeros introduces an error in the filtered array which can, however, be compensated by applying the same Gaussian filter to another auxiliary array and combining the two. '''


 This implementation preserves detail around the edges of an image. There are valid reasons to criticize the method, so only use edge preservation if you can explain why you are using it. 

 
 import spm_smooth from this file
 
 If you do not specify an output path, it will return a smoothed nibabel image

 If you do specity an output path, it will save it to that path and not retun anything
