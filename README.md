<head>
<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>
</head>

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
Exploration's major question as shown in fig. 1, is about how the agent should decide where to go to be able to explore as much as possible about the environment. Frontier exploration is the identification and methodical investigation of "frontiers," or "regions on the boundary between open space and unexplored space" [1]. These frontiers represent areas where the agent has incomplete or uncertain information about its surroundings and are typically associated with regions that could contain valuable information, obstacles, or points of interest. Frontier exploration is centred on the challenge of independently exploring and mapping these unexplored frontiers in order to identify noteworthy or interesting locations.

![fig1](https://github.com/Brandonio-c/Frontier-Exploration/assets/98168605/24f605d8-ae4a-4ee3-9f42-0d54de3e8b7e)

> _**Fig. 1.** Frontier exploration central question. Adapted from [5] and modified by the author._

Frontier exploration is a fundamental area within the field of autonomous robotics, primarily applied to Unmanned Aerial Vehicles (UAVs) and mobile robots. It plays a crucial role in numerous applications, notably search and rescue operations, environmental monitoring, and mapping of indoor or outdoor environments. Algorithms for frontier exploration, as seen in references [1] - [15], are developed to automate the process of path planning and obstacle avoidance along routes to these frontiers.

Frontier-based techniques for exploration can be broadly classified into single and multi-robot methods. The single robot frontier-based methods are divided based on various goals such as reducing computational overhead, reducing energy consumption, and minimizing redundant coverage. Similarly, multi-robot frontier-based techniques are divided based on goals like handling communication challenges, reducing energy consumption, and minimizing redundant coverage, as visualized in Fig. 2.

![fig2](https://github.com/Brandonio-c/Frontier-Exploration/assets/98168605/3b4a2e2e-e7d6-4e6a-9b7c-108a094fc570)

> _**Fig. 2.** Summary of frontier exploration uses for single robot and multi-robot. Adapted from [2]._

## Overview

### Frontier Exploration Algorithms

**Frontier-Based Exploration:**
Algorithms for frontier exploration concentrate on identifying and selecting frontiers with high discovery potential. Once an agent reaches these frontiers, it gathers fresh insights about the environment, pinpointing obstacles and their features. Primarily, there are two algorithmic strategies for Frontier Exploration:

1. **Coverage-Based Frontier Exploration:** 
These algorithms prioritize exploring every section of the environment. Patterns such as Spiral and grid-based methods assist in ensuring uniform coverage [2].
 
2. **Information-Gain Frontier Exploration:** 
Tailored to augment the agent's learning capacity, these algorithms generally follow metrics like entropy or mutual information. These metrics help focus on areas that offer the most valuable data [3].

However, irrespective of their individual strategies, all these algorithms follow a shared fundamental approach. Let's delve deeper into one of the alogrithms, [5], and see how it works to gain more insights. 

### Problem Formulation and Approach

A specific 3D space, represented as $V \subset R^3$, can be illustrated through a probabilistic occupancy cubic map, $M$. This map is composed of small cubes termed as voxels. The status of each voxel is categorized based on its occupancy probability, $M_{\text{prob}}$, into:

- Free, if $0 \leq M_{\text{prob}}(i, j, k) < 0.5$
- Unknown, if $M_{\text{prob}}(i, j, k) = 0.5$
- Occupied, if $0.5 < M_{\text{prob}}(i, j, k) \leq 1$

Initially, the entirety of space $V$ is perceived as unknown. The ultimate goal of autonomous exploration is to identify whether a specific observable voxel belongs to the free or occupied space. It's worth noting that there might be some voxels that can't be observed due to practical limitations, such as hollow spaces or narrow pockets. The exploration process is regarded as complete when there are no "unknown" voxels left in the observable section of the space. [3]

![fig3](https://github.com/Brandonio-c/Frontier-Exploration/assets/98168605/38b3ab6e-eb91-41cb-9796-fb104c1aed0a)
> _**Fig. 3.** Incremental frontier detection and clustering. The top showcases detection and removal of outdated frontiers. The bottom illustrates the detection of a new frontier and its subsequent division. Adapted from [5]_

In traditional frontier exploration, frontiers are perceived as the known-free voxels adjacent to unknown ones [1]. Such frontiers, which are usually identified by processing the complete map, provide relatively coarse information. For improved planning and scalability, especially in expansive scenes, the approach has been modified. Here, detailed information is extracted from frontiers through an incremental methodology, operating within the locally updated map.

**A. Frontier Information Structure:**
Every time a new frontier cluster is formed, an associated Frontier Information Structure (FIS) is calculated. This structure retains all cells of the cluster, their average position, and an axis-aligned bounding box (AABB) for the cluster. This AABB aids in rapidly recognizing frontier changes. For exploration planning, potential viewpoints surrounding the cluster are produced, and a linked list containing connection costs between this and all other clusters is maintained. 

**B. Incremental Frontier Detection and Clustering:**
Upon every map update, the AABB of the updated region is logged. Within this AABB, outdated frontier clusters are discarded, and new ones are sought.

**C. Viewpoint Generation and Cost Update:**
Some methods simply guided agents to a cluster's center, this approach advocates for detailed decision-making as shown in fig. 4. Upon the creation of a cluster, numerous viewpoints around it are generated. The cost between clusters, required for exploration planning, is estimated using an efficient collision-free path-finding algorithm, with provisions for incremental computations to enhance performance. 

![fig4](https://github.com/Brandonio-c/Frontier-Exploration/assets/98168605/a64eb888-1a0b-46ee-9fad-dbded2e8d2c2)
> _**Fig. 4.** Depicting exploration motion in three stages: determining the shortest tour encompassing frontier clusters, refining a local segment of this global tour, and finally generating a secure, time-optimized trajectory leading to the refined tour's initial viewpoint. Adapted from [5]_


### Frontier Exploration Sensors and Mapping
Frontier exploration is fundamentally dependent on sensors. Sensors provide an agent/robotic system information about its environment. Common sensors utilised within the field include LiDAR, cameras, depth sensors, inertial measurement units (IMU), time of flight (TOF) and many more. In recent frontier exploration projects, agents are able to create and update maps of the region being explored in real-time by employing Simultaneous Localization and Mapping (SLAM) algorithms which often employ 3D occupancy grid maps and aid in efficient real-time navigation when employed in a human-machine teamed environment [4] - [6].

### Decision-Making in Frontier Exploration
Decision-making in frontier exploration involves determining the agent's next optimal path of best action to arrive at a destination or waypoint. To make appropriate choices, this method integrates the agent's a-priori knowledge of the environment, sensor data, and exploratory policy [7]

**Balancing Exploration and Exploitation:**
Exploration is the process of seeking new information, while exploitation is the utilization of existing knowledge or resources. Effective frontier exploration strategies seek to obtain a policy which "balances the exploration of new actions and the exploitation of known good actions to improve the agent's performance" [8].

**Risk Assessment in Exploration:**
Risk assessment examines potential obstacles or risks in unexplored territories. To decide on safe exploration policies, agents must evaluate risks related to frontiers, such as collision danger or environmental concerns. Path planning is a field of research that deals with effective agent decision-making for robotic planning to enable agents to actively avoid obstacles within their environment whilst conducting frontier exploration and has been incorporated into many recent frontier-exploration projects [3] 

### Robotic Sensing and Perception
1. **Sensor Technologies in Frontier Exploration:**
Although modern-day sensor technologies are relatively precise, minor errors introduced due to environmental factors almost always introduce issues into agent navigation whereby agent localisation and/or pose estimation within the environment is cascadingly affected. The open research field of SLAM aims to solve this through algorithmic matching of environment features to correct agent pose and localisation errors and subsequent environment mapping [9].

2. **Perception Challenges in Unknown Environments:**
Navigating unknown environments poses perception various challenges. Agents must often deal with dynamic changes within the environment (e.g. people walking through a scene), varying lighting conditions, and the presence of unexpected obstacles, necessitating robust perception algorithms and techniques.

### Simultaneous Mapping and Localization (SLAM)
**Building Maps of the Explored Area:**
Mapping techniques like occupancy grids or voxel-based mapping are often used for constructing detailed representations of explored areas [4] - [6], [9].  Most modern projects aim to build 3D maps of the environment and these maps help the agent plan paths, avoid obstacles, and maintain spatial awareness. These maps are also crucial for use in the human-machine teamed environment as they allow human operators to interact with robotically sensed information in an efficient manner. 

## Key Results
![exploration_office](https://github.com/Brandonio-c/Frontier-Exploration/assets/98168605/12cd489e-52cc-4524-952f-c33d798ec1e2)
> _**Fig. 5.** Frontier exploration running in a simulation. Adapted from [5]_

Significant developments in the subject of frontier exploration have transformed the capacities of agents, especially UAVs and mobile agents, to navigate and survey unexplored territories. Important outcomes and accomplishments in this field include:

### Efficiency to explore unknown environments.
Frontier exploration algorithms have significantly improved in efficiency from when the field was first proposed by Yamauchi in 1997 [1] to today. State-of-the-art frontier exploration projects use algorithms such as

### Map Generation
Making accurate representations of the places explored environment is one of the primary objectives of frontier exploration. Significant improvement in map generation can be visually observed below by contrasting the first frontier-exploration-generated environment map to a generated map from a 2023 frontier-exploration project (EGO-Swarm, FUEL) [4],[5]: 

### Frontier-Selection.
Frontier selection algorithms incorporate factors like uncertainty, obstacles, and information gain, with the objective of optimal environment exploration to strategically prioritise frontiers. From the original concept, [1] presents a method that selects frontiers in evidence grids by identifying cells with open space adjacent to unexplored space, marking them as frontier edge cells, and grouping adjacent edge cells into frontier regions. In a more recent implementation, [5] selects frontiers by through a more complex algorithm that uses incremental frontier updates, rich viewpoint generation, and B-spline trajectory planning to more efficiently select frontiers. 

### Dynamic and Changing Environments:
Some modern frontier exploration algorithms [4] can adapt to dynamic changes and are not limited to static situations. Sensor-equipped agents continuously update their maps and exploration paths to account for moving objects, obstacles, and general dynamic environmental circumstances. This adaptability ensures that the goal of optimal environment exploration remains effective in scenarios where the environment is not static.


### Scalability and Adaptability: 
Multi-agent frontier exploration approaches [4], [2], [10] have showcased scalability for the use of unknown environmental mapping in a teamed/swarmed environment. Similar approaches are shown in [11] and also demonstrate robust and effective frontier exploration and mapping in  both small indoor (complex) environments and large-scale outdoor areas, making them versatile tools for a wide range of applications. 


## Relationship to Decision-Making in Robotics
Decision-making in robotics refers to the process by which an autonomous agent makes choices and takes actions to achieve the agent's goals or objectives. It involves selecting the most appropriate actions or behaviours based on the agent's current perception of the environment, its internal state, and predefined objectives. A Markov Decision Process (MDP) is a discrete-time stochastic control process that provides a mathematical framework to model decision-making in robotics and is defined by a four-part tuple; (S, A, P, R) where: 

S is the agent's state space <br>
A is the agent's action space <br>
P is the transition probability <br>
R is some reward funciton <br>

Frontier exploration is intimately tied to decision-making in robotics as it involves fully an agent constantly making autonomous choices and hence taking actions to achieve the goal of environment exploration wherein S is the environment (explored and unexplored), A is the agent's movement through and sensing of the environment, P is the transition probability given the environment and R is a provided function or policy that is used to influence the autonomous agent to explore frontiers. Frontier exploration uses MDPs to maximize the agent's actions in unexplored territories. Frontier exploration scenarios are particularly suited for MDPs because they offer a formal framework for modelling decision-making issues under uncertainty. The agent must autonomously decide an optimal policy on its exploration journey while accounting for a number of goals, such as information gathering and coverage. Every action, such as moving locations or gaining sensor information, has a corresponding benefit or cost, and the agent seeks to identify an action that maximizes its anticipated cumulative benefit over time.

Reinforcement Learning is a robotic decision-making paradigm used within machine learning whereby an agent learns an optimal policy by interacting with an environment and receiving rewards based on some goal. Recent frontier exploration projects [8], [12] have adopted reinforcement and deep-reinforcement learning techniques to take optimal actions in areas such as obstacle avoidance and path planning. These algorithms use a reward-based system wherein desirable actions, like successfully avoiding obstacles, are rewarded positively, while undesirable outcomes, like collisions, are penalized. The algorithm used in [12] employs a deep-RL strategy to "learn a frontier semantic policy that selects long-term exploration goals." which further demonstrates the direct applicability of frontier exploration to decision-making in robotics. 

## Variants

Frontier exploration is a diverse area of research, and many variations and extensions exist. A brief summary of several major variations is provided below:

1. **Multi-Agent Exploration:** 
The objective of multi-agent frontier exploration is to efficiently distribute exploration tasks among a team/swarm of agents. Agents explore various locations simultaneously while avoiding repetition and collisions thanks to coordination techniques including task allocation algorithms and communication protocols.

2. **Time-Optimal Frontier Exploration:**
The objective of time-optimized exploration is to reduce the amount of time needed to fully explore an environment. This variation takes into consideration variables such as agent speed and resource constraints. This group of algorithms focuses on designing path policies that allow agents to explore as much as they can in a constrained amount of time, which is useful in time-sensitive applications like search and rescue.

3. **Human-Robot Collaboration in Frontier Exploration:** 
This variation has a focus on the human-machine-teamed environment. Agents assist individuals in exploring new or hazardous environments by automatically recognizing obstacles or hazards and recommending potential areas of interest. Agent exploration can also be directed by human inputs, preferences, or high-level instructions. 

4. **Sparse Frontier Exploration:**
Rather than thoroughly surveying the entire area, sparse exploration concentrates on locating and investigating only the most valuable or informative frontiers. Agents can maximize their exploration efforts in applications like data collection by providing higher priority to locations with greater ambiguity or relevance.

## Important Applications
Frontier exploration has significant applications in several fields, enabling agents and autonomous systems to take on an array of tasks such as:

1. **Autonomous Exploration:** 
Frontier exploration techniques  will play a vital role in enabling robotic exploration of unexplored territories in environments that are inaccessible to humans. Autonomous navigation techniques, for instance, have been used by rovers like NASA's Curiosity to traverse the Martian landscape and acquire significant knowledge of the planet's geology and climate [Read More Here](https://www.jpl.nasa.gov/news/nasas-mars-curiosity-debuts-autonomous-navigation). Some recent expeditions for underwater robots used in deep-sea exploration have also employed autonomous exploration algorithms to explore previously unexplored depths, find new species, and examine underwater characteristics [Read more here](https://www.space.com/orpheus-ocean-autonomous-submarine-europa-technology). 

2. **Search and Rescue:** 
Frontier exploration may play a crucial role in future search and rescue operations, helping locate and assist individuals in disaster-stricken areas [13]. 


3. **Agriculture:** P
Frontier exploration may have applications in assisting with precision farming and agricultural field monitoring in agriculture settings [14].

5. **Mining:** 
Frontier exploration may have applications in the mining industry, where robots may be employed to explore and map underground mines to increase safety and efficiency [15]. 

## Open Research Questions

Frontier exploration is an active field with continuous research addressing numerous opportunities and difficulties. Open research issues and areas of investigation in this area include:

### Autonomous Exploration Efficiency:
1. **Multi-Robot Coordination:**
How can several agents work together effectively to explore new frontiers while maximizing coverage and reducing redundancy? Real-time coordination of various agents' actions is still a difficult task.
2. **Adaptive Exploration:**
How can agents modify their exploration tactics in response to environmental factors like resource availability, terrain roughness, or environmental conditions?

### Robotic Sensing and Perception: 
1. **Enhanced Sensor Integration:**
How can agents enhance their perception abilities in activities requiring frontier exploration by integrating and utilizing a wider variety of sensors, such as cutting-edge vision systems, radar, and spectroscopy?
2. **Dealing with Uncertainty:**
How can agents operate in unpredictable situations with noisy sensor data? It is crucial to have excellent mapping and perception methods that can function even under difficult circumstances.

### Decision-Making and Planning:
1. **Optimal Path Planning:** 
What path-planning algorithms are most effective and efficient for guiding agents through challenging environments? How do these algorithms take into account practical limits like energy restrictions or security concerns?
2. **Human-Robot Collaboration:**
How can agents effectively cooperate in a human-machine-teamed environment or support human operators in situations involving frontier exploration? This covers communication and joint decision-making techniques.

### Mapping and Localization:
1. **Long-Term Mapping:**
How can agents keep precise and current maps of their surroundings during prolonged periods of exploration, taking into account environmental changes and sensor deterioration?
2. **Resource-Efficient Mapping:**
How to create methods for resource-efficient mapping that maximize the use of their onboard processing power, memory, and communication bandwidth?

### Adaptation to Dynamic Environments:
1. **Dynamic Object Handling:**
How are agents capable of adjusting to dynamic and shifting surroundings, such as those with shifting topography or moving obstacles? It is crucial to develop methods for immediate re-planning and barrier avoidance.
2. **Environmental Changes:**
How are severe environmental changes, including those caused by emergencies or damaged infrastructure, detected and handled by agents during exploration missions?

### Human-Robot Interaction:
1. **User-Friendly Interfaces:** 
What are the most effective approaches to create user interfaces and interaction modalities that allow users to effectively monitor or control autonomous frontier exploration tasks?
2. **Safety and Ethical Considerations:**
How might safety precautions and ethical considerations be incorporated into autonomous exploration missions, particularly in situations when agents are operating close to people or in delicate environments?

### Scalability and Generalization:
1. **Scalable Solutions:**
How can efficiency be maintained while scaling up techniques and methodologies for frontier exploration in big, complicated, or uncharted environments?
2. **Generalization Across Domains:**
Can generalization across domains be made using the lessons acquired from one area of frontier exploration?

## References:

For more in-depth information on frontier exploration and related topics, please refer to the following references:

1. Yamauchi, B. (1997), A frontier-based approach for autonomous exploration, in 'Proceedings 1997 IEEE International Symposium on Computational Intelligence in Robotics and Automation CIRA97. Towards New Computational Principles for Robotics and Automation', IEEE Comput. Soc. Press, doi: 10.1109/cira.1997.613851

2. Jain, U., Tiwari, R. and Godfrey, W. W. (2017), Comparative study of frontier based exploration methods, in '2017 Conference on Information and Communication Technology (CICT)', IEEE, doi: 10.1109/infocomtech.2017.8340589

3. Chen, X., Zheng, J. and Hu, Q. (2023), 'A Hybrid Planning Method for 3D Autonomous Exploration in Unknown Environments With a UAV', IEEE Transactions on Automation Science and Engineering, 1--12. doi: 10.1109/tase.2023.3316207

4. Zhou, X., Zhu, J., Zhou, H., Xu, C. and Gao, F. (2021), EGO-Swarm: A Fully Autonomous and Decentralized Quadrotor Swarm System in Cluttered Environments, in '2021 IEEE International Conference on Robotics and Automation (ICRA)', IEEE doi: 10.1109/icra48506.2021.9561902

5. Zhou, B., Zhang, Y., Chen, X. and Shen, S. (2020), 'FUEL: Fast UAV Exploration using Incremental Frontier Structure and Hierarchical Planning', arXiv. doi: 10.48550/ARXIV.2010.11561

6. Schmid, L., Pantic, M., Khanna, R., Ott, L., Siegwart, R. and Nieto, J. (2020), 'An Efficient Sampling-Based Method for Online Informative Path Planning in Unknown Environments', IEEE Robotics and Automation Letters 5(2), 1500--1507.

7. Milas, A., Ivanovic, A. and Petrovic, T. (2023), 'ASEP: An Autonomous Semantic Exploration Planner With Object Labeling', IEEE Access 11, 107169--107183. doi: 10.1109/access.2023.3320645

8. Leong, K. (2023), 'Reinforcement Learning with Frontier-Based Exploration via Autonomous Environment', arXiv. doi: 10.48550/ARXIV.2307.07296

9. Zhu, S., Sun, X., Sun, Z. and Yuan, J. (2023), RGB-D SLAM: Active RGB-D SLAM with Active Exploration, Adaptive TEB and Active Loop Closure, in '2023 42nd Chinese Control Conference (CCC)', IEEE, doi: 10.23919/ccc58697.2023.10240308

10. Yui, Y., Zhang, X., Shen, H., Lu, H. and Tian, B. (2023), DPPM: Decentralized Exploration Planning for Multi-UAV Systems Using Lightweight Information Structure, IEEE Transactions on Intelligent Vehicles, 1-13. doi: 10.1109/TIV.2023.3322705

11. Saleh, I., Borhan, N., Yunus, A., Rahiman, W., Novaliendry, D. and Risfendra (2023), Simulation of Real-Time Frontier Exploration in Confined and Cluttered Environment, in '2023 IEEE International Conference on Automatic Control and Intelligent Systems (I2CACIS)', IEEE, doi: 10.1109/i2cacis57635.2023.10193051

12. Yu, B., Kasaei, H. and Cao, M. (2023), Frontier Semantic Exploration for Visual Target Navigation, in '2023 IEEE International Conference on Robotics and Automation (ICRA)', IEEE, doi: 10.1109/icra48891.2023.10161059

13. D. C. Schedl et al. ,(2021), An autonomous drone for search and rescue in forests using airborne optical sectioning.Sci. Robot.6,eabg1188, doi: 10.1126/scirobotics.abg1188

14. Fasiolo, D., Scalera, L., Maset, E., Gasparetto, A., (2023),  Towards autonomous mapping in agriculture: A review of supportive technologies for ground robotics, Robotics and Autonomous Systems, Volume 169, doi:  10.1016/j.robot.2023.104514.

15. C. Papachristos, S. Khattak, F. Mascarich and K. Alexis, "Autonomous Navigation and Mapping in Underground Mines Using Aerial Robots," 2019 IEEE Aerospace Conference, Big Sky, MT, USA, 2019, pp. 1-8, doi: 10.1109/AERO.2019.8741532.


    


