# OCR Software
 
The Optical Character Recognition Software extracts text from input images and attempt to predict it. The applications vary from the digitization of documents to automating accounting processes. This program is written in Python and uses PyTorch and OpenCV to create a simple pipeline. Note that by going through each Jupyter notebook, a more in depth description for the code is provided. 

<h1> The Pipeline </h1>

- Pre-process the input image through mutiple functions such as binarization, noise removal, and shadow removal
- Conduct character segmentation through two possible methods: histogram projections or contours

Both methods are tested and it seems like contours work much better as they leave little empty space around each character.

- Feed each character image into the trained CONVnet and concatenate the predictions

<h1> The CONVnet </h1>

The model used is quite simple with 3 convulutional layers and 2 fully connected layers after. The dataset used was a version of the EMINST dataset found on https://www.kaggle.com/crawford/emnist. In the end, the overall accuracy achieved was 88%. 

<h1> Next steps </h1>

This OCR Software could be drastically provided in two ways:

- Improving the CONVnet

This can be done by increasing the number of features of the network and adding more layers. Alternatively, transfer learning could be used an a pre-existing CONVnet model could be applied. As a result, the overall accuracy would ideally be increased to 98 or 99 percent which many CONVnets in present day can achieve easily. 

- A more sophisticated pipeline

The pipeline used is rather simple and could be further complicated to produce more accurate results. For example, an RNN could be used to predict the next character from the formed word and match with the prediction produced from the CONVnet. It would be more effective to have the software understand individual words and attempting to form them from the extracted text instead of relying on the individual character predictions. In addition, post-processes functions could be added to clean up the results.

Overall, these next steps would lead to a much more effective OCR software. For now though, the produced code provides a good entry into computer vision. 
