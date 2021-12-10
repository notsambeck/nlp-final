# Jolie & Sam's NLP project

## Notebook listing
* sam_manual_tests_on_model provides a (manual) way to write one-off tests against a pre-trained model
* training_script_breakdown
    * starts with the provided run.py
    * removes dependency on arg parser
    * sets everything for QA on Squad
    * chunks it up to make it easier to read & alter 
* checklist_tutorial/* are the unaltered Checklist tutorial notebooks

# Provided Starter Code: fp-dataset-artifacts

Project by Kaj Bostrom, Jifan Chen, and Greg Durrett. Code by Kaj Bostrom and Jifan Chen.

## How to run

`python3 run.py --do_eval --task qa --dataset squad --model ./trained_model/ --output_dir ./eval_output/`

**Descriptions of other important arguments are available in the comments in `run.py`.**

Data and models will be automatically downloaded and cached in `~/.cache/huggingface/`.
To change the caching directory, you can modify the shell environment variable `HF_HOME` or `TRANSFORMERS_CACHE`.
For more details, see [this doc](https://huggingface.co/transformers/v4.0.1/installation.html#caching-models).

An ELECTRA-small based NLI model trained on SNLI for 3 epochs (e.g. with the command above) should achieve an accuracy of around 89%, depending on batch size.
An ELECTRA-small based QA model trained on SQuAD for 3 epochs should achieve around 78 exact match score and 86 F1 score.

## Working with datasets
This repo uses [Huggingface Datasets](https://huggingface.co/docs/datasets/) to load data.
The Dataset objects loaded by this module can be filtered and updated easily using the `Dataset.filter` and `Dataset.map` methods.
For more information on working with datasets loaded as HF Dataset objects, see [this page](https://huggingface.co/docs/datasets/process.html).
