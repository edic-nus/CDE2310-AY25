# National University of Singapore 
 Autonomous Mobile Robots (AMRs) Intralogistics in a Smart IOT4.0 Warehouse
 CDE2310 ‐  Fundamentals of Systems Design 
 AY 25-26

*V1.0 | 6 Dec 2025 | Nicholas Chew*

## Introduction
In this year’s mission, CDE2310 student teams will design, implement, and validate an Autonomous Mobile Robot (AMR) workflow inspired by modern warehouse intralogistics. Using the TurtleBot3 platform, self-designed mechanisms and the ROS 2 framework, teams must execute a sequence of delivery tasks involving static targets, moving targets, and multi-level operations via an automated lift interface. The mission is structured in three progressive objectives, each introducing increasingly realistic challenges faced in industrial environments. Objective 3 is a bonus challenge intended only for teams who demonstrate strong engineering proficiency.

## Mission Context
Global warehouses are rapidly adopting AMRs for material handling, order fulfilment, vertical transport, and coordination with automated building systems. This mission simulates these real-world conditions by requiring robots to navigate complex spaces, detect fiducial markers, interact with moving mechanisms, and communicate with an external API (optional objective).

Your TurtleBot acts as a warehouse AMR, responsible for transporting payloads (represented by 3 ping pong balls) between designated drop-off stations inside a simulated warehouse maze (see maze layout drawing)
The overall mission for the team is to develop a system that can be efficiently operated by anyone. The system will comprise an autonomous navigation robot (turtlebot) with attached sensors (RPI camera V2 8MP will be provided) and mechanisms to locate landmarks (e.g. QR code, RFID, ArUco markers, etc) in an unknown area and "deliver" payloads to the correct locations. The payload delivery point will be replicated by a biscuit box tin as a unloading receptacle and students are free to choose any landmark detection medium which can be placed at any location of their choosing.

Due to the mission theme, line following navigation is forbidden henceforth. Each group will have exactly 25 minutes to set up the materials to execute the mission (groups with lesser members will be given more time) . The mission is considered complete once the robot delivers the required number of ping pong balls to each delivery station (i.e., considered successful when all 3 pingpong balls are SEQUENTIALLY delivered into receptable without falling out within 10 secs for the first difficulty level). For the second level of difficulty, the delivery receptacle will slide back and forth at a set speed limit so teams can test their creativity and engineering prowess to successfully deliver all 3 ping pong balls onto a dynamically-moving target (timing is not critical here).

Finally, there will be a 3rd bonus zone featuring a lift to deliver items to a 2nd level but it is not mission critical. Scaling an elevator via API calls while ignoring SLAM data and following external actions is challenging but bonus points will be awarded for successful completion of this added mission objective. Confident groups can attempt this after satisfying the basic objectives. The lift will always be in a known area of the warehouse zone (e.g. 1 of the top 4 corners of maze) and elevator/delivery specs (e.g. height, end-delivery location, lift activation commands, etc.) will also be made known by week 7.

## The Steps
The final examination will be divided into 3 periods, i) a Setup Period to install the equipment, ii) the mission and an iii) end Phase to clean the arena. The team will have exactly 25 minutes (or adjusted time limit depending on team strength) to set up the materials, complete the examination and leave (inclusive of cleanup) the area. 

###	1. THE SETUP PERIOD 
During the Setup Period, the team is to: 
- place marker (QR, ARUCO, RFID, etc) or beacons [limited to a max of 6 - 2 per each delivery zone]]
- place the robot at the start zone 
- set up the computer on the table near the start zone 
- start all the software
- Ensure ping pong balls are loaded into the robot
- Any other activity, setup, calibration or tests required for completion of the mission
  
During this time, the TA will read the group's user manual to be familiar with the functioning of the system and may ask for some clarifications from the team. 
When the team is ready, they have to stay at least one metre from the arena and tell the TA that they are ready to start the missions. After this, the team will not be authorized to teleoperate or perform any manual operations to the robot. 

Finally, the team will declare to start the mission and also express to examiner and TAs whether to attempt the bonus objective.

### 2. THE MISSION 
The mission will consist of 4 phases, i) a start zone, ii) a randomized maze zone, iii) the static delivery zone (Station A), iv) Dynamic delivery zone (Station B) and the iv) optional multi-level lift delivery zone (Station C). Upon activation, the robot must autonomously leave the start Zone and proceed into the warehouse operational space to begin its delivery sequence. In the maze zone, the robot is to map out the maze and detect any landmarks to execute the delivery instructions.

In the first operational phase, the robot must: Navigate to Station A, a fixed unloading shelf identifiable by a static QR code marker (or any other image-based detection markers of the team's choice). Detect the marker and align itself within the allowed docking tolerance. Execute the payload unloading sequence in a fixed timing pattern (more details in week 7) and dispense the payload into the collection receptacle. If an unloading error occurs (misalignment, partial unloading, or failure to dispense), the robot may attempt the unloading routine again. Multiple attempts incur time penalties and reflect inefficiencies similar to real-world AMR operations.

*All 3 ping pong balls must remain within the receptacle. Any ping pong balls that fall out will incur a penalty.

Upon completing Station A delivery, the robot transitions to the Dynamic Delivery Zone (reverse sequence is also allowed whereby Station B is unloaded first). Here, the target unloading platform is mounted on a motorised linear rail, oscillating back and forth. The robot must: Detect and identify the moving target’s QR code marker. Track the motion profile and time its docking manoeuvre (Platform will start moving when team gives start signal). Execute the second unloading sequence, depositing another payload batch (3 ping pong balls). As with the first zone, the robot may retry the unloading sequence if errors occur. Each additional attempt reflects reduced operational efficiency. After unloading successfully (or after all attempts are exhausted), the robot must proceed to the next zone or conclude. The official mission time will stop once this second unload is completed.

Depending on the team's mission direction, they may continue to execute the bonus objectives with the help of land-based markers and navigate to the final zone. Teams may continue to attempt bonus objectives after completing the primary mission. Performance in this phase does not affect the final score negatively; only successful bonus achievements add points. In this phase, the robot must: Navigate to the Lift Lobby (Station C) using land-based QR markers. Detect the lobby marker and initiate an API call to summon the lift. Enter the lift safely once arrival is confirmed. Emit the appropriate API command to travel to Level 2. Exit the lift at Level 2 and navigate to Station D, the final delivery point. Perform a final payload unloading sequence. Bonus points will be awarded based on the following progression:

i) Reaching the Lift Lobby (Station C)
ii) Successfully entering the lift and ascending to Level 2
iii) Completing the final delivery at Station D after exiting the lift

Additional bonus points will also be awarded for teams with a good understanding of ROS CLI to streamline deployment:
iv) Recording of ROSBAG data (this may be computationally intensive so run ROSBAGs at your own peril)
v) Only usage of 1 ros2 launch file for the entire robot operation (as compared to multiple ros2 packages being manually executed)

Errors or failures in this bonus phase do not impact the primary mission score.

The TA may catch and power off the robot if necessary to prevent any damage or contact with the arena walls, the robot or any other elements of the maze. In this case, the current mission attempt will end and the team will receive a penalty applied to the overall score. 

The team may declare an official stop and re-attempt the mission for multiple tries within the time limit. Groups are strongly advised to fulfill basic objectives first and then attempt bonus objectives.

During the missions, the TA will constantly fill the scoring form (in appendix 1, one for each mission). When he/she finishes filling in the form after each mission, the team will have two possibilities:

-  The team agrees with the final score and signs the form. 
-  The team disagrees with the final score or want to do a re‐attempt to obtain a better score. If so, the team will have access to the arena to adjust the robot, markers and make modifications to the software. The team must inform the TA if there they make any major changes. When the members are ready and leave the arena, the team will declare a fresh start to the mission. The team can have as many attempts as they want for each mission as long as it is within the stipulated time limit.

### 3. End Phase
At the end of the 25 minutes (or pro-rated time limit), the current mission will stop immediately. The TA will stop filling in the Scoring Form and calculate the score for that attempt. This score will be automatically validated for this mission. 
The team must remove all their material from the arena before the end of this 25 minutes. During this time, the TA will calculate the final score for the team but will not share it with the members until they schedule an appointment to disassemble their robots in the presence of a E2A lab staff. Any time-overrun or damaged components (with incident report) will result in demerit points for the overall attempt.

## THE USER MANUAL 
The teams are to submit a user manual of not more than 5 pages for inspection before the mission is allowed to start. More information on the user manual will be discussed in G2 lecture. The user manual must include all the information necessary to help the TA to operate the robot and the map makers. The TA will quickly read the manual during the Setup Period and may read it during the mission if he/she thinks it is relevant.

## Scoring
Scoring is spilt into mission achievement based scoring, and time based competative scoring with a bonus component. Achievement objectives will take precendence over mission timing (e.g. Team 1 completed mission both station A and B delivery but required 20mins, while team 2 completed only station A delivery but took 10mins. In this scenario, team 1 will naturally get higher marks)

### Mission Achievement Based scoring
For each mission, teams can score up to 100 points with an additional 20 point bonus component (it is theoretically possible to get over 100 points). Refer to the Scoring Form. 
After all teams have completed the missions objectives, they will be ranked based on the time required to setup the material and finish the missions. 
The final score will be the best score of the multiple attempts (i.e., points from each mission and points from the time ranking) and bonus points.

### Time based competative scoring
Assuming equal completion of objectives, teams will be timed based on
- Time taken to hit deliver all payloads.
- Map closure. Timing will be taken once TA Verify full map closure.

Example 1.
The team starts the mission and takes 7 minutes to reach the delivery zone A. The robot then re-enters the maze to map out the maze and 2nd delivery zone B. Full map closure is achieved at the 12 minute mark.
- Mission time = 7 minute
- Map closure time = 12 minute

Example 2. 
The team starts the mission and takes 7 minutes to develop a complete map of the maze. The robot then enters the first delivery zone at the 12 minute mark.
- Mission time = 12 minute
- Map closure time = 7 minute

No timing is recorded if milestones are not achieved.  

# ROBOT REQUIREMENTS 

You are free to experiment and test any system or path planning algorithms that can complete the mission.

## The Robot
The robot platform must be a Turtlebot 3 Burger and provided RPI camera for the landmark detection. No other requirement for the robot. 

## The Markers
The team is allowed to place temporary markers or beacons (up to a max of 6 - 2 per delivery zone) to help the robot complete the mission. These markers must be installed and removed within the 25-minute time that the team have for the mission and are costed into the project budget. There is no additional time given for removal of map markers. All markers must not leave a mark/stain/damage on any map element. 


## ADDENDUM 1
Mission Rules Update

1. All members of the team, except for ONE designated operator must be behind the checking table for the mission time to start.

2. The mission time will start if 
a. The robot operator request that we start the time
b. The robot moves off the start line

3. The mission will end if any part of the system or terminal is interrupted by anyone for any reason. This include TA catching the bot to prevent damage to the bot or the maze. The team can then bring the robot back to the start line to restart the mission

4. You must screen record the RVIZ map for submission regardless if you are aiming for map completion. 

5. NEW - Forfeit competitive scoring

At the 14th minute mark (6 minute before the end of allocated slot), the team can now choose to forfeit on the competitive scoring component. You can then start the mission from the 1st delivery zone, and score partial points for 

- Robot successfully detects landmark
- Robot successfully orientates to face the delivery station frontally
- Robot executes delivery successfully
- At least 1 of the Ping Pong ball is delivered with full points awarded to successful delivery sequence of all 3 balls.

An updated scoring sheet with this "white flag" scenario will be uploaded on github closer to final assessment date.

6. NEW - Line following for maze solving not accepted

100% Line-following fully closed Rviz map will not be accepted for competitive scoring. This decision is made as these map are considered human-solved and not autonomously developed. This apply to any other human-solved solution for "Mapping completion time" competitive scoring.The system must then autonomously seek for the unmapped area and complete the map. 

7. NEW - Adjusted target firing delay sequence

For station A, ping pong balls must be delivered in a specific timing delay sequence to be classified as successful. Each team will have a different timing sequence to be released in week 7.

8. NEW - Demerit points for damaged components

There will be some negative scoring given to groups that have damaged provided components over the course run. The demerit point system will be released in week 7.

--End--





