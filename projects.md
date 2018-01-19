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



### Nanoscale: Ultrastructural Quantitative Anatomy
   1. Scientific Goal: Determine statistics of cortical ultrastructural neuroanatomy
   1. Technical Challenges:
        1. infra (kasthuri11): 
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
    1. Collaborators: bobby kasthuri (argonne), albert cardona & marta zlatic (janelia), davi bock (janelia)    

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
    1. Collaborators: stephen smith (allen), rick huganir (jhu)
    
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
  1. Collaborators: karl deisseroth (stanford) & michaela gallager (jhu)
  
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
   1. Collaborators: alex badea (duke), mike milham (cmi), vince calhoun (mrn), kent kiehl (mrn), bruce rosen (martinos)
    
   
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
    1. Collaborators: ed lein (allen), mike hawrylycz (allen)
    
    
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
 1. Collaborators: florian engert (harvard) 
