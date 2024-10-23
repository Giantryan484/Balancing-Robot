# Task guide/Revised project plan (10/23/24)
I realized that my original plan was 1) completely incorrect with the estimated times and 2) neglected some tasks and specifics that needed to be addressed. This is my attempt to fix that.

## Ryan

### Overview:
Ryan will be in charge of designing and building the robot, as well as designing and building the reinforcement learning model that runs the robot's balancing system.

### Specifications:

**Step 1: Model it**
 - From electronics components to their enclosures, from the aluminum frame to its PETG joints, model *everything*. 
     - This is where I am currently. I'm unable to finish modelling until I receive all of my parts in the mail.

**Step 2: Build it**
- Using the completed design, print out parts on the Ender 3 and cut the aluminum stock to build the robot's frame, including the custom-designed bearing and electronics enclosures.
    - I'm also dabbling in this step concurrently with the first. I've been slowly cutting through my aluminum stock every since I finalized the cut list.

**Step 3: Simulate it**
- Using the 3D model and some basic physics libraries, design a controllable simulation that has similar inputs/outputs to what the real-world model will have.
    - I'm going to build off of the work Asher had already done under the last project plan.

**Step 4: Train it**
- Create a reinforcement learning program that will optimize the behavior of the simulated agent. This involves designing the DQN, perhaps with recursive abilities, and then training the model and tuning the reward parameters. 
    - I'm doing this in PyTorch, Tensorflow traumatized me in my last project.

**Step 5: Integrate it**
 - Once Asher and I have finished our separate tasks, I'm going to combine his code with my machine learning model, finish installing the electronics into the robotics enclosure, and run it. 
    - I give about a 2% chance that it runs on the first try.

## Asher

### Overview:
Asher will be in charge of writing code for the elcetronics system that Ryan designed, including sensor handling, multi-processing, and designing/displaying the facial expressions on the robot's facial screen.

### Specifications (in much more detail than Ryan's):

**Step 0: Setup git and your development environment**
 - Ryan can help you here.

**Step 1: Motor Control and Encoder Integration**
- Implement Motor Control:
  - Write a Python program on the Raspberry Pi that controls the motors based on a hard-coded speed value from 0 to 1 (e.g., 0.8 corresponds to 80% speed).
  - Utilize the given motor driver (L298N) along with the Raspberry Pi and the motors.
  - Use a PWM library like `RPi.GPIO` or `pigpio` to generate PWM signals for motor speed control. Look up diagrams to find the PWM pins on the pi or arduinos whenever needed.
- Encoder Integration:
  - Connect motor encoders to the Raspberry Pi GPIO pins configured as inputs.
  - Write code to read encoder pulses accurately, handling interrupts if necessary.
  - Implement functions to count encoder pulses and determine motor rotation.
- Calculate Motion Parameters:
  - Use the gear ratio and 6-inch wheel diameter to convert encoder counts to linear displacement. This may require you to count how many times the encoder pusles when you rotate the wheel 10 times, then divide by 10 and multiply by the circumference to have a constant conversion from encoder values to linear movement.
  - Create functions to calculate velocity and acceleration based on encoder data.
  - Abstract the logic into reusable functions (`calculate_position()`, `calculate_velocity()`, etc.) for future use.

**Step 2: IMU Integration**
- Set Up IMU Sensor:
  - Connect the IMU (MPU-6050) to the Raspberry Pi via I2C (Inter-Integrated Circuit). Google whatever you don't understand. Or make a deal with the devil, ChatGPT.
  - Enable I2C communication on the Raspberry Pi using `raspi-config`.
- Read IMU Data:
  - Write code to read raw accelerometer and gyroscope data from the IMU.
  - Use appropriate Python libraries (`smbus`, `smbus2`, or sensor-specific libraries) for I2C communication. I'm not entirely sure about specifics like these because, well, I haven't done these steps either.
- Process Sensor Data:
  - Interpret the raw data to obtain meaningful measurements (e.g., acceleration in m/s², angular velocity in °/s).
  - Implement sensor fusion algorithms (essentially averages the values of the accelerometer and gyroscope, see "complementary filter" on Google) to calculate orientation angles (pitch, roll, yaw).
- Function Development:
  - Create functions to retrieve and process IMU data (`get_acceleration()`, `get_angular_velocity()`, `get_orientation()`).
  - Ensure the output format aligns with the expected inputs for the reinforcement learning model, once chosen.

**Step 3: Establish Inter-Process Communication (IPC)**
- Create RL Model Placeholder Process:
  - Develop a separate Python process that will eventually host the RL model. For now, it will be a function that takes sensor inputs and returns random motor commands (2 values from 0-1 that represent how the base motors should spin).
- Set Up IPC Mechanism:
  - Use Python's `multiprocessing` module to manage separate processes.
  - Implement inter-process communication using `multiprocessing.Queue` or `multiprocessing.Pipe` to exchange data between the main process and the RL model process.
- Data Exchange:
  - Ensure the main process sends the necessary sensor data (from the IMU and encoders) to the RL process. Perhaps log it to the console, or something.
  - Receive motor command outputs from the RL process and use them to control the motors.
- Concurrency Management:
  - Make sure both processes run concurrently without blocking each other.

**Step 4: Develop Web Interface for User Input**
- Set Up Web Server:
  - Use the Flask web framework (or any other framework, I just figured if we're doing everything else in python we might as well do the web hosting too) to create a lightweight, development web server on the Raspberry Pi.
  - Install Flask and necessary dependencies.
- Design Webpage:
  - Create an HTML interface with arrow buttons (forward, backward, left, right).
  - Use simple HTML, CSS, and JavaScript to design the user interface.
- Implement Server-Side Logic:
  - Write Flask routes to handle HTTP POST requests when buttons are pressed.
  - Implement functions to print the respective direction to the console.
- Integrate with Main Process:
  - Modify the server-side code to send user input commands to the main process.
  - Use a shared queue or other IPC mechanism to pass commands from the web server to the motor control logic.
- Testing and Debugging:
  - Test the web interface from a device on the same network by accessing the Raspberry Pi's IP address.
  - Ensure that button presses result in the expected console outputs and, eventually, motor actions.

**Step 5: Design and Display Facial Expressions**
- Design Facial Expressions:
  - Create or source images representing different facial expressions (happy, sad, neutral, etc.).
  - Ensure images are sized appropriately for the LCD display (1024x600, or same aspect ratio).
- Develop Display Application:
  - Use Pygame to create an application that displays images on the LCD monitor connected via HDMI.
  - Write code to load and display the facial expression images.
- Run Concurrently with Other Processes:
  - Implement the facial expressions display as a separate process to run concurrently with motor control and sensor processes.
- Control Facial Expressions:
  - Develop a method to change facial expressions based on input from the main process or user interactions.
    - For example, change expressions when certain buttons are pressed or when specific events occur (e.g., robot starts moving or spins around).
  - Use IPC mechanisms to receive commands to change the displayed expression.
- Enhancements:
  - Consider adding animations or transitions between expressions for a more dynamic display.
  - Optimize performance to ensure smooth operation without affecting other processes.