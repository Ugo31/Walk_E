# Walk_E
Fork of my walk_e GITLAB private project.
[The code will be avaiable soon.]

A more complete presentation of the project in french can be found here : https://docs.google.com/document/d/11bqnRA6VvR8L3Jr-xuVALNyKkRS9XhcHQkwYpmjD0F8/edit?usp=sharing


The goal of this project is to solve the dynamic walking problem for bipedals robots. The robot used as an example here is called Walk-e, a 3D printed robot based on the Cassie model from agility robotics made by myself.

The robot is a simple structure with only 2 legs, each legs can be controled using 4 motors (2 on the hip 2on the leg) for a total of 6 motors.The robot motors are only controlled by position for budget reasons (they are just big servos). Each motor have only 25Nm of torque and can move at 1.2s/rad.On board odometry is using a intel T265 sensor ans the robot computer is a jetson nano 4Gb. The total wiegth of the robot is 8Kg for 85CM of heigth.

Here is a picture of the model used:

![walk-e and the goal](/Pictures/pic1.png)

The robot is obsiously not stable and it is impossible for walk-e to stand up without any control.

The philosophy behing the project is the following : by nature nothing is perfect, the ground is never flat and nothing is symetric, if you need perfect conditions and expensive components to make your robot walk, the control law should just be better. That is why walk-e is built using so cheap components besides the obvious lack of budget.

To make a solid control law, the project is using a reinforcement (**Soft Actor Critic** algorithm). All the phisics simulations are made in **pybullet** using a custom made Open AI **GYM environement**.

## Robot control

-The first step to control the robot is to make it stand up without falling :

![walk-e standing](/Pictures/standing.gif)

The control law is so good we can even force the robot to only use one leg.

![walk-e jumping](/Pictures/onefoot.gif)


>Goal is represented with the **blue cube**, feet frictions coeficients are random to help with a future real life test (it makes a more robust model)

-Second step it to make it walk where it need to go :

https://www.youtube.com/watch?v=-1DtWe3hP30&feature=youtu.be

Walking to the goal is still a **work in progress** rigth now the robot have har time stopping on the correct place.

-The last step before real life testing is random ground levels and random ground friction to simulate different types of terains :

![walk-e jumping](/Pictures/walke_realgroun.gif)

As seen here it works pretty well, even on one foot so I added some more perturbations by throwing small 200g balls at the robot at different speeds, the control law seems to handle the perturbations verry well.



## Future

Next steps for the project are:

- Test the network on the real robot in real conditions. But the step from simulation to real life will probably be really hard.
