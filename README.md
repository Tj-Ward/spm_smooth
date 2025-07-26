# SPM based smoothing function

A python implementation of the SPM smoothing function for nibabel compatible imaging data. 

The idea is that replacing the NaNs by zeros introduces an error in the filtered array which can, however, be compensated by applying the same Gaussian filter to another auxiliary array and combining the two. '''

This implementation preserves detail around the edges of an image. There are valid reasons to criticize the method, so only use edge preservation if you can explain why you are using it. 

Enjoy!
-Tyler J. Ward

import spm_smooth from this file
If you do not specify an output path, it will return a smoothed nibabel image
If you do specity an output path, it will save it to that path and not retun anything

