# Frontier Exploration and Decision-Making in Robotics
## Decision Making for Robotics - Mini Project 1
### Team Members: Brandon Colelough, Ahmed Ashry

Welcome to the GitHub Pages repository for the overview of frontier exploration related to decision-making for robotics. This page provides a comprehensive summary of the topic, from layman's terms to formal definitions, key results, and its significance in the field of robotics.

## Table of Contents

1. [Summary](#summary)
2. [Formal Definition](#formal-definition)
3. [Overview](#overview)
4. [Key Results](#key-results)
5. [Relationship to Decision-Making in Robotics](#relationship-to-decision-making-in-robotics)
6. [Variants](#variants)
7. [Important Applications](#important-applications)
8. [Open Research Questions](#open-research-questions)
9. [References](#references)

## Summary
Frontier exploration is motivated by the need to explore unknown environments that may be dangerous, unreachable, or just have not yet been visited by humans. These unexplored environments can be anything from deep-sea locales to regions of space to Earth's disaster-stricken areas. Mapping the investigated area, deciding where to explore next, and adapting to dynamic and changing conditions are among the primary open research areas of frontier exploration. In the following article, an agent refers to an autonomous robotic platform of some design (UGV, UAV etc)

## Formal Definition
Frontier exploration is the identification and methodical investigation of "frontiers," or unexplored boundaries that separate the known and unknown regions within an environment. These frontiers represent areas where the agent has incomplete or uncertain information about its surroundings and are typically associated with regions that could contain valuable information, obstacles, or points of interest. Frontier exploration is centred on the challenge of independently exploring and mapping these unexplored frontiers in order to identify noteworthy or interesting locations. 

Algorithms for frontier exploration, such as those observed in , are developed to automate the process of path planning and obstacle avoidance along routes to the frontiers.

ADD SOME INFO HERE ABOUT ALGORITHMS (MAYBE A FORMAL ALGORITHM?)

Frontier exploration is a fundamental area within the field of autonomous robotics, primarily applied to Unmanned Aerial Vehicles (UAVs) and mobile robots. Frontier exploration is essential for many applications, notably search and rescue operations, environmental monitoring, and mapping of indoor or outdoor environments.

ADD SOME PICS/ VIDS HERE FOR FRONTIER EXPLORATION 

## Overview 

### Frontier Exploration Algorithms
1. **Frontier-Based Exploration:**
Algorithms for frontier exploration focus on the frontiers, finding and choosing those that offer the most exciting potential for discovery. When the agent travels to these frontiers, it gains new knowledge about its surroundings, including the location of obstacles and their features.

ADD PICTURES AND EQUATIONS HERE

2. **Coverage-Based Frontier Exploration:**
These algorithms ensure that an agent thoroughly explores every region by giving priority to investigating new sections of the environment. Algorithms such as Spiral and grid-based patterns have been used to help achieve uniform coverage.


3. **Information-Gain Frontier Exploration:**
These algorithms are designed to maximize the agent's ability to learn. They frequently follow metrics like entropy or mutual information, which quantify the uncertainty or information content of uncharted territory, to concentrate on places that promise the most interesting data.

### Frontier Exploration Basic
1. **Sensors and Mapping:**
Frontier exploration is fundamentally dependent on sensors. Sensors provide an agent/robotic system information about its environment. Common sensors utilised within the field include LiDAR, cameras, depth sensors, inertial measurement units (IMU), time of flight (TOF) and many more. In recent frontier exploration projects, agents are able to create and update maps of the region being explored in real-time by employing Simultaneous Localization and Mapping (SLAM) algorithms which often employ 3D occupancy grid maps and aid in efficient real-time navigation when employed in a human-machine teamed environment

### Decision-Making in Frontier Exploration
1. **The Role of -Making:**
Decision-making in frontier exploration involves determining the agent's next optimal path of best action to arrive at a destination or waypoint. To make appropriate choices, this method integrates the agent's a-priori knowledge of the environment, sensor data, and exploratory policy.

2. **Balancing Exploration and Exploitation:**
Exploration is the process of seeking new information, while exploitation is the utilization of existing knowledge or resources. Effective exploration strategies often seek to strike a balance between exploitation and exploration.

ADD EXAMPLE HERE 

3. **Risk Assessment in Exploration:**
Risk assessment examines potential obstacles or risks in unexplored territories. To decide on safe exploration policies, agents must evaluate risks related to frontiers, such as collision danger or environmental concerns.


### Robotic Sensing and Perception
1. **Sensor Technologies in Frontier Exploration:**
Although modern-day sensor technologies are relatively precise, minor errors introduced due to environmental factors almost always introduce issues into agent navigation whereby agent localisation or pose estimation within the environment is cascadingly affected. The open research field of SLAM aims to solve this through algorithmic matching of environment features to correct agent pose and localisation errors. 

2. **Perception Challenges in Unknown Environments:**
Navigating unknown environments poses perception various challenges. Agents must often deal with dynamic changes within the environment (e.g. people walking through a scene), varying lighting conditions, and the presence of unexpected obstacles, necessitating robust perception algorithms and techniques.

### Simultaneous Mapping and Localization (SLAM)
1. **Building Maps of the Explored Area:**
Mapping techniques like occupancy grids or voxel-based mapping are often used for constructing detailed representations of explored areas [EXAMPLES HERE]. Most modern projects aim to build 3D maps of the environment and these maps help the agent plan paths, avoid obstacles, and maintain spatial awareness. These maps are also crucial for use in the human-machine teamed environment as they allow human operators to interact with robotically sensed information in an efficient manner. 

2. **Localization for Precise Navigation:**
Agents must be able to localize themselves accurately in order to navigate the mapped area effectively. Current state-of-the-art projects such as [ADD REFERENCE] achieve this by ""

ADD PICTURE HERE

## Key Results
Significant developments in the subject of frontier exploration have transformed the capacities of agents, especially UAVs and mobile agents, to navigate and survey unexplored territories. Important outcomes and accomplishments in this field include:

### Efficiency to explore unknown environments.
Frontier exploration algorithms have significantly improved in efficiency from when the field was first proposed by [ADD REFERENCE ] in 1997 to today. State-of-the-art frontier exploration projects use algorithms such as 

ADD REFERENCE AND FORMULAS HERE 

### Map Generation
Making accurate representations of the places explored environment is one of the primary objectives of frontier exploration. Significant improvement in map generation can be visually observed below by contrasting the first frontier-exploration-generated environment map to a generated map from a 2023 frontier-exploration project (FUEL): 

### Frontier-Selection.
Frontier selection algorithms incorporate factors like uncertainty, obstacles, and information gain, with the objective of optimal environment exploration to strategically prioritise frontiers. The integration of Markov decision processes (MDPs) and reinforcement learning has further optimized exploration strategies, enabling agents to take actions that maximize environmental understanding through pre-learned policies.

### Dynamic and Changing Environments:
Some modern frontier exploration algorithms [ADD REFERENCE] can adapt to dynamic changes and are not limited to static situations. Sensor-equipped agents continuously update their maps and exploration paths to account for moving objects, obstacles, and general dynamic environmental circumstances. This adaptability ensures that the goal of optimal environment exploration remains effective in scenarios where the environment is not static.

### Real-World Applications: 
Frontier exploration has transitioned from theoretical and simulation-based research to practical applications. Physical robotic agents equipped with frontier exploration capabilities are increasingly deployed in real-world scenarios such as search and rescue operations, precision agriculture, and infrastructure inspection. These applications demonstrate the field's impact on addressing critical challenges and improving decision support in domains where efficient exploration and mapping are essential [ADD REFERENCE].

### Scalability and Adaptability: 
Multi-agent frontier exploration approaches [ADD REFERENCE] have showcased scalability for the use of unknown environmental mapping in a teamed/swarmed environment. These approaches also demonstrate robust and effective frontier exploration and mapping in  both small indoor (complex) environments and large-scale outdoor areas, making them versatile tools for a wide range of applications. 


## Relationship to Decision-Making in Robotics
Frontier exploration in robotics is intimately tied to decision-making processes, frequently utilizing complex methods like Reinforcement Learning (RL) and Markov Decision Processes (MDPs) to maximize robot actions in uncharted areas. Frontier exploration scenarios are particularly suited for MDPs because they offer a formal framework for modelling decision-making issues under uncertainty. The agent must autonomously decide an optimal policy on its exploration journey while accounting for a number of goals, such as information gathering and coverage. Every action, such as moving locations or gaining sensor information, has a corresponding benefit or cost, and the agent seeks to identify an action that maximizes its anticipated cumulative benefit over time.

Reinforcement learning is a powerful tool employed in frontier exploration to take optimal actions in areas such as obstacle avoidance and path planning. For example, as observed in [ADD REFERENCE] an agent employs reinforcement learning algorithms to optimal paths to avoid obstacles within the environment whilst effectively exploring frontiers. These algorithms use a reward-based system wherein desirable actions, like successfully avoiding obstacles, are rewarded positively, while undesirable outcomes, like collisions, are penalized. Agents can modify their decision-making process and develop obstacle-avoidance policies by learning over time from these rewards. This allows agents to efficiently explore unexplored territories while navigating safely around obstacles within the terrain and making sensible choices to prevent collisions [ADD REFERENCE].

Deep Q-Networks (DQNs), have also been applied to frontier exploration tasks [ADD REFERENCE]. 

A real-world example of decision-making being employed by agents through frontier exploration is observed [ADD REFERENCE TO PROJECT]

## Variants

Frontier exploration is a diverse area of research, and many variations and extensions exist. A brief summary of several major variations is provided below:

1. **Multi-Agent Exploration:** 
The objective of multi-agent frontier exploration is to efficiently distribute exploration tasks among a team/swarm of agents. Agents explore various locations simultaneously while avoiding repetition and collisions thanks to coordination techniques including task allocation algorithms and communication protocols. A great example of this is shown below by the EGO-Planner Frontier exploration project [REFERNECE]

2. **Time-Optimal Frontier Exploration:**
The objective of time-optimized exploration is to reduce the amount of time needed to fully explore an environment. This variation takes into consideration variables such as agent speed and resource constraints. This group of algorithms focuses on designing path policies that allow agents to explore as much as they can in a constrained amount of time, which is useful in time-sensitive applications like search and rescue.

3. **Human-Robot Collaboration in Frontier Exploration:** 
This variation has a focus on the human-machine-teamed environment. Agents assist individuals in exploring new or hazardous environments by automatically recognizing obstacles or hazards and recommending potential areas of interest. Agent exploration can also be directed by human inputs, preferences, or high-level instructions.

4. **Sparse Frontier Exploration:**
Rather than thoroughly surveying the entire area, sparse exploration concentrates on locating and investigating only the most valuable or informative frontiers. Agents can maximize their exploration efforts in applications like data collection by providing higher priority to locations with greater ambiguity or relevance.

## Important Applications

Frontier exploration has significant applications in several fields, enabling agents and autonomous systems to take on an array of tasks such as:

1. **Autonomous Exploration:** 
Frontier exploration techniques are vital for enabling robotic exploration of unexplored territories in environments that are inaccessible to humans. These techniques, for instance, have been used by rovers like NASA's Curiosity to traverse the Martian landscape and acquire significant knowledge of the planet's geology and climate [Read More on Curiosity Rover Frontier Exploration Here](https://www.jpl.nasa.gov/news/nasas-mars-curiosity-debuts-autonomous-navigation). Some recent expeditions for underwater robots used in deep-sea exploration have also employed frontier-based algorithms to explore previously unexplored depths, find new species, and examine underwater characteristics [Read more here](https://www.space.com/orpheus-ocean-autonomous-submarine-europa-technology). 

2. **Search and Rescue:** 
Frontier exploration plays a crucial role in search and rescue operations, helping locate and assist individuals in disaster-stricken areas. [17]


3. **Agriculture:** P
Frontier exploration helps with precision farming and agricultural field monitoring in agriculture. agents that are autonomous and outfitted with cameras and sensors can systematically inspect fields, spot crop health problems, and make the best use of resources like fertilizer and water. These robots assist farmers in making data-driven decisions to increase crop yields, lower expenses, and have the least amount of negative environmental impact by efficiently exploring agricultural environments. They can also spot abnormalities like insect infestations or diseases and react to them, allowing for early crop protection and intervention. [Provide link]

4. **Mining:** 
In the mining industry, where robots are employed to explore and map underground mines to increase safety and efficiency, frontier exploration is valuable. LiDAR and mapping sensors on autonomous drones and ground robots allow them to navigate challenging underground areas, evaluate geological conditions, and produce accurate 3D maps of mines. This knowledge is useful for resource management, danger detection, and mining planning. Robots help to reduce risks for human miners and increase mining output by autonomously exploring and charting mines.

## Open Research Questions

Frontier exploration is an active field with continuous research addressing numerous opportunities and difficulties. Open research issues and areas of investigation in this area include:

1. **Autonomous Exploration Efficiency:** 
#### Multi-Robot Coordination: 
How can several agents work together effectively to explore new frontiers while maximizing coverage and reducing redundancy? Real-time coordination of various agents' actions is still a difficult task.
#### Adaptive Exploration: 
How can agents modify their exploration tactics in response to environmental factors like resource availability, terrain roughness, or environmental conditions?

2. **Robotic Sensing and Perception:** 
#### Enhanced Sensor Integration: 
How can agents enhance their perception abilities in activities requiring frontier exploration by integrating and utilizing a wider variety of sensors, such as cutting-edge vision systems, radar, and spectroscopy?
#### Dealing with Uncertainty: 
How can agents operate in unpredictable situations with noisy sensor data? It is crucial to have excellent mapping and perception methods that can function even under difficult circumstances.

3. **Decision-Making and Planning:**
#### Optimal Path Planning: 
What path-planning algorithms are most effective and efficient for guiding agents through challenging environments? How do these algorithms take into account practical limits like energy restrictions or security concerns?
#### Human-Robot Collaboration: 
How can agents effectively cooperate in a human-machine-teamed environment or support human operators in situations involving frontier exploration? This covers communication and joint decision-making techniques.

4. **Mapping and Localization:**
#### Long-Term Mapping:
How can agents keep precise and current maps of their surroundings during prolonged periods of exploration, taking into account environmental changes and sensor deterioration?
#### Resource-Efficient Mapping: 
How to create methods for resource-efficient mapping that maximize the use of their onboard processing power, memory, and communication bandwidth?

5. **Adaptation to Dynamic Environments:**
#### Dynamic Object Handling: 
How are agents capable of adjusting to dynamic and shifting surroundings, such as those with shifting topography or moving obstacles? It is crucial to develop methods for immediate re-planning and barrier avoidance.
#### Environmental Changes: 
How are severe environmental changes, including those caused by emergencies or damaged infrastructure, detected and handled by agents during exploration missions?

6. **Human-Robot Interaction:**
#### User-Friendly Interfaces: 
What are the most effective approaches to create user interfaces and interaction modalities that allow users to effectively monitor or control autonomous frontier exploration tasks?
#### Safety and Ethical Considerations: 
How might safety precautions and ethical considerations be incorporated into autonomous exploration missions, particularly in situations when agents are operating close to people or in delicate environments?

7. **Scalability and Generalization:**
#### Scalable Solutions: 
How can efficiency be maintained while scaling up techniques and methodologies for frontier exploration in big, complicated, or uncharted environments?
#### Generalization Across Domains: 
Can generalization across domains be made using the lessons acquired from one area of frontier exploration?

## References:

For more in-depth information on frontier exploration and related topics, please refer to the following references:

1. Yamauchi, B. (1997), A frontier-based approach for autonomous exploration, in 'Proceedings 1997 IEEE International Symposium on Computational Intelligence in Robotics and Automation CIRA97. Towards New Computational Principles for Robotics and Automation', IEEE Comput. Soc. Press, doi: 10.1109/cira.1997.613851

2. Jain, U., Tiwari, R. and Godfrey, W. W. (2017), Comparative study of frontier based exploration methods, in '2017 Conference on Information and Communication Technology (CICT)', IEEE, doi: 10.1109/infocomtech.2017.8340589

3. Yu, B., Kasaei, H. and Cao, M. (2023), Frontier Semantic Exploration for Visual Target Navigation, in '2023 IEEE International Conference on Robotics and Automation (ICRA)', IEEE, doi: 10.1109/icra48891.2023.10161059

4. Hui, Y., Zhang, X., Shen, H., Lu, H. and Tian, B. (2023), DPPM: Decentralized Exploration Planning for Multi-UAV Systems Using Lightweight Information Structure, IEEE Transactions on Intelligent Vehicles, 1-13. doi: 10.1109/TIV.2023.3322705

5. Leong, K. (2023), 'Reinforcement Learning with Frontier-Based Exploration via Autonomous Environment', arXiv. doi: 10.48550/ARXIV.2307.07296

6. Xiao, M., Bai, Y. and Liu, W. (2023), Hot Spots, Frontiers and Trends of International EDM/LA Research, in '2023 5th International Conference on Computer Science and Technologies in Education (CSTE)', IEEE, doi: 10.1109/cste59648.2023.00067

7. Chen, X., Zheng, J. and Hu, Q. (2023), 'A Hybrid Planning Method for 3D Autonomous Exploration in Unknown Environments With a UAV', IEEE Transactions on Automation Science and Engineering, 1--12. doi: 10.1109/tase.2023.3316207

8. Zhao, Y., Yan, L., Xie, H., Dai, J. and Wei, P. (2023), 'Autonomous Exploration Method for Fast Unknown Environment Mapping by Using UAV Equipped with Limited FOV Sensor', IEEE Transactions on Industrial Electronics, 1--10. doi: 10.1109/tie.2023.3285921

9. Zhu, S., Sun, X., Sun, Z. and Yuan, J. (2023), RGB-D SLAM: Active RGB-D SLAM with Active Exploration, Adaptive TEB and Active Loop Closure, in '2023 42nd Chinese Control Conference (CCC)', IEEE, doi: 10.23919/ccc58697.2023.10240308

10. Lee, E. M., Youn, D. and Myung, H. (2023), THE-Planner: Topological and Hierarchical Exploration Path Planner for Fast 3D Mapping of Outdoor Structures with UAVs, in '2023 20th International Conference on Ubiquitous Robots (UR)', IEEE, doi: 10.1109/ur57808.2023.10202255

11. Saleh, I., Borhan, N., Yunus, A., Rahiman, W., Novaliendry, D. and Risfendra (2023), Simulation of Real-Time Frontier Exploration in Confined &amp$$ Cluttered Environment, in '2023 IEEE International Conference on Automatic Control and Intelligent Systems (I2CACIS)', IEEE, doi: 10.1109/i2cacis57635.2023.10193051

12. Milas, A., Ivanovic, A. and Petrovic, T. (2023), 'ASEP: An Autonomous Semantic Exploration Planner With Object Labeling', IEEE Access 11, 107169--107183. doi: 10.1109/access.2023.3320645

13. Liu, Y.-F., Hsieh, C.-Y. and Kuo, S.-Y. (2023), Boomerang: Physical-Aware Design Space Exploration Framework on RISC-V SonicBOOM Microarchitecture, in '2023 IEEE 34th International Conference on Application-specific Systems, Architectures and Processors (ASAP)', IEEE, doi: 10.1109/asap57973.2023.00026

14. Zhou, X., Zhu, J., Zhou, H., Xu, C. and Gao, F. (2021), EGO-Swarm: A Fully Autonomous and Decentralized Quadrotor Swarm System in Cluttered Environments, in '2021 IEEE International Conference on Robotics and Automation (ICRA)', IEEE doi: 10.1109/icra48506.2021.9561902

15. Zhou, B., Zhang, Y., Chen, X. and Shen, S. (2020), 'FUEL: Fast UAV Exploration using Incremental Frontier Structure and Hierarchical Planning', arXiv. doi: 10.48550/ARXIV.2010.11561

16. D. C. Schedl et al. ,(2021), An autonomous drone for search and rescue in forests using airborne optical sectioning.Sci. Robot.6,eabg1188, doi: 10.1126/scirobotics.abg1188

    


