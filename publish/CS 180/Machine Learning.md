## Why study Machine Learning?
- Solving tasks that require a system to be adaptive
	- Speech and handwriting recognition
	- "intelligent" user interfaces
- Understanding human learning
	- How do we learn language?
	- How do we recognize faces?
- Creating "real" AI
	- An expert system-brilliantly designed, engineered and implemented; cannot learn not to repeat its mistakes
## Learning Framework
- "Change is the end result of all true learning."
- For an agent, learning means using their experiences and knowledge of the world to improve their performance on a task.
### A. Sensory Experience
- For a learning agent, the learning process usually starts with the data acquired through its sensors
- Generally, the more data that the agent receives, the more intelligent it gets
- In ML, these experiences are commonly referred to as **input, features, attributes, predictors, or independent variables** 
### B. Learned and Stored Knowledge
- Factored form
	- simplest representation of knowledge
	- knowledge is represented as a mapping from experience (input) to desired task outcome (output)
	- agent's goal then is to infer this mapping on its own
- Some learning agents have prior knowledge that we may store before acquiring any experience. This prior knowledge can help the agent learn faster. However, this prior knowledge could also introduce bias to the agent
### C. Task and Goal
- Different problems require different models.
- problems are categorized based on their task output, also referred to as **target, label, response** or **dependent variable** 
- Classified into three types of learning problems
	1. Classification
	2. Regression
	3. Clustering
#### Classification Problems
- agent's target is finite and discrete
- Given a sample input, the agent will learn a decision boundary (model) to determine the class (output) of the sample
- Examples of Classification Problems
		1. Optical Character Recognition
			- input samples = {document image}
			- output classes = {alphanumeric character | a-z, 0-9}
		2. Spam Filtering
			- input samples = {email}
			- output classes = {spam, ham}
		3. DNA Sequencing
			- input samples = {DNA sequence}
			- output classes = {gene family | human, animal}
#### Regression Problems
- the target is continuous, so the model becomes a continuous function
- Regression models help predict trends, forecast events, and find correlations between real-world properties
- Examples of Regression Problems:
	1. Stock Market Prediction:
		- input data = {date}
		- output trend = {stock price}
	2. Weather forecasting
		- input data = {time, temperature, humidity, wind, location}
		- output forecast = {precipitation forecast}
	3. Sports performance analysis
		- input data = {body composition, diet, training regimen}
		- output correlation = {strength, speed, endurance}
#### Clustering Problems
- agent's target is to group the samples based on their similarities
- samples are not labeled during the learning process, so it is the **agent's task to figure out the labels by itself**
- Examples of Clustering Problems:
	1. Medical Imaging
		- input data = {PET scans}
		- output groups = {tissue types}
	2. Social Network Analysis
	3. Product Recommendation
### D. Feedback and Performance
- Agents learn through a feedback loop
- If we **explicitly provide the target answers to the agents**, the process is called **supervised learning**
- On the other hand, if the agents are **left to find patterns in the data on their own**, it is called **unsupervised learning**
- The third type of learning, called **reinforcement learning, guides the agents with rewards and punishments.** 
#### Supervised Learning
- agent observes some example input-output pairs and learns a function that maps from input to output
- more straightforward approach to building ML models
- easier to verify whether the agents have learned the desired model by providing both the **input** samples and their corresponding target output
#### Unsupervised Learning
- agent learns patterns in the input even though no explicit feedback is supplied
- most common type is clustering, detecting potential useful clusters of input examples
#### Reinforcement Learning
- agent learns from a series of reinforcement - rewards and punishment
### What is the Learning Problem?
- Learning = improving with experience at some task
	- Improve over task T
	- with respect to performance measure P
	- based on experience E
- Example:
	- Learn to play checkers
		- T: Play checkers
		- P: percentage (%) of games won in world tournament
		- E: opportunity to play against self
## Issues in Machine Learning
- What algorithms can approximate functions well and when?
- How does the number of training examples influence accuracy?
- How does the complexity of hypothesis representation impact it?
- How does noisy data influence accuracy?
- What are the theoretical limits of learnability?