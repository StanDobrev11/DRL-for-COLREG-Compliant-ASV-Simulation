# DRL-for-COLREG-Compliant-ASV-Simulation
Project for the SoftUni's Deep Learning Course

## Abstract

Maritime transportation plays a critical role in global trade, accounting for over 80% of the world's goods movement. As automation advances, the development of autonomous surface vehicles (ASVs) is becoming increasingly relevant for safer and more efficient navigation. However, ensuring that ASVs comply with the International Regulations for Preventing Collisions at Sea (COLREGs) remains a significant challenge.

This study presents a partially implemented COLREG-compliant ASV simulation, where a reinforcement learning (RL) agent, trained using Proximal Policy Optimization (PPO), is responsible for navigating toward a waypoint while avoiding potential collisions. The agent is designed to handle static obstacles, head-on encounters, and crossing targets in a dynamic environment. Unlike many previous approaches that incorporate explicit waypoint tracking algorithms or cross-track error corrections, this implementation relies solely on a reward-based learning mechanism to shape the agent’s decision-making process.

By leveraging a structured reward function, the ASV learns collision avoidance behaviors without predefined path-following rules, demonstrating an emergent compliance with fundamental COLREG principles. The study provides insights into the effectiveness of reinforcement learning in maritime navigation and highlights the potential and limitations of a purely reward-driven training paradigm. Further improvements and extensions, including enhanced optimization strategies and real-world applicability, are discussed as part of future work.

### Assumptions and Limitations
This study makes several simplifying assumptions to focus on reinforcement learning-based collision avoidance without additional complexity:

Ship dynamics are ignored – The ASV's maneuvering characteristics, such as acceleration, turning radius, and inertia, are not explicitly modeled. The vessel is assumed to change course and speed instantly without delay.
Environmental dynamics are ignored – External factors like wind, currents, and waves are not considered in the simulation. The focus is solely on collision avoidance in an idealized static environment.
Target dynamics are stripped to basics - maintaining course and speed.
Limited scope due to time and complexity – Implementing full COLREG compliance in an RL-based agent is highly complex and time-consuming. Therefore, this research prioritizes the fundamental rules of collision avoidance and waypoint navigation.
By defining these constraints, this study aims to analyze how reinforcement learning alone, without traditional waypoint-tracking algorithms or cross-track error corrections, can develop COLREG-compliant behavior in an ASV. The results provide a foundation for future improvements and real-world applications.

### Video Rendering and Visualization
#### Visualization Elements
- White dot → Represents the own ship (ASV).
- Green dot → Represents the waypoint (WP), the ASV’s navigation goal.
- Blue dots → Represent the target ships, which may be moving or static obstacles.
#### Motion Vectors
To provide an intuitive representation of ship movements:

- Red line → Represents the own ship’s heading vector, with its length scaled to the ASV’s speed in knots.
- Blue line → Represents the heading vector of target ships, similarly scaled to target speed.
#### Tracking and CPA Visualization
- Purple ring → Displays the Closest Point of Approach (CPA) limit set for collision avoidance (default: 1 NM).
- White track line → Shows the historical path (trace) of the own ship, allowing for trajectory analysis.
- Blue track lines → Represent the path history of target ships, illustrating their movement over time.
================================================================================================================
Jupyter notebook - Project.ipynb

Link to the original repo with tracked commits: [here](https://github.com/StanDobrev11/DeepLearning/blob/master/ProjectNew/)

Link to youtube with uploaded video recordings of the training, default hyperparams agent acting and fine-tuned agent acting [here](https://youtube.com/@stanislavdobrev1369?si=eoqJwwWJWi6KfCqi)


## How to recreate results:

1. Ensure you have installed docker, ubuntu wsl and activated Docker WSL integration;
2. Clone the repo:
```bash 
git clone https://github.com/StanDobrev11/DRL-for-COLREG-Compliant-ASV-Simulation/
```
3. In the repo folder, run:
```bash
wsl
```
followed by:
```bash 
docker-compose up -d --build
```
4. Once the image has been built and up, execute:
```bash
 docker-compose logs
```
5. The above printed logs will have a line similar to:
```
pytorch-1  |     To access the server, open this file in a browser:
pytorch-1  |         file:///root/.local/share/jupyter/runtime/jpserver-7-open.html
pytorch-1  |     Or copy and paste one of these URLs:
pytorch-1  |         http://315d8b73b3aa:8888/lab?token=13636829fd2c8f3e948392078997844d1f7ef72628f3c8c2
pytorch-1  |         http://127.0.0.1:8888/lab?token=13636829fd2c8f3e948392078997844d1f7ef72628f3c8c2
```
6. Click on the last http link to run jupyter lab and access the project notebook.
7. Enjoy!
