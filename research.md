We have three primary research threads, each of them serving our connectome coding mission:

### Big NeuroData Storage, Management and Visualization

The raw data that we utilize to answer connectome coding questions often start as multidimensional, multimodal, and multiscale images. 
Typically these images are at least 3D, but often they are 4D or 5D, and often each image includes trillions of voxels requiring terabytes of storage. 
Regardless of the number of voxels, dimensions, modalities, and scales, 
studying them requires infrastructure to store, manage, and visualizing the data.
To that end, we are developing and/or enhancing a number of open source tools, including:

- [boss](https://github.com/neurodata/boss): a AWS deployed spatial database to store and manage large image volumes
- [neuroglancer](https://github.com/neurodata/ndviz): a Web-service to visualize these data
- [ndpush](https://github.com/neurodata/ndpush): a command-line interface to put data into our cloud storage
- [ndpull](https://github.com/neurodata/ndpull): a command-line interface to pull data from our cloud storage
- [ndweb](https://github.com/neurodata/ndwebtools): a Web-service that provides updated links to manage and visualize all the data in our cloud

The basic architecture and motivation for these tools are outlined in the following open access articles:

- R. Burns et al. A Community-Developed Open-Source Computational Ecosystem for Big Neuro Data. arXiv:1804.02835, 2018.
- D. Kleissas et al. The Block Object Storage Service (bossDB): A Cloud-Native Approach for Petascale Neuroscience Discovery. bioRxiv:217745, 2017.
- J. T. Vogelstein et al. To the Cloud! A Grassroots Proposal to Accelerate Brain Science Discovery. Neuron, (3)92:622-627, 2016.
- R. Burns, J. T. Vogelstein and A. S. Szalay From cosmos to connectomes: The evolution of data-intensive science. Neuron, (6)83:1249-1252, 2014.
- R. Burns et al. The Open Connectome Project Data Cluster: Scalable Analysis and Vision for High-Throughput Neuroscience. Proceedings of the 25th International Conference on Scientific and Statistical Database Management, 2013.
- J. T. Vogelstein Q&A: What is the Open Connectome Project?. Neural Systems & Circuits, (1)1:16, 2011.

### Scalable and Statistically Princpled Pipelines for Analysis of NeuroData 

We currently primarily focus our work on a few disparate experimental paradigms in neurobiology. 
For each, we are building pipelines, which we think of statistical tools with computational implementations.  
Because they are statistical in nature, that means we think of them as using data to estimate the value of parameters of the underlying neurobiology.
Based on that, we endeavor to make our pipelines have the following kinds of statistical guarantees:

1. consistent - the estimates from the pipelines converge to the true unknown values,
2. stable -  minor perturbations to the data only induce minor changes to the estimands, and
3. robust - large outliers only have minor impact on the estimands.

We also endeavor to make our pipelines have the following kinds of computational properties:
4. expedient - requires less time to run than to collect the data
5. parallelized - given more computational resources, will run faster
6. portable - can run on multiple different computers, operating systems, etc.
7. turn-key - does not require manual tuning to apply to a new dataset collected using the "same" experimental protocol
8. free and open source - so anybody can access it 
9. cloud deployed - runs on our cloud so we and others can run it easily



- nanoscale electron microscopy data
- microscale superresolution light microscopy data
- mesoscale light microscopy data
- macroscale magnetic resonance imaging data

