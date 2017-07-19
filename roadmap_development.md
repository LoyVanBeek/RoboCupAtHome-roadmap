How to develop a roadmap?
=========================

For roadmapping, I see two possible approaches: bottom-up and top-down. 
The bottom-up approach looks from what we have now and how that might evolve over time. 
The top-down approach looks at the final goals, the gaps with the current situation and tries to find stepping stones to cross the gap. 

For the top-down approach to work, the end-goal(s) need to be clear.
The bottom-up approach, like evolution is species, has no goal. 

Top-down approach
-----------------
For RoboCup@Home, I think a few goals need to be set in terms of what robots should be able to do. The distance between the stepping stones toward that goals wil be defined by what strides of evolution we can make a community and robotics community in general. 

To give concrete example: say a goal is to have robots make a sandwich. To prepare a sandwich in the same way a human does (there might be a single-task device that can do this more efficiently perhaps), a robot must be able to open a butter cup, wield knife, get a plate, get a slice of bread from a loaf, open a door or drawer to get a loaf of bread. 
Barely any of these skills are currently mastered by RoboCup@Home robots. 
The question is then: which of these prerequsite skills is the best or nearest stepping stone? 

I would like to first see a list of tasks RoboCup@Home robots should be able to do. 
Then, those tasks are split up in skills needed to implement each task. Some skills are employed in multiple tasks, and thus we get some sort of dependency graph, possibly of multiple layers.
Tasks are checked off when RoboCup@Home robots can do them. 
From the remaining tasks, we determine which have the most dependencies, i.e. which skill(s) enable the most other skills and tasks.

Bottom-up approach
------------------
RoboCup@Home teams are certainly not the only people developing capable robot hardware and software. The RoboCup challenges should keep an eye on other research and see what that might enable for RoboCup@Home.

For example: our robots usualy grasp something from the same, safe pose but this might fail. [GPD](https://github.com/atenpas/gpd) is a neural net that performs Grasp Point Determination. This enables more advanced manipulation. 
More advanced manipulation, however, is not a goal in itself. 
**RoboCup@Home should, in my opinion, always consider how a skill might be useful to the robot's users.**
A robot doing fancy tricks only is useless except for some entertainment. 

The RoboCup@Home committees cannot be the sole judge of usefullness though.
I think tasks and their division into skills have to be proposed by the teams.