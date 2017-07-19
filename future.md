RoboCup@Home Future
===================

RoboCup@home is a difficult competiton where robots must master a wide array of skills and be able to integrate them.
Even when a robot excels in one skill, it may still fail many tests if the excel skill is not well-integrated or when others skills of the robot are lacking. 
Sometimes, the best integrator or 3rd party software performs best. 

For the future of RoboCup@home, we should gather which recent advances in AI and roborics are applicable to our competition and see what tasks they might enable. 

The tasks in RoboCup@Home should be related to or simplified versions of real use-cases of service robots. 
Potential users of service robots are:
- Disabled people
- Elderly people
- Fully able people looking to ease their every day life. 

For some tasks, home robots already exist:
- Floor vacuum cleaning
- Floor mopping

These are not the tasks RoboCup@Home should focus on as they can be solved by much simpler robots. 
Equiping a humanoid robot with a vacuum cleaning for humans is nonsense, given the existing floor vacuum robots. 

Other housekeeping chores:
- Cleaning bathroom
- Cleaning furniture, dusting things off
- Laundry
what skills are needed to eventually accomplish these tasks?

Challenges
----------

### Speech and Person Recognition
SPR involves answering questions about the environment. The focus is ASR, NLP and a bit of NLU.
The environment is currently fixed, all knowledge of the environment (except the crowd) is static. 

An obvious extension of this challenge would be to have the robots gather knowledge about the environment. 
E.g. give the robots a minute to drive around and gather knowledge before answering questions, 
OR to ask a question and have the robot go around and figure out the answer, with a follow up question perhaps.

### Storing Groceries
Groceries are put on a table before the robts can start using them. Objects are put up easy to grasp.

Instead, just pour the groceries on the table directly from the bag or leave the groceries in the shopping crate. 

### (EE)-GPSR
Do everything as GPSR or do GPSR in a new environment with a limited time for learning that environment. 
Some tasks can be described in terms of GPSR but some not yet because the amount of detail involved, which is not easily conveyed by voice or text.

E.g. Help-me-carry is a chain of one-off commands. 
Storing groceries however requires doing a complex action (put object near something of the same/similar class) for a set of objects (all on the table). 


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
 - [ ] Recognize speaker by voice (accept command s only from owner)
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