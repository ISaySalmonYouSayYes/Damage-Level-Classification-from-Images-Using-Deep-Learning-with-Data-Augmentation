# **Damage Level Classification from Images Using Deep Learning with Data Augmentation**
## **0. Introduction**
This project is dedicated to explore the best cost-performance value of deploying ResNet model in different sizes of database.  
Accuracy = correct/total  

## **1. result**

| Model(833 images)                  | Val Loss | Val Acc | Test Acc | Training Time | Epoch Ended | Rank |
|------------------------------------|----------|---------|----------|---------------|-------------|------|
| ResNet18                           | 0.9694   | 0.7246  | 0.7289   | 60s           | 13          | 5    |
| ResNet18 + fine-tuning             | 0.5266   | 0.8024  | 0.7711   | 60s           | 18          | 3    |
| ResNet18 + data Augmentation       | 0.7036   | 0.7365  | 0.7229   | 120s          | 34          | 6    |
| ResNet18 + fine-tuning + Augmentation | 0.5409   | 0.7844  | 0.7711   | 170s          | 47          | 4    |
| ResNet50                           | 0.8773   | 0.6587  | 0.6145   | 70s           | 4           | 8    |
| ResNet50 + fine-tuning             | 0.6015   | 0.8084  | 0.7771   | 100s          | 9           | 2    |
| ResNet50 + data Augmentation       | 0.2832   | 0.6527  | 0.6386   | 140s          | 18          | 7    |
| ResNet50 + fine-tuning + Augmentation | 0.6202   | 0.7725  | 0.8012   | 140s          | 16          | 1    |

| Model(2280 images)                 | Val Loss | Val Acc | Test Acc | Training Time | Epoch Ended | Rank |
|------------------------------------|----------|---------|----------|---------------|-------------|------|
| ResNet18                           | 0.4777   | 0.8509  | 0.8399   | 80s           | 6           | 6    |
| ResNet18 + fine-tuning             | 0.3322   | 0.8925  | 0.8772   | 120s          | 10          | 3    |
| ResNet18 + data Augmentation       | 0.4773   | 0.8531  | 0.8553   | 240s          | 29          | 5    |
| ResNet18 + fine-tuning + Augmentation | 0.3962   | 0.8772  | 0.8662   | 720s          | 51          | 4    |
| ResNet50                           | 0.5105   | 0.818   | 0.8158   | 150s          | 8           | 8    |
| ResNet50 + fine-tuning             | 0.3338   | 0.8772  | 0.8904   | 180s          | 6           | 2    |
| ResNet50 + data Augmentation       | 0.5119   | 0.8311  | 0.8311   | 450s          | 33          | 7    |
| ResNet50 + fine-tuning + Augmentation | 0.3888   | 0.8816  | 0.8947   | 300s          | 18          | 1    |

| Model(19104 images)                | Val Loss | Val Acc | Test Acc | Training Time | Epoch Ended | Rank |
|------------------------------------|----------|---------|----------|---------------|-------------|------|
| ResNet18                           | 0.5387   | 0.8129  | 0.8223   | 400s          | 5           | 6    |
| ResNet18 + fine-tuning             | 0.4644   | 0.8411  | 0.8427   | 600s          | 6           | 4    |
| ResNet18 + data Augmentation       | 0.5424   | 0.8076  | 0.7995   | 840s          | 14          | 8    |
| ResNet18 + fine-tuning + Augmentation | 0.4349   | 0.839   | 0.8487   | 1600s         | 34          | 1    |
| ResNet50                           | 0.5461   | 0.8076  | 0.8154   | 1200s         | 7           | 5    |
| ResNet50 + fine-tuning             | 0.4291   | 0.8396  | 0.8448   | 780s          | 3           | 3    |
| ResNet50 + data Augmentation       | 0.5306   | 0.8074  | 0.8026   | 3100s         | 38          | 7    |
| ResNet50 + fine-tuning + Augmentation | 0.4401   | 0.8469  | 0.8463   | 1800s         | 18          | 2    |






## **2. Takeaway**
### 1. Why use data augmentation?
- the model sees the same base dataset, but different augmented images in every epoch. Even if the dataset is small, augmentation effectively creates "new" training samples by introducing variations, making the model more robust.
### 2. While using early stop, Val loss or Val acc?
- Using Val loss is better, espeically when the class is not balanced. If using Val acc, the model would prefer to **guess** the dominant class. In other words, the model would lost the ability to forceast the rare case.
### 3. Epoch & Patience  
- Patience should be 10–20% of the total epochs.

### 3. ResNet18 v.s. ResNet50?

| Feature           | ResNet-18           | ResNet-50           |  
| ------------------ |:------------------:| -------------------:|  
| Architecture Depth | 18 layers          | 50 layers           |  
| Parameters         | ~11.7M             | ~25.6M              |  
| Training Speed     | Faster (lighter)   | Slower (heavier)    |  
| Inference Speed    | Faster             | Slower              |  
| Model Size         | Smaller            | Larger              |  
| Capacity           | Lower (simpler tasks) | Higher (complex tasks) |  



