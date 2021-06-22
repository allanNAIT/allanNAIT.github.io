---
layout: page
title: Linear Mechanics
---
## Introduction
This lesson will extend the concepts learned in Lesson 3.1 to include how to get object moving and what happens when they are moving. To accomplish use this introduction of Newton’s Laws.

Modern mechanics has evolved from the classical mechanics of Sir Isaac Newton; the inclusion of the work by Albert Einstein, and others, has changed, somewhat, the work done by Sir Isaac Newton. The fundamentals of Newton’s work is summarized in his three laws.

>**Newton's First Law**<br>Every body persists in a state of being at rest or of moving uniformly straight forward, except insofar as it is compelled to change its state by force impressed.

>**Newton's Second Law**<br>The acceleration of a body is proportional to (and in the same direction as) the net external force acting on the body, and inversely proportional to the mass of the body:<br>
<img src="https://latex.codecogs.com/svg.latex?\large&space;F=mA"/>

>**Newton's Third Law**<br>To every action there is always an equal and opposite reaction. Or, the force of two bodies on each other are always equal and directed in opposite directions.

So, looking at the 1<sup>st</sup> law why does an object not keep moving, it eventually comes to a stop, after it is compelled to move? Friction. Friction is an external force that opposes motion, but it was quite the statement in its day. Also, a force is required to move an object.

The 2<sup>nd</sup> law’s formula is so simple but very important; it is fundamental to this lesson. Using the standard units for mass and acceleration we get:

<img src="https://latex.codecogs.com/svg.latex?\large&space;1N=1kg\times{1\frac{m}{s^2}}=1kg\frac{m}{s^2}"/>

It is important that a force does not produce velocity, only acceleration; an application of the linear motion equations from lesson 3.1 will yield a given velocity, and displacement, over a period.

Finally, the 3<sup>rd</sup> law. This law will come into play in almost every situation. For example, a body that is seen to be not moving does not mean that there are no forces acting on it, simply that this could be true, or all the forces balance each other out in opposite directions and thus no motion.

One thing that is important in real world physics is that the continued application of an applied force, over a very large period, does not result in speeds greater than the speed of light. Additionally, as Einstein formulated, and what has been learned so far, everything is relative to a certain view of the world, game world or real world.

## Simple Forces
### Key Concepts
The key concepts for this part of the lesson are:
* Calculation of net force
* Calculation of acceleration on a body

### Lesson
As an application of the 1<sup>st</sup> and 3<sup>rd</sup> laws consider an object sitting at rest on a table, or other suitable platform. What is known about this object? It has _mass_, and therefore **weight** (please note that _mass_ and **weight** are different). All force values must be vectors; examining the 2<sup>nd</sup> law it should be obvious that this is a vector multiplied by a _scalar_, which results in a vector.

![forces-01](files/forces-01.jpg)

The value of **-981N** is the result of the 1<sup>st</sup> law:<br>
<img src="https://latex.codecogs.com/svg.latex?\large&space;Weight=mass\times{Gravity}"/>

The other value, **981N**, balances out weight, <img src="https://latex.codecogs.com/svg.latex?\large&space;-981+981=0"/>. What is this force? This is the equal and opposite force of gravity (3<sup>rd</sup> law) called **Normal Force** (F<sub>N</sub>); F<sub>N</sub> is a reactive force in that it is the _surface pushing back_, _assuming it does not bend or break_, and will increase and decrease depending on the weight of the object resting on the surface.

Consider the scenario shown in the figure below in which an external force is applied to the object.<br>
![forces-02](files/forces-02.jpg)

In this scenario what would have to exist for the block to move? _The applied force must overcome friction_. How can the amount, magnitude, of friction be determined? _The value of friction depends on the surfaces involved and whether the object is initially at rest or initially moving_. It is important here to make mention that Friction, like Normal Force, is a reactive force, and will increase to a maximum value before the object will be able to move.

The two types of Friction are static (the object is not moving) and kinetic (the object is already in motion). The notations will be F<sub>s</sub> and F<sub>k</sub> respectively, and are calculated as:

<img src="https://latex.codecogs.com/svg.latex?\large&space;F_s=\mu_sF_N"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;F_k=\mu_kF_N"/>

Refer to an internet source, for some standard values of μ.

As an example, using the scenario shown in the figure above, with <img src="https://latex.codecogs.com/svg.latex?\large&space;F_{applied}=250N"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;\mu_s=0.2"/> calculate F<sub>net</sub>:

<img src="https://latex.codecogs.com/svg.latex?\large&space;F_s=(0.2)(981)=196.2N"/>

The direction of this vector must be opposite the relative motion of the surfaces, or <img src="https://latex.codecogs.com/svg.latex?\large&space;F_s=-196.2N"/>. Next calculate the net force. To do this correctly **all** external forces must be used and used as vectors.

<img src="https://latex.codecogs.com/svg.latex?\large&space;F_{net}=W+F_N+F_s+F_{applied}=\left[\begin{array}{c}0\\-981\end{array}\right]+\left[\begin{array}{c}0\\981\end{array}\right]+\left[\begin{array}{c}-196.2\\0\end{array}\right]+\left[\begin{array}{c}250\\0\end{array}\right]=\left[\begin{array}{c}53.8\\0\end{array}\right]N"/>

Questions:
* Why do friction and applied force have no y-component?
* What if the applied force was only 150N?
* What is the acceleration on this object?

<img src="https://latex.codecogs.com/svg.latex?\large&space;A=\frac{F_{net}}{m}=\frac{1}{100}\left[\begin{array}{c}53.8\\0\end{array}\right]=\left[\begin{array}{c}0.538\\0\end{array}\right]m/s^2"/>

Consider the scenario shown in the figure below, where the object is at rest on an inclined surface.<br>
![forces-03](files/forces-03.jpg)

Note that weight is always perpendicular to the ground, not the surface the object is resting on, and Normal Force is always perpendicular to the surface the object is resting on. As the surface, not the ground, is responsible for providing F<sub>N</sub>. The weight vector needs to be split into its components, relative to the surface, not the ground as shown in the figure below.<br>
![forces-04](files/forces-04.jpg)

_Note: It can be proven that the angle θ of the incline is the same angle of the right triangle formed by the components of weight._

Question now is whether the object is moving or not. In this initial state which direction is friction? _It will be up the ramp regardless of the whether the object is moving or not_. Using the same object, and friction coefficient as before, but now have the ramp angle at 10<sup>o</sup> calculate net force. First calculate weight.

<img src="https://latex.codecogs.com/svg.latex?\large&space;Wsin\theta=(100)(-981)(sin(10))\approx{-170.3498N}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;Wcos\theta=(100)(-981)(cos(10))\approx{-966.0964N}"/>

Next calculate <img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{F_N}\Vert"/>:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{F_N}\Vert=-Wcos(10)\approx{966.0964N}"/>

Next the maximum friction:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{F_s}\Vert=(0.2)(966.0964)\approx{193.2993N}"/>

Determine if the object is moving. It is clear that <img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{-170.3489}\vert{<\vert{193.2193}\vert}"/> therefore the object is at rest; the x-component of gravity was not sufficient to overcome friction, therefore <img src="https://latex.codecogs.com/svg.latex?\large&space;F_{net}=0N"/>. What would happen if the incline angle were increased to 20<sup>o</sup>?

<img src="https://latex.codecogs.com/svg.latex?\large&space;Wsin\theta=(100)(-981)(sin(20))\approx{-335.5218N}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;Wcos\theta=(100)(-981)(cos(20))\approx{-921.8385N}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{F_N}\Vert=-Wcos(20)\approx{921.8385N}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{F_s}\Vert=(0.2)(921.8385)\approx{184.3677N}"/>

At this point it should be clear that the x-component of weight exceeds, in magnitude, the maximum value of friction, therefore the object will be moving down the ramp:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{F_{net}}\Vert=-336.5218+0+184.3677\approx{-151.1541N}"/>

![forces-math-1](files/forces-math-1.jpg)
