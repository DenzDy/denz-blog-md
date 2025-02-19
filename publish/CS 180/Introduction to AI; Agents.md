## Some Definitions of AI
- Term coined in 1956 by Darthmouth Assistant Professor John McCarthy
1. The ability to acquire and apply knowledge and skills.
2. machine's ability to perform tasks that require any form of intelligence-human or otherwise.
3. science of intelligent programs
4. The science and engineering of making intelligent machines, especially intelligent computer programs.asdfasdfsdfasdf
## Concerns of Artificial Intelligence (AI)
5. systems that act like humans (Turing Test Approach)
6. systems that think like humans (Cognitive Modeling Approach)
7. systems that think rationally (Laws of Thought Approach)
8. systems that act rationally (Rational Agent Approach)

## Act like humans: Turing Test
- the computer passes the test if a human interrogator, after posing some questions, cannot tell whether the written responses come from a person or not.
## Think like humans: Cognitive Modeling Approach
- brings together **computer models from AI** and **experimental techniques in psychology** to construct precise and testable theories on the workings of the human mind
### Think rationally: Laws of Thought Approach
- the **laws of thought** or commonly termed as **logic** were supposed to govern the operation of the mind.
### Act Rationally: Rational Agent Approach
- Acting rationally doesn't necessarily involve thinking (e.g. reflex actions)
- Bounded/Limited rationality - acting under bounds of time and space
### Foundations of AI
- disciplines that contributed ideas, viewpoints, and techniques to AI
	- Philosophy
	- Mathematics
	- Economics
	- Neuroscience
	- Psychology
	- Computer Engineering
	- Control Theory and Cybernetics
	- Linguistics
### AI Core Competencies
1. Problem Solving
2. Learning
3. Reasoning
4. Decision-making
### Agents
##### Definition
- a system that perceives its environment through its sensors, and acts on that environment through its actuators.
	![[Pasted image 20250203171634.png]]
##### Example: Vacuum Cleaner World
![[Pasted image 20250203171734.png]]
#### The Generic Intelligent Agent
- A *rational agent* is an agent that *acts rationally* so as to achieve one's goals, given one's beliefs
- Must evaluate the following:
	1. How much success the agent achieves
	2. when it was able to achieve its goal
- Performance Measure
	- indicates how successful the agent is
	- Example: Vacuum Cleaning Agent
		- amount of dirt cleaned up in a day
		- consider also electricity consumed and noise generated
- rational agent performance must be measured given what has been perceived
- What is rational at any given time depends on:
	1. performance measure
	2. perpetual history (percept sequence) - everything that the agent has perceived so far = experience
	3. knowledge of the environment
	4. the actions that the agent can perform
- agent's choice of action at a given instant depends on all these, but not on anything that has not yet been perceived
### Rational Agents
- an agent should strive to "do the right thing" based on what it can perceive and the action it can perform
- the right action is the one that will cause the agent to be most successful
- *Information gathering* - doing actions in order to modify future percepts is part of rationality
	- exploration - probing unknown environment
### Optimal vs Rational
- Optimality is essentially omniscience; rationality is based on expected events
- Intelligent agent is a rational agent
	- Rational agent: maximize expected outcome
	- Perfect agent: maximize actual outcome (only possible in an ideal environment)
### Definition of an Ideal Rational Agent
- For each possible percept sequence, an ideal rational agent should do whatever action is expected to *maximize it's performance measure* on the basis of the evidence provided by the percept sequence and whatever built-in knowledge the agent has.
- Behavior of the rational agent can then be viewed as a mapping from percept sequences to actions
	- mapping can be in the form of a look-up table, or in most cases, a sophisticated algorithm
### Autonomy
- In AI, it's the *ability to adapt to its environment*; flexibility
- No autonomy if the agent relies **solely** on its built-in knowledge and completely disregards the environment.
- A good rational agent acts according to:
	1. built-in knowledge - often imperfect or partial
	2. own experience (percept sequence)
- A system is autonomous to the extent that its behavior is determined by its own experience
### Structure of an Intelligent Agent
1. **Agent program** - implementation of the mapping from percepts to actions
2. **Architecture** - the computing device on which the agent program runs
- Agent = architecture + program
- Agent: **P**erformance **E**nvironment **A**ctuators **S**ensors
### PEAS
- What is rational at any given time depends on four things:
1. Performance Measure
2. External Environment
3. Actuators
4. Sensors
### Nature of Environment
##### Probability
- Deterministic
	- action on current state completely determines next state
- Stochastic
	- action on current state may have different possible outcomes
##### Observability
- Fully observable
	- perceive complete state of environment
- Partially observable
	- perceive only part of the environment
- Unobservable
	- cannot perceive the environment at all
##### Knowledge
- Known
	- full knowledge on all laws governing the environment
- Unknown
	- incomplete knowledge on all laws governing the environment
##### Events
- Episodic
	- past actions do not affect future decisions
- Sequential
	- past actions affect future decisions
##### Measurement
- Discrete
	- fixed locations or time intervals
- Continuous
	- more precise locations or time intervals
##### State
- Static
	- agent doesn't need to keep sensing while deciding what action to take, no need to worry about time
- Dynamic
	- environment changes while agent is thinking
##### Number of Players
1. Single agent
2. Cooperative (shared goals)
3. Competitive (competing goals)
### Examples of Rational Agents
1. Chess player
	- deterministic
	- fully observable
	- known
	- sequential
	- discrete
	- static
	- single agent
2. Self-driving car
	- stochastic
	- partially observable
	- unknown
	- episodic
	- continuous
	- dynamic
	- single agent
### Types of Agents
1. Table-Driven Agent
	- Store percept sequence in memory and use it as an index to a table which contains the appropriate action for all possible sequences
2. Simple Reflex Agent
	- selects action on the basis of the current percept, ignores percept history
3. Model-based Reflex Agent
	- reflex agent but with an internal state that keeps track of the part of the world it cannot see now
4. Goal-based Agent
	- incorporate goal information in deciding what to do (it considers the future)
5. Utility-based Agent
	- goals may be viewed as world states which make the agent happy
6. Learning Agent
	- any type of agent that may incorporate learning