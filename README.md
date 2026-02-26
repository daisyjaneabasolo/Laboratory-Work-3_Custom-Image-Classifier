# Laboratory-Work-3_Custom-Image-Classifier

## Guide Questions (Student Reflection & Explanation)
Students must answer the following:
1. Dataset Preparation
- How did you organize your dataset in Google Drive?
  - I organized my dataset by creating a main folder inside Google Drive. Inside that folder, I created separate subfolders for each class/category of images.
- Why is folder structure important for TensorFlow image loading?
  - Folder structure is important because TensorFlow’s image_dataset_from_directory() function automatically assigns labels based on folder names. If the folders are not organized properly, the model will not correctly identify which image belongs to which class.
    
2. Model Training
- What is the role of convolutional layers in image classification?
  - The convolutional layers act like the eyes of the model—they look for patterns in the images.
- Why do we split data into training and validation sets?
  - We split the dataset into: Training set used to train the model. Validation set used to test the model during training. This helps us check if the model is learning properly or just memorizing the training data.
    
3. Performance Analysis
- What accuracy did your model achieve?
  - My model achieved approximately 97.8% training accuracy and  47.7% validation accuracy.
- How did the number of images affect the model’s performance?
  - With roughly 250 images per class, there’s a decent amount of data to start with. But I noticed the validation loss went up while training loss kept going down (e.g., Epoch 10: loss 0.10 vs val_loss 3.10). This confirms overfitting—the model learned the training images very well but struggled with unseen images.
    
4. Critical Thinking
- What challenges did you encounter while using your own dataset?
  -   Overfitting was the biggest problem. Also, each epoch took over 150 seconds, so training was slow.
- How can data augmentation improve your model?
  -  To fix overfitting, I could use data augmentation. This means rotating, flipping, or zooming images so the model sees different versions of the same plant. That way, it learns to recognize the plant in more real-world situations.
    
5. Application
- Suggest a real-world application for your trained model.
  -  This model could be used in a Plant Identification App. Gardeners or hikers could take a picture of a vine or trailing plant, and the app would identify it and give care tips.
- How can this system be integrated into a mobile or web application?
  -   Mobile: Convert the model to TensorFlow Lite so it can run on Android or iOS offline.
      Web: Export it to TensorFlow.js and host it with Flask or FastAPI. Users can upload a photo, and the backend  predicts the plant type.
--- 
# Activity 3A: Improving and Evaluating a Custom Image Classifier
## Guide Questions (Student Explanation & Reflection)
Students must answer:
Visualization & Overfitting

1.What signs indicated overfitting in your first model?
   - The training accuracy became very high at 98.49%, but the validation accuracy stayed low at only 48.10%. I also observed that while the training loss kept decreasing, the validation loss started increasing after epoch 4. This showed that the model was memorizing the training data instead of actually learning patterns that could generalize to new images.
     
2.How did data augmentation affect validation accuracy?
  - The training accuracy became slightly lower, the validation accuracy improved because the model was forced to learn more meaningful and consistent features instead of memorizing specific image details.
    
Model Improvement

3.What is the purpose of dropout layers?
  - By randomly turning off some neurons during training, dropout prevented the model from depending too much on certain connections. This made the model more robust and helped reduce overfitting.
    
4.Why does data augmentation improve generalization?
  - Data augmentation improves generalization because it increases the variety of the training data. By applying transformations like rotation, zooming, and flipping, the model learns to recognize objects in different positions and perspectives, similar to real-world conditions.

Performance Comparison

5.Compare accuracy before and after improvements.
  - Before applying improvements, the model only achieved 48.10% validation accuracy. After adding dropout and data augmentation, the validation performance became more stable and improved, while the validation loss decreased. This indicates that the model generalized better to unseen data.

6.Which technique contributed most to improvement?
  - Among the techniques used, data augmentation contributed the most improvement because it directly addressed the limited diversity of the dataset. Dropout also helped by acting as a regularizer and stabilizing the learning process.

Deployment & Application

7.Why is saving the model important?
  - Saving the model is very important because it allows us to reuse the trained weights without retraining the entire model again. This makes deployment faster and more practical, especially when integrating the system into applications.

8.How can this model be deployed in a real-world system?
  - This model can be deployed in real-world systems such as a mobile app for plant identification, a web-based image classification service, or an agricultural monitoring system integrated into drones or automated devices that classify crops in the field.
