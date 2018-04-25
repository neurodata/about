We have three primary research threads, each of them serving our connectome coding mission:

- [infrastructure](#infrastructure)
- [pipelines](#pipelines)
- [statistics](#statistics)
- [neurobiology](#neurobiology)
- [summary](#summary)

### Infrastructure
#### Big NeuroData Storage, Management and Visualization

The raw data that we utilize to answer connectome coding questions often start as multidimensional, multimodal, and multiscale images. 
Typically these images are at least 3D, but often they are 4D or 5D, and often each image includes trillions of voxels requiring terabytes of storage. 
Regardless of the number of voxels, dimensions, modalities, and scales, 
studying them requires infrastructure to store, manage, and visualizing the data.
For each project, the goals are to build tools that are:

1. easy 
2. fast
3. inexpensive

Any pair of the above 3 goals are mutually competing with one another, so we must make a number of trade-offs. 
Given that caveat, we are developing and/or enhancing a number of open source tools, including:

- [boss](https://github.com/neurodata/boss): a AWS deployed spatial database to store and manage large image volumes
- [neuroglancer](https://github.com/neurodata/ndviz): a Web-service to visualize these data
- [cloud_volume](https://github.com/seung-lab/cloud-volume): a client for reading and writing to Neuroglancer precomputed volumes on cloud services.
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

### Pipelines
#### Scalable and Statistically Princpled Pipelines for Analysis of NeuroData 

We currently primarily focus our work on a few disparate experimental paradigms in neurobiology.  For each, we are building pipelines, which we think of statistical tools with computational implementations.   Because they are statistical in nature, that means we think of them as using data to estimate the value of parameters of the underlying neurobiology. Based on that, we endeavor to make our pipelines have the following kinds of statistical guarantees:

1. consistent - the estimates from the pipelines converge to the true unknown values,
2. efficient - estimates converge to small errors with relatively little data, 
3. stable -  minor perturbations to the data only induce minor changes to the estimands, and
4. robust - large outliers only have minor impact on the estimands.
5. model-based and data-driven - incorporates biophysical knowledge (e.g., as priors or constraints) but does not limit performance to rigid biophysical assumptions about the data generative process, rather, allows the inferences to be flexible with respect to the domain knowledge.

We also endeavor to make our pipelines have the following kinds of computational properties:

6. expedient - requires less time to run than to collect the data
7. parallelized - given more computational resources, will run faster
8. portable - can run on multiple different computers, operating systems, etc.
9. turn-key - does not require manual tuning to apply to a new dataset collected using the "same" experimental protocol
10. cloud deployed - runs on our cloud so we and others can run it easily
11. free and open source - so anybody can access it 


We are building pipelines with the above properties for the following disparate kinds of data:

- **nanoscale** electron microscopy [data](https://neurodata.io/data/) 
  - Experiments: collaborators (and papers of theirs) studying this kind of data include [bobby](http://www.cell.com/cell/pdfExtended/S0092-8674(15)00824-7) (argonne), [albert cardona & marta zlatic](https://www.nature.com/articles/nature23455) (janelia), [davi bock](https://www.nature.com/articles/nature09802) (janelia).  
  - Pipeline: We have a somewhat antiquated [pipeline](https://www.frontiersin.org/articles/10.3389/fninf.2015.00020/full) for these data, though [sebastian seung's group](http://seunglab.org/) (amongst others) is currently building the state of the art work here.      
- **microscale** superresolution light microscopy [data](https://neurodata.io/project/synaptomes/)
  - Experiments: collaborators (and papers of theirs) studying this kind of data include: stephen smith [1](http://www.jneurosci.org/content/35/14/5792.short), [2](https://www.frontiersin.org/articles/10.3389/fnana.2015.00100/full), [3](http://www.cell.com/neuron/abstract/S0896-6273(10)00766-X) (allen), rick huganir (jhu). 
  - Pipeline: Our current (in progress) pipeline includes synapse detection [guillermo sapiro](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005493) (duke), and analysis of the resulting matrices using [meda](https://github.com/neurodata/meda).
- **mesoscale** light microscopy [data]](https://neurodata.io/data/tomer15/)
  - Experiments: These data come either from karl deisseroth [1](https://www.sciencedirect.com/science/article/pii/S009286741630558X), [2](https://www.sciencedirect.com/science/article/pii/S009286741500851X) (stanford) or michaela gallager (jhu). 
  - Pipeline: includes [terastitcher](http://abria.github.io/TeraStitcher/) for stitching the images together to form volumes and [ndreg](https://github.com/neurodata/ndreg) for image corrections and registration to an atlas
- **macroscale** magnetic resonance imaging [data](https://neurodata.io/project/projectomes/)
  - Experiments: Including both functional and diffusion magnetic resonance imaging, we are primarily collaborating with mike milham [healthy brain network](https://www.nature.com/articles/sdata2017181), [NKI enhanced](https://www.frontiersin.org/articles/10.3389/fnins.2012.00152/full) (child mind institute), bruce rosen's human lifespan data, and kent kiehl's [psychopathy](https://onlinelibrary.wiley.com/doi/abs/10.1002/hbm.24028) data
  - Pipeline: [ndmg](https://github.com/neurodata/ndmg) processes s/f/d-MRI data to estimate and analyze connectomes (see [draft](https://www.biorxiv.org/content/early/2018/04/24/188706) for details).
  
 ### Statistics
 #### Statistical Methods to Estimate, Test, and Model Neurobiology

