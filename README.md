# Walk_E
Fork of my walk_e GITLAB private project.
[The code will be avaiable when I thing it's good enougth to be public.]

The goal of this project is to solve the dynamic walking problem for bipedals robots. The robot used as an example here is called Walk-e, a 3D printed robot based on the Cassie model from agility robotics made by myself.

The robot is a simple structure with only 2 legs, each legs can be controled using 4 motors (2 on the hip 2on the leg) for a total of 6 motors.The robot motors are only controlled by position for budget reasons (they are just big servos). Each motor have only 25Nm of torque and can move at 1.2s/rad.On board odometry is using a intel T265 sensor ans the robot computer is a jetson nano 4Gb. The total wiegth of the robot is 8Kg for 85CM oh heigth.

Here is a picture of the model used:

The robot is obsiously not stable and it is impossible for walking to stand up without any control law.

The philosophy behing the project is the following : In nature nothing is perfect, the ground is never flat and nothing is symetric, if you need perfect conditions and expensive components to make your robot walk, the control law should just be better. That is why I use so cheap components besides the obvious lack of budget.


##Robot control

The first step to control the robot is to make it stand up without falling :

Goal is represented with the blue cube, foot frictions coeficients are random to help with a future real life test (it makes a more robust model)

Then make it walk where it need to go :

https://www.youtube.com/watch?v=-1DtWe3hP30&feature=youtu.be

Walking to the goal is still a work in progress rigth now the robot have har time stopping on the correct place.

##Future

Next steps for the project are :

>Test the network on the real robot in real conditions. But the step from simulation to real life will probably be really hard.

>Train the network to be able to walk on non flat grounds
