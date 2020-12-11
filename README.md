# Walk_E
Fork of my walk_e GITLAB private project.
[The code will be avaiable when I thing it's good enougth to be public.]

The goal of this project is to solve the dynamic walking problem for bipedals robots.
The robot used as an example here is called Walk-e, a 3D printed robot based on the Cassie model from agility robotics made by myself.

The robot is a simple structure with only 2 legs, each legs can be controled using 4 motors (2 on the hip 2on the leg) for a total of 6 motors.The robot motors are only controlled by position for budget reasons (they are just big servos). Each motor have only 25Nm of torque and can move at 1.2s/rad.Onbaord odometry is using a intel T265 sensor ans the robot computer is a jetson nano 4Gb. The total wiegth of the robot is 8Kg for 85CM oh heigth.

The philosophy behing the project is the following : In nature nothing is perfect, the ground is never flat nothing is symetric, if you need perfect conditions ans expensive components to make your robot walk, the control law should just be better.






Before making a path palning algoruthm we need to be able to control how the robot move :


