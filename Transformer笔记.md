## the credit assignment problem(信用分配)
With CNNs and RNNs, it is also difficult to determine which past actions contributed to current rewards（如何确定现在的奖励由哪些过去的行为所贡献？）  
[1]Michel Ma, Pierluca D’Oro, Yoshua Bengio, and Pierre-Luc Bacon. 2021. Long-Term Credit Assignment via Model-based Temporal Shortcuts. In Deep RL Workshop NeurIPS 2021.

---
## tansformer in rl(应用)
Most RL algorithms optimize the agent’s policy to select actions that maximize the expected cumulative reward.  
In deep RL, neural networks are used as function approximators for mapping the current state of the environment to the next action and for estimating future returns.
This approach is beneficial when dealing with large or continuous state spaces that make tabular methods computationally expensive and has been successful in challenging applications  
（深度学习在强化学习中经常扮演函数逼近器，用来预测在当前环境下的下一步动作和回报，它比网格式计算量更少）  
[2]Kai Arulkumaran, Marc Peter Deisenroth, Miles Brundage, and Anil Anthony Bharath. 2017. Deep Reinforcement Learning: A Brief Survey. IEEE Signal Process. Mag. 34, 6 (2017), 26–38.  
[3]Siddique Latif, Heriberto Cuayáhuitl, Farrukh Pervez, Fahad Shamshad, Hafiz Shehbaz Ali, and Erik Cambria. 2023. A survey on deep reinforcement learning for audio-based applications. Artif. Intell. Rev. 56, 3 (2023), 2193–2240.  
[4]Thanh Thi Nguyen, Ngoc Duy Nguyen, and Saeid Nahavandi. 2020. Deep Reinforcement Learning for Multiagent Systems: A Review of Challenges, Solutions, and Applications. IEEE Trans. Cybern. 50, 9 (2020), 3826–3839.  

---
## 多模态输入集成
Sometimes different data modalities, such as text, audio, and images are combined to provide additional information to the agent  
[5]
[6]
[7]

---
## transformer的应用
Transformer 模型于 2017 年首次提出[174]，并迅速对深度学习领域产生了深远影响[99]，  
[174]Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Lukasz Kaiser, and Illia Polosukhin. 2017. Attention is All you Need. In 30th Annual Conference on Neural Information Processing Systems. 5998–6008  
显著提升了自然语言处理（NLP）和计算机视觉（CV）任务的性能。这种神经网络架构的核心思想是利用自注意力机制来捕捉数据中的长程关系。  
这种跨序列建模大规模上下文的能力最初使 Transformer 模型非常适合机器翻译任务。  
此后，Transformer 模型已被应用于处理更复杂的任务，例如图像分割[144]、视觉问答[217]和语音识别[34]。  
[144] Olivier Petit, Nicolas Thome, Clément Rambour, Loic Themyr, Toby Collins, and Luc Soler. 2021. U-Net Transformer:Self and Cross Attention for Medical Image Segmentation. In Machine Learning in Medical Imaging - 12th International Workshop, MLMI, MICCAI, Vol. 12966. Springer, 267–276.  
[217] Huasong Zhong, Jingyuan Chen, Chen Shen, Hanwang Zhang, Jianqiang Huang, and Xian-Sheng Hua. 2021. Self-Adaptive Neural Module Transformer for Visual Question Answering. IEEE Trans. Multim. 23 (2021), 1264–1273.  
[34] Linhao Dong, Shuang Xu, and Bo Xu. 2018. Speech-Transformer: A No-Recurrence Sequence-to-Sequence Model for Speech Recognition. In 2018 IEEE International Conference on Acoustics, Speech and Signal Processing, ICASSP 2018, Calgary, AB, Canada, April 15-20, 2018. IEEE, 5884–5888.  

## 传统rl的难题
训练不稳定性（Unstable Training）、信用分配难题（Credit Assignment，即难以追溯奖励与动作的关联）、可解释性缺失（Lack of Interpretability）、部分可观测性（Partial Observability，智能体仅能获取环境的局部信息）  
训练不稳定性：基于梯度的 RL 算法（如 DQN、PPO）易受样本分布波动、学习率调整等影响，导致收敛困难；  
信用分配难题：长序列决策中，奖励信号往往延迟出现，传统算法难以精准定位对最终奖励有贡献的关键动作；  
部分可观测性：实际场景中，智能体难以获取环境的完整状态（如机器人导航仅依赖局部视觉），传统模型（如 MLP）难以建模状态间的依赖关系；  
可解释性差：传统神经网络的 “黑箱” 特性，导致无法追溯决策的逻辑链条，限制了在高风险场景（如医疗、自动驾驶）的应用。  


---
## tranformer的特性及其适配性
Transformer 的核心是自注意力机制（Self-Attention），其本质是通过计算序列中每个元素与其他元素的关联权重，建模全局依赖关系。这一特性使其天然适配 RL 的挑战  

