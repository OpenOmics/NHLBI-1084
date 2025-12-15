<div align="center">
   
  <h1>NHLBI-1084 🔬</h1>
  
  **_long pipeline name_**

  [![tests](https://github.com/OpenOmics/iso-seek/workflows/tests/badge.svg)](https://github.com/OpenOmics/iso-seek/actions/workflows/main.yaml) [![docs](https://github.com/OpenOmics/iso-seek/workflows/docs/badge.svg)](https://github.com/OpenOmics/iso-seek/actions/workflows/docs.yml) [![GitHub issues](https://img.shields.io/github/issues/OpenOmics/iso-seek?color=brightgreen)](https://github.com/OpenOmics/iso-seek/issues)  [![GitHub license](https://img.shields.io/github/license/OpenOmics/iso-seek)](https://github.com/OpenOmics/iso-seek/blob/main/LICENSE) 
  
  <i>
    This is the home of the pipeline, iso-seek. Its long-term goals: to accurately ...insert goal, to infer ...insert goal, and to boldly ...insert goal like no pipeline before!
  </i>
</div>

## Overview
Welcome to iso-seek! Before getting started, we highly recommend reading through [iso-seek's documentation](https://openomics.github.io/iso-seek/).

The **`./iso-seek`** pipeline is composed several inter-related sub commands to setup and run the pipeline across different systems. Each of the available sub commands perform different functions: 

 * [<code>iso-seek <b>run</b></code>](https://openomics.github.io/iso-seek/usage/run/): Run the iso-seek pipeline with your input files.
 * [<code>iso-seek <b>unlock</b></code>](https://openomics.github.io/iso-seek/usage/unlock/): Unlocks a previous runs output directory.
 * [<code>iso-seek <b>install</b></code>](https://openomics.github.io/iso-seek/usage/install/): Download reference files locally.
 * [<code>iso-seek <b>cache</b></code>](https://openomics.github.io/iso-seek/usage/cache/): Cache remote resources locally, coming soon!

**iso-seek** is a comprehensive ...insert long description. It relies on technologies like [Singularity<sup>1</sup>](https://singularity.lbl.gov/) to maintain the highest-level of reproducibility. The pipeline consists of a series of data processing and quality-control steps orchestrated by [Snakemake<sup>2</sup>](https://snakemake.readthedocs.io/en/stable/), a flexible and scalable workflow management system, to submit jobs to a cluster.

The pipeline is compatible with data generated from Illumina short-read sequencing technologies. As input, it accepts a set of FastQ files and can be run locally on a compute instance or on-premise using a cluster. A user can define the method or mode of execution. The pipeline can submit jobs to a cluster using a job scheduler like SLURM (more coming soon!). A hybrid approach ensures the pipeline is accessible to all users.

Before getting started, we highly recommend reading through the [usage](https://openomics.github.io/iso-seek/usage/run/) section of each available sub command.

For more information about issues or trouble-shooting a problem, please checkout our [FAQ](https://openomics.github.io/iso-seek/faq/questions/) prior to [opening an issue on Github](https://github.com/OpenOmics/iso-seek/issues).

## Dependencies
**Requires:** `singularity>=3.5`  `snakemake>=6.0`

At the current moment, the pipeline uses a mixture of enviroment modules and docker images; however, this will be changing soon! In the very near future, the pipeline will only use docker images. With that being said, [snakemake](https://snakemake.readthedocs.io/en/stable/getting_started/installation.html) and [singularity](https://singularity.lbl.gov/all-releases) must be installed on the target system. Snakemake orchestrates the execution of each step in the pipeline. To guarantee the highest level of reproducibility, each step of the pipeline will rely on versioned images from [DockerHub](https://hub.docker.com/orgs/nciccbr/repositories). Snakemake uses singularity to pull these images onto the local filesystem prior to job execution, and as so, snakemake and singularity will be the only two dependencies in the future.

## Installation
Please clone this repository to your local filesystem using the following command:
```bash
# Clone Repository from Github
git clone https://github.com/OpenOmics/iso-seek.git
# Change your working directory
cd iso-seek/
# Add dependencies to $PATH
# Biowulf users should run
module load snakemake singularity
# Get usage information
./iso-seek -h
```

## Contribute 
This site is a living document, created for and by members like you. iso-seek is maintained by the members of OpenOmics and is improved by continous feedback! We encourage you to contribute new content and make improvements to existing content via pull request to our [GitHub repository](https://github.com/OpenOmics/iso-seek).


## Cite

If you use this software, please cite it as below:  

<details>
  <summary><b><i>@BibText</i></b></summary>
 
```text
Citation coming soon!
```

</details>

<details>
  <summary><b><i>@APA</i></b></summary>

```text
Citation coming soon!
```

</details>

<!---
# Setup from iso-seek template
```bash
# Add your new pipeline name here,
# whatever you set here will be the
# name of your cli too. Please make 
# sure it does not contain any spaces
# It should only contain, alpha-numeric
# characters and hyphens. 
new_pipeline_name="add_your_pipeline_name_here"

# Dry-run: This step automagically builds a 
# command to update any instances of the string
# iso-seek with your new pipeline name, please
# make sure to set the variable above to whatever
# you want to name the pipeline and CLI.
find . -type f -not -path '*/.iso-seek_version' -not -path '*./CHANGELOG.md' -not -path '*/.git/*' -exec grep 'iso-seek' {} /dev/null \; | awk -F ':' '{print $1}' | sort | uniq | sed "s/^/sed -i 's@iso-seek@$new_pipeline_name@g' /g"

# Updates any instances of the string iso-seek
# with the name you decided/set above.
find . -type f -not -path '*/.iso-seek_version' -not -path '*./CHANGELOG.md' -not -path '*/.git/*' -exec grep 'iso-seek' {} /dev/null \; | awk -F ':' '{print $1}' | sort | uniq | sed "s/^/sed -i 's@iso-seek@$new_pipeline_name@g' /g" | bash

# Rename the cli or main entry point 
# of the pipeline
mv iso-seek "$new_pipeline_name"
```
-->


## References
<sup>**1.**  Kurtzer GM, Sochat V, Bauer MW (2017). Singularity: Scientific containers for mobility of compute. PLoS ONE 12(5): e0177459.</sup>  
<sup>**2.**  Koster, J. and S. Rahmann (2018). "Snakemake-a scalable bioinformatics workflow engine." Bioinformatics 34(20): 3600.</sup>  
