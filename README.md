## Abstract

We consider here the problem of how a teacher algorithm can enable an unknown Deep Reinforcement Learning (RL) student 
to become good at a skill over a wide diversity of environments. To do so, we study how teacher algorithms can automate 
a learning curriculum, whereby it sequentially samples parameters for stochastic procedural generation of environments. 
Because the teacher does not initially know the capacities of its student, a key challenge for the teacher is to discover
 which environments are easy, difficult or unlearnable, and in what order to propose them to maximize the efficiency of 
 learning over the learnable ones. To achieve this, we leverage a general approach in which this problem is transformed 
 into a surrogate bandit problem where the teacher aims at sampling environments in order to maximize absolute learning 
 progress. We study several algorithms that implement this approach, applying them for the first time to Deep RL, including 
 a new algorithm mapping learning progress with Gaussian mixture models (ALP-GMM). Using parameterized variants of the 
 BipedalWalker environment, we study their efficiency to personalize a learning curriculum for learners of different 
 capacities (due to different bodies), their robustness to the ratio of learnable/unlearnable environments, and their 
 scalability to higher-dimensional non-linear parameter spaces.


# Additional Visualizations


## Stump Tracks
We tested the ALP-GMM teacher when paired with 3 different walker morphologies. For each of these walkers we show the
learned walking gates after being trained on a curriculum generated by ALP-GMM. A single run of ALP-GMM allows to train
 Soft Actor-Critic controllers to master a wide range of track distributions.

####  ALP-GMM + short agent &nbsp; |ALP-GMM + default agent| ALP-GMM + quad. walker

![short](graphics/walker_gates/demo_short_stump_gmm_asquad_0.gif){:height="32%" width="32%"}
![short](graphics/walker_gates/demo_default_stump_gmm_asquad_0.gif){:height="32%" width="32%"}
![short](graphics/walker_gates/demo_quadru_stump_gmm_compact_0.gif){:height="32%" width="32%"}

![short](graphics/walker_gates/demo_short_stump_gmm_asquad_3.gif){:height="32%" width="32%"}
![short](graphics/walker_gates/demo_default_stump_gmm_asquad_1.gif){:height="32%" width="32%"}
![short](graphics/walker_gates/demo_quadru_stump_gmm_compact_3.gif){:height="32%" width="32%"}

![short](graphics/walker_gates/demo_short_stump_gmm_asquad_2.gif){:height="32%" width="32%"}
![short](graphics/walker_gates/demo_default_stump_gmm_asquad_2.gif){:height="32%" width="32%"}
![short](graphics/walker_gates/demo_quadru_stump_gmm_compact_2.gif){:height="32%" width="32%"}


![short](graphics/walker_gates/demo_short_stump_gmm_asquad_1.gif){:height="32%" width="32%"}
![short](graphics/walker_gates/demo_default_stump_gmm_asquad_3.gif){:height="32%" width="32%"}
![short](graphics/walker_gates/demo_quadru_stump_gmm_compact_1.gif){:height="32%" width="32%"}

The following videos show the evolution of parameter sampling by ALP-GMM for short, default, and quadrupedal walkers.
Learning curricula generated by ALP-GMM are tailored to the capacities of each student it is paired with.

####  ALP-GMM + short agent &nbsp; |ALP-GMM + default agent| ALP-GMM + quad. walker
![short](graphics/GMM_gmmcshortcpu21-0611.gif){:height="32%" width="32%"}
![short](graphics/GMM_gmmcdefaultcpu21-063.gif){:height="32%" width="32%"}
![short](graphics/GMM_gmmclongcpu21-060.gif){:height="32%" width="32%"}



## Hexagon Tracks
To assess whether ALP-GMM is able to scale to parameter spaces of higher dimensionality, containing irrelevant
 dimensions, and whose difficulty gradients are non-linear, we performed experiments with quadrupedal walkers on Hexagon Tracks,
  our 12-dimensional parametric Bipedal Walker environment. The following videos shows walking gates learned in a single ALP-GMM run.
![short](graphics/walker_gates/stump_gmm_demo_26.gif)

![short](graphics/walker_gates/stump_gmm_demo_compact_3.gif){:height="31%" width="31%"}
![short](graphics/walker_gates/stump_gmm_demo_compact_8.gif){:height="31%" width="31%"}
![short](graphics/walker_gates/stump_gmm_demo_compact_10.gif){:height="31%" width="31%"}
![short](graphics/walker_gates/stump_gmm_demo_compact_19.gif){:height="31%" width="31%"}
![short](graphics/walker_gates/stump_gmm_demo_compact_48.gif){:height="31%" width="31%"}
![short](graphics/walker_gates/stump_gmm_demo_compact_36.gif){:height="31%" width="31%"}