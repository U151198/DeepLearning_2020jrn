# LunarLander

This code is based on Pytorch Tutorial code, however we have done many modifications. Now the DQN is a fully connected network as the input will no longer be images as on Pytorch Tutorial. 

The inputs to the network will now be the 8x1 state vector returned by the gym enviroment. We decided to modify the inputs of the model as being able to learn to play just from frames of the screen is something much more complex which requires a lot of time to be trained. 

This would have not been a problem if we could have ran our code in the cluster, but due to some technical difficulties we could not install gym library in it. That is why we decided to change the approach and use the state returned by our enviroment. By using this approach we could obtain a nice model within the time limit of Google Colab.

The best generated model, will be stored at your Google Drive in the folder My Drive/ReinforcementLearningOnVideoGames-master/data/models/ with the name Lunar_Lander_model.ckpt.

Also a soft update of the target network parameters has been used as we read that it improved performance. Because we were not able to do this update and copy the parameters into the target network we used the code from https://gist.github.com/abhinavsagar/a7cd1d67ad5a71589d576cd84f15b648.

We have also changed the structure of the code of the tutorial as we believe it is more structured and easier to follow in this way. The code provides functions to train the model and also a way to test how the model performs. By using the functions show_video and wrap_env from https://colab.research.google.com/drive/1A75J2xFYjpJvNWXCSM1Xcty7K3WIGrud, we can create a video showing how the model plays when running the code at Google Colab. In case the video cannot be seen here at the notebook in GitHub we have stored the video in the folder data/results.

Last but not least, we have tried different combinations of hyperparameters and kept the ones which gave us the best results. Also we have fixed the seed of the enviroment, torch and the random module so that you can obtain the same results than us by running the code.

The code structure is based on the one found in https://github.com/RMiftakhov/LunarLander-v2-drlnd/blob/master/dqn_agent.py. However, we have done some modifications to the code in order to improve the performance and selected the optimal parameters in order to improve the average obtained score.
