# Simulink---Project---Automotive-Performance-Package
## Objective
In this project, the aim is to simulate the logic for an automotive performance package. 
Rapid development of technology has made it possible for motor vehicles to have control functions that adjust the motor behaviors in response to data. This explains how sophisticated motor vehicles have sensors. 

## Literature 
This project shows a simplified system that responds to two main sensors: 
- speed
- lateral acceleration
- 
These sensors determines a high performance and economy mode.
The Signal Editor Block is used for the model simulation.
NB: The Signal Editor Block is another type of source like Sine Wave and Ramp.

## Methodology
- Step 1:
Add an Abs block to take the absolute value of lateral acceleration.
(Simulink > Math Operations > Abs)

<img width="456" height="143" alt="Step 1" src="https://github.com/user-attachments/assets/f809f5db-c9d6-4d54-b1c3-66de1e6941ab" />

- Step 2:
Add three Compare to Constant blocks to the model. Set their conditions to
 ">= 100, >= 35, >= 3"
Connect the blocks to their appropriate signals, which is shown below as:

<img width="485" height="212" alt="Step 2" src="https://github.com/user-attachments/assets/0058d524-d1fa-4dcc-85be-cbac6838bf29" />

- Step 3:
Add a Logical Operator block to the model. Use the default Operator value, AND. Then, connect the appropriate Compare to Constant blocks to create the statement:
speed >= 35 km/h AND
  abs(lateral acceleration) >= 3 m/s2
Connect the output of the Logical Operator block to the Signal Assessment block.

<img width="378" height="234" alt="Step 3" src="https://github.com/user-attachments/assets/e63abbc2-c562-42d5-a015-ab728778a47d" />

- Step 4:
Add a second Logical Operator block to the model. Change its Operator to OR.
Connect the blocks to create the statement:
(speed >= 100 km/h) OR (speed >= 35 km/h AND
  abs(lateral acceleration) >= 3 m/s2)
Connect the output of the OR Logical Operator block to the Signal Assessment block.

<img width="374" height="170" alt="Step 4" src="https://github.com/user-attachments/assets/f6ed94ff-87c8-4d4a-bbea-f4b4014bed36" />

- Step 5:

The final step is to add the logical statement, as follows:
if (speed >= 100 km/h) OR 
 (speed >= 35 km/h AND abs(lateral acceleration) >= 3 m/s2)
    use mode 2
else
    use mode 1
end

Add a Switch block to the model and connect the output from the previous step to the control signal. 
Add two Constant blocks, with values 1 and 2, to represent the driving modes. 
Connect the blocks to the appropriate locations on the Switch block.

<img width="379" height="216" alt="Step 5" src="https://github.com/user-attachments/assets/0157f9a1-5fad-4799-b9c7-234cf3c47ca6" />

## Conclusion
This project consist of fundamentals of dynamics system modeling, from Mathematical Operators to Basic Logics and Conditional Statements. This is to lay foundational of the project element. 
The aim of the project was achieved by using the blocks and components from the Simulink library. 

















