# Ossw final project
We need to take brain MRI images as pixels and create a model that classifies brain tumors into four calss

4 calss : 'glioma_tumor', 'meningioma_tumor', 'no_tumor', 'pituitary_tumor'

only use scikit-learn

# Load data
load image data (image_size = 58)
and divide the image into pixels and store them in an array



# FIt model
I use svc, rf and knn.

I used pipelines to eliminate unnecessary processes during training

In order to improve accuracy, the data was not divided into trainset,testset , but i trained model using a whole data

Data preprocessing  (PCA and scaling)

-svc 

PCA(n_components=800,random_state=18)

Normalizer

SVC(probability=True,C=150,gamma = 40,random_state=18)

-rf 

 PCA(n_components=800,random_state=64
 
Normalizer

RandomForestClassifier(criterion='entropy',max_features=4,n_estimators=1000, random_state=2,n_jobs=-1)


-knn

KNeighborsClassifier(n_neighbors=1)


And three models were combined with hard voting

model = VotingClassifier(
    estimators=[
        ('SVC', svc),
        ('RF',   rf),
        ('KNN', knn),
    ],
    voting='hard' 
)



# Load my_model
I used pickle 

so there is already a trained model, and can use it to measure accuracy



