# Generative-GCN
My master's dissertation at the University of Glasgow in 2023. Original title: _**"Generative modelling for shapes using graph convolutional networks"**_.
This project attempts to build a model pipeline consisting of Graph Convolutional Networks which:
1. takes in 3D abdominal scans(CT)
2. isolates specific organs and
3. attempts to generate 3D shapes of the selected organ.
The project was carried out mainly on Jupyter Notebook using PyTorch, PyG and other libraries. It is based on the [study done by Soodeh Kalaie](https://openreview.net/pdf?id=Ao0D2HMB8P) but uses a different dataset and had to implement the codes from the ground up.

# List of Items:
## A. Documentation
The documentation of the full study is included as a PDF file. The content covered:
1. Introduction
2. Background
3. Methodology
4. Experiment and Results
5. Conclusion

## B. Jupyter Notebooks
There is a total of 3 notebooks for the end-to-end processes of this project. The description is as follows:
1. `Data Exploration & Preprocessing`: explore the data, check and understand the shapes of images, extract slices for specific organs using the label, then turn the CT scans into 3D mesh objects
2. `ASMG Framework`: custom dataset to prep mesh objects for GCN use, implement a generative pipeline consisting of a VGAE, an Attention Mechanism, Domain Transformation and B-VAE which _**attempts**_ to generate 3D organ shapes. 
3. `Evaluation`: evaluate the quality of the generation using metrics like Hausdorff Distance (HD) and the average of minimum Euclidean distance (ED).

## C. Data (not included due to size)
The dataset used in this project is the AMOS dataset from the MICCAI Challenge 2022, a set of abdominal multi-organ medical image scans, with more details found in the documentation file. This project focuses on CT scans and the organ of the gallbladder. 


# Future Enhancements
There are some areas to improve upon on this project that I would like to revisit in the future (if I have the time) that are not implemented due to time and other constraints.
1. interpolate the CT scans to generate smoother mesh
2. regularise the mesh, fixing the number of nodes & edges
3. better segmentation (this study used the segmentation label that came with the data source, seems like it is not 100% accurate)
4. implement the refinement loss that is found in the original ASMG framework by Soodeh Kalaie. The reference paper compared results from two types of generation (w and w/o refinement loss), the refinement loss is not a make-or-break.
5. trying out another generation framework (GAN) instead of B-VAE
6. hyperparameter tuning and early stopping

** The meshes generated are viewed using Paraview.
