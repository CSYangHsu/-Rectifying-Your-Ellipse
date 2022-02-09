# Rectifying-Your-Ellipse
In the former project ["Perfecting-Your-Drawing"](https://github.com/CSYangHsu/Perfecting-Your-Drawing),i fitted the ellipses using the quadratic form (1): "a x^2 + b xy + c x^2 y + d x + e y = 1"   
This approaches has many drawbacks. In this project, i will find the standard form of the ellipse best approxmating to the drawing with two new algorithms. 

## Problems
- the quadratic form is not only for ellipse. It is for all kinds of conic sections, including circle, ellipse, parabola, and hyperbola. How to tell the shape of the drawing? 
- the quadratic form is not the standard ellipse we are familar with, as shown in Figure 1. From the coefficients in general quadratic form, we do not know what the parameters of the ellipse, such as the width and the height.
![fig1](https://user-images.githubusercontent.com/86723888/153245803-e36aa976-436e-48ef-80dd-c977fc2742ba.png)

## Table of Contents
* [Algorithm 1: quadratic formulation](#quadratic-formulation)
* [Algorithm 2: PCA](#PCA)
* [DEMO](#DEMO)

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

## DEMO
- example1:  
<img width="50" alt="bean" src="https://user-images.githubusercontent.com/86723888/153259615-04a469ec-aead-4091-8f96-0161f942fcaa.png">     
  
algorithm1　　　　　　　　　　　　algorithm2　　　　　　　　　　　　compare    
![beam1](https://user-images.githubusercontent.com/86723888/153259724-355241fe-49f8-42bf-a79e-1b3ee29a80a2.png)![beams2](https://user-images.githubusercontent.com/86723888/153259820-65cd9f69-7ea3-4a20-b9f9-3b9b143733f1.png)![beamscmp](https://user-images.githubusercontent.com/86723888/153261158-56d7245e-09a6-40a4-b69d-8077f3326ed6.png)







- example2:  
![eclipse-1](https://user-images.githubusercontent.com/86723888/153258073-e2b36170-25c8-4d86-ae45-030328637a9d.png)
  
algorithm1　　　　　　　　　　　　algorithm2　　　　　　　　　　　　compare 
![ex21](https://user-images.githubusercontent.com/86723888/153261704-cbf4dc42-a410-48c4-82f1-d82a84819c9c.png)![ex22](https://user-images.githubusercontent.com/86723888/153261698-a12e3356-0ac7-4543-b7e4-ae2e8582f222.png)![ex23](https://user-images.githubusercontent.com/86723888/153261703-c06f8c66-176d-48fa-bb43-78032ac57b53.png)






- example3:  
![eclipse-2](https://user-images.githubusercontent.com/86723888/153258150-f02953db-b1fc-4c35-9e66-e5ef944e2688.png)

- example4:  
![eclipse-3](https://user-images.githubusercontent.com/86723888/153258173-14bd076d-6693-4890-a252-10754af41d9b.png)

