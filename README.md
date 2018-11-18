# Regional Autoencoders 

This fork of OpenAI Baselines is modified to include an implementation of Nicholas Samoray's Undergrad Thesis: Regional Autoencoders with Deep Reinforcement Learning. All changed code is contained within the ```common/atari_wrappers.py``` file. The Regional Autoencoder is used only as a preprocessing step, with the final output being a 20 x 20 x 6 tensor to be fed into any network of your choosing. This means it can hypothetically work with any RL method the user wants. As to it's actual effectiveness for any given RL method however, that's a little less clear. For details on the implementation and general idea, check out the linked paper and slides:

[Paper](https://drive.google.com/file/d/0ByPtgS8fLWfQZ2pwZUVPT00xYVVUYS1hbEc4SzJFVjNQLUVJ/view?usp=sharing)

[Slides](https://docs.google.com/presentation/d/140BnuztjXdWlSPe8wHoPKsaLIMEI2QoChnVOQfIWVT4/edit?usp=sharing)

This was implemented with OpenAI's baselines project in order to provide a standardized approach to testing the preprocessing effectiveness. Not included with this though is the code to create the actual autoencoder that is loaded in as part of the methodology. Currently this project cannot be run "as-is" since it requires a trained autoencoder to encode the sprite values, the weight files of which were deleted. If you wish to use this before it's updated with demo weight files, any network that takes in an 8 x 8 image and outputs 2 autoencoded values should generally work fine, we specifically used a VAE. 

Below is the original description for this project.
<!--
<img src="data/logo.jpg" width=25% align="right" /> 
-->

# Baselines

OpenAI Baselines is a set of high-quality implementations of reinforcement learning algorithms.

These algorithms will make it easier for the research community to replicate, refine, and identify new ideas, and will create good baselines to build research on top of. Our DQN implementation and its variants are roughly on par with the scores in published papers. We expect they will be used as a base around which new ideas can be added, and as a tool for comparing a new approach against existing ones. 

You can install it by typing:

```bash
git clone https://github.com/openai/baselines.git
cd baselines
pip install -e .
```

- [A2C](baselines/a2c)
- [ACER](baselines/acer)
- [ACKTR](baselines/acktr)
- [DDPG](baselines/ddpg)
- [DQN](baselines/deepq)
- [GAIL](baselines/gail)
- [HER](baselines/her)
- [PPO1](baselines/ppo1) (Multi-CPU using MPI)
- [PPO2](baselines/ppo2) (Optimized for GPU)
- [TRPO](baselines/trpo_mpi)

To cite this repository in publications:

    @misc{baselines,
      author = {Dhariwal, Prafulla and Hesse, Christopher and Klimov, Oleg and Nichol, Alex and Plappert, Matthias and Radford, Alec and Schulman, John and Sidor, Szymon and Wu, Yuhuai},
      title = {OpenAI Baselines},
      year = {2017},
      publisher = {GitHub},
      journal = {GitHub repository},
      howpublished = {\url{https://github.com/openai/baselines}},
    }
