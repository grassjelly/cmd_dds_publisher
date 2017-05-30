### Running the demo
1. Run the demo launch file.

    ```sh
    $ roslaunch cmd_dds_publisher demo.launch 
    ```
2. Drive the robot from the same terminal.

3. Open a new terminal and echo "cmd_vel" topic to see the received ROS msgs.

    ```sh
    $ rostopic echo cmd_vel
    ```
4. Run fake DDS 'cmd_vel' overwrite (optional).

    ```sh
    $ rosrun cmd_dds_publisher Velocities_publisher
    ```

5. Check the received messages in No.3 . User input should be disabled when Velocities_publisher is run (No.4) since DDS control has more priority than ROS control.


### Notes:
1. DDS Domain ID: 0

2. DDS Topic Name: "CommandVelocities"

3. Published Data Structure:

    struct Velocities  
    {  

    long robot_id;  
    double linear_velocity_x;  
    double linear_velocity_y;  
    double angular_velocity_z;  

    };  

