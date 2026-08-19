
# course plan
### Sessions 1 and 2: Programming in NetLogo (2.5h)

- Lecture (Gary): 10 min on LLMs and coding versus learning. LLMs make you a code reviewer not a code developer. We think it is better to learn to code first, then you can use an LLM to generate it for you to review it. It is not really fair to ask us to debug Chat GPT's code because we are teaching you not AI! Please be honest if you have used Chat GPT – the objective is not to get the answers right, but to do the learning needed so that you can get the answers right.
  - To do: can we detect who is using Co-pilot or Chat GPT by packet sniffing? Can we rig an alarm that goes off when Chat GPT is used?
- Instruction and exercises to allow people to work at their own pace.
- 10 min lectures on different aspects of programming, with 20 mins on exercise cards – somehow these exercises would build up to complete one task that they can run. We need FIVE 10 min lectures. Suggested topics:
  - Commenting and documentation
  - Sequence and selection (decision trees?)
  - Implementing mathematical equations (setting and changing variables; floating point arithmetic!)
  - Iteration (and that this with sequence and selection means you can do anything)
  - Lists and list processing (data types and how they have different ways of operating)
  - Procedures and reporters to split code up
- Just general programming for now, no specialist ABM stuff – that's tomorrow

# previous teaching
I’ve extracted and organised the editable slide text below. Text embedded within screenshots or images is excluded.

# Presentation text extraction

## Slide 1 — Programming in NetLogo

- Part 1
- Gary Polhill

## Slide 2 — Outline

- May continue into the afternoon
- Natural and formal languages
- Navigating the NetLogo Code Tab
  - A NetLogo ‘template’ model
- Writing your model structure in NetLogo – bulk of this talk
  - Agent breeds, Attributes, Relations
- Basics of algorithms
- Data structures

## Slide 3 — Natural & formal languages

*No additional editable slide text found.*

## Slide 4 — Natural and formal languages

- Natural languages are those spoken and written by humans and non-human animals
  - Meanings are determined by norms and context
  - Though natural languages have grammatical structure…
    - … We can still understand what is meant
- Formal languages (Chomsky 1956)
    - Have a (finite) set of symbols – cannot ‘mis-spell’
    - Have a (formal) grammar – must be adhered to
    - Usually have a formal semantics (Tarski 1944)
      - Relate meanings to mathematics

## Slide 5 — Examples of natural and formal languages?

*No additional editable slide text found.*

## Slide 6 — All programming languages are formal languages

*No additional editable slide text found.*

## Slide 7 — Naming things

- Computer code contains:
  - Things that make sense to the computer
    - Commands, built-in procedures, etc. (see the NetLogo dictionary)
  - Things that make sense to you
    - Names for variables, procedures, kinds of agent, etc.
    - These help you understand what the computer code is doing
    - The computer only cares that you use these names consistently
      - But has NO IDEA about what they might refer to in the real world

## Slide 8 — The NetLogo Code Tab

*No additional editable slide text found.*

## Slide 9 — The NetLogo Code Tab

- Navigation
- Find…
- Check
  - Happens automatically when switching tab and saving
- Procedures drop-down
- Indent automatically
- Code Tab in separate window
- Useful idea when collaborating:
  - Use preferences settings to ‘Show Line Numbers (in editor)’
    - Mac: NetLogo >> Settings
    - Windows: Tools >> Preferences
  - Disambiguates what you are referring to

## Slide 10 — The NetLogo Code Tab

- An empty model: create & save
- Notice the way we write a procedure
  - to name-of-procedure
  - end
- Comments start with a ; and continue to the end of the line
- Commands
  - clear-all – delete everything to start afresh
  - reset-ticks – set tick counter to 0 and initialize plots
  - tick – advance tick counter by 1
- Notice the colouring: ‘syntax highlighting’

## Slide 11 — Setup, Step and Go

- Add these buttons to the interface

## Slide 12 — Naming things

- Quick question
  - Ignore the comments
  - What are two names with meaning to humans rather than the computer in the empty template model?

## Slide 13 — Naming things

- Answer
  - setup – name of the procedure to call when you click a button you create that you expect to be clicked when the user wants to initialize the model
  - go – similar, but to execute one timestep
- You could call them anything you want, as long as you always use the same name in your program to mean the same thing
  - allez, gehen, carrots, xvc324

## Slide 14 — Naming conventions in NetLogo

- Use lower case for your names
  - In fact, NetLogo is not case-sensitive (boo), but upper case looks like you are ‘shouting’
- Begin names with an alphabetic character
- If your name has many words in it, you cannot use spaces to separate the words
  - Use a - (minus) – e.g. set-up-the-model
    - Known as ‘kebab case’
  - To do subtraction, you must put a space on both sides of the operator
    - Spaces can be part of a formal language’s grammar (as non-terminals)!
    - a-b – name of a variable
    - a - b – subtract the value of variable b from the value of variable a

## Slide 15 — Other characters in names

- Other characters (numbers and even punctuation) can be used in variable names in NetLogo
  - So long as you start with an alphabetic character
  - Recommended to avoid this, with a few exceptions:
    - Boolean variables (true or false) by convention end with a question mark ?
    - Some people use % at the end of percentage variables
- Accented characters can be used in variable names

## Slide 16 — Model structure in NetLogo

*No additional editable slide text found.*

## Slide 17 — Naming ‘things’

- ‘Things’ are objects and agents that are part of your model
- They have different classes or categories, which in NetLogo are called ‘breeds’
- breed [ plural singular ]
  - Declare that a category of things with plural and singular names exists in your model
  - Examples:
    - breed [persons person]
    - breed [mice mouse]
  - Note the square brackets to contain the plural and singular forms, which must differ
  - Breed declarations usually appear before setup

## Slide 18 — Mini model of disease infection

- Working on this today

## Slide 19 — Exercise

- Infectious disease transmission in a workplace
- Declare some breeds you think you might need using breed []
- Check the syntax
- Goal of the exercise:
  - Just to practice writing code and checking it is correct

## Slide 20 — (No) Answers!

- What breeds did you think of?
- Person
- Virus / Bacterium
- Workplace Room
- Door
- Desk
- Keyboard
- Phone
- Canteen
- Meeting Room
- Corridor
- Light Switch
- Toilet
- Are ontologies discovered or constructed? How context-sensitive are they?

## Slide 21 — Free classes!

- patches and turtles
- The ‘world’ on the Interface tab is divided up into square cells known as ‘patches’
  - N.B. ‘patch’ is terminology from ecology
  - Provides spatial locations for the agents
    - Can be useful for visualization – even in models without space
- All ‘agents’ in the model are called ‘turtles’
  - This dates back to the family of languages known as ‘logos’
    - Programs were written to instruct ‘turtles’ to draw pictures

## Slide 22 — Let’s create some of these agents

- create-breed [ ]
- Press setup

## Slide 23 — Let’s create some of these agents

- move-to, one-of, patches
- We can issue commands to each newly created person
- Here we use move-to to place an agent somewhere random
  - patches returns the set of all patches in the model
  - one-of chooses a random member of a set or list
- Try pressing setup now

## Slide 24 — Attributes

- Attributes of agents are data about them as individuals that are relevant to the model
- Various purposes:
  - State variables
    - How do you tell one agent apart from another?
    - What makes this agent different from other agents?
  - Useful computational variables
    - Save time recomputing values by storing them with the agent
      - General point: computing time/memory storage trade-off in computing

## Slide 25 — Attributes

- breeds-own [ ], turtles-own [ ], patches-own [ ]
- Add attributes of all agents using turtles-own [ ]
  - turtles-own [ n-legs]
- Add attributes of particular types of agent using breeds-own [ ]
  - persons-own [ education-level]
- Add attributes of patches using patches-own [ ]
  - patches-own [ coverage]

## Slide 26 — Attributes

- breeds-own [ ], turtles-own [ ], patches-own [ ]
- Add attributes of all agents using turtles-own [ ]
  - turtles-own [ n-legs]
- Add attributes of particular types of agent using breeds-own [ ]
  - persons-own [ education-level]
- Add attributes of patches using patches-own [ ]
  - patches-own [ coverage]
- Note the indentation:
- Indentation makes code more readable
- Develop an indentation style and use it consistently

## Slide 27 — Free attributes!

- Most often used attributes common to all turtles
- breed
- color
  - 75
- heading
  - 261
    - 0 is north/up
- hidden?
- label
  - "another turtle"
- shape
  - "default"
- label-color
  - 9.9
- pen-mode
  - "down"
- pen-size
  - 10
- size
- who
- xcor, ycor

## Slide 28 — Free attributes!

- All attributes common to all turtles
- breed
- color
  - 75
- heading
  - 261
    - 0 is north/up
- hidden?
- label
  - "another turtle"
- shape
  - "default"
- label-color
  - 9.9
- pen-mode
  - "down"
- pen-size
  - 10
- size
- who
- xcor, ycor

## Slide 29 — Default values

- If you want to change them, you have to write the code to do that
- Random heading
- Random color
- "default" shape
- xcor and ycor 0
  - Remember we had to use move-to to get something like what’s shown on the right
- Empty label
- hidden? false
- pen-mode "up"
- who is a number in order of creation

## Slide 30 — Default patch attributes

- pcolor
- plabel
- plabel-color
- pxcor
- pycor
- ask patch 0 0 [
- set plabel (word "patch " pxcor " " pycor)
- set plabel-color green
- set pcolor brown – 1
- ]

## Slide 31 — Exercise

- Add attributes to breeds – make them up for now
- In your disease transmission model, give your breeds some attributes that you think might be relevant – you can work with persons and files if you want to follow the example
- Remember:
  - turtles-own []
  - breeds-own [ ; note plural form]
  - patches-own []
  - Naming conventions (kebab case)
- You can use comments to explain the variable names
  - Everything after a ; to the end of the line is a comment
- Useful shortenings to save typing:
- n- “number of”
- p- “probability of” and/or “proportion of”
- pct- “percentage”
- Remember you can use ? for Booleans and % for percentages at the end of the variable name

## Slide 32 — My answer

- Yours might differ…
- ... but the example will continue using this

## Slide 33 — Now let’s initialize some of these attributes

- set, literals
- N.B. All attributes named using -own are 0 unless you provide a different value
  - Recommendation: initialize all attributes
- Literals are fixed values
  - Booleans: true false
  - Numbers: 0 1
  - Strings: "person"
  - Colours: pink blue green
    - See Tools >> Color Swatches
- Use set to set a variable to a value

## Slide 34 — Now let’s initialize some of these attributes

- ask, with [ ], count, breeds-here, comparison
- Use ask to tell a set of things to do something
- Use with [ ] to select a subset
  - Put a Boolean expression in the square brackets
  - Examples: =, >
- count tells you how many members of a set there are
- breeds-here tells you how many agents are on the patch

## Slide 35 — ‘Global’ attributes

- Sometimes it helps to have variables accessible anywhere
- Global variables are variables accessible from anywhere in the code
  - Not just turtles, patches, links
- Useful for
  - Saving time by storing data that are expensive to calculate and don’t change often
  - Properties of the ‘world’ rather than individual patches
  - Storing time series, filenames you don’t want changed by the user, etc.
- Some computer programmers frown on them
  - Code is more interdependent
- Declare them at the top of your code with globals [ ]

## Slide 36 — Relations

- Theory
- Mathematically, a relation specifies a mapping on a set (or from one set to another)
  - The relation does not have to hold for all members of a set
  - Various properties of relations (transitivity, symmetry, reflexivity, etc.)
  - Relations can be thought of as a matrix of Booleans
    - If the row set member has the relation with the column set member then the matrix entry is true, otherwise it is false
    - In a symmetric relation, only a triangular matrix is needed
- Examples: greater-than (numbers), parent-of (people)

## Slide 37 — Relations in NetLogo

- directed-link-breed [ ], undirected-link-breed [ ]
- Relations are called ‘links’ in NetLogo
  - Generally used for social networks
  - All are irreflexive (you cannot have a link between a turtle and itself)
- You can define two different kinds of so-called ‘link-breed’
  - Symmetric relations: undirected-link-breed [ plural singular ]
    - Example: undirected-link-breed [ siblings sibling ]
  - Not (necessarily) symmetric relations: directed-link-breed [ plural singular ]
    - Example: directed-link-breed [ parents parent ]
    - N.B. not antisymmetric – if A is the project manager of B and B is the project manager of A, A and B are not the same person (there could be two different projects)

## Slide 38 — Exercise

- Declare some link breeds in your workplace infection model
- What relations might be important in a workplace?
- Are they directed or undirected?

## Slide 39 — One Answer

- Some link breeds in the example workplace infection model

## Slide 40 — What is an agent?

- Revisited
- In NetLogo, lots of things are thought of as agents
  - Turtles, Patches, Links and various Breeds and Link Breeds we declare
- From a software perspective, what makes something an ‘agent’?
  - Autonomy, Goals, Reasoning, Acting on behalf of a human, Special protocols for interaction, …
  - Software agents and agent-based models are separate domains of endeavour
- Pragmatism is a philosophy!
  - What works in NetLogo…
  - One thing that doesn’t work: getting hung up for ages on what an agent is!

## Slide 41 — ‘Reified’ relations

- link-breeds-own [ ]
- You can give relations attributes using link-breeds-own [ ]
  - For example:
    - friends-own [ friendversary ; date friendship was formed]
- For computer scientists, this is known as ‘reification’ of a relation
  - Not anything to make an issue of in NetLogo

## Slide 42 — Default link attributes

- In NetLogo, links already have some attributes
- Commonly used:
  - end1, end2, hidden?
- Other visualization:
  - color, shape, thickness
  - label, label-color
- Others:
  - breed, tie-mode

## Slide 43 — Let’s create a workplace social network

- Management hierarchy
- Lots of ways to do this
  - The nw extension is very helpful here
- We’re going to do this by hand – a bit advanced
  - Don’t worry if you can’t keep up…
- Think from the perspective of an individual. For each person
  - Who are the potential managers?
    - If I’m not managed yet, and there’s a potential manager, choose one of them
  - Who are the potential people I could manage?
    - If I don’t manage anyone and there’s someone needing managed, choose one of them

## Slide 44 — Let’s create a workplace social network

- Management hierarchy
- If we want a group of agents to do anything, we use ask

## Slide 45 — Let’s create a workplace social network

- Management hierarchy
- The potential managers are those who already manage somebody
- The let command creates a temporary variable for us and assigns it a value
  - We’re creating a temporary variable called management
- other persons is the set of persons that isn’t the agent running the code
- with [ ] lets us choose a subset
  - directed links use out-breed-neighbors to get the agents at the ‘head’ of the arrow
  - any? is true if there’s at least one member of the set

## Slide 46 — Let’s create a workplace social network

- Management hierarchy
- if [ ] executes some instructions if a Boolean expression is true
- We want to choose a manager for ourselves if:
  - We’re not already managed by someone
    - not any? in-manage-neighbors
  - and there’s someone who could manage us
    - any? management
- To make the directed link from another agent to us, we use create-breed-from
  - Here we use one-of to choose a random member of management

## Slide 47 — Let’s create a workplace social network

- Management hierarchy
- Now we need to find persons who aren’t managed by anyone and aren’t a member of the management team
- We use other persons with [ ] like before to store potential people to manage in a temporary variable using let
  - Not managed by anyone:
    - not any? in-manage-neighbors
  - Not in the management team
    - not member? self management
- self is the agent executing the code
  - Who is executing the code in the with [ ] ?

## Slide 48 — Let’s create a workplace social network

- Management hierarchy
- Finally, if there’s anyone not managed we can use create-manage-to to manage a random one-of them
- An additional condition (optional)
  - We don’t already manage someone
- Note:
  - Using temporary variables management and unmanaged saved us reconstructing the sets every time we wanted to refer to them
  - More readable
  - Saved computing time

## Slide 49 — Let’s create a workplace social network

- Management hierarchy
- Want to show off the network?
- layout-radial command takes a set of agents (persons) and a set of links (manages), and automatically arranges the network starting with one agent at the centre
  - We want to start with someone who is not managed
    - one-of persons with [ not any? in-manage-neighbors]
- Note use of visualization to help check code is working

## Slide 50 — Basics of Algorithms

*No additional editable slide text found.*

## Slide 51 — Basics of algorithms

- Computing anything computable
- Let’s look again at that code to build the ‘manages’ network
- There are three important things that all programming languages need to provide
  - Sequence
  - Selection
  - Iteration

## Slide 52 — Basics of algorithms

- Sequence
- A sequence is doing on thing, finishing it, moving on to the next thing
  - There can be one or more instructions in a sequence
- Where are the sequences in the code?

## Slide 53 — Basics of algorithms

- Sequence
- Where are the sequences in the code?
  - Define a temporary variable
  - Check and create a manage link
  - Define another temporary variable
  - Check and create another manage link
- 1
- 2
- 3
- 4

## Slide 54 — Basics of algorithms

- Some other sequences
- Get the set of persons
- Calculate Boolean expression
- Calculate Boolean expression
- Create a manage link
- Get the set of persons
- Calculate Boolean expression
- Calculate Boolean expression
- Create a manage link

## Slide 55 — Basics of algorithms

- Selection
- Selection is allowing the execution of a sequence of code under restricted conditions
- Where do we have selection in this code?

## Slide 56 — Basics of algorithms

- Selection
- 1
- 2
- Where do we have selection in this code?
  - Persons that are not the asked agent
  - Assignment to a set under restricted conditions
  - Creating a manage link under restricted conditions
  - Persons that are not the asked agent
  - Assignment to another set under restricted conditions
  - Creating a manage link under restricted conditions
- 3
- 4
- 5
- 5

## Slide 57 — Basics of Algorithms

- if – else if… – else
- We have already seen if [ ]
- We use ifelse [ ] [ ] when we want to do something different if the condition tested is false
- We can use (ifelse [ ] [ ] … [ ]) when there are multiple conditions to test
  - Always start with the more specific tests
- In the example on the right, we want to stop our model when:
  - Everyone is immune – note all?
  - No-one is infected
- But we want to keep going with the rest of go otherwise
  - So the else sequence is empty
    - And we put a comment in to note that this is deliberate

## Slide 58 — Basics of algorithms

- Iteration
- Iteration is repeatedly executing a sequence
- Where do we have iteration in this code?

## Slide 59 — Basics of algorithms

- Iteration
- Where do we have iteration in this code?
  - We are asking each person to do something

## Slide 60 — Basics of algorithms

- Iteration
- Where do we have iteration in this code?
  - We are asking each person to do something
  - We also need to find persons with a certain property
    - When one iteration appears in the context of another this is referred to as ‘nested iteration’
    - Note that with [ ] does selection and iteration in one command!

## Slide 61 — Basics of algorithm

- Nested iteration
- Why do we care about nested iteration?

## Slide 62 — Basics of algorithm

- Nested iteration
- Nested iteration affects how the estimated run-time of the algorithm performs
  - This is the basis of much of the theory of computing science
  - How long will our algorithm take as the number of persons increases?
    - Nested iteration means the time taken grows with the square of the number of persons
      - Suppose it takes a microsecond to run the nested code
        - For small numbers of agents, it hardly matters
        - But for a million agents we need a million million microseconds (~11.5 days!)
    - It also means the nested code is the first place to look to speed things up
- As well as computing time, theory of computing science is concerned with storage space

## Slide 63 — So how does the algorithm perform?

- Smoothed curve of time taken in seconds versus n-persons
- Series: t

## Slide 64 — Basics of algorithms

- Iteration with repeat [ ]
- If you know how many times you will need to do something you can use repeat [ ]
  - Here’s a silly example and its output

## Slide 65 — Basics of algorithms

- Iteration with while [ ] [ ]
- If you don’t know how many times you want to do something, you can use while [ ] [ ] to repeat some code (in the second square brackets) while a Boolean expression (in the first square brackets) is true
  - It’s then important that it’s possible for the Boolean expression to be false
    - e.g. The repeated code will eventually change the truth of the Boolean expression
  - Tools >> Halt is your friend
    - Try it now – the screenshot shows how long it tool me to do Tools >> Halt after clicking the step button with nine n-persons

## Slide 66 — Data structures

*No additional editable slide text found.*

## Slide 67 — Data structures

- Literals
- We have already encountered the concept of literals in some of the example code we’ve been working with
  - Numbers: 0, -4, 7.5, pi, e
    - Careful when pasting negative numbers from other sources where a - might be autocorrected into an ‘M dash’ –
  - Colours: use names (grey, black, orange, yellow, etc.) or numbers in the range [0-140[
  - Booleans: true and false
    - For programmers in other languages 1 ≠ true and 0 ≠ false
  - Strings (comp. sci. speak for text): put them in double quotes (not “smart” quotes – careful when pasting from other apps)
    - "hello world"
- NetLogo colours literals in brown in the Code tab

## Slide 68 — Data structures

- Agent sets
- We have also encountered agent sets in code examples
  - persons, turtles, patches, manages, links
  - Using with [ ] to get a subset of them
- There are other tools provided by NetLogo to get agent sets
  - neighbors, neighbors4 – access patches around a patch or turtle’s location
  - in-radius – restrict an agent set to those within a given Euclidean distance
  - turtles-here, breeds-here – all the turtles (of a particular breed) on the current patch
  - turtles-on, breeds-on – all the turtles (of a particular breed) on a specified patch
  - turtle-set – make a set union of various agent sets

## Slide 69 — Making the colleagues network

- Using Social Circles algorithm

## Slide 70 — self and myself

- Don’t worry, takes some getting used to…
- self
  - The agent currently executing the code
- myself
  - The agent executing the code that has got the agent to execute the currently running code

## Slide 71 — self and myself

- Don’t worry, takes some getting used to…
- self
  - The agent currently executing the code
- myself
  - The agent executing the code that has got the agent to execute the currently running code
- We hate it too!

## Slide 72

*No editable slide text found.*

# Presentation text extraction

## Slide 1

### Welcome

## Slide 2

### Overview of the day

Four guest lectures  
Modelling decision-making using algorithms from Artificial Intelligence  
Validation in agent-based models: what can we learn from Neural Networks?  
Understanding ontologies and their application to agent-based modelling  
What’s ‘wrong’ with FEARLUS?

## Slide 3

### Outcomes

There are various easy-to-use algorithms from AI literature that can be used to simulate decision-making in agents  
… and some that aren’t so easy!  
Validation isn’t just about fit-to-data  
Greater descriptive power in ABMs mean we need to think about ontologies  
There’s More Than One Way To Do It (Perl motto)

## Slide 4

### Modelling decision-making using algorithms from Artificial Intelligence

Gary Polhill  
From work with: Nick Gotts, Tony Craig, Noelia Sanchez-Maroño,  
Amparo Alonso-Betanzos, Oscar Fontenla-Romero

## Slide 5

### Outline

Simulating Decision-Making  
Decision Trees  
Case Based Reasoning  
Neural Networks

## Slide 6

### Decision-making

Utility functions and constraints  
Still used in some ABMs  
Heuristic rules  
Linear and Mathematical Programming  
Algorithms from Artificial Intelligence  
BDI Logics  
Case-Based Reasoning  
Rule Based Systems  
Memetic Algorithms  
Neural Networks  
Decision Trees

## Slide 7

### Decision trees

A decision tree is an acyclic directed graph (of which a tree is a special case) data structure in which the nodes are tests, and the arcs correspond to results of the ‘from’ test  
A single ‘root’ node is the start of the decision process  
‘Leaf’ nodes represent the final decision  
There are various decision tree learning algorithms that can map explanatory variables onto a response variable  
e.g. C4.5 [Quinlan, 1993]  
Essentially, these search for orthogonal hyperplanes in the explanatory variable space that optimally separate the response variable into discrete classes

[< 5 km]  
[> 300 km]  
Car  
[raining]  
Bus  
[in a hurry]  
Cycle  
[ticket < €100]  
Walk  
Train  
Plane

## Slide 8

### Advantages and disadvantages

Issues  
Decision tree structure can be sensitive to source data  
Numbers of different learning algorithms, each of which can generate different tree structures  
Plus algorithms themselves have parameters that affect structure  
All the usual problems with calibration and validation  
BUT  
Results are easy to explain  
Structure of a tree easy to understand  
Decision tree can be discussed with experts  
So:  
Don’t take the results of the learning algorithm at face value  
Check with field researchers and theorists and adjust if need be

## Slide 9

### Case study

## Slide 10

### Decision trees and norms

Injunctive norms  
You receive an instruction to behave in a particular way  
Descriptive norms  
You observe others and do what they do  
Questions are asked about these in a questionnaire  
IF norms are an explanatory variable in a decision tree, then use model state to determine node result  
Injunctive: Has the agent received a message telling it to behave more pro-environmentally?  
This means one ‘meta’ pro-environmental behaviour is to tell others to behave pro-environmentally  
Descriptive: Are most of the agents in the agent’s social network behaving pro-environmentally?

## Slide 11

### Netlogo model implementation

## Slide 12

### Issues developing decision trees

Some concern about how to do this without abusing measurement theory  
nominal – numbers can only be compared for equality (order is irrelevant – e.g. bus numbers)  
ordinal – numbers can be compared for order, but strictly speaking arithmetic operators should not be used (e.g. positions in a race, and Likert scales)  
cardinal – can use arithmetic operators (e.g. kilometres)  
Preprocessing  
Use questionnaire responses directly, or processed variables?  
Feature selection?  
Discretisation?  
Clustering? (Research suggests there are clustering algorithms that can work with ordinals)

## Slide 13

### A collective mind?

An important theoretical issue with decision trees is what exactly they represent…  
They are learnt from the responses of several individuals  
As such, they summarise collective responses  
Heterogeneity of agents determines path through tree  
Agent based models assume individual decision-making  
Do decision trees detract from agent-ness?  
Many ABMs use the same algorithm for all the agents anyway…

## Slide 14

### Case-Based Reasoning

Psychologically-plausible algorithm for decision-making by experts  
‘Episodic Memory’ of experiences. Each experience:  
Summary of the situation  
Decision taken  
Outcome  
New situation:  
Pattern match against experienced situations  
Compare outcomes of various decisions of matching experiences

## Slide 15

### The case base

Episodic Memory  
Single Episode

Data structure with ‘relevant’ attributes:  
Social  
Environmental  
Individual

Information about chosen option  
Could be a simple ID  
Could be a complex plan or series of actions

Again, ‘relevant’ data  
Potential issue of attribution  
Was this really because of the action?  
Comparison operator needed  
Multidimensional outcomes lead to ‘trade-offs’

Situation  
Action  
Outcome  
Situation  
Action  
Outcome  
Situation  
Action  
Outcome  
Situation  
Action  
Outcome  
Situation  
Action  
Outcome  
Situation  
Action  
Outcome

## Slide 16

### Deciding what to do

salience can adjust trade-off line  
trade-off  
Multidimensional outcomes require a trade-off function to choose preferred action  
Experiment with new action if no option is good enough  
Or seek advice…

outcome attribute 2  
*  
X  
match  
Expected  
Situation  
Minimum acceptable outcome attribute values  
X  
outcome attribute 1  
X  
*  
X

## Slide 17

### Case study

## Slide 18

### Motivation

Following CAP reform in the EU, subsidies to farmers are shifting away from production towards environmental goods  
Farmers, however, still have a predominantly productivist mindset (Burton/Wilson, various)  
… more so now food security is on the agenda  
Subsidies are only a part of a number of factors influencing farm decision-making  
… not all of which are profit-based  
What kinds of incentive scheme might work under different circumstances?  
Use ABM as ‘typifications’ (Boero & Squazzoni, 2005) to answer ‘in principle’ questions—requires 000s of runs  
FEARLUS (Polhill/Gotts et al., various) for ABM of LUCC  
Couple with SPOMM (Moilanen (2004), but with enhancements to allow multiple species and interaction among them) to model species

## Slide 19

### Coupling FEARLUS and SPOMM

## Slide 20

### Case-Based Reasoning Advice Land Manager

[Mean Estate Profit per unit area >= Profit Aspiration  
& Mean Net Approval from Managers not Disapproved of >= Social Aspiration]

Keep the same Land Use on all Parcels

For each Parcel:

[Rand(0 <= X < 1) <= Imitative Probability]

Use imitative Strategy  
Use non-imitative Strategy

[Rand(0 <= X < 1) <= CBR Probability]

Expected State = {Parcel, Last Climate, Last Economy}

For each Land Use:

Best Case = Case Base (best match for Expected State, Land Use)

[No Case found]

Advice List = Advice Strategy (neighbour list)

[Advice List empty]

Advisor = Remove first item from Advice List

Land Use of Parcel = Random selection among those with maximum Estimated Utility

Best Case = Advisor Case Base  
(best match for Expected State, Land Use)

[No Case found]

Estimated Utility (Land Use)  
= Profit Outcome (Best Case) * Profit Salience  
+ Social Outcome (Best Case) * Social Salience

Estimated Utility (Land Use)  
= Profit Aspiration * Profit Salience  
+ Social Aspiration * Social Salience

## Slide 21

### Experiment setup

Land Managers (farmers) use Case Based Reasoning (Aamodt & Plaza) to choose Land Uses for their Land Parcels  
Make no change if profit aspirations for the whole farm met  
Six land uses: Two main types ‘A’ and ‘G’ in three levels of intensity  
AL1 (low intensity), AL2, AL3; GL1, GL2, GL3 (high intensity)  
Low intensity land use tend to be better for biodiversity, but less profitable  
Ten species: A1, A2, A3, G1, G2, G3, G4, G5, G6, C  
C outcompetes G1, G2 and G3 after 3 years

## Slide 22

### Parameters explored

Incentive scheme:  
Reward for an activity, or reward for an outcome  
Reward farmers individually, or reward extra if neighbours do the same  
Key parameter: How much to reward?  
And how much will that cost overall?  
Market for crops:  
Variable or flat  
Farmers’ aspirations  
High or low  
Operating costs  
High or low

## Slide 23

### Results: GAM

Generalised Additive Models (Hastie, 1990) were used to fit functions to the relationship between the incentives offered by a scheme and the biodiversity outcome (measured by species richness)  
Incentives are difficult to compare across different rules for implementing a scheme  
Expenditure, though an outcome of a scheme, may offer a way of making the comparison  
Think in terms of: ‘if you are incentivising in this way in this context, you will need to allow this much for the budget’  
GAMs tend to overfit data, but are still useful for identifying trends

## Slide 24

### Some expectations

Biodiversity

Naïvely, one might expect more money always means more biodiversity  
But there’s a point below which the incentive is too small to have any influence  
And there’s a limit to the biodiversity achievable  
In general, it doesn’t seem unreasonable to expect biodiversity to be a monotone increasing function of incentive

Incentive

## Slide 25

### Some results seem to follow this model

Activity, variable market, low costs, low aspirations  
Activity, flat market, low costs, high aspirations

## Slide 26

### More interesting are those that don’t

Biodiversity peaks and then declines…  
One explanation for Activity cases is that the government isn’t asking the farmers to do the right thing  
Wallis de Vries et al. (1998) found that reducing grazing intensity had a negative impact on biodiversity  
Not so here, it’s more a problem with the decision making  
Satisficing means an incentivised activity won’t be adopted no matter how much is offered for it  
Aspirations are at the farm scale, allowing cross-subsidy of loss-making activities. (cf. Identity)  
Untried activities are assumed to meet aspirations, so won’t be adopted if farmers have experienced better activities

Cluster-Activity, flat market, low costs, high aspirations

## Slide 27

### Decision tree analysis

Below a threshold of expenditure, the market drives outcomes, and species richness is lower  
Above the threshold, policy is the main driver  
Outcome based incentives seem more robust to other influences (market, input costs, aspirations)

## Slide 28

### Other approaches

Memetic algorithms  
‘Evolve’ decision-making using GAs / GP  
Manson (2005, AgEE) SYPRIA model  
Beliefs Desires Intentions  
Based on Dennett’s (1987) intentional stance  
Contrast with physical and biological stances for explaining behaviour  
Assume rationality (believe your beliefs and their logical consequences)  
Ascribe beliefs, desires and intentions and use them to predict behaviour  
Balke & Gilbert (2014, JASSS)  
Rule Based Systems  
Bharwani (2006, KnETs)

## Slide 29

### Neural networks

“Connectionism” in AI  
‘Symbolic’ AI seen as ‘brittle’  
Need symbols for everything  
In machine learning, not clear how to treat an unfamiliar symbol  
Neural networks not just about AI  
Will be clearer why I focus on NN in next talk

NN  
AI

## Slide 30

### Real vs artificial neuron

Response  
Dendrites  
Signal  
output∈ [0, 1]  
Axon  
weight ∈ ℝ  
input ∈ ℝ  
([0, 1] if another neuron)  
output is a nonlinear function of weighted input  
Stimulus

## Slide 31

### Neural network

Network (directed graph) of artificial neurons (units)  
‘Topology’ is the structure of the network  
‘Feed-forward’ if graph acyclic  
‘Layered’ if units are arranged in layers with full connectivity between successive layers, and no other connections  
‘Hidden’ layers and units are those that are only connected to other units (not input or output)

Input  
Layer  
Output  
Layer  
Hidden  
Layers

## Slide 32

### Equations

Notation  
excitation of unit j  
output of unit i  
weight from unit i to unit j  
‘bias’ weight to unit j  
Excitation  
Nonlinearity  
(differentiable)

## Slide 33

### Points to note

Input units typically have outputs set to data values  
Bias weight can be simulated as a unit connected to all other (non-input) units with an output always = 1  
Weights are the parameters of the neural network  
For a given topology  
Each unit separates its input space into two halves  
Hyperplane ‘manifold’

Bias unit  
Unit has output = 1 on one side of the plane  
Bias weights

## Slide 34

### Training

Training NN is finding values for weights  
Various options  
Backpropagation  
Assumes ‘desired behaviour’ known  
Gradient descent – requires differentiable functions  
Genetic algorithms  
Reinforcement learning  
‘Training’ signal comes from the environment  
Most suited to ABM…  
Could not (quickly) find an example…

[Rumelhart et al. 1986]

## Slide 35

### Examples

Curran & O’Riordan (http://jasss.soc.surrey.ac.uk/10/4/3.html)  
Train using GAs  
Altaweel et al. (http://jasss.soc.surrey.ac.uk/13/1/15.html)  
Use NN to simulate social structure  
Wei et al. (http://jasss.soc.surrey.ac.uk/16/3/10.html)  
Train using backpropagation

## Slide 36

### Conclusion

Algorithms from AI are used widely in ABM  
Decision trees  
Quick, transparent, empirical  
Need data, fixed structure, ‘collective mind’  
Case-based reasoning  
Agents learn from experience  
How to initialize? Computational efficiency?  
Neural networks  
Not widely used  
Opaque (Reich http://jasss.soc.surrey.ac.uk/7/4/4.html)

## Slide 37

### Discussion points

Contrasting views of rationality  
Economics vs. BDI  
Other approaches: where is rationality? Should we care?  
How would you choose decision-making algorithm?  
What would you base your choice on?  
Imagine MIT had a server that you could access to simulate human decision-making perfectly  
Would you use it?  
What data do you think you’d have to send it?  
Connectionism vs. rule-based systems  
Emergent intelligence?  
What approach would you adopt to simulate human intelligence?  
What criteria would you use to make the assessment?  
Which of those are scientific, which pragmatic?

## Slide 38

### Further reading

Izquierdo, L. R., Gotts, N. M. and Polhill, J. G. (2004) Case-based reasoning, social dilemmas, and a new equilibrium concept. *Journal of Artificial Societies and Social Simulation* 7 (3), 1. http://jasss.soc.surrey.ac.uk/7/3/1.html

Polhill, J. G., Gimona, A. and Gotts, N. M. (2013) Nonlinearities in biodiversity incentive schemes: A study using an integrated agent-based and metacommunity model. *Environmental Modelling and Software* 45, 74–91. (doi:10.1016/j.envsoft.2012.11.011)

Sánchez-Maroño, N., Alonso-Betanzos, A., Fontenla-Romero, O., Brinquis-Núñez, C., Polhill, J. G., Craig, T., Dumitru, A. and García-Mira, R. (2015) An agent-based model for simulating environmental behavior in an educational organization. *Neural Processing Letters* 42 (1), 89–118. (doi:10.1007/s11063-014-9390-5)

Polhill, J. G., Craig, T., Alonso-Betanzos, A., Sánchez-Maroño, N., Fontenla-Romero, O., Dumitru, A., García-Mira, R., Bonnes, M., Bonaiuto, M., Carrus, G., Maricchiolo, F., Fornara, F., Ilin, C., Steg, L., Ruepert, A. and Keizer, K. (2017) Interactions matter: Modelling everyday pro-environmental norm transmission and diffusion in workplace networks. In Alonso-Betanzos, A., Sánchez-Maroño, N., Fontenla-Romero, O., Polhill, J. G., Craig, T., Bajo, J. and Corchado, J. M. (eds.) *Agent-Based Modeling of Sustainable Behaviors*. Cham, Switzerland: Springer. pp. 27–52. (doi:10.1007/978-3-319-46331-5_2)

Sánchez-Maroño, N., Alonso-Betanzos, A., Fontenla-Romero, O., Polhill, J. G. and Craig, T. (2017) Empirically-derived behavioral rules in agent-based models using decision trees learned from questionnaire data. In Alonso-Betanzos, A., Sánchez-Maroño, N., Fontenla-Romero, O., Polhill, J. G., Craig, T., Bajo, J. and Corchado, J. M. (eds.) *Agent-Based Modeling of Sustainable Behaviors*. Cham, Switzerland: Springer. pp. 53–76. (doi:10.1007/978-3-319-46331-5_3)

---
Text embedded in screenshots is marked **OCR** and may contain minor recognition errors.

## Slide 1: Programming in NetLogo

Part 2

Gary Polhill



## Slide 2: Outline

Continued from this morning

Reporters  
Working with strings  
Working with lists  
Boolean expressions  
Mathematical expressions  
Procedures  
Moving agents



## Slide 3: Reporters



## Slide 4: Reporters

Main points

Sometimes we want to use code repeatedly in different parts of the program  
It’s generally seen as ‘bad form’ to cut and paste code  
Why do you think that might be?



## Slide 5: Reporters

Main points

Sometimes we want to use code repeatedly in different parts of the program  
It’s generally seen as ‘bad form’ to cut and paste code  
Why do you think that might be?  
You won’t remember everywhere you cut and paste it if you need to correct a mistake  
Reporters are code that do something useful and return a value  
Built-in reporters are syntax highlighted in purple



## Slide 6: Reporters

How to make a reporter

A reporter always begins with to-report and ends with end  
After to-report, you give your reporter a name  
Then you write some code to calculate the useful value  
If you cannot do this in a single expression  
And you ‘return’ it to the ‘calling’ code with report value  
For example, suppose our model changed the managers (e.g. due to staff turnover)  
Rather than always typing persons with [

```text
any? out-manage-neighbors
```

] we can create a reporter called management-team  
This can also help with making code more readable  
Notice that the reporter now appears in the Procedures drop-down menu on the code tab

### Text embedded in images (OCR)

```text
Code
© ; v | —— | indent automatically
74 ask fp setup
75 fag: management-team Ra Qohay
76 m0 192nembe ___. f collea
77 ]) in-radius colleagues-r [
78 set color yellow
79 ]
80—tsd
81
82 reset-ticks
83 end
84
858 to-report management—team
86 report persons with [
87 any? out-manage-neighbors
88 ]
89 end
```



## Slide 7: Reporters

Providing reporters with data

Sometimes a reporter needs some data before it can calculate the value  
The calling code can provide that data as ‘arguments’ to the reporter  
These arguments become temporary variables the reporter can use for its calculations  
When writing your reporter, you give the arguments as a list of variable names in square brackets after the name of the reporter

### Text embedded in images (OCR)

```text
to-report intersection [ set1 set2 ]
let common (turtle-set nobody)
ask set1 [
if member? self set2 [
set common (turtle-set self common)
]
]
report common
end
```



## Slide 8: Exercise

Whom do we both know?

Write a reporter that will tell you the colleagues a person has in common with another person given as argument  
Hint: The intersection reporter (previous slide and top-right) should help  
You should be able to write the code on the right in setup (after creating the colleagues network) to test it  
And learn count and with-max while you are at it!

### Text embedded in images (OCR)

```text
ask one-of persons with-max [
count colleague-neighbors
; someone with lots of colleagues
) [
set color yellow
ask one-of colleague-neighbors with-max [
count colleague-neighbors
; one of their colleagues with
; lots of colleagues
) [
set color yellow
ask common-colleagues myself [
set color red
]
]
]
to-report intersection [ set1 set2 ]
let common (turtle-set nobody)
ask set1 [
if member? self set2 [
set common (turtle-set self common)
]
]
report common
end
```



## Slide 9: One answer

Whom do we both know?

Supplementary question  
What can run this procedure?  
observer, patches, links, turtles

### Text embedded in images (OCR)

```text
to-report common-colleagues [ someone-else ]
report intersection colleague-neighbors (
[colleague-neighbors] of someone-else
)
end
```



## Slide 10: One answer

Whom do we both know?

Supplementary question  
What can run this procedure?  
observer, patches, links, turtles

### Text embedded in images (OCR)

```text
to-report common-colleagues [ someone-else ]
report intersection colleague-neighbors (
[colleague-neighbors] of someone-else
)
end
@ You can't use COMMON-COLLEAGUES in an observer context,
because COMMON-COLLEAGUES is turtle-only.
IO
9Q show common-colleagues turtle 0
100
101 reset-ticks
102 end
```



## Slide 11: One answer

Whom do we both know?

Supplementary question  
What can run this procedure?  
observer, patches, links, turtles

### Text embedded in images (OCR)

```text
to- repo rt col ruled br Rte ala COMMON-COLLEAGUES
repo rt inti called by Button ‘setup’
[colleag Show internal details Copy
)
end
99 show [
100 common-colleagues turtle 0
101 ] of patch 0 @
102
103 reset-ticks
104 end
oO oO Runtime Error
this code can't be run by a patch, only a turtle
error while observer running COMMON-COLLEAGUES
called by procedure SETUP
called by Button ‘setup’
Show internal details Copy Dismiss _
```



## Slide 12: One answer

Whom do we both know?

Supplementary question  
What can run this procedure?  
observer, patches, links, turtles

There’s no harm in trying things out!

### Text embedded in images (OCR)

```text
99 show [
100 common-colleagues turtle @
101 ] of one-of colleagues
102
103 reset-ticks
104 end
i wom ) Runtime Error
this code can't be run by a link, only a turtle
error while observer running COMMON-~COLLEAGUES
called by procedure SETUP
called by Button ‘setup’
| Show internal details Copy Dismiss —
```



## Slide 13: Working with strings



## Slide 14: Working with Strings

Brief introduction

Strings are data structures containing some text  
In NetLogo, string literals are created using straight double quotes `"` at the start and end of the text  
The empty string is `""`  
If you want to put a double quote in a string, use a backslash: `"He said, \"She said!\""`  
Strings are case-sensitive: `"dog" != "Dog"`  
There are various situations where strings might be used  
As ‘symbols’ representing states for agents  
Processing string Chooser and Input entries on the Interface tab  
Working with file names provided by the user and processing the contents of those files  
Providing output to the user  
… in your own output files as well as print, output-print and error messages



## Slide 15: Working with Strings

The most useful functions

The NetLogo dictionary’s string section has just under 20 commands to help you work with strings  
For Python, R and Java programmers, there are fewer tools than you’re used to  
Individual characters are strings of length 1 (there’s no distinct datatype)  
Besides the operators (= and != are the most useful)  
item index string – the character at position index (first character is position 0)  
length string – how many characters are in the string  
member? substr string – does a substring appear  
position substr string – find where a substring starts – N.B. the position of the first character is 0  
read-from-string string – ‘parse’ a string into a NetLogo datatype  
substring string position1 position2 – take a substring of a string  
(word value1 value2 value3 …) – build a string from lots of variables (which do not have to be strings)



## Slide 16: Exercise

Convert to upper case

Build a reporter that will convert a string so that all lower case characters are upper case  
e.g. to-upper `"Hello R2D2"` = `"HELLO R2D2"`  
You can test your reporter using the Command Center on the Interface Tab  
This is especially useful when processing input data that may be inconsistent in its use of case  
Though you might ‘clean’ such data separately first and use the cleaned file as input to your model  
Feel free to investigate the dictionary to look for commands that might help  
But you can do this with `<`, `ifelse [ ] [ ]`, `item`, `length`, `let`, `member?`, `position`, `report`, `set`, `to-report/end`, `while [ ] [ ]`, `word`



## Slide 17: Answers

Convert text to upper case

Probably slower, but uses fewer local variables and some new commands: first, but-first, is-number? and replace-item

### Text embedded in images (OCR)

```text
1468 to-report to-upper [ string ]
147 let lower-case “abcdefghijklmnopqrstuvwxyz"
148 let upper-case “ABCDEFGHIJKLMNOPQRSTUVWXYZ"
149 let n length string
150 let i @
151 let answer ""
152. while [i<n] [
153 let character item i string
154 ifelse member? character lower-case [
155 let pos (position character lower-case)
156 set answer (word
157 answer (item pos upper-case)
158 )
159 } [
160 set answer (word answer character)
161 ]
162 set ii+l
163 ]
164 report answer
165 end
1468 to-report to-upper [ string ]
147 let lower-case "abcdefghijklmnopqrstuvwxyz"
148 let upper-case "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
149
15@ while [ length lower-case > 2 ] [
151 let lower first lower-case
152 let upper first upper-case
153 set lower-case but-—first lower-case
154 set upper-case but-—first upper-case
155 let pos position lower string
156 while [ is-number? pos ] [
157 set string replace-item pos string uppe
158 set pos position lower string
159 ]
16 ]
161 report string
162 end
```



## Slide 18: Working with lists



## Slide 19: Working with Lists

Introduction

Lists are data structures allowing ordered storage of arbitrary data  
Examples in the real world: shopping list, restaurant menu, wine list  
Examples in mathematics: vectors  
Most common use-case in NetLogo: making a memory for each agent  
Strings can be thought of as lists of individual characters  
Notice in the dictionary that NetLogo has commands that work with strings and lists  
Lists can be created as literals by putting the space-separated items in the list in square brackets:

```text
let shopping-list [ "beans" "carrots" "potatoes" "wine" ]
let an-empty-list []
```



## Slide 20: Working with Lists

Creating lists

Normally we create lists programmatically  
Various functions create lists for us  
n-values – creates a list of n items  
e.g. `n-values 5 "a" = [ "a" "a" "a" "a" "a" ]`  
(list items…) – creates a list of some specific items (values of variables, for example)  
[ ] of agent-set – makes a list of values for each agent in the agent-set (in random order)  
e.g. `[ infected? ] of persons`  
We can also make lists from existing lists  
fput item list – make a new list with item on the front of list  
lput item list – make a new list with item on the end of list



## Slide 21: Exercise

Make a Fibonacci number reporter

Fibonacci numbers start with the sequence 0, 1, and then all subsequent numbers are the sum of the previous two  
Your reporter should expect a list as input  
If the list is empty, the result should be `[ 0 1 ]`  
If the list has one member, the result should be `[ x x + 1 ]` where x is the one member of the input list  
Otherwise, the result should be a list of length 1 + the input, with the last member being the sum of the previous two  
Hints: last returns the last item in a list; but-last returns the list without the last item

### Text embedded in images (OCR)

```text
observer> show fibonacci []
observer: [@ 1]
observer> show fibonacci [3]
observer: [3 4]
observer> show fibonacci [@ 1 1]
observer: [@ 1 1 2]
observer> show fibonacci fibonacci fibonacci fibonacci fibonacci []
observer: [@ 11 2 3 5]
```



## Slide 22: Answer

Make a Fibonacci number reporter

Note the use of the error command to handle unexpected input  
As well as is-list? there are commands to check for numbers, Booleans, turtles, links, strings, etc.  
It can be good practice to anticipate and trap potential errors

### Text embedded in images (OCR)

```text
1645 to-report fibonacci [ input ]
165 if not is-list? input [
166 error "I expected a list"
167 ]
168 (ifelse length input = 2 [
169 report [01 ]
170 ] length input = 1 [
171 report lput (1 + last input) input
172 Jl
173 report lput (
174 last input + (
175 last but-Last input
176 )
177 ) input
178 })
179 end
Oli OW VULC ai CiiU
173
[@) Runtime Error 1/ 4
| expected a list 175
error while observer running ERROR
called by procedure FIBONACCI 1/7 6
called by Command Center 17 7
Show internal details Copy Dismiss _ 178
1/79
```



## Slide 23: Working with Lists

More list functions

range x returns a list that starts at 0 and ends at x – 1  
In the earlier strings example, we used `while [ i < n ] [ … ]` to loop through all the characters in a string, and had to remember to `set i i + 1` to avoid an infinite loop  
With lists, you can do `foreach list [ item-var -> … ]`  
Which means you can do:

```text
foreach range n [ i -> … ]
```

A common iteration idiom that most languages provide for  
Two and three argument forms – `(range start finish)` and `(range start finish step)` – are available  
See the dictionary  
Can you apply this to convert a string into a list of characters?

### Text embedded in images (OCR)

```text
1695 to-report to-upper [| string |
170 let lower-case "abcdefghijklmnopqrstuvwxyz"
171 let upper-case "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
172
173 let answer ""
174 foreach range (length string) [ i —>
175 let character item i string
176 ifelse member? character lower-case [
177 let pos (position character lower-case)
178 set answer (word
179 answer (item pos upper-case)
180 )
181 ) [
182 set answer (word answer character)
183 ]
184 ]
185 report answer
186 end
```



## Slide 24: Working with Lists

Recursion

Compare the two answers to the challenge on the previous slide in lines 205 to 221 on the right  
‘Recursion’ is when a function calls itself (see line 218)  
To some, explode-recursively is more ‘elegant’ code  
No need for the answer local variable  
Though mostly a question of style, recursion can be useful to work with nested lists  
Lists that have lists as elements  
e.g. `[1 [2 3 [4] [5 6]] [7] [[8] 9]]`  
Can also be known as ‘trees’  
Challenging to work with using iteration  
Exercise: write a recursive reporter called flatten that turns lists of lists (of lists etc.) into a list with no lists as element  
e.g. the above list becomes `[ 1 2 3 4 5 6 7 8 9 ]`

### Text embedded in images (OCR)

```text
2058 to-report explode-foreach [ string ]
206 let answer []
207 foreach range length string [ i —>
208 set answer lput (item i string) answer
209s JJ
210 report answer
211 end
212
2138 to-report explode-recursively [ string ]
214 ifelse length string = 2 [
215 report []
216 «6 cL
217 report fput (first string) (
218 explode-recursively but-first string
219 )
220 ]
221 end
```



## Slide 25: Working with Lists

Answer to flatten challenge

Note new function sentence, which is to lists what word is to strings  
Yes, part of the training is learning to use the NetLogo dictionary to look for built-in commands that might help

### Text embedded in images (OCR)

```text
223=to-report flatten [ list-of-lists ]
224 (ifelse length list-of-lists = @ [
225 report []
226 |] is-list? first list-of-lists [
227 report (sentence
228 (flatten first list-of-lists)
229 (flatten but-first list-of-lists)
230 )
231 Jl
232 report fput first list-of-lists (
233 flatten but-first list-of-lists
234 )
235 = ))
236 end
```



## Slide 26: Working with Lists

More powerful list functions

There are three functions that let you write short expressions with lists  
filter Boolean-reporter list – returns a new list containing all the items in list for which Boolean-reporter returned true  
reduce reporter list – computes a single value (‘reduces’) the list using the reporter to operate on its values  
Confusingly, the ‘single’ value can itself be a list with some idiomatic programming  
map reporter list – returns a new list in which reporter has been applied to each item  
(map reporter list1 list2 …) – returns a new list in which reporter has operated on multiple lists (which must all be of the same length)  
Getting too ‘fancy’ with these leads to brief but unintelligible code



## Slide 27: Working with Lists

More powerful functions – examples

filter can be useful for mathematical calculations  
`mean filter [ i -> i > 0 ] [ salary ] of citizens`  
Compute the average salary of people who earn anything  
map is handy in a similar way  
`map [ i -> i * 1.2 ] [ untaxed-price ] of goods`  
Add VAT to a price list  
These can be combined – for example to avoid mathematical errors  
`mean map [ i -> 100 / i ] filter [ i -> i != 0 ] [ pain-% ] of patients`  
Mean inverted pain % score of patients in any pain (not really sure if that’s a useful measure…)  
Note that division by zero is an error in NetLogo that will stop your model continuing to run



## Slide 28: Working with Lists

reduce

The documentation for reduce in the dictionary even suggests it’s difficult to grasp!  
The reporter takes two items, the result so far and the next item in the list  
You then use the reporter to calculate the result you want from the result so far and the next item  
`reduce [ [ result next ] -> result + next ] (range 1 11)`  
Calculate the sum of the first ten natural numbers  
`reduce * (range 2 (x + 1))`  
Calculate x! (1 times 2 times 3 times … times x)



## Slide 29: Working with Lists

Using reduce to build a list

With fput [] some-list as the second argument to reduce, you have an idiomatic expression that lets you use reduce to build a list  
Here’s some code that returns the list of the first n Fibonacci numbers

```text
reduce [
  [r ignored] -> lput (last r + last but-last r) r
] fput [0 1] n-values (n - 2) [i -> 0]
```

Note that the bottom line creates a list like `[ [0 1] 0 0 0 0 0 … ]` as the list reduce will operate on  
Discussion point: Is this good coding style and practice?



## Slide 30: Boolean expressions



## Slide 31: Boolean expressions

Quick summary

We’ve been using Boolean expressions in various examples so far  
Boolean expressions evaluate to true or false  
Various commands use them – e.g. filter, if [], ifelse [] [], while [] []  
Comparison operators generate Booleans: =, !=, >, <, <=, >=  
NetLogo burn for programmers in other languages  
= is always comparison, never assignment  
Can be used on strings as well as numbers  
Various other functions report Booleans – e.g. is-string?, member?  
Look for the ?  
Boolean operators: and, or, not



## Slide 32: Boolean expressions

Inline ifelse [] [] – ifelse-value [] []

ifelse-value Boolean [value if true] [value if false]  
Useful for setting variables and reporting values  
e.g. `let drink ifelse-value (age <= 5) ["milk"] ["tea"]`  
Also useful for implementing decision trees  
Code on the left

### Text embedded in images (OCR)

```text
ta-report dt-drive-efficiently
report ifelse-volue (get-value-of “VB.1" "BW.8" < 3) [
tfelse-value (get-walue-of “IWO.3" “BW.6" <= 1) [@ + rondem-floot @.7) [
ifelse-value (get-volue-of "VE.2° “BW.6" <= 2) [3.5 + random-float 3.5) [
ifelse-volue (get-value-of "G1" “BW.6" <= 1) [
ifelse-volue (get-value-of "VA.2" "SW.6" <= 3) [8.7 « random-floot @.7) (3.5 + random-floot 3,5)
j
C
ifelse-volue (get-value-of "GE." "BW.6" <- &) [
ifelse-value C(get-value-of “IWO.3" “BW.6" <= 5) [
ifelse-value (get-value-of "Q3" “BN.6" <= 3) [8.7 + rondom-floot @.7) [@ + random-float 8.7)
]
) [3.S + random-fleat 3.5) © 4fe1se-value Boolean [value if true] [value if false]
[3.5 + rondos-flost 3.5] ¢@ Useful for setting variables and reporting values
J
7} °® eg.let drink ifelse-value (age <= 5) ["milk"] [
} | © Also useful for implementing decision trees
[3.5 + random-floot 3.5] © Code on the left
end
```



## Slide 33: Boolean expressions

Decision trees

### Text embedded in images (OCR)

```text
o
v (343 0156.0)
rganizational idertity (Praise) <= tOrganizational Identity (Praise) > t
‘int-O.
.
goism {Wealth} <= \Egoisn (Weath) > 2
3.5-nty
(oo) —
‘Geeder <= 1\ Gerdes > 1
O ‘+.
‘Atrasin {Peace} <= 3A (Peace) >3 Outcome Elficacy (Contribution) <= Outcome Efficacy (Contribution) > 6
0.7-1.4) (3.5-inty
Bono (8.0) v (4.0)
Organizadonal Wentty (Prase) <= hOrgarizateral Identity (Praise) > 5
(3.0/1.0)
Education <= AEducaton > 3
'0,7+1.4) +int-©.7]'
```



## Slide 34: Mathematical expressions



## Slide 35: Mathematical expressions

Brief summary of the dictionary

We have also seen mathematical expressions in some of these examples  
Full list of arithmetic operators: +, * (multiply), -, /, ^ (exponentiation), sqrt, mod  
Some constants: pi, e  
Various standard mathematical functions: ln, log, exp, abs, floor, ceiling, int, round  
floor and int behave differently with negative numbers  
Trigonometric functions work with degrees not radians: sin, asin, cos, acos, tan  
Arctangent (atan) is a two argument form that copes with the fact that 0 degrees is up not right, and degrees increase in a clockwise not anticlockwise direction  
atan x y is the number of degrees clockwise from up when you go x patches right and y patches up  
Some useful functions for initializing variables from statistical distributions  
Statistical functions that operate on lists of numbers: min, max, sum, mean, median, variance, modes  
Useful for plotting



## Slide 36: Exercise

Let’s write our own arc-tan reporter!

The Taylor expansion for arctan x if x is in [-1, 1] is:  
Write a reporter that calculates the nth term in the sum  
Write another reporter arc-tan that sums a list of the first n terms in the expansion for a given x  
If x = 0.99, how high does n have to be before you get the same answer?



## Slide 37: Answer

Taylor expansion for arc-tangent

I got 1466 for 0.99  
This isn’t the best (or fastest) way to do it  
You’d construct the sum as you went along without making a list  
Stop adding when taylor-arc-tan returns 0  
Or < 1e-100

### Text embedded in images (OCR)

```text
2378 to-report taylor-arc-tan [ x n ]
238 let two-n-add-1 (2 * n + 1)
239 let sign (-1) *n
240 report sign * (x * two-n-add-1) / two-n-add-1
241 end
242
2438 to-report arc-tan [ x len ]
244 report sum n-values len [ n ->
245 taylor-arc-tan x n
246 ]
247 end
248
2498 to-report how-high [ x ]
250 let len 2
251 let ans arc-tan x 1
252 let prev-ans arc-tan x 2
253 while [ ans != prev-ans ] [
254 set len len + 1
255 set prev-ans ans
256 set ans arc-tan x len
257 ]
258 report len
259 end
```



## Slide 38: Mathematical expressions

Floating point arithmetic

Computers are calculation engines  
A ‘computer’ used to be a job – the machine is named after the first job it replaced  
So you’d think they’d represent numbers accurately…  
Integers {…, -3, -2, -1, 0, 1, 2, 3, …} are fine  
…but decimals are approximated using floating point numbers  
The closest representable binary (power of two denominator) fraction  
N.B. 0.4 is not exactly representable in binary

### Text embedded in images (OCR)

```text
observer> show 0.4 + 0.4 = 0.8
observer: true
observer> show 0.4 + 0.4 + 0.4 = 1.2
observer: false
©Copyright JASSS
J. Gary Polhill, Luis R. Izquierdo and Nicholas M. Gotts (2005)
The Ghost in the Model (and Other Effects of
Floating Point Arithmetic)
Journal of Artificial Societies and Social Simulation vol. 8, no. |
<https://www.jasss.org/8/1/5 .html>
To cite articles published in the Journal of Artificial Societies and Social Simulation, reference the above information and include
paragraph numbers if necessary
Received: 09-May-2004 Accepted: 01-Aug-2004 Published: 31-Jan-2005
```



## Slide 39: Procedures



## Slide 40: Procedures

Brief introduction

Procedures are like reporters, but they don’t return a value to the calling code  
Procedures perform useful functionality that you need more than once  
If you find yourself cutting and pasting code, you should write a procedure  
Procedures also help ‘break code down’  
Some programmers regard procedures that are  
‘too long’ as bad practice  
In NetLogo, a procedure:  
Starts with to  
Then the name of the procedure  
Then optional arguments  
Then the procedure’s code  
Finishes with end

### Text embedded in images (OCR)

```text
1128 to go
113
114 (ifelse all? persons [immune?] [
115 print "Everyone is immune!"
116 stop
117 ] not any? persons with [infected?] [
118 print "No-one is infected!"
119 stop
120 ] [
121 ; Do nothing
122 })
123
124
125 tick
126 end
```



## Slide 41: Procedures

Let’s start thinking about our model

Each agent is going to do the following:  
Create a paper file (doing some work)  
Give a file in person to one of their colleagues (share some work)  
Give a file they have received to their manager (deliver some work)  
If the recipient doesn’t have a manager, they ‘sign off’ the file and it is destroyed  
Files act as disease vectors  
We can break this down as shown on the right

### Text embedded in images (OCR)

```text
1128 to go
113
114 (ifelse all? persons [immune?] [
115 print “Everyone is immune!"
116 stop
117 ] not any? persons with [infected?] [
118 print "No-one is infected!"
119 stop
120 )[
121 ; Do nothing
122 }))
123
124 ask persons [
125 do-some-work
126 ]
127 ask persons [
128 share-some-work
129 ]
130 ask persons [
131 deliver-some-work
132 ]
133
134 tick
135 end
136
1378 to do-some-work
138
139 end
140
1418 to share-some-work
142
143 end
144
1458 to deliver-—some-work
146
147 end
```



## Slide 42: Exercise

Write the do-some-work procedure

You need to  
Create a file  
N.B. turtles hatch- rather than create-, which only the observer can do (patches sprout-)  
tie it to the creator  
Guess where you’ll be told to find out about that command…  
Hints:  
You will need another link bread  
To test it, you might want a switch that turns off the infection checks at the beginning of go



## Slide 43: An answer

Write the do-some-work procedure

N.B. undirected-link-breed [

```text
works work
```

]

### Text embedded in images (OCR)

```text
1415 to do-some-work
142 hatch-files 1 [
143 set shape “square 2"
144 set color white
145 set heading random 360
146 move-to myself
147 fd 1
148 create-work-with myself [
149 set hidden? true
150 tie
151 ]
152 ]
153 end
```



## Slide 44: Exercise

Write the share-some-work procedure

You need to:  
Choose a random colleague  
Move to where they are  
Give a random file you’re linked to to the colleague  
Delete your link (ask it to die)  
Have the colleague link to it  
Move back where you started  
The deliver-some-work procedure will work in a very similar way  
Write that too



## Slide 45: An answer

share-some-work and deliver-some-work

Did you spot the opportunity to create a new procedure to handle the common code?

### Text embedded in images (OCR)

```text
1762 to hand-over-some-work [ someone ]
177 let piece-of-work one-of work-neighbors
178 let location patch-here
179
180 ask work-with piece-of-work [
181 die
182 ]
183
184 move-to someone
185
186 ask someone [
187 create-work-with piece-of-work [
188 set hidden? true
189 tie
190 ]
191 ]
192
193 move-to location
194 end
1628 to share-some-work
163 if (any? colleague-neighbors and
164 any? work-neighbors) [
165 hand-over-—some-work one-of colleague-neighbors
166 ]
167 end
168
1698 to deliver-some-work
170 if (any? in-manage-neighbors and
171 any? work-neighbors) [
172 hand-over-some-work one-of in-manage-neighbors
173 ]
174 end
```



## Slide 46: Signing off work

Modifying the rules

We haven’t implemented signing off, but the rules so far probably weren’t great  
If only the CEO can sign-off, we’re going to get a lot of files  
Typically managers summarize information when reporting to their neighbors  
So in do-some-work, the file created by managers could be seen as a summary of some of the files they have  
Make a sign-off-some-work procedure that uses a parameter (sign-off-rate) to delete some of the files the person has a work link with  
In do-some-work, ask management to call sign-off-some-work



## Slide 47: Signing off work

An answer

### Text embedded in images (OCR)

```text
1415 to sign-of f-some-work
142 repeat random sign-off-rate [
143 if any? work-neighbors [
144 ask one-of work-neighbors [
145 die
146 ]
147 ]
148 ]
149 end
151s to do-some-work
152 ask persons with [ any? out-manage-neighbors ] [
153 sign-of f-some-work|
154 ]
155 hatch-files 1 [
156 set shape “square 2"
157 set color white
158 set heading random 360
159 move-to myself
160 fd 1
161 create-work-with myself [
162 set hidden? true
163 tie
164 ]
165 ]
166 end
File Proliferation
10
a
0 3430
```



## Slide 48: Adding disease dynamics

Changing setup

In setup we need to make at least one agent sick  
Check out the n-of and up-to-n-of commands in the dictionary and add a parameter to the Interface (init-n-sick)  
We need to know how long they will be sick for  
Create another parameter (t-infected) on the Interface  
In setup make the sick agents have a random infection-time no more than that parameter  
Why don’t we set them all to t-infected?



## Slide 49: Adding disease dynamics

Changing setup

### Text embedded in images (OCR)

```text
83 ask up-to-n-of init-n-sick persons [
84 set infected? true
85 set infection-time 1 + random t-infected
86]
87
88 reset-ticks
89 end
```



## Slide 50: Adding disease dynamics

Changing go

Get the persons who are infected? to reduce their infection-time  
When it’s zero, set infected? false and immune? true



## Slide 51: Adding disease dynamics

Changing go

### Text embedded in images (OCR)

```text
133 ask persons with [infected?] [f
134 set infection-time infection-time - 1
135 if infection-time = @ [
136 set infected? false
137 set immune? true
138 od
139 ]
140
141 ask persons [
142 do-some-work
143 ]
144 ask persons [
145 share-some-work
146 ]
147 ask persons [
148 deliver-—some-work
149 ]
150
i | tick
152 end
```



## Slide 52: Adding disease dynamics

Infecting files

In do-some-work, any file created by an infected? person needs to be contaminated?  
In hand-over-some-work, any recipient of a contaminated? file who is not immune? or infected? needs to be infected? and have infection-time set to t-infected



## Slide 53: Adding disease dynamics

Infecting files

### Text embedded in images (OCR)

```text
1642 to do-some-work 20:
165 ask persons with [ any? out-manage-neighbors ] 22:
166 sign-of f-some-work 201
167 ] 20:
168  hatch-files 1 [ 20!
169 set shape "square 2" 20!
170 set color white 21
171 set heading random 360 21.
172 move-to myself 21.
173 fd 1 21:
174 create-work-with myself [ 21.
175 set hidden? true 21!
176 tie 211
177 ] 21
178 set contaminated? [infected?] of myself 21!
179 ] 21°
180 end 22(
204 move-to someone
205
206 ask someone [
207 create-work-with piece-of-work [
208 set hidden? true
209 tie
210 ]
211
212 if not immune? and not infected? [
213 set infected? [contaminated?] of piece-of-work
214 if infected? [
215 set infection-time t-infected
216 ]
217 ]
218 if infected? [[)
219 ask piece-of-work [
220 set contaminated? true
221 ]
222 ]
223 ]
224
225 move-to location
226 end
```



## Slide 54: Moving agents



## Slide 55: Moving agents

Let’s make movement more realistic



## Slide 56: Moving agents

Changing the model again

So far we have just teleported the agents from one patch to another using move-to as they hand over work  
That’s not very realistic, so we’d like to move the agents  
When they’re moving they cannot hand over or do work  
So we need three statuses: working, moving and meeting  
This is the sort of thing we use strings for  
Carefully…  
We also need to think about how long meeting and working take in comparison with moving  
Moving’s quickest, so let’s have two parameters t-working and t-meeting  
And let’s get rid of the simulate-disease? switch  
And add workplace, movement-target, status and status-time as attributes of person



## Slide 57: Moving agents

Changing go

Now we need agents to do things depending on their status  
If status = `"working"`  
Decrement status-time  
If status-time = 0  
Set status to `"moving"` and choose a movement-target

If status = `"moving"` move towards the movement-target  
If reached:  
If target is a person set status `"meeting"` and status-time t-meeting  
If target is a patch set status `"working"` and status-time t-working  
If status = `"meeting"`  
Decrement status-time  
If status-time = 0  
Set status to `"moving"` and  
movement-target workplace

Useful commands:  
face, distance, fd



## Slide 58: Answer

Big changes to go

### Text embedded in images (OCR)

```text
135 ask persons [
136 (ifelse (status = “working") [
137 set status-time status-time - 1
138 if status-time = @ [
139 do-some-work
140 set status "moving"
141 (ifelse (any? colleague-neighbors
142 and any? in-manage-neighbors) [
143 set movement-target (
144 ifelse-value random-float 1 < 0.5 [
145 one-of colleague-neighbors
146 1 [
147 one-of in-manage-neighbors
148 ]
149 )
150 ] any? colleague-neighbors [
151 set movement-target one-of colleague-neighbors
152 ] any? in-manage-neighbors [
153 set movement-target one-of in-manage-neighbors
154 } [
155 error "BUG!!!"
156 })
157 ]
158 ] (status = “moving") [
158 ] (status = "“moving") [
159 ifelse distance movement-target < 1 [
160 move-to movement-target
161 set status "meeting"
162 set status-time t-meeting
163 }[
164 face movement-target
165 fd 1
166 ]
167 ] (status = "meeting") [
168 set status-—time status-time — 1
169 if status-time = @ [
170 (ifelse is-person? movement-target [
ty | hand-over-some-work movement-target
172 set status "moving"
173 set movement-target workplace
174 ] is-patch? movement-target [
175 set status "working"
176 set status-time t-working
177 }[
178 error "BUG!!!"
179 })
180 ]
181 }[
182 error “BUG!!"
183 })
184 ]
```



## Slide 59: Answer

Big changes to go

### Text embedded in images (OCR)

```text
135 ask persons [
136 (ifelse (status = “working") [
137 set status-time status-time - 1
138 if status-time = @ [
139 do-some-work
140 set status "moving"
141 (ifelse (any? colleague-neighbors
142 and any? in-manage-neighbors) [
143 set movement-target (
144 ifelse-value random-float 1 < @.5 [
145 one-of colleague-neighbors
146 1 [
147 one-of in-manage-neighbors
148 ]
149 )
150 ] any? colleague-neighbors [
151 set movement-target one-of colleague-neighbors
152 ] any? in-manage-neighbors [
153 set movement-target one-of in-manage-neighbors
154 ]
156 })
157 ]
158 ] (status = “moving") [
158 ] (status = “moving") [
159 ifelse distance movement-target < 1 [
160 move-to movement-target
161 set status "meeting"
162 set status-time t-meeting
163 ) [
164 face movement-target
165 fd 1
166 ]
167 ] (status = "meeting") [
168 set status-—time status-time — 1
169 if status-time = @ [
170 (ifelse is-person? movement-target [
171 hand-over-—some-work movement-target
172 set status "moving"
173 set movement-target workplace
174 ] is-patch? movement-target [
175 set status "working"
176 set status-time t-working
177 } [
179 })
180 ]
181 ]
183 })
184 ]
```



## Slide 60: Being suspicious

Trap bugs where they occur

Beware of thinking “this will never happen”  
There are 3 possible statuses for a person: working, moving and meeting  
Why not assume if the status isn’t working or moving, it must be meeting?



## Slide 61: Being suspicious

Trap bugs where they occur

Beware of thinking “this will never happen”  
There are 3 possible statuses for a person: working, moving and meeting  
Why not assume if the status isn’t working or moving, it must be meeting?  
Typo elsewhere in the code  
Future extension entailing a new status and forget to update here  
Use the ‘else’ code block to raise an error



## Slide 62: Further modifications

Finishing off the changes

In setup  
Set workplace to patch-here when initializing persons  
After creating the colleagues network make sure everyone has at least one colleague  
If you want to see the trails as everyone chases after each other, use pen-down  
When hatching files in do-some-work you might want to pen-up  
In hand-over-some-work  
Add a check that there’s some work to hand over  
Remove the move-tos  
You can delete share-some-work and deliver-some-work



## Slide 63: More advanced topics

Not covered here

In this model, the agents could walk through offices and meeting rooms, and even through each other  
A more realistic approach would have been to have a proper building layout, route finding, and obstacle avoidance  
Think about what you might need to do these things  
Route-finding is a common problem, so you’d expect to find a solution  
Dijkstra’s algorithm  
More generally, learning to implement algorithms (in pseudocode) is a good idea

Dijkstra’s algorithm on Wikipedia

### Text embedded in images (OCR)

```text
1 function Dijkstra(Graph, source):
2
3 for each vertex v in Graph.Vertices:
4 dist[v] + INFINITY
5 prev[v] + UNDEFINED
6 add v to Q
7 dist[source] + 0
8
9 while Q is not empty:
10 u «+ vertex in Q with min dist[u]
11 remove u from Q
12
13 for each neighbor v of u still in Q:
14 alt «+ dist[u] + Graph.Edges(u, v)
15 if alt < distl[v]:
16 dist[v] + alt
17 prev[v] « u
18
19 return dist[], prev[]
```



## Slide 64: Concluding thoughts

Models are more fluid than they may appear  
Think about how we modified the model when moving the agents  
This means version control is important  
Especially for repeatability of published models  
Make use of the documentation  
Learn to break down your problem until you can start to see steps that there are NetLogo commands to execute  
Be suspicious of your past, present and future selves  
Code ‘defensively’: anticipate bugs and avoid assuming you’ve got it right



## Slide 65

*No extractable text.*

