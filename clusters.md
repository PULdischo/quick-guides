# Adroit Cluster [quick guide]
The Adroit Cluster at Princeton University offers high powered
computing capabilities to students, staff, faculty and other
researchers at Princeton. 

This guide explains how to get up and running with the clusters. The
process is split into several steps:
1. logging into the cluster and navigating to your home folder
2. cloning a git repository into the cluster
3. installing software packages and virtual environments
4. running a job 

## logging into the cluster and navigation
First, fill out a [registration form](https://forms.rc.princeton.edu/registration/?q=adroit) for access to the clusters. 

Use ssh (a secure shell) to log into the clusters remotely. See more
on [logging into the clusters](https://researchcomputing.princeton.edu/systems/adroit#access).

```console
ssh <YourNetID>@adroit.princeton.edu
```

Then, navigate to your personal folder, where you can add your files
and run jobs.
```console
cd /scratch/network/<YourNetID>
```

## cloning a git repo
In the case that your files are on github, you can easily clone them
into adroit. 

This will create a folder in the current directory. 

```console
git clone [your-github-repo]
```

## installing software
To run jobs, you'll need to install the necessary software, like
python. See more on [installing Python and related
software](https://researchcomputing.princeton.edu/support/knowledge-base/python)
on the clusters. 

First, load up Anaconda to activate python
```console
module load anaconda3/2023.3
```

Then, create a virtual environment. Below is a sample environment you
might create for machine learning with the `transformers` library.

```console
conda create --name ml ipykernel transformers transformers[torch] accelerate
datasets trl --channel conda-forge 
```

After creating the environment, verify that it exists in the list of
environments.

```console
conda info --envs # list current envs
```

Then you can activate your environment.

```console
conda activate ml
```

## running a job
Running a job involves creating a `job.slurm` file.

You can create one by running the following commands:
```console
nano job.slurm 
```

An editor will pop up inside your terminal program. Here, you can copy
and paste the job info. Make sure you edit the email line and the
environment and script lines to match your software.

See more on [creating a slurm job](https://researchcomputing.princeton.edu/get-started/guide-princeton-clusters/3-first-slurm-job).

```console
#!/bin/bash
#SBATCH --job-name=py-matinv     # create a short name for your job
#SBATCH --nodes=1                # node count
#SBATCH --ntasks=1               # total number of tasks across all nodes
#SBATCH --cpus-per-task=1        # cpu-cores per task (>1 if multi-threaded tasks)
#SBATCH --mem-per-cpu=4G         # memory per cpu-core (4G is default)
#SBATCH --time=00:01:00          # total run time limit (HH:MM:SS)
#SBATCH --mail-type=begin        # send email when job begins
#SBATCH --mail-type=end          # send email when job ends
#SBATCH --mail-type=fail         # send email if job fails
#SBATCH --mail-user=<YourNetID>@princeton.edu

module purge
module load anaconda3/2023.9
conda activate ml

python train.py
```

Then, you can run the job.

```console
sbatch job.slurm 
```

Finally, you can print the results.

```console
cat slurm-* #prints the results
```

## Contributors
This guide was created by Filipa Calado.

<!--
## downloading models and tokenizers for offline use

First activate your virtual environment

~conda activate mly~

Then import the models

#+begin_src python
from transformers import AutoTokenizer, AutoModelForSeq2SeqLM, AutoModelForCausalLM

tokenizer = AutoTokenizer.from_pretrained("mistralai/Mistral-7B-v0.1")

model = AutoModelForCausalLM.from_pretrained("mistralai/Mistral-7B-v0.1")
  
#+end_src

Then save the models to the space specifying a path

#+begin_src python 
tokenizer.save_pretrained("./pre_models/Mistral-7B-v0.1")
model.save_pretrained("./pre_models/Mistral-7B-v0.1")
#+end_src

Now when you’re offline, reload your files with PreTrainedModel.from_pretrained() from the specified directory:

#+begin_src python
tokenizer = AutoTokenizer.from_pretrained("./path/Mistral-7B-v0.1")

model = AutoModel.from_pretrained("./path/Mistral-7B-v0.1")
#+end_src

### transferring files
Sometimes
https://researchcomputing.princeton.edu/support/knowledge-base/transfer-files
### augmenting storage
### setting environment variable to use cached models

First, activate the environment. Then:

conda env config vars list

conda env config vars set my_var=value

reactivate your environment:

conda activate test-env

To check if the environment variable has been set, run

conda env config vars list

Run 🤗 Transformers in a firewalled or offline environment with
locally cached files by setting the environment variable

TRANSFORMERS_OFFLINE=1
-->
## resources on Adroit:
- [getting started on the clusters](https://researchcomputing.princeton.edu/get-started/guide-princeton-clusters)
- [Research Computing workshop on the clusters](https://github.com/PrincetonUniversity/hpc_beginning_workshop)
- [using Jupyter Notebooks on the
clusters](https://researchcomputing.princeton.edu/support/knowledge-base/jupyter) 
- [transferring files to/from the clusters](https://researchcomputing.princeton.edu/support/knowledge-base/transfer-files)

## resources about using `transformers` and virtual environments
- [huggingface installation instructions](https://huggingface.co/docs/transformers/en/installation)
- [managing python virtual
  environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) 


  
