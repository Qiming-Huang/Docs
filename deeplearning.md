# Record the learning about deep learning
* Convolutional neural network
	* padding: if the sliding step is 1, an input image size is 8x8, the kernel size is 3x3, the output is (8-3+1)*(8-3+1) = 6x6. It's called downsample because the size of the image is decreasing. The probloms about the edge feature missing will happen. The center fearture was computed many times but the edge was not. Hence, it's importtant to get the feature of the edge.

	* in order to make the output image unchange. The padding is = (f-1)/2 which f is the kernel size.
	