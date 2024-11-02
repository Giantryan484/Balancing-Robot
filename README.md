# Balancing Robot

<div align="center">
    This repository store the code and 3D modelling files for a Balancing Robot that I'm building with a friend of mine, Asher Levin. It's currently a Work-In-Progress, but maybe the progress we've made so far is of interest to you.
    <br/><br/>
    <img src="Proposal Sketches/11_1_24-robot.jpeg" height="400px">
    <img src="Proposal Sketches/robot_sketch.png" height="400px">
</div>

## About the repository

My partner and I are working on this project at the exact same time, so we're keeping our work as separate as possible. Because of this, and because I don't want to install unneeded files onto the Raspberry Pi, we've separated our work onto multiple branches in this repo. 

I, _Ryan McCormick_, am in charge of mechanical design and assembly; buying and building all the parts; and designing/training a model in the reinforcment learning environment. You can see all my 3D models on the `3D_Designs` branch. I might expand to other branches for the machine learning process as well.

My partner, _Asher Leven_ is in charge of the computer system inside of the robot, including all sensors, motors, and an eventual real-time connection to my reinforcment learning model. You can see most of his work on the `pi` branch, containing all the code he has written on the Raspberry Pi. Eventually, he might make other branches for extra code snippets, perhaps for our arduino nanos.

On the main branch is a few shared files, largely relating to communication between us and you. Perhaps it can give you insight into our collaboration environment. I might also post occasional project updates every once in a while, to give insight into our current build process.

## What We're doing now

Currently working through our assigned tasks in the [updated project plan.](10-23-24_Task_Guide.md)

## About the Project
(filled out by Ryan)

<details>
  <summary>Project summary</summary>
<hr/>
This is a remotely-controlled robot that balances itself upright on the two wheels it uses as its mode of transportation. It can roll around, turn, and eventually we will give it arms to use to pick up items and carry cargo. All of this movement is controlled by an deep learning model running on the raspberry pi, acting as a sort of "brain" trained via reinforcement learning. This robot represents the greates mechanical design task I've taken on up until now, and also represents my first dive into electronics and applied Artificial Intelligence systems.
<br/><br/>
</details>

<details>
  <summary>Project highlight</summary>
  <hr/>
My favorite thing thus far has to be the satisfaction that comes from hours upon hours of CAD coming together so quickly. After a month of design and parameterizing, I printed the parts, cut the aluminum stock, and assembled the robot's frame in less than a week's time! I suspect I'll find a similar payoff once we finally put the brains of the robot together.
<br/><br/>
</details>

<details>
  <summary>Contributions and credit </summary>
  <hr/>
  I'm taking on this project in collaboration with Asher Levin, partially to practice collaborative learning techniques, and partially because I simply wouldn't have enough time to complete it on my own given my current busy schedule. You can see our tasks clearly divided in our most recent project proposal, which contains an updated plan of who will do what and when.
  <br/><br/>
  I have no mentors of this project, in fact, I haven't my teachers at school about it at all. They're kind of left wondering where I've disappeared to for the past month... I guess they'll get to see when I bring in the robot to work on it next semester.
<br/><br/>
</details>

<details>
  <summary>Background context</summary>
  <hr/>
The main goal of this project is to learn robotics from scratch. It's not for any particularly revolutionary goals, in fact many people have probably built this exact thing already, instead it's a project for my own exploration of what a career in engineering might have to offer.
<br/><br/>
There were some massive contraints for this project, particularly in the realm of tools and equipment. I'm stuck using a $99 3D printer because I can't bring myself to get a better one, so you'll notice my print quality sucks and I probably wasted about half a roll of filament on failed prints. I also don't have proper tools when I really need them. For example, I spent an entire saturday cutting the aluminum rods with the world's tiniest hacksaw and some garden shears, staying up well into the night because of how inefficient my process is. I'm also using the cheapest soldering iron I could find online, because it was the only one I could afford at the time I bought it.
<br/><br/>

</details>

<details>
  <summary>Build process</summary>
  <hr/>
   - Tell us more about your build. What was your approach, and why did you decide to do it that way? If there was a design/testing process, what did you do? Consider attaching photos in the subsequent media uploader page to demonstrate your build process.

The building processes of this robot involved ordering parts, cutting stock, and planning electronics all while the 3D-printed connectors were being printed. All of this was also in the middle of writing my college essays and finalizing the applications, making for a pretty chaotic week.
<br/><br/>
I decided to make it mostly 3D printed because that was the most available form of fabrication to me. I also used aluminum rods to add some sturdiness to the frame while keeping it light and while using feasible for me to trim with the tools I have on hand. The rods and connectors are held together with threaded inserts. 
<br/><br/>
I've used a mix of threaded inserts and embedded nuts throughout the model for easy disassembly. In the final result, the entire robot can be completely disassembled into its original parts. This was an intentional choice because I know this project will be modified significantly over the next few months, and I'd also like to be able to completely replace any parts that break in falls or through usual wear.
<br/><br/>
</details>

<details>
  <summary>Reflection and learnings</summary>
  <hr/>
   Everything has gone pretty smoothly until now, so most of my lesson-learning will come later down the line I'm sure. The only problems I encountered were mostly sourced from my poor-quality 3D printer, which would often create prints with non-existent layer adhesion after I changed literally 0 settings. So far, this project has satisfied my goal of giving me a fully-fledged, cross-disciplinary engineering experience.
<br/><br/>
</details>
