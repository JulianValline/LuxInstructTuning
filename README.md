# Synthesizing an Instruction Tuning Dataset for Luxembourgish

This repository contains the code and data accompanying my Master thesis on "Synthesizing an Instruction Tuning Dataset for Luxembourgish". The thesis explores the creation of a Luxembourgish instruction tuning dataset for fine-tuning state-of-the-art large language models (LLMs).

## Instruction Tuning Dataset (Samples)

|instruction|response|text|
|:---|:---|:---|
|Wat ass mam Gebai vum Schumacher geschitt, nodeems de Policemusée do installéiert gouf?|De Policemusée vun der Asbl 'Le musée de la police grand-ducale – le gardien de la mémoire' gouf 2010 am Gebai installéiert. Mä 2017 gouf de Musée zougemaach, well d'Gebai plazeweis baufälleg ass.|"The following provides an instruction in form of a question.   Give a response that answers the question accurately.<br><br>###Instruction: Wat ass mam Gebai vum Schumacher geschitt, nodeems de Policemusée do installéiert gouf?<br><br>###Response: De Policemusée vun der Asbl 'Le musée de la police grand-ducale – le gardien de la mémoire' gouf 2010 am Gebai installéiert. Mä 2017 gouf de Musée zougemaach, well d'Gebai plazeweis baufälleg ass."|
|Wéini huet de Victor Tedesco seng Prisongstrof ugefaangen?|No der gescheiterter Expeditioun vun Exilbelsch am Revolutiounsjoer 1848.|"The following provides an instruction in form of a question.   Give a response that answers the question accurately.<br><br>###Instruction: Wéini huet de Victor Tedesco seng Prisongstrof ugefaangen?<br><br>###Response: No der gescheiterter Expeditioun vun Exilbelsch am Revolutiounsjoer 1848."|
|Wat fir Concoursen organiséiert d'Musekshéichschoul Franz Liszt Weimar?|D'Musekshéichschoul Franz Liszt Weimar organiséiert ënner anerem de 'Louis Spohr Wettbewerb' fir jonk Violonisten, den 'Internationalen Franz Liszt Wettbewerb' fir jonk Pianisten, de 'Bach-Liszt Wettbewerb' fir Uergel oder de 'Bundeswettbewerb Schulpraktisches Klavierspiel Grotrian-Steinweg' fir schoulpraktesche Piano.|"The following provides an instruction in form of a question.   Give a response that answers the question accurately.<br><br>###Instruction: Wat fir Concoursen organiséiert d'Musekshéichschoul Franz Liszt Weimar?<br><br>###Response: D'Musekshéichschoul Franz Liszt Weimar organiséiert ënner anerem de 'Louis Spohr Wettbewerb' fir jonk Violonisten, den 'Internationalen Franz Liszt Wettbewerb' fir jonk Pianisten, de 'Bach-Liszt Wettbewerb' fir Uergel oder de 'Bundeswettbewerb Schulpraktisches Klavierspiel Grotrian-Steinweg' fir schoulpraktesche Piano."|
|Wat war d'Haaptaarbechtsgebitt vum Martin Schwarzschild?|Säin Haaptaarbechtsgebitt war d'Stärenentwécklung.|"The following provides an instruction in form of a question.   Give a response that answers the question accurately.<br><br>###Instruction: Wat war d'Haaptaarbechtsgebitt vum Martin Schwarzschild?<br><br>###Response: Säin Haaptaarbechtsgebitt war d'Stärenentwécklung."|
|Wat war den Devolutiounskrich a wéi huet e sech ofgespillt?|Den Devolutiounskrich war e militäresche Konflikt tëscht Spuenien an dem Franséische Kinnekräich, deen 1667-1668 gedauert huet. E gouf ausgeléist, wéi de Kinnek Louis XIV. vu Frankräich Deeler vun de Spueneschen Nidderlande beusprocht huet, nodeem den spuenesche Kinnek Felipe IV. 1665 gestuerwen war. De Krich huet mat der Ënnerschrëft vum Friddenstraité vun Oochen den 2. Mee 1668 geendet, an deem Spuenien eng Rëtsch Territoiren huet missen ofginn.|"The following provides an instruction in form of a question.   Give a response that answers the question accurately.<br><br>###Instruction: Wat war den Devolutiounskrich a wéi huet e sech ofgespillt?<br><br>###Response: Den Devolutiounskrich war e militäresche Konflikt tëscht Spuenien an dem Franséische Kinnekräich, deen 1667-1668 gedauert huet. E gouf ausgeléist, wéi de Kinnek Louis XIV. vu Frankräich Deeler vun de Spueneschen Nidderlande beusprocht huet, nodeem den spuenesche Kinnek Felipe IV. 1665 gestuerwen war. De Krich huet mat der Ënnerschrëft vum Friddenstraité vun Oochen den 2. Mee 1668 geendet, an deem Spuenien eng Rëtsch Territoiren huet missen ofginn."|


## Project Overview

The project involved comparing different open-source LLMs for their Luxembourgish text generation capabilities, selecting the best performing model (Llama-3.1-405B-instruct), and using it to generate a synthetic dataset of instruction-answer pairs. The dataset was then evaluated using a reward model and human evaluators.

## Repository Contents

*   **Datasets:** Contains all synthetically generated instruction tuning datasets and evaluated datasets in both Luxembourgish and English translated, where necessary.
*   **Instruction_tuning_data_from_RTL.ipynb:** Jupyter notebook for generating the instruction-answer pairs from RTL news data.
*   **Instruction_tuning_data_from_wiki.ipynb:** Jupyter notebook for generating instruction-answer pairs from Wikipedia.
*   **Instruction_tuning_set_eval.ipynb:** Jupyter notebook for evaluating the English translated Luxembourgish instruction tuning set, given Nvidia Nemotron’s model reward scores and human evaluation scores.
*   **Instruction_tuning_set_reward.ipynb:** Jupyter notebook for rewarding the English translated Luxembourgish instruction tuning set, generated by Llama-3.1-405b-instruct.
*   **Merge_sets.ipynb:** Jupyter notebook to merge instruction-answer pairs from RTL news articles and Wikipedia data into the Luxembourgish instruction tuning dataset.
*   **sample_lux_data.ipynb:** Jupyter notebook for randomly sampling a subset from the original Luxembougish instruction tuning set for evaluation purposes. It samples the same rows as done in the reward and evaluation Jupyter notebooks. 
*   **master\_thesis\_draft.pdf:** PDF version of my master thesis.

## Data

The datasets used in this project include the entirety of the Luxembourgish Wikipedia and all RTL news articles up to May 2024. Due to resource constraints, only a subset of these datasets was used for generating the instruction tuning dataset. The RTL news data is not provided as it is not publicly available.

## Evaluation

A subset of the generated instruction tuning dataset was evaluated using the Nemotron-4-340B-reward model and human evaluators, assessing the quality and usability of the synthetic data.

## Usage

The Jupyter notebooks in this repository can be used to replicate the experiments or to generate additional instruction-answer pairs. The generated dataset can be used for fine-tuning LLMs on Luxembourgish tasks.

## Conclusion

This project has successfully demonstrated the feasibility of creating a Luxembourgish instruction tuning dataset and highlighted its potential for enhancing the capabilities of LLMs in the Luxembourgish language. I hope that this work will serve as a catalyst for further research and development in this domain, paving the way for more capable and accessible language technologies for the Luxembourgish-speaking community.
