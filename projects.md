- [Current Scientific Goals](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#current-scientific-goals)
  - [EM](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#nanoscale-ultrastructural-quantitative-anatomy)
  - [AT](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#sub-microscale-synapse-diversity)
  - [CLARITY](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#super-microscale-cellular-engrams)
  - [MRI](https://github.com/neurodata/weekly-experiments/blob/master/projects.md#mesoscale-connectome-coding)



## Projects

To facilitate successful achievement of our mission, our projects have the following properties:

1. answers an important neuroscientific question,
2. solvies interesting technical (statistical and/or computational) challenges,
3. (ideally) provides a resource to the community to build upon (e.g., R package, data source, etc.),
4. while working closely with a dedicated scientific collaborator providing data & insight.



### Nanoscale: Ultrastructural Quantitative Anatomy
   1. Scientifi Question: Determine statistics of cortical ultrastructure
   1. Technical Challenges
        1. infra: 
            - kasthuri11 in cloud
            - kasthuri11 annotations & metadata in cloud
            - ndviz links overlays annotations on images
            - python notebooks runs and reproduces results
        2. machine vision: (nothing urgent)
            - synapse detection on EM with mask (frank wood)?
        3. comp stat: n/a
        4. stat theory: n/a
        5. analysis: (not urgent) test whether synapses are uniformly distributed in space
    1. Resources:
        - EM data
        - Annotations
        - Python notebooks
    1. Collaborators: **bobby**, albert/marta, davi, florian
    

### Sub-Microscale: Synapse Diversity
  1. Scientific Question: Discover synapse taxonomies across conditions
  1. Technical Challenges:
        1. infra:
            - all data in cloud
            - synapse centroids in cloud
            - vis overlay of centroids & data
            - synaptograms button
        2. vision:
            - "clean" raw data (eg, register, stitch, etc.)
            - 1-click synapse detection qith quantitative validation and quality assurance
        3. comp stat
            - spectral clustering on 1M points in WxHxDxC (~11x11x11x20)
        4. stat theory
            - K-sample test for differences between distributions
            - relative efficiency of different clustering schemes (k-means, GMM, energy)
            - theoretical results for non-parametric clustering
        5. analysis: make sense of clustering tree
    1. Resources:
        1. AT data
        2. synapse locations
        3. synapse cluster ID
        4. clustering package
    1. Collaborators: forrest, austin
### Super-Microscale: Cellular Engrams
 1. Scientific Question: Uncover the principles of cellular resolution brain-wide neural circuits 
 1. Technical Challenges
            1. infra:
              - A in an hour
              - viz cells & processes
            2. vision
              - detect cells with quantitative validation & QA
              - track processes with quantatiative validation & QA
            3. comp
              - LDDMM on 10 micron brain
            4. stat
              - how can we estimate connectivity efficiently
            5. analysis: ???        
  1. Resources
        - clarity brains registered to atlas (& vice versa)
        - links to viz
        - ndreg in cloud
  1. Collaborators: ailey & audrey
### Mesoscale: Connectome Coding
  1. Scientific Question: Reveal the latent structure of connectomes at the voxel resolution
   1. Technical Challenges:
        1. infra
            - ndmg/sic "on demand"
            - data & derivatives in cloud datastor
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
            - alex badea: what is the difference between genotypes? genders?
            - milham: what vertices are useful for predicting CCI? personality? are predictions operationally useful?
   1. Resources
        - data,  derivatives, and viz for all MRI data
        - ndmg in cloud
   1. Collaborators: badea & milham
