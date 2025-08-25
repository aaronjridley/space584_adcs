---
layout: spec
latex: true
---

# Space 584 - Fall 2025

## Course Overview

The goal of this class is to design, build, and test a cubesat-like observation platform that will take images of a remote object. 
In order to accomplish this, the cubesat will need an actual *attitude determination and control* system.
The point of this is to take a project from design through implementation, including thorough testing.  
Students form teams with diverse backgrounds to accomplish parts of the project, and then integrate everything together to create a whole platform.

## Locations and Times

Tuesday/Thursday 9:30 - 11:30 AM

2424 CSRB (Lab: B516 CSRB)

## Instructor Information

Prof: Aaron Ridley

Contact over Slack as a primary means of communication

## Course Objectives

The goal of the class is to take remote images of an object in as short of time as possible. This object will be placed on one side of the room. The observation platform will be placed into a 1D axis rotation device (testbed) and will be imparted with a given rotation rate. The platform must then slow the rotation rate, point in the correct direction, and observe the object. The testbed will have a Helmholtz coil around it, so there will be a known strong magnetic field. In addition, there will be sources of light at known locations (i.e., a star field) and a large hot source (i.e., the Earth or Sun) that can be used to determine orientation. The platform must operate autonomously, storing critical data locally and pushing it to a "ground-station". The goal mass is less than 1 kg, with a volume of 10 cm x 10 cm x 10 cm.A series of tests will determine the capabilities of the platform, including increasing initial rotations rates and placing the object at increasing distances from the testbed.  

## Course Structure

This class will primarily be lab sessions. I expect students to show up during class times to work with their fellow teammates. We will have weekly team meetings to make sure that the teams are keeping up with the plan.

We will have to order things online. You should work with the teaching staff to put in orders.  They will consolidate the orders and try to minimize shipping. If you absolutely HAVE to order something on your own (highly discouraged!!!), **the parts must be shipped to me/the class here at the University or you will not be reimbursed.**

## Goals

The project can be broken down into a bunch of different sub-projects than need to be completed and then brought back into a full system.

- Computer system (command and data handling system):
    1. Power system running CDH with a remove before flight pin
    2. CDH set up with accounts and remote connection capable
    3. All required software installed (e.g., python, C++)
    4. Computer system that can be used for communications

- Structure:
    1. Design + CAD drawings
    2. Build
    3. Fit test all components
    4. Iterate

- Sensors:
    1. Gyro working and calibrated
    2. Magnetometer working and calibrated
    3. IR camera working and fully characterized
    4. Star camera working and fully characterized
    5. Science camera working and fully characterized

- Controllers:
    1. Motor controller + motor working and fully tested
    2. Torque rod(s) working and calibrated

- Databases:
    1. Starfield database
    2. B-field map
    3. Sun/Earth size/location

- Algorithms:
    1. Derive starfield map from orientation and camera characteristics (should probably include rotation rate for streaking due to camera integration)
    2. Derive Sun/Earth (IR) image from orientation (should probably include rotation rate for streaking due to camera integration)
    3. Derive B-field from orientation
    4. Derive orientation from starfield image
    5. Derive orientation from IR image
    6. Derive orientation from B-field measurement
    7. Create kinematic model of system that will update spin rate and orientation as a function of time, given initial conditions and external torques
    8. Specify torque on system given voltage applied to torque rods
    9. Specify torque on system given PWM signal as a function of time (i.e., change of PWM in unit of time provides torque)
    10. Build entire control modeling system linking together all components

- Testbed:
    1. Rod plus mounts for payload structure
    2. Suspension mechanism (if magnetic, this must not strongly interfere with the magnetic field at the center of the Helmholtz cage)
    3. 1D Helmholtz cage that is capable of producing at least 3x Earth field at center 
    4. Starfield with unique spacing and brightness map
    5. Large heat source that is either close to the structure and opposite the starfield (Earth), or far away and within the starfield (Sun)
    6. Mechanism for spinning the payload to a specific rotation rate, then disengaging so that it does not drag (if magnetic, it must not strongly interfere with the magnetic field at the center of the Helmholtz cage)

- Documents:
    1. Requirements flowdown to each component
    2. System-level and sub-system-level block diagrams for both hardware and software
    3. Interface documents for both hardware and software

## Teaming Arrangements

There are enough required elements that it would be challenging to attempt to produce more than one to two complete systems. Therefore, teaming arrangements should be made on the different sub-project components.  For example, the following teams could be formed:
- Testbed development (this would probably be limited to the first half of the semester) + Structure (ME heavy)
- Algorithm development (CS heavy)
- Sensors and Controllers (EE heavy)
- Project manager who leads the team and is in charge of documentation (systems engineering heavy)

I could be very interesting to have two of each team. If one team runs into challenges, the other similar team can help debug.  Some of the teams could be more challenging than others, since they require more work, or there may be less expertise on the team. This should be considered when forming the teams. 

## Schedule

We have an extremely compressed schedule to fully design, build, test, and deploy this system.  Therefore, it is very important to have checkpoints along the way.  Once critical checkpoint is fall break, which is after 7 full weeks of the semester.  After fall break, there are only 5 full weeks and 1 partial week before the project needs to be completed.

Other checkpoints include:

- Second Tuesday in the semester (Sept. 2):
    1. Teams fully established, with roles/deliverables specified for each team member
    2. Team names if desired
    3. Lab space established

- Second Thursday in the semester (Sept. 4):
    1. Requirements flowdown to each component
    2. Initial list of components to use and purchase
    3. Initial designs 

- 4th Tuesday in the semester (Sept. 23):
    1. Star field and IR source placed with database created
    2. Testbed to a point where other teams can use information to move forward
    3. Algorithms outlined and well understood
    4. Easy sensors and motor controllers tested and understood; magnetic torquers designed
    5. Diagrams and Interfaces Documents due
    6. Official updates given

- Thursday before Fall break (Oct. 9):
    1. Testbed completed; structure rev 1 designed
    2. All cameras and sensors characterized
    3. Torque rods built; motors + wheels fully built and characterized
    4. Any PCBs designed
    5. Kinematic algorithm with (most) determination software and artificial torques implemented; control algorithm not working yet
    6. Official updates given
    7. Teaching staff release final testing procedure

- First Thursday in November (Nov. 6):
    1. Structure rev 2 complete
    2. Star + IR cameras providing data to ADCS system; algorithms can swap out hardware vs software solutions
    3. Torque rods validated and characterized
    4. Control algorithm should be able to stop initial spin and desaturate wheel using hardware
    5. If system is completely stationary, algorithm should be able to specify orientation with error estimate
    6. Science camera should have complete data pipeline (take image, store image, send image to ground); validation of camera performance
    7. Official updates given

- Thursday before Thanksgiving (Nov. 20):
    1. Goal for completion, so there is margin in schedule

- Dec. 4:
    1. Last day of class
    2. System will be officially tested at this point

- Day of the Final Exam (Tue. Dec. 16th):
    1. Final results must be turned in before this time.
    2. All equipment must be checked back in (in working condition).
    3. Lab spaces must be cleaned.

## Grading

The class will be graded using the following criteria:

(5 pts) Working science payload:
- Fully characterize camera, showing that it meets all requirements.
- Remote, automated operations of the camera with full delivery of images to ground station.
- Processing of data to show that it passes tests.

(10 pts) Working spacecraft including structure, power, comms:
- Structure that holds all components with a power system that operates the system for required amount of time.
- Meets required mass (< 1kg) and volume (10 cm x 10 cm x 10 cm).
- Communicates to ground station and provides all ADCS data.

(15 pts) Working attitude determination system components:
- Test results that show that individual components work as required.
- Components include gyro, magnetometer, IR camera, star camera.

(10 pts) Working control system components:
- Test results that show that individual components work as required.
- Components include a wheel and at least one magnetic torque rod.

(20 pts) Working ADCS algorithm:
- All components of the algorithm work as expected with both software and hardware in the loop.
- This algorithm can be broken down into certain modes, such as "reduce spin", "move to target", "desaturate wheel", etc.
- Each of these can be demonstrated to work if the algorithm as a whole does not work.

(15 pts)) Working testbed:
- Testbed that holds the spacecraft within an operational Helmholtz cage (producing a large magnetic field);
- provide an initial (specified) rotation on the system;
- reduced friction so that the system will freely rotate for some specified period of time;
- a starfield with enough stars placed with enough angles and brightnesses that the ADCS system can work as required; and
- a heat source placed as either the Sun or Earth.

(10 pts) Requirements Flow Down:
- Requirements flowdown don't have to be extremely formal, but should outline all of the design decisions and how they were made (i.e., complete!).
- This should start from a series of level-1 requirements and flow down into the subsystems that capture things like resolution, precision, accuracy, sensitivity, etc.
- This should be done for every aspect of the project - for example, how fast must an algorithm produce a starfield image given the orientation?

(5 pts) Diagrams and Interface Documents:
- These documents should clearly illustrate the electrical connections, mechanical connections, and software interfaces for the various components.
- These should be used as references for when building interfaces (of all kinds) for the system.

(3 x 2 pts) All updates:
- These are informal presentations throughout the semester that provide opportunity for feedback.
- They are also good milestones for completing each stage of the project.

(10 pts) Final Report:
- This should contain all of the results from the final tests and should be in the form of a report.
- The team should list their requirements and show/prove how each was met by the final performance.
- There is no formal length requirement, but there is an expectation that the report should be extremely easy to use to check that everything was completed (or not) to the team's satisfaction.
- If something was not completed or did not operate as expected, there should be some explaination as to why.

(5 pts) Team feedback:
- During the semester, there will be plenty of opportunity for discussion with me on the team members.
- I expect to have no real surprises on the team feedback at the end of the semester.
- Having said that, 5\% of your grade will be based on peer evaluations.

(5 pts) Lab Stewardship:
- All teams must treat the lab space with the upmost respect.
- It is expected that the teams keep their areas organized, respect other team’s (and other lab!) equipment, and clean up their area when they are done with the semester.


## Extras

Motors and motor controllers can be found here: https://www.pololu.com/

There are cameras for the Raspberry Pi with lenses.



