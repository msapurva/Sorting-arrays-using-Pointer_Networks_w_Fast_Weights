# Pointer Networks Using Fast Weights: Novel Architecture
## Task - Priority Sorting of Arrays


Pointer networks, by Vinyals et al.[8], introduce a way to overcome the fixed length problem and mention sorting as a task that can potentially be tackled through Pointer Networks. The Priority Sorting task here, starts by evaluating Pointer Networks on the sorting task, something not explored in [8]. It further explores Fast Weights based Pointer Networks as a way to overcome the drawbacks identified in performance of Pointer Networks on sorting tasks, primarily handling numbers that are close to each other.

Priority Sort has been attempted in the past via Neural Turing Machines (NTM), which were introduced by Graves et al.[4]. The work presents preliminary experiments showcasing NTM’s ability to tackle sorting sequences of predefined lengths but suffers with the drawback of requiring sequence length to be fixed during training.

## Code Usage

### Code Dependencies

- **Platform**:The code was developed, tested and run on Google Colab
- **Libraries**: The code uses the following libraries:
    - TensorFlow 1.13.1
    - Keras 2.2.4
    - NumPy 1.16.3  
    - Matplotlib 3.0.3
- **Colab Runtime Configuration**: Please use GPU runtime type by setting it within the Run menu bar option of Google Colab
- The code uses TensorFlow's Eager Execution which makes it a flexible machine learning platform for research and experimentation, providing an intuitive interface, easier debugging and natural control flow


### Setting up the LSTM and Fast Weights Model
Most configurations are listed in code within a cell in the **Experiment Configuration** section. These include:

Training and Dev Data
- minSeqSize=2
- maxSeqSize=5

Training Data
- batchSize=32
- numOfBatches=200
- datasize=batchSize*numOfBatches*(maxSeqSize-minSeqSize+1)

Dev data
- devBatchSize=64
- devNumBatches=10

Test data
- testBatchSize=64
- testNumBatches=10

Ptr Model Config
- hidden_dimensions=300

##### FW Model Config(directly modifies the class default values)
- fwS=1
- fwlearningrate=0.5
- fwdecayrate=0.9

For reproducing ablation on input dimension on transformation.A None value leads the system to use the default value of hidden_dimensions. Change this to required integer to get a new value
- given_fw_x_size=None

Number of epochs to run are present later within the *Train Model - Config and run training* section. Please change the variable *epochsToRun* to update epochs to run

Please refer the Experiment Configuration section of each code for full list of configuration options.


## References

[1] Jimmy Ba, Geoffrey Hinton, Volodymyr Mnih, Joel Z. Leibo and Catalin Ionescu. Using Fast Weights to Attend to the Recent Past. arXiv:1610.06258v3, 2016. https://arxiv.org/pdf/1610.06258.pdf.

[2] Jimmy Lei Ba, Jamie Ryan Kiros and Geoffrey E. Hinton. Layer Normalization. arXiv preprint arXiv:1607.06450, 2016. https://arxiv.org/pdf/1607.06450.pdf.

[3] John Duchi, Elad Hazan, and Yoram Singer. "Adaptive subgradient methods for online learning and stochastic optimization." Journal of Machine Learning Research: 2121-2159, 2011. http://www.jmlr.org/papers/volume12/duchi11a/duchi11a.pdf .

[4] Alex Graves, Greg Wayne, and Ivo Danihelka. Neural turing machines. arXiv preprint arXiv:1410.5401, 2014. https://arxiv.org/pdf/1410.5401.pdf.

[5] Sepp Hochreiter and Jürgen Schmidhuber. Long-Short Term Memory. In Neural Computations 9(8), pages 1735 -1780, 1997. https://www.bioinf.jku.at/publications/older/2604.pdf.

[6] Diederik P. Kingma and Jimmy Ba. Adam: A method for stochastic optimization. arXiv preprint arXiv:1412.6980, 2014. https://arxiv.org/pdf/1412.6980.pdf .

[7] Karen Ullrich, Jan Schlüter, and Thomas Grill. Boundary Detection in Music Structure Analysis using Convolutional Neural Networks. In The International Society of Music Information Retrieval, pages 417-422, 2014. https://grrrr.org/pub/ullrich_schlueter_grill-2014-ismir.pdf.

[8] Oriol Vinyals, Meire Fortunato, and Navdeep Jaitly. Pointer networks. In Advances in Neural Information Processing Systems, pages 2692–2700, 2015. https://arxiv.org/pdf/1506.03134.pdf.

[9] Jimei Yang, Brian Price, Scott Cohen, Honglak Lee, and Ming-Hsuan Yang. Object contour detection with a fully convolutional encoder-decoder network. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pages 193-202, 2016. https://eng.ucmerced.edu/people/jyang44/papers/cvpr16_contour_final.pdf .

