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

Frontier exploration is motivated by the desire to investigate areas that are dangerous, unreachable, or have not yet been visited by humans. These unexplored environments can be anything from deep-sea locales to regions of space to Earth's disaster-stricken areas. Mapping the investigated area, deciding where to explore next, and adapting to dynamic and changing conditions are among the primary open research areas of frontier exploration. In the following article, an agent refers to an autonomous robotic platform of some design (UGV, UAV etc)

## Formal Definition

Frontier exploration is the identification and methodical investigation of "frontiers," or unexplored boundaries that separate the known and unknown regions within an environment. These frontiers represent areas where the agent has incomplete or uncertain information about its surroundings and are typically associated with regions that could contain valuable information, obstacles, or points of interest. Frontier exploration is centred on the challenge of independently exploring and mapping these unexplored frontiers in order to identify noteworthy or interesting locations. 

Algorithms for frontier exploration, like ADD PAPER FROM REFERENCES, are developed to automate the process of path planning and obstacle avoidance along routes to the frontiers.

ADD SOME INFO HERE ABOUT ALGORITHMS (MAYBE A FORMAL ALGORITHM?)

Frontier exploration is a fundamental area within the field of autonomous robotics, primarily applied to Unmanned Aerial Vehicles (UAVs) and mobile robots. Frontier exploration is essential for many applications, notably search and rescue operations, environmental monitoring, and mapping of indoor or outdoor environments.

ADD SOME PICS/ VIDS HERE FOR FRONTIER EXPLORATION 

## Overview 

### Frontier Exploration Basic
1. **Key Components: Sensors and Mapping:**
Frontier exploration is fundamentally dependent on sensors. Sensors provide an agent/robotic system information about its environment. Common sensors utilised within the field include LiDAR, cameras, depth sensors, inertial measurement units (IMU), time of flight (TOF) and many more. In recent frontier exploration projects, agents are able to create and update maps of the region being explored in real-time by employing Simultaneous Localization and Mapping (SLAM) algorithms which often employ 3D occupancy grid maps and aid in efficient real-time navigation when employed in a human-machine teamed environment

### Frontier Exploration Algorithms
1. **Frontier-Based Exploration:**
Algorithms for frontier exploration focus on the frontiers, finding and choosing those that offer the most exciting potential for discovery. When the agent travels to these frontiers, it gains new knowledge about its surroundings, including the location of obstacles and their features.

ADD PICTURES AND EQUATIONS HERE

2. **Coverage-Based Frontier Exploration:**
These algorithms ensure that an agent thoroughly explores every region by giving priority to investigating new sections of the environment. Algorithms such as Spiral and grid-based patterns have been used to help achieve uniform coverage.


3. **Information-Gain Frontier Exploration:**
These algorithms are designed to maximize the agent's ability to learn. They frequently follow metrics like entropy or mutual information, which quantify the uncertainty or information content of uncharted territory, to concentrate on places that promise the most interesting data.


### Decision-Making in Frontier Exploration
1. **The Role of Decision-Making:**
Decision-making in frontier exploration involves determining the agent's next optimal path of best action to arrive at a destination or waypoint. To make appropriate choices, this method integrates the agent's a-priori knowledge of the environment, sensor data, and exploratory policy.

2. **Balancing Exploration and Exploitation:**
Exploration is the process of seeking new information, while exploitation is the utilization of existing knowledge or resources. Effective exploration strategies often seek to strike a balance between exploitation and exploration.

ADD EXAMPLE HERE 

4. **Risk Assessment in Exploration:**
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
Frontier selection algorithms incorporate factors like uncertainty, obstacles, and information gain, with the objective of optimal environment exploration to strategically prioritizs frontiers. The integration of Markov decision processes (MDPs) and reinforcement learning has further optimized exploration strategies, enabling agents to take actions that maximize environmental understanding through pre-learned policies.

### Dynamic and Changing Environments:
Some modern frontier exploration algorithms [ADD REFERENCE] can adapt to dynamic changes and are not limited to static situations. Sensor-equipped agents continuously update their maps and exploration paths to account for moving objects, obstacles, and general dynamic environmental circumstances. This adaptability ensures that the goal of optimal environment exploration remains effective in scenarios where the environment is not static.

### Real-World Applications: 
Frontier exploration has transitioned from theoretical and simulation-based research to practical applications. Physical robotic agents equipped with frontier exploration capabilities are increasingly deployed in real-world scenarios such as search and rescue operations, precision agriculture, and infrastructure inspection. These applications demonstrate the field's impact on addressing critical challenges and improving decision support in domains where efficient exploration and mapping are essential [ADD REFERENCE].

### Scalability and Adaptability: 
Multi-agent frontier exploration approaches [ADD REFERENCE] have showcased scalability for the use of unknown environmental mapping in a teamed/swarmed environment. These approaches also demonstrate robust and effective frontier exploration and mapping in  both small indoor (complex) environments and large-scale outdoor areas, making them versatile tools for a wide range of applications. 


## Relationship to Decision-Making in Robotics
Frontier exploration in robotics is intimately tied to decision-making processes, frequently utilizing complex methods like Reinforcement Learning (RL) and Markov Decision Processes (MDPs) to maximize robot actions in uncharted areas. Frontier exploration scenarios are particularly suited for MDPs because they offer a formal framework for modelling decision-making issues under uncertainty. The agent must autonomously decide an optimal policy on its exploration journey while accounting for a number of goals, such as information gathering and coverage. Every action, such as moving locations or gaining sensor information, has a corresponding benefit or cost, and the agent seeks to identify an action that maximizes its anticipated cumulative benefit over time.

Reinforcement learning is a powerful tool employed in frontier exploration to take optimal actions in areas such as obstacle avoidance and path planning. For example, as observed in [ADD REFERENCE] an agent employs reinforcement learning algorithms to optimal paths to avoid obstacles within the environment whilst effectively exploring frontiers. These algorithms use a reward-based system wherein desirable actions, like successfully avoiding obstacles, are rewarded positively, while undesirable outcomes, like collisions, are penalized. Agents can modify their decision-making process and develop obstacle-avoidance policies by learning over time from these rewards. This allows agents efficiently explore unexplored territories while navigating safely around obstacles within the terrain and making sensible choices to prevent collisions [ADD REFERENCE].

Deep Q-Networks (DQNs), have also been applied to frontier exploration tasks [ADD REFERENCE]. 

A real world example of decision making being employed by agents through frontier exploration is observed [ADD REFERENCE TO PROJECT]

## Variants

Frontier exploration is a versatile field, and there are several variants and extensions of the basic frontier exploration concept. Here's a brief overview of some notable variants:

1. **Multi-Robot Exploration:** 
In scenarios involving multiple robots or drones, the coordination and collaboration of robots become crucial. Multi-robot frontier exploration focuses on distributing exploration tasks among a team of robots efficiently. Coordination mechanisms, such as task allocation algorithms and communication protocols, are used to ensure that robots explore different areas while avoiding redundancy and collisions.

2. **Dynamic Environment Exploration:** 
Dynamic environment Frontier Exploration: In dynamic environments where objects or obstacles can move or change over time, dynamic frontier exploration adapts to these changes. Robots continuously update their maps and exploration plans to account for dynamic obstacles or evolving environmental conditions, ensuring effective exploration even in volatile settings.

3. **Time-Optimal Frontier Exploration:** Optimizing exploration considering limited resources.
Time-optimized exploration aims to minimize the time required to explore an environment fully. This variant considers factors like robot speed, battery life, and the urgency of exploration. Algorithms in this category focus on planning paths that allow robots to explore as much as possible in a limited time frame, which is valuable in time-sensitive applications like search and rescue.

4. **Dynamic environment Frontier Exploration:** 
In dynamic environments where objects or obstacles can move or change over time, dynamic frontier exploration adapts to these changes. Robots continuously update their maps and exploration plans to account for dynamic obstacles or evolving environmental conditions, ensuring effective exploration even in volatile settings.

5. **Human-Robot Collaboration in Frontier Exploration:** 
This variant emphasizes the collaboration between robots and human operators. Robots assist humans in exploring unknown or hazardous environments by autonomously identifying frontiers and suggesting points of interest for further investigation. Human inputs, preferences, or high-level directives can guide robot exploration.

6. **Sparse Frontier Exploration:**
Sparse exploration focuses on identifying and exploring only the most valuable or informative frontiers, rather than exhaustively covering the entire environment. By prioritizing regions with higher uncertainty or relevance, robots can optimize their exploration efforts in applications like scientific data collection.


7. **Adaptive Frontier Exploration:**
Adaptive exploration techniques enable robots to adjust their exploration strategies based on real-time feedback and changing mission objectives. Machine learning and adaptive control methods play a role in helping robots learn and adapt their exploration behaviours over time.

## Important Applications

Frontier exploration has found important applications across various domains, empowering robots and autonomous systems to tackle diverse challenges:

1. **Autonomous Exploration:** Enabling robots to explore uncharted territories in space, deep sea, and hazardous environments.
Frontier exploration techniques are vital for enabling robots to explore uncharted territories in environments that are inaccessible or hazardous to humans. In space exploration, rovers like NASA's Curiosity have employed these methods to traverse the Martian landscape and gather valuable data about the planet's geology and climate. In deep-sea exploration, underwater robots equipped with sonar and cameras use frontier-based algorithms to navigate the unexplored depths, discover new species, and investigate underwater features. Additionally, frontier exploration aids in the exploration of hostile environments such as nuclear facilities, volcanoes, and radioactive zones, where robots can safely gather data without exposing humans to danger.


2. **Search and Rescue:** Finding and assisting people in disaster-stricken areas.
Frontier exploration plays a crucial role in search and rescue operations, helping locate and assist individuals in disaster-stricken areas. Unmanned aerial vehicles (UAVs) equipped with thermal cameras and sensors can swiftly search for survivors in the aftermath of earthquakes, hurricanes, or avalanches. These robots use frontier-based techniques to identify areas with potential signs of life or survivors in need of help. Furthermore, ground robots can navigate hazardous terrain and debris to reach trapped victims, enhancing the effectiveness of search and rescue missions.


3. **Agriculture:** Precision farming and monitoring of crop fields.
In agriculture, frontier exploration contributes to precision farming and the monitoring of crop fields. Autonomous ground robots equipped with sensors and cameras can systematically survey fields, identify crop health issues, and optimize the use of resources like water and fertilizers. By efficiently exploring agricultural landscapes, these robots help farmers make data-driven decisions to improve crop yields, reduce costs, and minimize environmental impact. They can also detect and respond to anomalies such as pest infestations or diseases, enabling early intervention and crop protection.

4. **Mining:** Exploring and mapping mines to enhance safety and efficiency.
Frontier exploration is valuable in the mining industry, where robots are used to explore and map underground mines to enhance safety and efficiency. Autonomous drones and ground robots equipped with LiDAR and mapping sensors can navigate complex underground environments, assess geological conditions, and create detailed 3D maps of mines. This information aids in mine planning, hazard identification, and resource management. By exploring and mapping mines autonomously, robots contribute to minimizing risks for human miners and improving the productivity of mining operations.


## Open Research Questions

Frontier exploration is a dynamic field with ongoing research that addresses various challenges and opportunities. Some of the open research questions and areas of exploration in this field include:

1. **Autonomous Exploration Efficiency:** 
### Multi-Robot Coordination: 
How can multiple robots collaborate efficiently in frontier exploration tasks to maximize coverage and minimize redundancy? Coordinating the actions of multiple agents in real-time remains a complex challenge.
### Adaptive Exploration: 
How can robots adapt their exploration strategies based on the characteristics of the environment, such as terrain ruggedness, resource distribution, or environmental conditions?

2. **Robotic Sensing and Perception:** 
### Enhanced Sensor Integration: 
How can robots integrate and leverage a broader range of sensors, including advanced vision systems, radar, and spectroscopy, to improve their perception capabilities in frontier exploration tasks?
### Dealing with Uncertainty: 
How can robots handle uncertainty and noisy sensor data in unknown environments? Robust perception and mapping techniques that can operate effectively in adverse conditions are essential.

3. **Decision-Making and Planning:**
### Optimal Path Planning: 
What are the most efficient and effective path-planning algorithms for robots to navigate complex and dynamic environments? How can these algorithms account for real-world constraints, such as energy limitations or safety considerations?
### Human-Robot Collaboration: 
How can robots effectively collaborate with humans or work alongside them in frontier exploration scenarios? This includes shared decision-making and communication strategies.


4. **Mapping and Localization:**
### Long-Term Mapping:
How can robots maintain accurate and up-to-date maps of environments over extended periods of exploration, considering changes in the environment and sensor degradation?
### Resource-Efficient Mapping: 
Can robots develop techniques for resource-efficient mapping, optimizing the use of onboard computation, memory, and communication bandwidth?

5. **Adaptation to Dynamic Environments:**
### Dynamic Object Handling: 
How can robots adapt to dynamic and changing environments, such as those with moving obstacles or evolving terrain? Developing strategies for real-time re-planning and obstacle avoidance is essential.
### Environmental Changes: 
How can robots detect and respond to significant changes in the environment, such as natural disasters or infrastructure alterations, during exploration missions?

6. **Human-Robot Interaction:**
### User-Friendly Interfaces: 
What are the best ways to design user interfaces and interaction modalities that allow humans to supervise or intervene in autonomous frontier exploration tasks effectively?
### Safety and Ethical Considerations: 
How can ethical considerations and safety protocols be integrated into autonomous exploration missions, especially in scenarios where robots operate near humans or sensitive environments?

7. **Scalability and Generalization:**
### Scalable Solutions: 
How can frontier exploration algorithms and methods scale up to handle large, complex, or unknown environments while maintaining efficiency?
### Generalization Across Domains: 
Can lessons learned from one domain of frontier exploration be applied to others, facilitating cross-domain generalization?

## References

For more in-depth information on frontier exploration and related topics, please refer to the following references:

1. [Zhou, B., Zhang, Y., Chen, X. and Shen, S. (2020), 'FUEL: Fast UAV Exploration using Incremental Frontier Structure and Hierarchical Planning', arXiv. doi: 10.48550/ARXIV.2010.11561 ](#zhou2020)

2. [Schmid, L., Pantic, M., Khanna, R., Ott, L., Siegwart, R. and Nieto, J. (2020), 'An Efficient Sampling-Based Method for Online Informative Path Planning in Unknown Environments', IEEE Robotics and Automation Letters 5(2), 1500--1507.doi: 10.1109/lra.2020.2969191](#schmid2020)

3. [Zhou, X., Zhu, J., Zhou, H., Xu, C. and Gao, F. (2021), EGO-Swarm: A Fully Autonomous and Decentralized Quadrotor Swarm System in Cluttered Environments, in '2021 IEEE International Conference on Robotics and Automation (ICRA)', IEEE doi: 10.1109/icra48506.2021.9561902](#zhou2020)

4. [Leong, K. (2023), 'Reinforcement Learning with Frontier-Based Exploration via Autonomous Environment', arXiv. doi: 10.48550/ARXIV.2307.07296](#leon2023)

5. [Jain, U., Tiwari, R. and Godfrey, W. W. (2017), Comparative study of frontier based exploration methods, in '2017 Conference on Information and Communication Technology (CICT)', IEEE, doi: 10.1109/infocomtech.2017.8340589](#jain2017)

6. [Yamauchi, B. (1997), A frontier-based approach for autonomous exploration, in 'Proceedings 1997 IEEE International Symposium on Computational Intelligence in Robotics and Automation CIRA97. Towards New Computational Principles for Robotics and Automation', IEEE Comput. Soc. Press, doi: 10.1109/cira.1997.613851](#yama1997)

7. [Yu, B., Kasaei, H. and Cao, M. (2023), Frontier Semantic Exploration for Visual Target Navigation, in '2023 IEEE International Conference on Robotics and Automation (ICRA)', IEEE, doi: 10.1109/icra48891.2023.10161059](#yu2023)

8. [Zhao, Y., Yan, L., Xie, H., Dai, J. and Wei, P. (2023), 'Autonomous Exploration Method for Fast Unknown Environment Mapping by Using UAV Equipped with Limited FOV Sensor', IEEE Transactions on Industrial Electronics, 1--10. doi: 10.1109/tie.2023.3285921](#zhao2023)

9. [Zhu, S., Sun, X., Sun, Z. and Yuan, J. (2023), RGB-D SLAM: Active RGB-D SLAM with Active Exploration, Adaptive TEB and Active Loop Closure, in '2023 42nd Chinese Control Conference (CCC)', IEEE, doi: 10.23919/ccc58697.2023.10240308](#zhu2023)

10. [Lee, E. M., Youn, D. and Myung, H. (2023), THE-Planner: Topological and Hierarchical Exploration Path Planner for Fast 3D Mapping of Outdoor Structures with UAVs, in '2023 20th International Conference on Ubiquitous Robots (UR)', IEEE, doi: 10.1109/ur57808.2023.10202255](#lee2023)

11. [Saleh, I., Borhan, N., Yunus, A., Rahiman, W., Novaliendry, D. and Risfendra (2023), Simulation of Real-Time Frontier Exploration in Confined &amp$$ Cluttered Environment, in '2023 IEEE International Conference on Automatic Control and Intelligent Systems (I2CACIS)', IEEE, doi: 10.1109/i2cacis57635.2023.10193051](#saleh2023)

12. [Milas, A., Ivanovic, A. and Petrovic, T. (2023), 'ASEP: An Autonomous Semantic Exploration Planner With Object Labeling', IEEE Access 11, 107169--107183. doi: 10.1109/access.2023.3320645](#milas2023)

13. [Liu, Y.-F., Hsieh, C.-Y. and Kuo, S.-Y. (2023), Boomerang: Physical-Aware Design Space Exploration Framework on RISC-V SonicBOOM Microarchitecture, in '2023 IEEE 34th International Conference on Application-specific Systems, Architectures and Processors (ASAP)', IEEE, doi: 10.1109/asap57973.2023.00026](#liu2023)

14. [Chen, X., Zheng, J. and Hu, Q. (2023), 'A Hybrid Planning Method for 3D Autonomous Exploration in Unknown Environments With a UAV', IEEE Transactions on Automation Science and Engineering, 1--12. doi: 10.1109/tase.2023.3316207](#chen2023)

15. [Xiao, M., Bai, Y. and Liu, W. (2023), Hot Spots, Frontiers and Trends of International EDM/LA Research, in '2023 5th International Conference on Computer Science and Technologies in Education (CSTE)', IEEE, doi: 10.1109/cste59648.2023.00067](#xiao2023)

16. [Hui, Y., Zhang, X., Shen, H., Lu, H. and Tian, B. (2023), 'DPPM: Decentralized Exploration Planning for Multi-UAV Systems Using Lightweight Information Structure', IEEE Transactions on Intelligent Vehicles, 1-13. doi: 10.1109/TIV.2023.3322705](#hui2023)



Feel free to explore the sub-pages for additional details on each section. If you have any questions or suggestions, please don't hesitate to contact us 
