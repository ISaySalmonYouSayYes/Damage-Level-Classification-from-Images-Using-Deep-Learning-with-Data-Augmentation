# **Damage Level Classification from Images Using Deep Learning with Data Augmentation**
## **0. Introduction**
This project is dedicated to explore the best cost-performance value of deploying ResNet model in different sizes of database.  
Accuracy = correct/total  

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



