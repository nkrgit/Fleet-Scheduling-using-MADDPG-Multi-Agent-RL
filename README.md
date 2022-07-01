# Fleet-Scheduling-using-MADDPG-Multi-Agent-RL

<h3>Goal:</h3>

* To solve a Multi-Agent Environment (i.e. Vehicle Scheduling Environment) using Multi Agent Deep Deterministic Policy Gradient (MADDPG) algorithm.

<h3>Multi-Agent Environment</h3>

* Two cars in a 4x4 environment
  * 1st car – Goal - To reach top right of the environment
  * 2nd car – Goal - To reach top left of the environment
  * State space: 16 states: {s0, s1, s2,...s15}
  * Action space: {0: down, 1: up, 2: right, 3: left, 4: no move}
  * Reward structure
    - Towards the target: 1
    - Away from the target: -3
    - Stays in same position: -5
    - Reaches target: 100
 <img src = ''>
    
<h3>Simple Adversary - OpenAI Multi Agent particle environment</h3>

* 3 agents – 1 adversary, 2 good agents (Physical deception)
* Environment – 2 landmark (Green – target landmark, Black – dummy landmark)
* Rewards:
  * For agents:
    * Positive reward - based on distance between the closest agent to target landmark
    * Negative reward – based on distance between the adversary to target landmark
  * For adversary:
    * Positive reward – based on distance between the adversary to target landmark
    
<h3>Implementation:</h3>

* Implemented Q-learning and MADDPG on both Vehicle Scheduling and Simple Adversary Environments

<h4>MADDPG:</h4>

* Every Agent has 
    * Actor Network:
       * Inputs: States, actions
       * Outputs: Probs

    * Critic Network:
       * Inputs: states, actions
       * Outputs: Q values
* To freeze weights to avoid running targets
  * Target Actor Network (i.e. performed soft updates)
  * Target Critic Network (i.e. performed soft updates)
  
<img src='https://github.com/nkrgit/Fleet-Scheduling-using-MADDPG-Multi-Agent-RL/blob/main/MADDPG_Arc.png'>

