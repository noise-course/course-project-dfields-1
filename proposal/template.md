# Reproducing the nPrint OS Detection Task Benchmark Score

## Project Participants

| First Name | Last Name | cnet ID | Project Role |
|-------------|------------|---------|---------------|
| Daniel | Fields | dfields | Sole Participant |

## Project Description

In this project, I will attempt to re-produce the current leaderboard score for the nPrint OS Detection task. In this task, packets from the CICIDS 2017 dataset are grouped by source IP address before being partitioned into examples containing 100 packets, and each example is mapped to a label describing the operating system of its source device. The current leaderboard score for this task is a balanced accuracy metric of 77.1 obtained with the AutoML library, which automatically determines the optimal model and corresponding hyperparameters for a given task. I want to verify whether or not the data is linearly separable, so I will begin with linear models such as the Perceptron, the Support Vector Machine, and Logistic Regression. I will also use dimensionality reduction techniques such as Principal Components Analysis to further help me understand whether or not the data lends itself well to linear classifiers. If linear classification proves to be ineffective in producing a score close to that of the benchmark, I will switch to using a RandomForest model, which can use an ensemble of decision trees to make classification decisions on complex, non-linear datasets. Identifying the source operating system type of packets is an important problem to investigate from a security perspective: An enterprise might use OS detection to fingerprint and investigate potentially malicious communications, and at the same time, hackers might use OS detection to identify benign machines which are susceptible to certain exploits. Besides the current benchmark, I am not aware of any related work. This task relates to the overall theme of the course because it employs machine learning to classify groups of packets from a packet trace by their operating system type,  based on relevant network features. From a machine learning perspective, I want to learn how to decide which models are suited for different real-world inference tasks. For example, in this course I was thinking about which types of datasets would be normally distributed, allowing us to use a Mixture of Gaussians probabilistic model. I believe that this dataset is likely not normally distributed, so I will not be attempting to apply such models, but I have the same question about which datasets are linearly separable and which lie on a non-linear manifold, and I hope to use this project to gain insight into these questions. From a networking perspective, I hope to discover which features of packets are most useful in predicting the operating system type of the source device.

## Data

I will be using the dataset published on the nPrint OS Detection Task website (https://nprint.github.io/benchmarks/os_detection/nprint_os_detection.html), which can be parsed with pcapml to obtain each sample and its corresponding label, which in this case is the example’s OS. I will then parse this dataset into a Pandas dataframe before beginning the classification task.

## Deliverables

For the final project, I will turn in a notebook containing my code that prepares 
the dataset, performs classification which each of the models I have chosen, and
evaluates each model in the same way as the benchmark. Like the creators of the benchmark, I will split the dataset into a 75% train split and a 25% test split for model evaluation. Consistent with the creators, I will use the standard multi-class classification evaluation metrics of balanced accuracy, ROC AUC, and macro F1-score, and I will also make sure to plot a confusion matrix to examine the specific counts of correct and incorrect classifications among each class. I will also plot a multi-class ROC curve for each model to examine how changing the threshold of each model might affect true positive rates and false positive rates. I will then present a comparison between the balanced accuracy, ROC AUC, and Macro F1 metrics obtained by the benchmark creators along with the metrics I obtained, along with an analysis of these results and what I have discovered about the data.


  

