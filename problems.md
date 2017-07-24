Problems
========

The current implementation of RoboCup@home, as I see it, has some problems. 

- High barrier of entry
- Little code reuse
- We want to test too much
- Robots are still inflexible
- Performance seems to be going don last couple of years

High barrier of entry
---------------------
New teams usually start from square one: they start building a robot and have to figure everything. 
ROS helps a bit to not reinvent everything but developing a RoboCup@Home capable robot is still a major undertaking. 

The standard platforms of course help in this regard, so I hope this is now maybe solved. 
Robots are still expensive though. 

Little code reuse
-----------------
Tightly related to the previous problem (high barrier of entry).
Even if all teams would have the same robot hardware, this is no guarantee that they share software, best practivces or other knowledge. 
Each team has their own research agenda, which they should have. 
The downside however is that for common problem, no common solution is used. 

For example: the current top-5 teams each employ some sort of world modeling system, all completely incompatible with one another. 
Another example: ROS move_base is nice but not perfect. Some teams are very very good at navigation. Why doesn't everybody learn from that or use that software as a baseline for next year?

Some hardware differentces exist, but the basics are quite similar for each of the OPL robots:
- Holonomic or differential drive base
- Laser range finder at 10-20cm from ground level. 
- Pan/tilt RGBD camera mounted high up
- Microphone mounted high up
- 1 (maybe 2) arm(s) with a parallel or scissoring gripper
- Arms, camera and microphone can optionally adjust height

You'd say some level of abstraction over this type of platform should enable much more software reuse and sharing?

###Possible fixes
Besides standardizing to ROS, impose more standardisation via defined interfaces. Best implementation is basis for next year, adjustment to interface are allowed. 

We want to test too much
------------------------
To be a capable home service robot, it needs a lot of skills. Testing all of those is simply too much, perhaps, especially when you want to test each separately and when you want more than 1 sample per robot (we currently take 3 samples/attempts). 

Besides hauling groceries, storing them, answering questions, executing random commands, helping in a restaurant and executing complex random commands, set a table, I want them to also:
- Sort my laundy
- Prepare food
- Clean my house
- ... ... ...
But the competition is only a few days, which are already so busy , there's no time to have a proper chat with another team. 

To make GPSR for fair, everyone should get the same tasks (this is boring for everyone). 
I also don't want to test just 3 commands, I want to **test dozens of commands**!

In comparison: the Amazon Robotics Challenge only tests 2 very similar tasks. Each of those is just one part of our challenges. 

### Possible fixes
- Less challenges
- Less repetition
- Only do GPSR (have queue of robots line up, one gets & executes a few commands and exits again to the back of the queue when told so. This way, challenges can be done in terms of GPSR and no more time is wasted on state-machines but actual algorithms)

Robots are still inflexible
---------------------------
Each challenge is still essentially a big state machine (at least in the teams I speak with). GPSRs (at least at TechUnited) is a set of state machines configured via a voice command. 
If something goes wrong, there are little problem solving skills. 
These problem solving skills (can be just replanning), are non-existent as far as I know. 

A way to test this is to simple mess with the robots and block their plans. 
This is already a category in EE-GPSR. Perhaps we should always give at least one command in this category. 

Performance seems to be going down last couple of years?
--------------------------------------------------------
I think this is due to the rulebook not being stable. Things need time to be finetuned and that takes time. 
This does mean the robots are not as flexible as they should though, that programming for tasks is still too much effort that is discarded when the rulebook changes. 

We should not be focussing on specific tasks but on generality (GPSR)