Zhang-Suen Thinning Algorithm, Python and Matlab Implementation
================================================
Algorithm Description:
------------------------------------------------
This algorithm is used for thinning binary image. Two steps will be successively applied to the image.  <br/>
Here arrange the eight neighbors of P1 in a clockwise order: <br/>
>    
     P9 P2 P3 
     P8 P1 P4 
     p7 P6 P5 
     
Define N(P1) = the number of non-zore pixel neighbours of P1 ( = sum(P2 .. P9) ) <br/>
Define S(P1) = the number of transitions from 0 to 1, (0 -> 1) in the sequence P2,P3,...,P8,P9,P2. <br/>

### Step 1:<br/>
All pixels are tested and pixels satisfying all the following conditions (simultaneously) are just noted at this stage. After iterating over the image and collecting all the pixels satisfying all step 1 conditions, all these noted pixels are set to 0.<br/>
>   
    Condition 0: The pixel is 1 and has eight neighbours 
    Condition 1: 2 < = N(P1) < = 6 
    Condition 2: S(P1) = 1
    Condition 3: P2 * P4 * P6 = 0 
    Condition 4: P4 * P6 * P8 = 0 

### Step 2:<br/>
All pixels are again tested and pixels satisfying all the following conditions are just noted at this stage. After iterating over the image and collecting all the pixels satisfying all step 2 conditions, all these noted pixels are again set to 0. <br/>
>   
    Condition 0: The pixel is 1 and has eight neighbours 
    Condition 1: 2 < = N(P1) < = 6  
    Condition 2: S(P1) = 1   
    Condition 3: P2 * P4 * P8 = 0   
    Condition 4: P2 * P6 * P8 = 0   

### Iteration:   <br/> 
If any pixels were set in this round of either step 1 or step 2 then all steps are repeated until no image pixels are so changed. The last thing to note for this algorithm is that in each step the deletion of the noted points must be delayed until all the pixels of the image have been visited in order to avoid changing of pixels of the image during each step. <br/> 

### Reference:   <br/> 
Page48-50, "Character Recognition Systems: A Guide for Students and Practitioners" By Mohamed Cheriet, Nawwaf Kharma, Cheng-Lin Liu, Ching Suen <br/> 

Implement Results:
------------------------------------------------
Testing Environment: <br/>
Python 2.7 ([scikit-image](http://scikit-image.org/) + matplotlib) <br/>
Matlab 2012 <br/>
<br/>
![image](https://github.com/linbojin/Skeletonization-by-Zhang-Suen-Thinning-Algorithm/blob/master/results/test1.jpg)
![image](https://github.com/linbojin/Skeletonization-by-Zhang-Suen-Thinning-Algorithm/blob/master/results/test2.jpg)
![image](https://github.com/linbojin/Skeletonization-by-Zhang-Suen-Thinning-Algorithm/blob/master/results/test4.jpg)




