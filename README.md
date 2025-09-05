# Bicopter-DRehm-Flight 

# Setup of RC
This code defines the ESCs as servo motors and does not use the oneshot protocol. Can be used with regular ESCs like SimonK, Hobbywing, ReadytoSky etc.
1. I am using PPM based transmitter (Flysky FSi6X) so uncomment the corresponding PPM protocol in user-specified defines. <br>
2. For PPM transmitter, connect ch1 to pin 23, and the power and ground. No need of connecting other channels. In the code make sure ppm is defined on pin 23 and is uncommented <br>
3. Uncomment `printRadioData()` to see the values on every channel after setting up RC. <br>
4. Ch5 has been assigned to arm and disarm the motors, recommend setting a switch on channel 5. Flipping the switch arms the ESCs automatically. <br>

# Setup of Gyroscope - Calibration
1. I am using an MPU6050. Uncomment the corresponding gyroscope in the user defined variables section. <br>
2. Set all the error variables to 0 in the code initially. <br>
`float AccErrorX = 0;` <br>
`float AccErrorY = 0;` <br>
`float AccErrorZ = 0;` <br>
`float GyroErrorX = 0;` <br>
`float GyroErrorY= 0;` <br>
`float GyroErrorZ = 0;` <br>
3. Now uncomment the `calculate_IMU_error()` function in the void setup. Note the values you get in the serial monitor and paste them in place of the above 0 values of AccErrorX etc. <br>
4. Now you can uncomment `printGyroData()` to see the values from the gyroscope <br>

# Run the model
1. The control mixer has the algorithm for the bicopter model. <br>
2. Arm the escs using the switch assigned to channel 5 and increase the throttle to see it fly.
