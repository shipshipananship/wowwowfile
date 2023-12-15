# Ossw final project
20233456 안상민

# Load data
load image data (image_size = 58)
and load the various libraries i used


# FIt model
I use svc, rf and knn.
I used pipelines to eliminate unnecessary processes during training
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
I use pickle 


Need to load the model and check it
