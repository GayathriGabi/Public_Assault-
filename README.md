# PUBLIC HUMAN ASSAULT PREDICTION USING HUMAN ACTIVITY RECOGNITION WITH ARTIFICIAL INTELLIGENCE
Abstract: Human Activity Recognition (HAR) is an essential process for human safety and social well-being. This makes to develop a cost-effective and accurate HAR classification method for surveillance applications. The proposed work consists of three steps such as, pre-processing, feature extraction, and classification. First step, apply the pre-processing technique in order to reduce the dimensionality of the input data by using Temporal Singular Value Decomposition (TSVD) technique. This step reduces the total addressable input data, while increasing the speed and efficiency of the HAR method. In the second step, the features are extracted from the preprocessed data with the help of spatio-temporal feature extraction technique. This technique uses the temporal extraction capability of the optical flow algorithm and the spatial feature extraction capability of the Discrete Cosine Transform (DCT). Finally, the extracted features are classified using the Spatio-Temporal Neural Network (STNN) model and an alert message will be sent to the police by a newly created application. The proposed technique is implemented by using the KTH video dataset and the results are compared with existing deep learning algorithms to find the capability of the model for real-time applications. The proposed method was found to have an efficiency of about 98%, which is far more efficient than existing deep learning-based classification methods.  

Keywords: Human activity recognition, Deep learning, Feature extraction, Video-based surveillance, Discrete cosine transform. 

# Contributions of the Proposed Work
The main contributions of the proposed work are given below.

* Traditional machine learning-based HAR techniques are computationally expensive and memory intensive with a lack of scalability due to over-dependence on the hyper-parameters. The deep learning algorithm also has inferior classification accuracy for real work-sensitive applications. The proposed STNN focuses on combining spatial and temporal data, aiming to boost performance in areas like action recognition, video analysis, and other related sequential data processing tasks. It helps to achieve a 98% of accurate predictions results than the existing deep learning model.
* A mobile application is developed using react native which will be held by the police, the camera recognizes abnormal actions from a human, an alert notification is sent and live streaming is enabled.
The proposed article has been organized as follows. The related research works are explained in section 2. The detailed explanation of the proposed methodology is given in Section 3. Discussion of the experimental results mentioned in section 4. Finally, the conclusion is given in Section 5.
# Proposed Methodology
The whole process of HAR consists of three processes: 1. Pre-processing using TSVD, 2. Feature extraction using DCT algorithm and spatio-temporal extraction technique, 3. Classification using Spatio-Temporal Neural Network Algorithm. The KTH dataset is divided into training and testing data which helps to train and test the designed model. The proposed method uses linear algebra methods to extract the features from the dataset. To classify the identified features a new spatio-temporal neural network algorithm is designed and implemented.  

The HAR system serves a range of purposes, notably in road surveillance. Leveraging the KTH video dataset, this system first processes data to extract specific frames and then employs techniques such as Pixel and Optical Flow techniques for feature extraction. Visualization aids in understanding these features. The Spatio-Temporal Net, an advanced deep learning algorithm, is employed for classifying human activities. The system is integrated into road cameras; upon detecting anomalies like altercations, alerts are sent to the police. 

The camera recognizes abnormalities in humans, such as fights, assault, etc., and an alert notification is sent to the police. A mobile application is developed using react native which will be held by the police, the camera recognizes abnormal actions from a human, an alert notification is sent and live streaming is enabled. Thus, this project successfully provides a Human activity recognition model incorporating AI into the cameras which can be used in real-time applications such as a solution to prevent and provide evidence of an abnormal detection on road.

# Data Preprocessing using TSVD
The computational cost of the HAR technique can be enhanced using the dimensionality reduction technique using the Temporal Singular Value Decomposition (TSVD) algorithm. The total video frame value N can be divided into multiple sequences based on the application of the proposed algorithm. The sequence number can be represented using the value M. The total number of extracted temporal sequences can be calculated as N/M. Each of these temporal frames is then applied with the TSVD algorithm to reduce the dimensionality in the frames Xt. 
  X_t=U_t ε_t V_t   (1)
The singular values of the frame with dimension of m×n 
After decomposing single frames, ranking r for individual frames is calculated. 
The foundational step of data preprocessing entails refining raw data to align with deep learning model requirements. This transformation ensures data compatibility and facilitates streamlined processing in areas like data mining and deep learning. Such preparatory techniques are pivotal in the nascent stages of AI and deep learning model construction to guarantee precision in subsequent stages. Crafting a robust neural network hinges not just on the intricacies of its architecture but also on the pristine nature of input data. Image datasets commonly incorporate parameters such as image count, height, width, channel count, and pixel intensity levels. Predominantly, image data encompasses three channels representing the RGB spectrum, with pixel intensities typically ranging between [0,255]. The motion sequence is provided as
      K_(1:M)  = [K_1,K_2,K_3…..K_M]	(2)
Consisting of M consecutive human poses where K_t∈R^N denotes the human pose at a time ‘t’ and ‘n’ is the dimension size of the pose at each frame. The main purpose is to predict the actions in the frames for the next two frames.
Feature Extraction using DCT and Spatio-Temporal technique
The whole process of feature extraction is done in two steps. The first step is spatial feature extraction with the help of the DCT algorithm. This will help to identify the change in pixel intensity value along the image by calculating the cosine transform value of each independent block in the image. Then, using the sum of the square of all the cosine coefficients, the value of energy of each block of image is calculated. Then motion estimation is done using the optical flow analysis method in which changes in pixel intensity across various frames are calculated. Both these values are combined to form the feature results of the proposed technique. The whole feature extraction method used in our proposed method 
Optical flow, or motion estimation, calculates shifts in image intensities, typically associated with object movements within a scene. The optical flow calculation can be done by estimating the change in input concerning time t (frames). 
      I(x,y,t)=I(x+dx,y+dy,tdt)     (3)
Where dx and dy are the change in the x and y coordinates of the object in the frame and the change in frames dt. Therefore, the windowed system equation can be given using the formula
         IV=T    (4)
 The value of T represents the temporal gradients which is used to estimate the motion derivatives of the optical flow equation. The derivatives are estimated with the help of the Sobel gradient and can be used to estimate the motion of objects in the frames. 	
The spatial features in the frame can be calculated with the help of the discrete cosine transform (DCT) algorithm. DCT can remove high-frequency noises in the signal and capture the changing intensity pixel data in the images. 
Let 〖{X}〗_(i=1)^k  represent the angle of data of frame 1 to k the coefficients can be calculated as
G_(i,j)= √(2/N) ∑_(n=1)^k▒〖y_(k,n)  1/√(1+∂_l1 ) cos⁡(π/N (n-1/2)l-1) 〗   (5)
Where l ∈{1,2,3….N} and ∂_(i,j)={1,i=j||0, i≠j, and the computed sequence of coefficients are fed to the temporal features. These values are then used to analyze the energy value of each pixel block in the frame. 
E_(i,j)=∑_(i=1)^m▒∑_(j=1)^n▒G(i,j)      (6)
Spatial features depict alterations in position due to object motion, while temporal attributes encapsulate time-related nuances of the motion. Combined, these spatiotemporal attributes pinpoint an object's location at specific timestamps within a frame. Finally, the processed values should be changed to the inverse discrete cosine transform (IDCT) to obtain the output data, and the equation for that process will be shown as
Where l ∈{1,2,3….N} and ∂_(i,j)={1,i=j||0, i≠j, and the computed sequence of coefficients are fed to the temporal features.

# Classification Using Spatio-Temporal Neural Network
The proposed Spatio-temporal neural network consists of both CNN and recurrent neural networks (RNN) layers with a pooling architecture. There are more than seven CNN layers and three RNN layers with 3 pooling layers in the architecture. The combined spatio-temporal neural network layers can be represented using the formulas.
F_t=f_CNN (x_t)   (7)
Where〖 tx〗_ is the input frame pixel intensities. The temporal dynamic of the input image can be extracted with the help of the RNN algorithm. The output of the CNN layer is fed to the RNN layer to calculate temporal dynamics. 
H_t=f_RNN (F_t,h_(t-1))  (8)
The output temporal component along with feature maps or spatial components are then fed to the classification layer represented by a softmax function. 
y=f_softmax (W_t h_t+b)  (9)
	The value of W_t is the weight value of each of the layers and b is the bias value that is used for classification. The number of layers in the neural network can be calculated by defining the objective of the operation and the dataset that is used for human activity recognition. 

# Conclusion
This proposed work has successfully implemented the Human Activity Recognition to automatically recognize the abnormal actions in the frame using the Spatio-Temporal Neural Network (STNN) algorithm. The proposed TSVD dimensionality reduction technique performs better than the existing algorithm in reducing dimension of the input image. The feature extraction technique using spatial and temporal feature extraction performs effectively even for complex inputs and this technique can be used for facial and hand gesture recognition problems as well. Finally, a mobile application is developed using react native, if the camera recognizes abnormal actions from a human, an alert notification is sent and live streaming is enabled. The classification accuracy of the proposed Spatio-temporal neural network stands at 98% which is higher than most classification techniques considering the reduced computational complexity. The training of the algorithm was found to have a slight overfitting problem which can be overcome with proper selection of training dataset. 
In the coming future, we have to develop an application that is safe and secure to monitor human assault in public places and it can promote all types of human activity recognitions with more accuracy. In this field, there are more chances to develop or convert this project in many ways. The accuracy of the prediction will be increased by using different efficient techniques and algorithms. Thus, this project has an efficient scope in the coming future where manual predicting can be cheaply converted to computerized production.
