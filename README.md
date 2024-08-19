# Connecting PROTEAN-CR with other tools in the ITCR Network

Repository that connects PROTEAN-CR to other related tools in the ITCR Network!

## Connections

This repo currently contains two jupyter notebooks, with more ITCR connections to come in the future:
- One examples that runs the APE-Gen2.0 software with a selected peptide and MHC allele.
- One example that scans the **CEDAR database**, a cancer Epitope Database which houses T cell peptidic epitopes (see more [here](https://cedar.iedb.org/)) for *Hepatitis B-derived peptides* and models these peptides structurally with APE-Gen2.0. Such a workflow can be easily customized for peptides of different origins (viral, tumor), and with different arguments, customing the workflow to one's needs.
- More connections with ITCR tools will follow, stay in touch for changes!

## Usage

There are two ways to use this particular repo:
1) Using the binder link here:[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/KavrakiLab/protean-cr-connections/HEAD)
**IMPORTANT**: Binder is highly unstable on our end, and it might be the case that the link above won't work for you, as building the image properly largely is on binder's side. In case this happens, see 2). 

2) Cloning the repo and run examples *locally*. 
- This requires a local installation of [docker](https://docs.docker.com/get-docker/). As soon as you install docker on your system (follow the instructions in the link), you will need to build the docker image using the `Dockerfile` provided in the repo. Enter the directory of the repo that you cloned, and simply execute the following command:
```
docker build -t apegen2.0-binder-image .
```
This will create a docker image named `apegen2.0-binder-image` on your system that you can use. 

- After the image is successfully created in your local computer, simply run
```
docker run -it --rm -v $(pwd):/home/binderuser -p 8888:8888 apegen2.0-binder-image jupyter notebook --NotebookApp.default_url=/lab/ --ip=0.0.0.0 --port=8888
```
This will create a docker container with a jupyter notebook instance that you have access to. Following the provided link with the notebook token will direct you to an interface where you can use the workflows provided. 

## References

If you're using APE-Gen2.0 in you application, please cite: 
```
@article{Fasoulis2024,
  title = {APE-Gen2.0: Expanding Rapid Class I Peptide–Major Histocompatibility Complex Modeling to Post-Translational Modifications and Noncanonical Peptide Geometries},
  volume = {64},
  ISSN = {1549-960X},
  url = {http://dx.doi.org/10.1021/acs.jcim.3c01667},
  DOI = {10.1021/acs.jcim.3c01667},
  number = {5},
  journal = {Journal of Chemical Information and Modeling},
  publisher = {American Chemical Society (ACS)},
  author = {Fasoulis,  Romanos and Rigo,  Mauricio M. and Lizée,  Gregory and Antunes,  Dinler A. and Kavraki,  Lydia E.},
  year = {2024},
  month = feb,
  pages = {1730–1750}
}
```
