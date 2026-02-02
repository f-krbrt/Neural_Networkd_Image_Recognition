The first version of my model simply used a single Conv2D / MaxPooling block. This version gave me really poor results (Accuracy = 0.0546 | loss = 3.5003). So I tried to create a slightly larger block with Conv2D / Conv2D / MaxPooling and the results improved significantly (Accuracy = 0.9672 | loss = 0.1308). However, the loss remained quite high (0.1308). To improve my model, I moved to two blocks: Conv2D / Conv2D / MaxPooling / Conv2D / MaxPooling and the results became even better (Accuracy = 0.9846 | loss = 0.0632). I also tried using a third block Conv2D / Conv2D / MaxPooling / Conv2D / MaxPooling / Conv2D / MaxPooling but the results degraded.

Other tests: Without dropout, it s the only time that the model's accuracy on test data was lower than the accuracy found at epoch 10 (Epoch 10 : accuracy: 0.9784 - loss: 0.0886 | Test data : accuracy: 0.9714 - loss: 0.1495). This highlights the necessity of dropout to limit overfitting. I also noticed that by progressively increasing the number of filters (32 to 64), slightly better results could be obtained.
The final modification I made was to increase the number of epochs from 10 to 20, which resulted in improved performance (slightly higher accuracy and notably lower loss).




