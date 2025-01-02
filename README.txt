# Project

The code is developed for the dissertation and includes the following notebooks.
ToT-data-ETL.ipynb
ToT-data-answer-generator-and-checker.ipynb
ToT-prompt-test.ipynb
ToT-evaluate-Mixtral.ipynb
ToT-evaluate-Mistral.ipynb
ToT-tuning-1.ipynb
ToT-tuning-2.ipynb
ToT-tuning-3.ipynb
ToT-evaluate-Mistral-tuned.ipynb
ToT-test-Mistral-tuned.ipynb
ToT-analysis-results.ipynb

This project is based on the MMLU dataset (Hendrycks et al, 2021a; Hendrycks et al, 2021b; Hendrycks et al, 2023).

# Prerequisites

Register at (Hugging Face, n.d.a), perform the access request at (Mistral AI, 2024), follow (Hugging Face, n.d.b) to insert your private secret in the code like indicated in particular notebooks instead of "" as indicated in (Hugging Face, n.d.b).

# How to run the code

Please note, the code was run and tested on MacBook M3 Max with RAM 128 GB. The provided instructions assume that you use the same computer if you want to run the code. If another computer or environment is used, then some adjustments could be required to run the code, especially, the code related to large language models.
Python 3.12.2 should be used
Create a virtual environment using the requirements file and use the virtual environment for the notebooks
Run the ToT-data-ETL.ipynb notebook to generate full_train_dataset, full_validation_dataset and full_test_dataset files
Install (Ollama, 2024a) and install this model (Ollama, 2024b) to your computer or environment. Further guidance could be found at (Ollama, 2024c). 
Please note that you need to have enough GPU for this, otherwise you would need to use another model and edit the code for the model in the ToT-data-answer-generator-and-checker.ipynb and ToT-prompt-test.ipynb notebooks accordingly
Ensure that (Ollama, 2024a) is opened and run the ToT-data-answer-generator-and-checker.ipynb notebook to generate datasets for tuning
Ensure that (Ollama, 2024a) is opened and run the ToT-prompt-test.ipynb notebook to test the prompt. Please note that different results could be generated for each run of the notebook and you could need to run the notebook a few times to generate similar results as those indicated in this notebook
Ensure that (Ollama, 2024a) is opened and run the ToT-evaluate-Mixtral.ipynb notebook.
Ensure that (Ollama, 2024a) is opened and run the ToT-evaluate-Mistral.ipynb notebook. Please note that you have to register at (Hugging Face, n.d.a) according to the prerequisites and according to the instructions in the notebook to run it. Please also note that you could be required to control the available GPU for (Mistral AI, 2024) for the generation of data and for (Ollama, 2024a; Ollama, 2024b) for the evaluation functionality yourself on your computer before running the particular parts.
Run the ToT-tuning-1.ipynb notebook. This notebook is required to run before ToT-evaluate-Mistral-tuned.ipynb notebook. Please note that you have to register at (Hugging Face, n.d.a) according to the prerequisites and according to the instructions in the notebook to run it.
Run the ToT-tuning-2.ipynb notebook. This is the optional step. Please note that you have to register at (Hugging Face, n.d.a) according to the prerequisites and according to the instructions in the notebook to run it.
Run the ToT-tuning-3.ipynb notebook. This is the optional step. Please note that you have to register at (Hugging Face, n.d.a) according to the prerequisites and according to the instructions in the notebook to run it.
Ensure that (Ollama, 2024a) is opened and run the ToT-evaluate-Mistral-tuned.ipynb notebook. Please note that you have to register at (Hugging Face, n.d.a) according to the prerequisites and according to the instructions in the notebook to run it. Please also note that you could be required to control the available GPU for the tuned Mistral with base (Mistral AI, 2024) and a checkpoint from the ToT-tuning-1.ipynb notebook for the generation of data and for (Ollama, 2024a; Ollama, 2024b) for the evaluation functionality yourself on your computer before running the particular parts.
Run ToT-analysis-results.ipynb notebook. Please note that the notebook requires data from the ToT-evaluate-Mixtral.ipynb, ToT-evaluate-Mistral.ipynb and ToT-evaluate-Mistral-tuned.ipynb.
Run ToT-test-Mistral-tuned.ipynb notebook. Please note that you have to register at (Hugging Face, n.d.a) according to the prerequisites and according to the instructions in the notebook to run it.

# Other

Please note, just in case it is needed, the following code was not needed in ToT-data-answer-generator-and-checker.ipynb notebook in the generate_and_check_answers function in the second if statement. 
However, it was needed in, for example, ToT-evaluate-Mixtral.ipynb notebook in the generate_and_check_answers function in the second if statement.

# Code adapted from: pandas, 2024. pandas.isna (v.2.2) [Online]. 
# Available from: https://pandas.pydata.org/docs/reference/api/pandas.isna.html#pandas-isna [Accessed 15 October 2024].
pd.isna(dataset_record.generated_answer) == True
#

The file with libraries was created according to the instructions at (The pip developers, 2022), e.g., (The pip developers, 2022, para.14) and (The pip developers, 2022, para.15).

(GitHub, 2024) was referred to load the data online (GitHub, 2024).

# References

Ollama, 2024a. Ollama [computer program]. Available from: https://ollama.com [Accessed 1 September 2024].
Ollama, 2024b. mixtral 8x7b-instruct-v0.1-fp16 [Online]. Available from: https://ollama.com/library/mixtral:8x7b-instruct-v0.1-fp16 [Accessed 25 September 2024].
Ollama, 2024c. README.md [computer program]. Available from: https://github.com/ollama/ollama/blob/main/README.md [Accessed 1 September 2024].
Hugging Face, n.d.a. The AI community building the future [Online]. Available from: https://huggingface.co [Accessed 19 October 2024].
Hugging Face, n.d.b. User access tokens [Online]. Available from: https://huggingface.co/docs/hub/en/security-tokens [Accessed 19 October 2024].
Mistral AI, 2024. Model Card for Mistral-7B-Instruct-v0.3 [Online]. s.l.: Hugging Face. Available from: https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.3 [Accessed 19 October 2024].
Hendrycks, D., Burns, C., Basart, S., Zou, A., Mazeika, M., Song, D. and Steinhardt, J., 2021a. Dataset Card for MMLU [Online]. s.l.: Hugging Face. Available from: https://huggingface.co/datasets/cais/mmlu [Accessed 5 August 2024].
Hendrycks, D., Burns, C., Basart, S., Zou, A., Mazeika, M., Song, D. and Steinhardt, J., 2021b. Measuring Massive Multitask Language Understanding. ICLR 2021, 4 May 2021, Vienna. Ithaca: Cornell University Library, arXiv.org, pp.1-27. Available from: https://arxiv.org/pdf/2009.03300.pdf [Accessed 5 August 2024].
Hendrycks, D., Burns, C., Basart, S., Critch, A., Li, J., Song, D. and Steinhardt, J., 2023. Aligning AI With Shared Human Values. ICLR 2021, 4 May 2021, Vienna. Ithaca: Cornell University Library, arXiv.org, pp.1-29. Available from: https://arxiv.org/pdf/2008.02275.pdf [Accessed 5 August 2024]. 
The pip developers, 2022. pip freeze [computer program]. Available from: https://github.com/pypa/pip/blob/main/docs/html/cli/pip_freeze.rst [Accessed 25 December 2024].
GitHub, 2024. Git Init [Online]. Available from: https://github.com/git-guides/git-init [Accessed 25 December 2024].