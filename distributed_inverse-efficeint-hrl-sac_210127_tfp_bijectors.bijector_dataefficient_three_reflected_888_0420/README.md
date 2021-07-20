Code for performing Hierarchical RL based on the following publications:

"Hierarchical Reinforcement Learning with OptimalLevel Synchronization based on a Deep GenerativeModel" by
JaeYoon Kim, Junyu Xuan, Christy Liang, and Farookh Hussain (http://arxiv.org/abs/2107.08183).

Requirements:
* TensorFlow (see http://www.tensorflow.org for how to install/upgrade)
* Gin Config (see https://github.com/google/gin-config)
* Tensorflow Agents (see https://github.com/tensorflow/agents)
* OpenAI Gym (see http://gym.openai.com/docs, be sure to install MuJoCo as well)
* NumPy (see http://www.numpy.org/)

The code is working on Tensorflow 1.xx.
The detailed requirements are in written in condalist.txt and piplist.txt.

The code combines HIRO code with Latent space code as follows.

HIRO github : https://github.com/tensorflow/models/tree/master/research/efficient-hrl
Latent space github : https://github.com/haarnoja/sac

Quick Start:

Run a training job based on the original HIRO paper on Ant Push Single as a default setting:
(Actor  of  FDMG  :  130,  All  other  NNs:  150, a_z-state =  19)

The command is the same as HIRO.

```
python scripts/local_train.py test1 hiro_orig ant_push_single base_uvf suite
```

Basic Code Guide:

The code for setting the size of neural network of each policy is included in two
files, 'agents/ddpg_agent.py' and 'configs/base_uvf.gin'.

The size of actor of FDMG is policy_s_t_units of BIJECTOR_PARAMS.
All other policies's size and a_z-state are located on 'configs/base_uvf.gin'.

All other coditions are the same as HIRO.

Maintained by Johnny Kim.
