- [Overview](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#Overview)
- [Nano](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#nanoscale-ultrastructural-quantitative-anatomy)
- [Micro](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#microscale-synapse-diversity)
- [Meso](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#mesoscale-cellular-engrams)
- [Macro](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#macroscale-connectome-coding)
- [Angstro](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#angstro-spatial-transcriptomics)
- [Multi](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#multiscale-virtual-zebrafish)


## Overview

To facilitate successful achievement of our [mission](mission.md), our projects have the following properties:

1. answers an important neuroscientific question,
2. solves interesting technical (statistical and/or computational) challenges,
3. provides a resource to the community to build upon (e.g., R package, data source, etc.),
4. while working closely with a dedicated scientific collaborator providing data & insight.


Some generic background that could be useful for many different projects in our lab:
1. large spatial data: [open connectome project](https://dl.acm.org/citation.cfm?doid=2484838.2484870),  [cosmos to connectomes](http://linkinghub.elsevier.com/retrieve/pii/S0896-6273(14)00746-6http://linkinghub.elsevier.com/retrieve/pii/S0896-6273(14)00746-6), [bossDB](https://www.biorxiv.org/content/early/2017/11/10/217745)
2. scalable analytics: [knor for k-means](https://arxiv.org/abs/1606.08905), [FlashR](https://arxiv.org/abs/1604.06414), [FlashMatrix](https://arxiv.org/abs/1602.02864), [FlashEigen](https://arxiv.org/abs/1602.01421), [FlashGraph](https://arxiv.org/abs/1408.0500), 
3.  statistics: [graph stat survey](https://arxiv.org/abs/1709.05454), [testing](https://arxiv.org/abs/1609.05148), [graph matching](https://arxiv.org/abs/1405.3133), [classification](https://arxiv.org/abs/1709.01233), [random forest](https://arxiv.org/abs/1506.03410)
4. cloud computing: [to the cloud](http://www.cell.com/neuron/abstract/S0896-6273(16)30783-8), [sic](https://academic.oup.com/gigascience/article/6/5/1/3062833), [gigantum](http://gigantum.io/)

### Nanoscale: Ultrastructural Quantitative Anatomy
   1. Scientific Goal: Determine statistics of cortical ultrastructural neuroanatomy
   1. Technical Challenges:
        1. infra: 
            - cloud raw images and downsampling operational
            - cloud annotations & metadata operational
            - ndviz links overlays annotations operational
            - Jupyter notebooks runs and reproduces results
        2. machine vision: 
            - synapse detection on EM with mask
        3. comp stat: n/a
        4. stat theory: n/a
        5. analysis: test whether synapses are uniformly distributed in space
    1. Resources:
        1. Image data in cloud
        2. Annotation data in cloud
        3. Interactive ndviz links to annotations overlaid on images
        4. Jupyter notebooks
        5. R/Python package for analysis 
    1. Collaborators & references: [bobby kasthuri](http://www.cell.com/cell/pdfExtended/S0092-8674(15)00824-7) (argonne), [albert cardona & marta zlatic](https://www.nature.com/articles/nature23455) (janelia), [davi bock](https://www.nature.com/articles/nature09802) (janelia)    

### Microscale: Synapse Diversity
  1. Scientific Goal: Discover synapse taxonomies across conditions
  1. Technical Challenges:
        1. infra (new cAT data):
            - cloud raw images and downsampling operational
            - cloud annotations & metadata operational
            - ndviz links overlays annotations operational
            - synaptograms button
            - python notebooks runs and reproduces results
        2. vision:
            - "clean" raw data (eg, register, stitch, etc.)
            - 1-click synapse detection qith quantitative validation and quality assurance
        3. comp stat
            - spectral clustering on 1M points in WxHxDxC (~11x11x11x20)
        4. stat theory
            - statistical consistency for non-parametric multiscale clustering methodologies
            - K-sample test for differences between distributions
            - Mitigating batch effects upon combining multiple disparate datasets
            - relative efficiency of different clustering schemes (k-means, GMM, energy)
        5. analysis: make sense of clustering tree
    1. Resources:
        1. Image data in cloud
        2. Annotation data in cloud
        3. Interactive ndviz links to annotations overlaid on images
        4. Jupyter notebooks
        5. R/Python package for clustering analysis 
    1. Collaborators: stephen smith [1](http://www.jneurosci.org/content/35/14/5792.short), [2](https://www.frontiersin.org/articles/10.3389/fnana.2015.00100/full), [3](http://www.cell.com/neuron/abstract/S0896-6273(10)00766-X) (allen), rick huganir (jhu), [guillermo sapiro](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005493) (duke)
    
### Mesoscale: Cellular Engrams
 1. Scientific Question: Uncover the principles of cellular resolution brain-wide neural circuits 
 1. Technical Challenges
            1. infra:
              - Ailey in a a Day
              - viz cells & processes
            2. vision
              - detect cells with qualitative & quantitative QA
              - track processes with qualitative & quantitative QA
            3. comp
              - Ailey in a a Day
            4. stat
              - how can we estimate connectivity efficiently
            5. analysis: ???        
  1. Resources
        1. Image data in cloud
        2. Annotation data in cloud
        3. Interactive ndviz links to annotations overlaid on images
        4. Jupyter notebooks
        5. R/Python package for registration, cell detection, and tractography analysis 
  1. Collaborators: karl deisseroth [1](https://www.sciencedirect.com/science/article/pii/S009286741630558X), [2](https://www.sciencedirect.com/science/article/pii/S009286741500851X) (stanford) & michaela gallager (jhu), alan yuille and [seyoun park](http://onlinelibrary.wiley.com/wol1/doi/10.1118/1.4811203/full) (jhu), [michael miller](https://link.springer.com/chapter/10.1007/978-3-319-66182-7_32) (jhu), [terastitcher](http://abria.github.io/TeraStitcher/), [n4itk](http://ieeexplore.ieee.org/document/5445030/authors?ctx=authors) 
  
### Macroscale: Connectome Coding
  1. Scientific Question: Reveal the latent structure of connectomes at various resolutions
   1. Technical Challenges:
        1. infra
            - ndmg/sic "on demand"
            - data & derivatives in cloud datastore
            - viz for images, tensors, fibers, & graphs
        2. vision
            - fngs integration
            - odf estimation
            - prob tractography
        3. comp stats
            - joint embedding 5k graphs with 1M vertices & 100M edges each
        4. stat theory
            - which embedding is better when?
            - how can we jointly embed graphs with multiple edge types?
            - how can we identify the important vertices for a given graph attribute?
            - how can we mitigate batch effects?
        5. analysis
            - what is the difference between genotypes? genders?
            - what vertices are useful for predicting CCI? personality? are predictions operationally useful?
   1. Resources
        1. Raw data in cloud
        2. Processed data in cloud
        3. LIMS for navigating data
        4. Jupyter notebooks
        5. R/Python package for analysis 
   1. Collaborators: [alex badea](https://academic.oup.com/cercor/article/25/11/4628/2367615) (duke), [mike milham](https://www.biorxiv.org/content/early/2017/06/13/149369) (cmi), vince calhoun (mrn), [kent kiehl](https://www.amazon.com/Psychopath-Whisperer-Science-Without-Conscience/dp/0770435866) (mrn), bruce rosen [1](https://www.sciencedirect.com/science/article/pii/S1053811915007983?via%3Dihub), (martinos)
    
   
### Angstro: Spatial Transcriptomics

   1. Scientific Goal: Determine diversity of cell types in brain
   1. Technical Challenges: 
        1. infra: unclear 
        2. machine vision: n/a 
        3. comp stat: non-parametric clustering and evaluation for multi-GB data
        4. stat theory: consistency proof of clustering
        5. analysis: cluster O(10^4) cells each with O(10^4) gene expressions, as well as several other pieces of metadata, including layer, species, sex, etc. 
    1. Resources:
        4. Jupyter notebooks
        5. R/Python package for analysis 
    1. Collaborators: [ed lein](https://www.biorxiv.org/content/early/2018/01/19/239749) (allen), [mike hawrylycz](https://www.biorxiv.org/content/early/2017/12/06/229542) (allen)
    
    
 ### Multiscale Virtual Zebrafish
 
   1. Scientifi Goal: Build a biofidelic simulation of a zebrafish behaving naturally
   1. Technical Challenges: 
        1. infra: 
            - Nano EM data in cloud
            - Micro Ca++ imaging data in cloud
            - Meso regions and projections in cloud
            - ndviz links overlays annotations operational
            - Jupyter notebooks runs and reproduces results
        2. machine vision:
            - cell detection in Ca++ data
            - tractography of myelinated axons
        3. comp stat: unclear
        4. stat theory: unclear
        5. analysis: unclear
    1. Resources:
 1. Resources
        1. Image data in cloud
        2. Annotation data in cloud
        3. Interactive ndviz links to annotations overlaid on images
        4. Jupyter notebooks
        5. R/Python package for registration, cell detection, and tractography analysis 
 1. Collaborators: florian engert [1](https://www.nature.com/articles/nature11057), [2](https://www.nature.com/nmeth/journal/v12/n11/abs/nmeth.3581.html) (harvard), [jeff lichtman](https://www.nature.com/articles/nature22356) (harvard)
