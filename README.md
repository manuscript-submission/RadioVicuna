# RadioVicuna
Repository linked to the manuscript "Unlocking Information Extraction from Free-Text Radiological Reports: Accuracy of an Open-Source GPT Model" submitted to Radiology.


## Installation

(Optional) - Download text-generation-webui https://github.com/oobabooga/text-generation-webui

1 - Download the vicuna 1.3 13B weights
If you installed text-generation-webui, just execute :

```bash
  python download-model.py lmsys/vicuna-13b-v1.3
```
2- Install FastChat :

```bash
    pip3 install fschat
```
3- Edit the script_extraction.py file from this repository to update the paths to your Vicuna weights and source reports and name the table the script will create

4- Copy the auto_inference.py file from this repository to /FastChat/FastChat/serve

5- Edit the auto_inference.py file to match the variables you want to extract from the reports

6- Launch the script !

```bash
    python script_extraction
```


## Reports preparation

Reports must be in a singe .txt file, separated by a keyword you can change in auto_inference.py (default keyword is "NEXT_CASE")
We advise that you segment your reports to concentrate on the pertinent section. Future work will be done to implement 16K context to process full reports.

## Prompting

You can modify the prompts from the script_extraction.py file.  
We advise you to use short, natural prompts.  
We find that asking for a list variables tagged with the caracteristics of interest is a good default prompt.  
Examples :  

## Few-shot

We show that few-shot in-context learning improves the information extraction performance.  
Best results are usually obtained with 2-6 examples.  
To add or remove examples, simply edit the prompt variable from the script_extraction.py file to add or remove dialogues from the list.  

## Available models

Nothing limits this method to Vicuna. All models compatible with FastChat can be implemented by just downloading them and madding the path to the weights in the script_extraction.py file.
