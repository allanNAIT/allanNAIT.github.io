---
layout: page
title: Other Forces - Momentum & Collisions
---
## Introduction
This lesson will include an additional concept related to Linear Mechanics.

## Momentum & Impulse
### Key Concepts
The key concepts for this part of the lesson are:
* Calculations based on Momentum
* Calculations based on Impulse forces

### <a ID="references">References for this lesson</a>
* [Introduction to momentum](https://www.khanacademy.org/science/physics/linear-momentum/momentum-tutorial/v/introduction-to-momentum){:target="_blank"}
* [Momentum: Ice skater throws a ball](https://www.khanacademy.org/science/physics/linear-momentum/momentum-tutorial/v/momentum-ice-skater-throws-a-ball){:target="_blank"}
* [2-dimensional momentum problem](https://www.khanacademy.org/science/physics/linear-momentum/momentum-tutorial/v/2-dimensional-momentum-problem){:target="_blank"}
* [2-dimensional momentum problem (part 2)](https://www.khanacademy.org/science/physics/linear-momentum/momentum-tutorial/v/2-dimensional-momentum-problem-part-2){:target="_blank"}
* [Fast, Accurate Collision Detection Between Circles or Spheres](https://www.gamasutra.com/view/feature/131424/pool_hall_lessons_fast_accurate_.php?page=3){:target="_blank"}

### Lesson
Which object, a 1000kg car or a 5000kg truck, both travelling at the same speed, will come to a stop once their respective drivers stop pressing the accelerator pedals (assuming both at the same time, and both having the same friction on the road surface). The answer should be that the truck will take longer to slow to a complete stop. The reason is that the truck has a larger momentum. Using Newton’s First Law, <img src="https://latex.codecogs.com/svg.latex?\large&space;F=mA"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;V=A\Delta{t}"/>, the equation of Momentum is derived as follows:

<img src="https://latex.codecogs.com/svg.latex?\large&space;A=\frac{F}{m}"/>

Substitute this into the velocity equation

<img src="https://latex.codecogs.com/svg.latex?\large&space;V=\frac{F}{m}\Delta{t}"/>

Now some simple algrbraic rearranging

<img src="https://latex.codecogs.com/svg.latex?\large&space;mV=F\Delta{t}=P"/>

The units of momentum can be expressed as _kg∙m/s_ or _N∙s_. It should also be obvious, based on the equations used, that Momentum is a vector quantity; has both magnitude and direction.

Example: Consider the car and truck from the opening lesson statement, both traveling at 60 km/h calculate the momentum of each vehicle and the time it will take each vehicle to come to a complete stop with a braking force of 10N.

<img src="https://latex.codecogs.com/svg.latex?\large&space;\frac{60km}{hr}=\frac{60\times{1000}}{1}\times{\frac{1}{60\times{60}}}=\frac{50}{3}m/s"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;P_{car}=1000\times{\frac{50}{3}}\approx{16666.6667Ns}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;P_{truck}=5000\times{\frac{50}{3}}\approx{83333.333Ns}"/>

Now calculate the time to stop each vehicle:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Delta{t_{car}}=\frac{P_{car}}{F_{brake}}=\frac{\frac{50000}{3}}{10}\approx{1666.6667s}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Delta{t_{truck}}=\frac{P_{truck}}{F_{brake}}=\frac{\frac{250000}{3}}{10}\approx{8333.3333s}"/>

Clearly the truck will take 5 times longer to slow to a complete stop, which makes sense as its mass is 5 times that of the car.

The equation <img src="https://latex.codecogs.com/svg.latex?\large&space;F\Delta{t}=P"/> is often referred to as the Impulse equation; one symbol used for Impulse is J but as Impulse is the push to get Momentum this course will use the symbol **P** for Impulse.

As an extension of Newton’s Laws there is a **Law of Conservation of Momentum** which states that momentum in closed system remains constant unless there is an external force. This law can be applied to what is seen in almost every video game, collisions. At this point watch the [Khan Academy videos](#references). Make sure to pause at appropriate spots to check the your understanding of what you have learned so far (you should be able to figure out some steps before the videos explain or show the answers).

After the last video, can you explain why the sample questions assumed perfectly inelastic (car colliding with a stationary truck) of perfectly elastic (the two balls example). In collisions there is a wide range of possibilities between each of these possible extremes. Starting with the general conservation of momentum equation:

<img src="https://latex.codecogs.com/svg.latex?\large&space;P_i=P_f"/> **OR** <img src="https://latex.codecogs.com/svg.latex?\large&space;m_1V_{1i}+m_2V_{2i}=m_1V_{1f}+m_2V_{2f}"/>

This equation is for perfectly elastic collisions; collisions where no loss of momentum (and thus velocity, or no change in mass) due to friction or objects compressing during the collision. In a pool game simulation, the programmer would almost always use this as there is very little inelasticity of the collisions of pool balls. However, it the game involved something like a beach ball, or other soft, “spongy” ball, there would need to be another form of this equation as the balls during collision would compress then expand back to _normal_ after the collision. This effect is inelasticity and is often seen in bouncing balls in real life.

The factor that needs to be included in the calculations is the **Coefficient of Restitution** <img src="https://latex.codecogs.com/svg.latex?\large&space;\varepsilon"/>; <img src="https://latex.codecogs.com/svg.latex?\large&space;0\leq{\varepsilon}\leq{1}"/>. When <img src="https://latex.codecogs.com/svg.latex?\large&space;\varepsilon=0"/> the collision is perfectly inelastic (object remain as one larger object after the collision), and when <img src="https://latex.codecogs.com/svg.latex?\large&space;\varepsilon=0"/> the collision is perfectly elastic (no deformations of the objects during the collision). Anywhere in between the objects are deformed to some degree during the collision.

To solve problems with partially elastic collisions it is necessary to treat each object’s collision separately as each object has its own ε value. The equation shown below, which has the value k as the collision response impulse:

<img src="https://latex.codecogs.com/svg.latex?\large&space;k=\frac{(\varepsilon+1)(V_1-V_2)}{\left(\frac{1}{m_1}+\frac{1}{m_2}\right)(n\cdot{n})}"/>

It is important to note that **n** is the normal of the collision point.

A more interesting case, which is quite common in video games such as a game of pool or billiards, is that of two objects colliding. Often these objects do not collide in a direct path, but more often collide in glancing blows (see the [Gamasutra reference](#references) for more details). For this begin with two circular objects, A with a mass of 1 kg and B with a mass of 2 kg. The equation for the circles at (very near) to the collision point are:

A: <img src="https://latex.codecogs.com/svg.latex?\large&space;(x+0.6)^2+(y-0.6)^2=1"/>

B: <img src="https://latex.codecogs.com/svg.latex?\large&space;(x-0.6)^2+(y+1)^2=1"/>

This gives the centers of each circular object as <img src="https://latex.codecogs.com/svg.latex?\large&space;A_c=(-0.6,0.6)"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;B_c=(0.6,-1)"/> as shown in the figure below:<br>
![collision-1](files/collision-1.jpg)

To know that these two circular objects are in contact, calculate the distance between the centers of the objects. If this distance is exactly the sum of the two radii, then they are contacting in exactly one point.

<img src="https://latex.codecogs.com/svg.latex?\large&space;(sum radii)^2=(1+1)^2=4"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;(distance between centers)^2=(x_B-x_A)^2+(y_B-y_A)^2=(0.6+0.6)^2+(-1-0.6)^2=4"/>

Now that a collision is possible, consider the initial velocities of the objects are <img src="https://latex.codecogs.com/svg.latex?\large&space;V_{Ai}=\left[\begin{array}{c}3\\1\end{array}\right]m/s"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;V_{Bi}=\left[\begin{array}{c}2\\3\end{array}\right]m/s"/>
