# Rectifying-Your-Ellipse
In the former project "Perfecting-Your-Drawing", i fitted the ellipses using the general quadratic form,  
                    "a x^2  + b xy + c x^2 y + d x + e y  =  1"--(1)    
This approaches has many drawbacks. In this project, i will find the standard form of the ellipse best approxmating to the drawing with two new algorithms. 

## Problems
- the quadratic form is not only for ellipse. It is for all kinds of conic sections, including circle, ellipse, parabola, and hyperbola. How to tell the shape of the drawing? 
- the quadratic form is not the standard ellipse we are familar with, as shown in Figure 1. From the coefficients in general quadratic form, we do not know what the parameters of the ellipse, such as the width and the height.
![fig1](https://user-images.githubusercontent.com/86723888/153245803-e36aa976-436e-48ef-80dd-c977fc2742ba.png)

## Algorithms
* [quadratic formulation](#quadratic-formulation)
* [PCA](#PCA)

## quadratic-formulation
![alg1](https://user-images.githubusercontent.com/86723888/153251265-cc20161d-68c7-4a1b-a09b-884f7100fbe8.png)


## PCA
The basic idea is to translate and rotate them into the standard ellipse. The first step is to find the center of those points, which is the mean, and then translate them so the center will be the new origin. The second step is to form a special matrix, called "covariant matrix".  

![alg2](https://user-images.githubusercontent.com/86723888/153251384-212ebb0c-2a33-44bb-8754-0a7be3a7aabd.png)

The last step is to express the fitted ellipse back into the general quadratic
form, as in (1). Since we already know the translation and rotation, we can
reverse the process.  
  
Let ![螢幕擷取畫面 2022-02-10 010526](https://user-images.githubusercontent.com/86723888/153252115-2915e2f9-218f-4e9f-b137-5b39efdb9407.png)  

S = U * Σ * U^T  be the eigen-decomposition of the covariant matrix, and ( ¯x¯, ¯y¯) be
the center of data. The quadratic form that fits the original data will be  
![螢幕擷取畫面 2022-02-10 010916](https://user-images.githubusercontent.com/86723888/153252789-9cb88326-ffa2-41e3-842a-a342f653e2a1.png)  

After expanding the above equation, we can have the general quadratic form.
