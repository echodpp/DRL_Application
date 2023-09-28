## 1. Review the tutorial notebooks in SB3:
https://github.com/Stable-Baselines-Team/rl-colab-notebooks/tre e/sb3
[Requirements]:
- GettingStartedColabNotebook 
- Saving,loadingColabNotebook
- MultiprocessingColabNotebook
- MonitorTrainingColabNotebook
- AtarigamesColabNotebook
- PyBullet:Normalizinginputfeatures
- ColabNotebook Pre-trainingusingBehaviorCloning
- ColabNotebook RLBaselines3ZooColabNotebook
- AdvancedSavingandLoadingColabNotebook
- GettingStartedColabNotebook
- GymWrappers,savingandloadingmodelsColabNotebook MultiprocessingColabNotebook
- CallbacksandhyperparametertuningColabNotebook
- CreatingacustomgymenvironmentColabNotebook

## 2. Train an agent to play any game/task in SB3 using A2C with Colab:
Hint: in this task, you don’t need to modify the source code and just need to use the APIs provided in SB3 to run the Google Colab experiments and to train/test the RL agent.
[Requirements]:
- Pick a task/game in SB3.
- Add a TensorBoard to visualize the training curves.
- Include/record the final evaluation video.
- Saving/loading the policy/model.
[Submission]:
Submit a link to the Colab notebook including the training/testing experiments and results.

## 3. Compare the n-step advantage with n-step return (mentioned in the class), vanilla advantage, GAE, as well as MC advantage for A2C algorithm:
Hint: SB3 implements Generalized Advantage Estimation (GAE) for A2C. In particular, you can find the implementation of the advantage in the method def compute_returns_and_advantage method in buffer.py (stable-baselines3/stable_baselines3/common/buffers.py) (https://github.com/DLR-RM/stable-baselines3/blob/master/stabl e_baselines3/common/buffers.py). You can also play with the hyper-parameter (gae_lambda) to get different advantages without making model/algo implementation code changes. [Requirements]:
- Compare the n-step advantage with the (vanilla) advantage, MC advantage, as well as GAE. Note that MC advantage is just optional for this assignment.

## [Submission]:
(We don’t need a link to your Google Drive. We only need the link to your GitHub using the Colab notebook)
1. CreateanewColabnotebook.
2. !pipinstallgit+”yourgithubURL”
3. Training/testingexperimentsusingtheColabnotebook.
