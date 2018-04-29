### Intro

Every research project we embark on is motivated by a [neurobiological](#neurobiology) question.  For each question, there are often various kinds of challenges, including: 
- [infrastructure](#infrastructure), 
- [pipelines](#pipelines), and 
- [statistics](#statistics). 

We therefore strive to build general tools in the service of answering these, and eventually other questions.  


### Neurobiology


- **nanoscale** electron microscopy [data](https://neurodata.io/data/)
   - Goal: Estimate basic statisticas of ultrastructural neuroanatomy
   - Collaborators:  [bobby](http://www.cell.com/cell/pdfExtended/S0092-8674(15)00824-7) (argonne), [albert cardona & marta zlatic](https://www.nature.com/articles/nature23455) (janelia), [davi bock](https://www.nature.com/articles/nature09802) (janelia).  
- **microscale** superresolution light microscopy [data](https://neurodata.io/project/synaptomes/)
  - Goal: Discovery synapses taxonomies across conditions
  - Collaborators: stephen smith [1](http://www.jneurosci.org/content/35/14/5792.short), [2](https://www.frontiersin.org/articles/10.3389/fnana.2015.00100/full), [3](http://www.cell.com/neuron/abstract/S0896-6273(10)00766-X) (allen), rick huganir (jhu). 
- **mesoscale** light microscopy [data]](https://neurodata.io/data/tomer15/)
  - Goal: Decipher the principles of cellular resolution brain-wide neural circuits (cellular engrams)
  - Collaborators: 
   - CLARITY: karl deisseroth [1](https://www.sciencedirect.com/science/article/pii/S009286741630558X), [2](https://www.sciencedirect.com/science/article/pii/S009286741500851X) (stanford), 
   - Magnetic Resonance Microscopy: [alex badea](https://academic.oup.com/cercor/article/25/11/4628/2367615) (duke), 
   - iDisco: michaela gallager (jhu),
   - X-ray Microtomography: [bobby and eva](http://www.eneuro.org/content/early/2017/09/25/ENEURO.0195-17.2017)
- **macroscale** magnetic resonance imaging [data](https://neurodata.io/project/projectomes/)
  - Goal: Reveal the connectome code, that is, the latent structure of brains determined by genetics and experience), at various resolutions, partially by mitigating batch effects across studies
  - Collaborators: mike milham [healthy brain network](https://www.nature.com/articles/sdata2017181), [NKI enhanced](https://www.frontiersin.org/articles/10.3389/fnins.2012.00152/full) (child mind institute), bruce rosen's human lifespan data, and kent kiehl's [psychopathy](https://onlinelibrary.wiley.com/doi/abs/10.1002/hbm.24028) data
- **angstrocale** spatial transcriptomics
  - Goal: Determine the diversity of cell types in the brain
  - Collaborators: [ed lein](https://www.biorxiv.org/content/early/2018/01/19/239749) (allen), [mike hawrylycz](https://www.biorxiv.org/content/early/2017/12/06/229542) (allen)
- **multiscale** virtual zebrafish
  - Goal: Build a biofidelic simulation of a zebrafish behaving naturally
  - Collaborators: florian engert [1](https://www.nature.com/articles/nature11057), [2](https://www.nature.com/nmeth/journal/v12/n11/abs/nmeth.3581.html) (harvard), [jeff lichtman](https://www.nature.com/articles/nature22356) (harvard)



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
4. feature-rich

Any 3 of the above goals are mutually competing with one another, so we must make a number of trade-offs. 
Given that caveat, we are developing and/or enhancing a number of open source tools, including:

- [boss](https://github.com/neurodata/boss): a AWS deployed spatial database to store and manage large image volumes, primarily currently developed by the Applied Physics Laboratory
- [neuroglancer](https://github.com/neurodata/ndviz): a Web-service to visualize these data, primarily developed by Google
- [cloud_volume](https://github.com/seung-lab/cloud-volume): a client for reading and writing to Neuroglancer precomputed volumes on cloud services, primarily developed by Sebastian Seung's lab.
- [ndpush](https://github.com/neurodata/ndpush): a command-line interface to put data into our cloud storage
- [ndpull](https://github.com/neurodata/ndpull): a command-line interface to pull data from our cloud storage
- [ndweb](https://github.com/neurodata/ndwebtools): a Web-service that provides updated links to manage and visualize all the data in our cloud

The basic architecture and motivation for these tools are outlined in the following open access articles:

- R. Burns et al. [A Community-Developed Open-Source Computational Ecosystem for Big Neuro Data.](https://arxiv.org/abs/1804.02835) arXiv:1804.02835, 2018.
- D. Kleissas et al. [The Block Object Storage Service (bossDB): A Cloud-Native Approach for Petascale Neuroscience Discovery.]((https://www.biorxiv.org/content/early/2017/11/10/217745) bioRxiv:217745, 2017.
- J. T. Vogelstein et al. [To the Cloud! A Grassroots Proposal to Accelerate Brain Science Discovery.](http://www.cell.com/neuron/abstract/S0896-6273(16)30783-8) Neuron, (3)92:622-627, 2016.
- R. Burns, J. T. Vogelstein and A. S. Szalay [From cosmos to connectomes: The evolution of data-intensive science.](http://linkinghub.elsevier.com/retrieve/pii/S0896-6273(14)00746-6http://linkinghub.elsevier.com/retrieve/pii/S0896-6273(14)00746-6) Neuron, (6)83:1249-1252, 2014.
- R. Burns et al. [The Open Connectome Project Data Cluster: Scalable Analysis and Vision for High-Throughput Neuroscience.](https://dl.acm.org/citation.cfm?doid=2484838.2484870) Proceedings of the 25th International Conference on Scientific and Statistical Database Management, 2013.
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

- Nano: We have a somewhat antiquated [pipeline](https://www.frontiersin.org/articles/10.3389/fninf.2015.00020/full) for these data, [synapse detection](https://arxiv.org/abs/1403.3724), and [color correction](https://arxiv.org/abs/1310.0041), though [sebastian seung's group](http://seunglab.org/) (amongst others) is currently building the state of the art work here.  - Micro: Our current (in progress) pipeline includes synapse detection [guillermo sapiro](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005493) (duke), and analysis of the resulting matrices using [meda](https://github.com/neurodata/meda).
- Meso: [terastitcher](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-13-316) includes for stitching the images together to form volumes and  for image corrections and LDDMM ([1](https://link.springer.com/chapter/10.1007/978-3-319-66182-7_32), [2](https://arxiv.org/abs/1612.00356), [3](https://arxiv.org/abs/1605.02060)) registration to an atlas.
- Macro: [ndmg](https://www.biorxiv.org/content/early/2018/04/24/188706) processes s/f/d-MRI data to estimate and analyze connectomes, and [science in the cloud](https://academic.oup.com/gigascience/article/6/5/1/3062833).
  
The code bases that we continue to develop and/or support include:

- [ndmg](https://github.com/neurodata/ndmg) for multimodal connectome analysis
- [ndreg](https://github.com/neurodata/ndreg) for whole cleared brain analysis
- [terastitcher](http://abria.github.io/TeraStitcher/) for stitching 2D images into 3D volumes


 ### Statistics
 #### Statistical Methods to Estimate, Test, and Model Big Neurobiological Data
 
 
- Testing: [Multiscale Graph Correlation](https://arxiv.org/abs/1609.05148), [theory of MGC](https://arxiv.org/abs/1710.09768), [applications to network topology vs vertex attributes](https://arxiv.org/abs/1703.10136)
- [Supervised Manifold Learning](https://arxiv.org/abs/1709.01233)
- Decision forests: [ROFLMAO](https://epubs.siam.org/doi/abs/10.1137/1.9781611974973.56), and [RerF](https://arxiv.org/abs/1506.03410)
- Clustering: [fast k-means](https://arxiv.org/abs/1606.08905), [energy clustering](https://arxiv.org/abs/1710.09859), 
- [Time-series analysis](https://arxiv.org/abs/1509.03927)
- Scalable [graph analytics](https://arxiv.org/abs/1408.0500), [matrix multiplication](https://arxiv.org/abs/1602.02864), [eigendecomposition](https://arxiv.org/abs/1602.01421), [in R](https://arxiv.org/abs/1604.06414), 
- Graph Statistics: [survey on latent structure models](https://arxiv.org/abs/1709.05454), as well ass graph matching [1](https://arxiv.org/abs/1112.5507) and [2](https://arxiv.org/abs/1311.6425), [vertex classification](https://arxiv.org/abs/1311.5954), mean graph estimation [1](https://arxiv.org/abs/1609.01672) and [2](https://arxiv.org/abs/1707.03487), joint embedding [1](https://arxiv.org/abs/1507.08376), [2](https://arxiv.org/abs/1703.03862), 


And the code that we continue to develop and/or support includes:

- [Randomer Forest](https://github.com/neurodata/R-RerF) for nonlinear classification and regression
- [LOL](https://github.com/neurodata/LOL) for linear dimensionality reduction
- [MGC](https://github.com/neurodata/mgc) for hypothesis testing
- [graphstats](https://github.com/neurodata/graphstats) for graph statistics
