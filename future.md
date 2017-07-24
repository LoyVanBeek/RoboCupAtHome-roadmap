RoboCup@Home Future
===================

RoboCup@home is a difficult competiton where robots must master a wide array of skills and be able to integrate them.
Even when a robot excels in one skill, it may still fail many tests if the excel skill is not well-integrated or when others skills of the robot are lacking. 
Sometimes, the best integrator or 3rd party software performs best. 

For the future of RoboCup@home, we should gather which recent advances in AI and robotics are applicable to our competition and see what tasks they might enable. 

The tasks in RoboCup@Home should be related to or simplified versions of real use-cases of service robots. 
Potential users of service robots are:
- Disabled people
- Elderly people
- Fully able people looking to ease their every day life. 

A major obstacle to home robot adoption is the price vs. value of robots.
There are currently no robots that can accomplish the same tasks a personal servant might be able to do. Robots in RoboCup@Home are generally not engineered to be very cost efficient. Focussing *price* on this might also be a topic for RoboCup@Home. 

Existing service robots and their tasks
---------------------------------------
For some tasks, home robots already exist:
- Floor vacuum cleaning
- Floor mopping
- Window cleaning
- Lawn mowing

These are not the tasks RoboCup@Home should focus on, as they can be solved by much simpler devices, which one would not call robots anymore. 

For example:
- Washing dishes: dirty dishes are cleaned by dishwashing machines. The dishes are to be put in by a human though. 
- Washing clothes: washing & drying machine. Not a mechanical human using a washboard and soap. Humans do need to sort clothes and move them in/out of the machine
- Floor cleaning: Not a mechanical human with a broom or vacuum cleaner, but self-driving vacuum cleaners.
- Cooking: prepackaged microwave food exists, but is of lower quality. One could also have food delivered or order take-out food. Not many people do this on a daily basis. 
- Transporting goods: multiple companies are getting into this (Fetch, Amazon, Magazino, ...). Arms not really needed. 

Note that all these devices can do only a single task. RoboCup@Home has so far focussed on more versatile, multifunctional robots. 

Potential service robot applications
------------------------------------
### Housekeeping chores
- Cleaning bathroom
- Cleaning furniture, dusting things off
- Laundry
    + Gathering all clothes in the house
    + Sorting/separating clothes
    + Putting clothes in/out washing machine
    + Ironing
    + Putting clothes in the closet

### Other home-related activities
- Cooking
    + Selecting a recipe
    + Chopping food

what skills are needed to eventually accomplish these tasks?

Challenges
----------

### Speech and Person Recognition
SPR involves answering questions about the environment. The focus is ASR, NLP and a bit of NLU.
The environment is currently fixed, all knowledge of the environment (except the crowd) is static. 

Possible extensions:
- Robots gather knowledge about the environment. E.g. give the robots a minute to drive around and gather knowledge before answering questions OR to ask a question and have the robot go around and figure out the answer, with a follow up question perhaps. 

### Help-me-carry
Help-me-carry involves various aspects of (social) navigation: following a human, collision-free autonomous driving, guiding a human, meanwhile opening a door. 

Possible extensions:
- carrying a big item together with a human (e.g. operator got new furniture instead of groceries)

### Storing Groceries
Groceries are put on a table before the robts can start using them. Objects are put up easy to grasp.

Possile extensions:
- Pour the groceries on the table directly from the bag or leave the groceries in the shopping crate/bag. 

### (EE)-GPSR
Do everything as GPSR or do GPSR in a new environment with a limited time for learning that environment. 
Some tasks can be described in terms of GPSR but some not yet because the amount of detail involved, which is not easily conveyed by voice or text.

E.g. Help-me-carry is a chain of one-off commands. 
Storing groceries however requires doing a complex action (put object near something of the same/similar class) for a set of objects (all on the table). 

### Restaurant
In the restaurant challenge, robots act like waiters. In previous years, robots learned tables by following a human who stopped at each table. In 2017, this is replaced by having guests simply wave at the robots


Recent advancements
-------------------

Recently, deep neural learning of deep neural networks has given various AI subtasks a boost. 
For example:
- Image recognition (VggNet, used in RoboCup by TechUnited in a transfer-learning setup)
- Face recognition (OpenFace, used by TechUnited)
- Human pose estimation (OpenPose, many RoboCup@Home teams by now)
- Gender estimation
- Emotion estimation

Some DNN applications not yet used (AFAIK) in RoboCup@Home are:
- Learning motor skills (Google/Deepmind, no RoboCup@Home teams AFAIK)
- Speech recognition (Google, no RoboCup@Home teams AFAIK)
- Visual question answering (e.g. more advanced SPR)
- Grasp pose determination

A major challenge in deep learning for robotics is the amount of data needed. 
Gathering millions or samples is often infeasible for robots. 
In some tasks, it might be interesting to see what robot can learn something the fastest, 
e.g:

 - [x] learn a new face
 - [ ] recognize/distinguish a new voice
 - [ ] learn a new object
 - [ ] learn a new motor skill
 - [ ] Learn a new object with a new word

Skills
------
General
- [ ] More flexible arena where stuff mores more and more

### ASR/NLP/NLU:
See https://github.com/RoboCupAtHome/RuleBook/issues/217

 - [x] 'Hear' short, single words E.g. "Yes" or "No"
 - [x] Hear and understand short, fully specified commands e.g. "Go to the kitchen"
 - [ ] Accept commands initiated by the user, not the robot asking for commands (less scripted scenarios)
 - [ ] Understand short, under-specified commands, e.g. "Go to a person"
 - [ ] Ask for more information in under-specified commands, e.g. "Go to a person" --> "Which person?"
 - [ ] Understand long commands
 - [ ] [Coreference resolution](https://en.wikipedia.org/wiki/Coreference), e.g. "The cookies are in the kitchen, bring me one"
 - [ ] [Coreference resolution ](https://en.wikipedia.org/wiki/Coreference) "Where are the cookies?" --> "In the cookie jar" --> "Bring it to me"
 - [ ] Information retrieval: Answering questions about (direct) environment
 - [ ] Information retrieval: answering general knowledge questions
 - [ ] Conversation initiated by human instead of robot
 - [ ] Robot can be called from a different room
 - [ ] Recognize speaker by voice (accept commands only from owner)
 - [ ] Differentiate between different speakers
 - [ ] Determine mood from voice
 - [ ] Be able to function in a noisy environment (e.g. a bar, party, etc)
 - [ ] ...

### Manipulation
See https://github.com/RoboCupAtHome/RuleBook/issues/76 & https://github.com/RoboCupAtHome/RuleBook/issues/205

 - [ ] grasp an object (basic)
 - [ ] grasp many objects (manipulating speed)
 - [ ] grasp an object besides the shelf (avoid obstacles when manipulating)
 - [ ] grasp a lying 'wide' object on the floor, like bottles (different postures to manipulate)
 - [ ] grasp an object which is very high or very low (manipulating space)
 - [ ] grasp a small object
 - [ ] grasp a strange object (like cloth)
 - [ ] Grasp something from a bin (with like 8-cm high borders)
 - [ ] Place the object face-forward (so you need bi-hand manipulation or at least re-grasp and plan)
 - [ ] Manipulate a switch
 - [ ] Manipulate a big object so you need 2 hands.
 - [ ] Arrange the groceries from the shopping bag into a shelf
 - [ ] Taking out the plastic bag from the trash bin.
 - [ ] Use a ladle to serve soup from a pot
 - [ ] Flipping omelette/meat
 - [ ] Whipping eggs or cream with a whisk (manually).
 - [ ] Mop the floor / Brush the floor (broomstick)
 - [ ] Pressing buttons in a keyboard (dialing phone, copy machine, calculator).
 - [ ] Handling digital (flat button) control panels (microwave, digital washing machine, conductive stove).
 - [ ] Picking something out of a box/bag
 - [ ] Grasp a soft cloth is hard enough...
 - [ ] Grasp a old-style phone horn
 - [ ] Wipe a table/shelf with a cloth (actual use case from @RobotRose)
 - [ ] Grasp a towel from a hanger
 - [ ] Pick up a pen
 - [ ] Pick up a pill
 - [ ] Pick up a tray/plate
 - [ ] Pick cutlery from the drawer
 - [ ] Grasp a moving object (with may be something simple for starters)
 - [ ] Sort clothes
 - [ ] Fold clothes

### Navigation
 - [ ] Follow through dense crowd (define 'dense')
 - [ ] Step aside in a corridor to make way for person in other direction


### Human interaction
 - [ ] Carry e.g. a table with a human
 - [ ] Help in/out of bed
 - [ ] Guide robot by hand