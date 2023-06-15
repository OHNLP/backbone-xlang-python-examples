# Example Python Backbone Module for the OHNLP Toolkit
This repository supplies a simple example of a python module/step for OHNLPTK Backbone 
pipelines.

To develop your own components, make a copy of this repository and instantiate 
a conda environment using `conda env create -n <environment_name> -f environment.yml`
and implement the following abstract classes (refer to wordcount.py as an example):
- `ohnlp.tookit.backbone.api.BackboneComponentDefinition`
- `ohnlp.tookit.backbone.api.BackboneComponent`
- Some DoFn class, namely one of:
  - `ohnlp.toolkit.backbone.api.BackboneComponentOneToOneDoFn` 
  - `ohnlp.toolkit.backbone.api.BackboneComponentOneToManyDoFn`

then update `backbone_module.json` accordingly.

To generate the zip file distributed with backbone, simply push to github with 
a tag following the format of `'v[0-9]+.[0-9]+.[0-9]+*'` or edit `build.yml` accordingly

If you do not wish to make your component public, then execute `conda-pack -o env-{win32|linux|darwin}.tar.gz` from within 
the project root directory and zip the entire folder. Note that this should be executed using the same OS on which you expect
OHNLP Toolkit to be ran. 

