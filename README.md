# SADIE: the Self-balancing AI for Dynamic Interaction and Experimentation

<div align="center">
    This repository stores the code and 3D files for a Robot that I'm in the process of building. Eventually, this will be an agent for exploring modern computer vision techniques and human-computer interaction. It's currently a Work-In-Progress, but maybe the progress I've made so far is of interest to you.
    <br/><br/>
    <img src="Banner.gif" height="400px">
</div>

## What I'm doing now

Currently, I'm taking a break from my projects so I can focus on my recent placement at Bedrock Research and the upcoming honor orchestra season. Eventually, I'll start to tackle the TODO list for this project. Here's the very next steps for me:
- Design the arms: I've got to decide what tools the robot will have access to and design the mechanism for using them and swapping them out. I suspect I'll build some sort of connector for both electrical and mechanical power (maybe I'll use a standard electrical connector alongside some sort of brake-cable mechanism). This would enable me to have both powered components (electromagnets, hydraulics) and mechanical components (arcade-style grippers) work with the same method of attachment.
- Establish communication: I need to build the web server (hosted on the Pi) that will function as the remote to control the robot's movements when needed. I also need to figure out how to interface with the motors and sensors, because I've never used these components before. Eventually, I'll need to build some sort of pipeline that connects the Pi's core logic to a separate process that's running the highly-optimized RL model on the CPU.
- Simulation: The robot is currently immobile... It's time to fix that. I need to train the Reinforcement-Learning model in a virtual physics environment, adding lots of variability to its physical properties and sensor data. This is required so the robot can adapt to a changing center of mass and moment of inertia when picking things up, because a purely analytical approach would require 10x as much work. Thank goodness for modern ML suites.
- Get creative: I still have lots of planning to do, especially in regards to fine-tuning the personalities and figuring out how they interact with each other. I also need to design their facial sprites and determine when they'll switch between them.
- Remake everything: My school's engineering teacher is letting me use their large-format 3D printer to reprint the entire model. I'll also use their manufacturing shop to make the panels look shiny and professional. Unfortunately, I can't really do this until I have the final design completely dialed-in, because that'd be a waste of a bunch of material.

## About the Project

<details>
  <summary>Project summary</summary>
  <hr/>
  SADIE is a robot that balances itself upright on two wheels, and it has many ways to interact with the environment. 
  <br/><br/>
  It's nowhere near complete, but I think you'd appreciate the progress so far. I've finished the mechanical and electrical design for the main body, and I've printed and assembled the core of the robot. This has been about 200–300 hours of work until now, but many significant tasks still remain.
  <br/><br/>
  Eventually, the Raspberry Pi at the core of this robot will use a Reinforcement-Learning model to balance itself upright using data from an IMU. There will also be a speaker and mic added that interface with a ChatGPT integration that reflects the personalities shown on screen. Finally, I'll add a chest-mounted camera that will be used for Computer Vision experiments, including object/face tracking and environment mapping.
  <br/><br/>
</details>

<details>
  <summary>Project highlight</summary>
  <hr/>
  The face is very silly. I love the creative freedom that it brings to this project. I constantly find myself imagining the final robot with the ChatGPT integration, listening to the personalities argue with each other or hold all sorts of conversations. Sometimes engineering feels too serious. I like adding small jokes here and there to lighten the mood. 
  <br/><br/>
  I even have a secret planned out. You see, attaching a magnetic, striped tie unleashes a 4th secret personality: TONY (the Tactful Orchestrator of Notorious Yapping). This is a mob-boss character that is extremely reluctant to follow any of the directions you give it. Randomly, it will become drunk and wobbly in its movement, and is overall just pure comedy.
  <br/><br/>
  I'm so excited for when I can bring this part of the build into reality. I think it will make other people love this project just as much as I do.
  <br/><br/>
</details>

<details>
  <summary>Contributions and credit</summary>
  <hr/>
  This was supposed to be a shared project between me and a friend, Asher Levin, but unfortunately he has not held up his side of the bargain. Originally, the plan was to have the entire electronics system completed by now, programmed by him. However, as you can see in the video, that has not happened. In the current situation, he hasn't shared a single line of code with me.
  <br/><br/>
  I don't blame him because I'm not giving him a salary, so instead I'm going to change it to a solo project. It'll be a lot of work for me, but I'll learn a heck of a lot more.
  <br/><br/>
  Citations:<br/>
  ----<br/>
  Electronic parts:<br/>
  Raspberry Pi 4 and Pi OS Lite<br/>
  NERMAK 12V 10Ah LiFePO4 battery<br/>
  HZWDONE 7-Inch IPS LCD Screen<br/>
  --<br/>
  Software:<br/>
  SolidWorks Student Edition<br/>
  OpenAI Gym (now "Gymnasium")<br/>
  --<br/>
  Tools:<br/>
  Ender 3 Pro<br/>
  BambuLab A1<br/>
  --<br/>
  Misc:<br/>
  BambuLab PETG HF and PLA Basic<br/>
  Aliexpress for online electronics sourcing
  <br/><br/>
</details>

<details>
  <summary>Background context</summary>
  <hr/>
  This project has no practical reason for its existence. This project serves solely as a learning experience. You see, I'm interested in investigating networks of small intelligent robots later in my career, so this project is simply me familiarizing myself with what building such robots would look like. 
  <br/><br/>
  Additionally, this project requires countless skills that I've never encountered before. There's reinforcement learning, computer vision, electrical design/assembly, and human-computer interaction—all fields I've never really touched. 
  <br/><br/>
  I started this project with a $0 budget. Within a week I realized that was silly. Given the rapidly approaching college deadlines, I needed quality tools and materials that could get the job done, so I bought them. Still, I wasn't afraid of a little jank. In fact, I spent a week trimming the aluminum rods with a pair of old branch cutters.
  <br/><br/>
</details>

<details>
  <summary>Build process</summary>
  <hr/>
  This project had lots of necessary planning required because of its complexity. I didn't touch my computer until I had made a dozen sketches of what the final design would look like. I didn't visit the store page until I had an exact list of every part I needed.
  <br/><br/>
  Once it was time to build, I began by transferring my sketches of the internal frame into SolidWorks, using 2 lawnmower wheels as guides for how big it needed to be. I used a 3D sketch and Weldments to mark out the aluminum rod placement and cut-lengths. Then, I designed connectors around it, including several platforms for electronics and such. Finally, I designed the armor plates by tracing the sketches with complex surface lofts.
  <br/><br/>
  I used a combination of multi-body and assembly modelling because some objects didn't justify their own file, but in the end everything fit perfectly. I was quite surprised myself, actually.
  <br/><br/>
</details>

<details>
  <summary>Reflection and learnings</summary>
  <hr/>
  A few times, I had to adjust the parameters of my 3D model to fit the size of the electronics because they arrived different sizes than specified. But aside from that, everything up until now has gone smoothly. I'm quite proud of how clean the robot looks in its current state.
  <br/><br/>
  As you know by now, this project has a long ways to go until completion. Still, I have some intermittent goals to share. Specifically, I have permission from my school for this robot to walk across the stage during graduation. I'll print it a custom graduation cap and give it a joyous personality to share. Additionally, I've been considering making a YouTube series about this. I love encouraging fellow students on their projects, and a video series would let me encourage thousands of curious minds with even grander ideas than me.
  <br/><br/>
</details>
