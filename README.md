# Knee_Project
The project is implemented to test the eight deep learning models on knee x ray images by rotating the activation functions.
This work focuses on automating the diagnosis of Knee Osteoarthritis (KOA) using deep learning techniques. Leveraging transfer learning and pretrained CNN architectures, the model classifies knee X-ray images according to the Kellgren-Lawrence (KL) grading system, which assesses KOA severity on a scale from 0 to 4. The model is further optimized by experimenting with various activation functions and custom dense layers.
The dataset used is derived from Osteoarthritis Initiative (OAI) or from relevant public repositories (e.g., Kaggle). It contains knee X-ray images labeled according to KL grades (0–4).
The base architecture is constructed using pretrained CNNs (e.g., NASNet, ResNet50, DenseNet) by freezing the base models layers. A custom classification head was added:

Flatten → Dense(1024, activation='swish') → 
Dense(512, activation='relu') → 
Dense(256, activation='elu') → 
Dense(5, activation='sigmoid')

In the first three layers Swish, ReLu, ELU activation functions are rotated as three Activation Function Schemes (AFS-1, AFS-2 and AFS-3) by fixing the sigmoid activation function at the last layer for the binary classification.The activation functions are rotated as three AFS as shown below:

AFS-1: elu --> swish--> relu --> sigmoid
AFS-2: swish --> relu --> elu --> sigmoid
AFS-3: relu --> elu --> swish --> sigmoid

Multiple activation function combinations were tested to find the optimal configuration and improve the diganosis accuracy.
