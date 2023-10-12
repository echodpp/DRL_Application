## Implement double DQN:
Hint: SB3 only implements (valinia) DQN (the one discussed in the class). This task asks you to implement double DQN and compare the performance of DQN with the one of double DQN. Double DQN is a minor modification of DQN. The only difference is that double DQN uses two Q networks to calculate the target labels. The reason that double DQN uses two Q networks is to reduce the over estimation of DQN. More details can be found in the slides, CS285, Berkeley Lecture 8, https://rail.eecs.berkeley.edu/deeprlcourse/static/slides/lec-8.pdf
There are two ways to complete this homework. You can either complete the exercises in the starter code notebook, https://colab.research.google.com/github/Stable-Baselines-Team/ rl-colab-notebooks/blob/sb3/dqn_sb3.ipynb, and submit the notebook. The exercises in this notebook will help you implement double DQN. Or you can directly modify the source code of DQN in SB3. If you decide to directly modify the source code of DQN in SB3 (in particular, modify the bootstrapped target), to submit, please create another Colab notebook and do something like !pip install git+”your SB3 github URL”, and run the training/testing experiments in this notebook.
   
 The source code of the 1-step TD (bootstrapped) target of DQN can be found in the train method, dqn.py (stable_baselines3/dqn/dqn.py ).
[Requirements]:
- Compare double DQN with DQN.


## [Submission]:
(We don’t need a link to your Google Drive. We only need the link to your GitHub using the Colab notebook)
1. Create a new Colab notebook.
2. !pip install git+”your github URL”
3. Training/testing experiments using the Colab notebook.
