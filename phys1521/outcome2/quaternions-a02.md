---
layout: page
title: Complex Numbers
---
## Introduction
Although not covered in the notes on Moodle, this topic may be of interest for those who want to know more about Quaternions. The original Quaternion, which is not the same as the one we are using for 3D rotations, is a mathematical construct using complex numbers. Complex numbers are a combination of real and imaginary numbers. You may have learned that <img src="https://latex.codecogs.com/svg.image?i=\sqrt{-1}" title="i=\sqrt{-1}" />. So a complex number could be represented as <img src="https://latex.codecogs.com/svg.image?a&plus;bi" title="a+bi" />.

## Complex Number Math
Given two complex numbers <img src="https://latex.codecogs.com/svg.image?a&plus;bi" title="a+bi" /> and <img src="https://latex.codecogs.com/svg.image?c&plus;di" title="c+di" /> then <img src="https://latex.codecogs.com/svg.image?(a&plus;bi)(c&plus;di)=ac&plus;adi&plus;cbi&plus;bdi^2=(ac-bd)(ad&plus;bc)i" title="(a+bi)(c+di)=ac+adi+cbi+bdi^2=(ac-bd)(ad+bc)i" />.

However for the quaternion to work two extra imginary numbers were needed. These were defined as <img src="https://latex.codecogs.com/svg.image?j^2=-1" title="j^2=-1" /> and <img src="https://latex.codecogs.com/svg.image?j^2=-1" title="k^2=-1" />. Using all three imginary numbers we have <img src="https://latex.codecogs.com/svg.image?ijk=-1" title="ijk=-1" />.

### Imaginary Number Math
Given that <img src="https://latex.codecogs.com/svg.image?ijk=-1" title="ijk=-1" /> if both sides of this expression are multipliedn by *i* we get:<br>
<img src="https://latex.codecogs.com/svg.image?iijk=-i" title="iijk=-i" /><br>
<img src="https://latex.codecogs.com/svg.image?i^2jk=-i" title="i^2jk=-i" /><br>
<img src="https://latex.codecogs.com/svg.image?-jk=-i" title="-jk=-i" /> or <br>
<img src="https://latex.codecogs.com/svg.image?jk=i" title="jk=i" />

The same math can be applied to different combinations of multiplying each side of the original expression, <img src="https://latex.codecogs.com/svg.image?ijk=-1" title="ijk=-1" />, to get the results shown in the table below:

|   | i | j | k |
|---| :---: | :---: | :---: |
| i | -1 | k | -j |
| j | -k | -1 | i |
| k | j | -i | -1 |

### Quaternions with Imaginary Numbers
As the origianl Quaternion was a complex number, this section uses that terminology.

Given <img src="https://latex.codecogs.com/svg.image?q_1=a&plus;bi&plus;cj&plus;dk" title="q_1=a+bi+cj+dk" /> and <br>
<img src="https://latex.codecogs.com/svg.image?q_2=e&plus;fi&plus;gj&plus;hk" title="q_2=e+fi+gj+hk" />

Then<br><img src="https://latex.codecogs.com/svg.image?q_1q_2=(a&plus;bi&plus;cj&plus;dk)(e&plus;fi&plus;gj&plus;hk)" title="q_1q_2=(a+bi+cj+dk)(e+fi+gj+hk)" /><br>
<img src="https://latex.codecogs.com/svg.image?q_1q_2=ae&plus;afi&plus;agj&plus;ahk&plus;bei&plus;bfi^2&plus;bgij&plus;bhik&plus;cej&plus;cfji&plus;cgj^2&plus;chjk&plus;dek&plus;dfki&plus;dgkj&plus;dhk^2" title="q_1q_2=ae+afi+agj+ahk+bei+bfi^2+bgij+bhik+cej+cfji+cgj^2+chjk+dek+dfki+dgkj+dhk^2" />

Substituting using the values of multiplying two imaginary numbers from the table above gives:<br> 
<img src="https://latex.codecogs.com/svg.image?q_1q_2=ae&plus;afi&plus;agi&plus;ahk&plus;bei-bf&plus;bgk-bhj&plus;cej-cfk-cg&plus;chi&plus;dek&plus;dfj-dgi-dh" title="q_1q_2=ae+afi+agi+ahk+bei-bf+bgk-bhj+cej-cfk-cg+chi+dek+dfj-dgi-dh" />

Collecting all the like terms to get:<br>
<img src="https://latex.codecogs.com/svg.image?q_1q_2=[ae&plus;bf-cg-dh,(af&plus;be&plus;ch-dg)i,(ag-bh&plus;ce&plus;df)j,(ah&plus;bg-cf&plus;de)k]" title="q_1q_2=[ae+bf-cg-dh,(af+be+ch-dg)i,(ag-bh+ce+df)j,(ah+bg-cf+de)k]" />

If the order of the multiplication is reveresed it can be shown that <img src="https://latex.codecogs.com/svg.image?q_1q_2\neq{q_2q_1}" title="q_1q_2\neq{q_2q_1}" />. However, the following is true:<br>
<img src="https://latex.codecogs.com/svg.image?(q_1q_2)q_3=q_1(q_2q_3)" title="(q_1q_2)q_3=q_1(q_2q_3)" />

## Rlationship to 3D Rotation Quaternions
Given <img src="https://latex.codecogs.com/svg.image?q_1=(a,bi,cj,dk)" title="q_1=(a,bi,cj,dk)" /> then *a* is the scalar (real) portion of the quaternion or <img src="https://latex.codecogs.com/svg.image?a\approx{w}" title="a\approx{w}" />. Then it can be said that the vector (imaginary) component <img src="https://latex.codecogs.com/svg.image?(bi,cj,dk)\approx{(x,y,z)}" title="(bi,cj,dk)\approx{(x,y,z)}" />.

## Exercises & Assignments
There are no exercises or assignments associated with this Addendum.

##### [Outcome Home](index.md)
### [PHYS1521 Home](../)