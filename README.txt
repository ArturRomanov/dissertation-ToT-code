THESE ARE THE NOTES. TO CONSIDER IF TO INCLUDE THE NOTES AND IF TO REFERENCE LIKE VSCODE REFERENCE TO THE WEBSITE
The initial virtual environment was created with the VSCode in the Jupyter Notebook.
The requirements txt file was generated according to https://pip.pypa.io/en/stable/cli/pip_freeze/ TO REFERENCE
To regenerate the requirements txt file
To tell that code was run and test on MacBook
To write to install Ollama and according model
To write how to run ToT-prompt-test
To include the required things according to the Llama or Mistral Apache licence
To consider to tell that created the git repository with the guide https://github.com/git-guides/git-init
To indicate that have to register at Hugging Face
Some optional outputs in ToT-evaluate-Mistral for Mistral simple generate and check answers and Mistral ToT generate and check answers were removed because GitHub could not display the code because the file was too large
To add references for the dataset here, to describe the difference between the ToT tuning files


Please note, the code was run and tested on MacBook M3 Max with RAM 128 GB. The provided instructions assume that you use the same computer if you want to run the code. If another computer or environment is used, then some adjustments could be required to run the code, especially, the code related to large language models.
1) Python 3.12.2 should be used
2) Create a virtual environment using the requirements file and use the virtual environment for the notebooks
3) Run the ToT-data-ETL notebook to generate full_train_dataset, full_validation_dataset and full_test_dataset files
4) Install (Ollama, 2024a) and install this model (Ollama, 2024b) to your computer or environment. Further guidance could be found at (Ollama, 2024c). 
Please note that you need to have enough GPU for this, otherwise you would need to use another model and edit the code for the model in the ToT-data-answer-generator-and-checker and ToT-prompt-test notebook accordingly
5) Ensure that (Ollama, 2024a) is opened and run the ToT-data-answer-generator-and-checker notebook to generate datasets for tuning
6) Ensure that (Ollama, 2024a) is opened and run ToT-prompt-test notebook to test the prompt. Please note that different results could be generated for each run of the notebook and you could need to run the notebook a few times to generate similar results as those indicated in this notebook
References
Ollama, 2024a. Ollama [computer program]. Available from: https://ollama.com [Accessed 1 September 2024].
Ollama, 2024b. mixtral 8x7b-instruct-v0.1-fp16 [Online]. Available from: https://ollama.com/library/mixtral:8x7b-instruct-v0.1-fp16 [Accessed 25 September 2024].
Ollama, 2024c. README.md [computer program]. Available from: https://github.com/ollama/ollama/blob/main/README.md [Accessed 1 September 2024].

Please note, just in case it is needed, the following code was not needed in ToT-data-answer-generator-and-checker notebook in the generate_and_check_answers function in the second if statement. 
However, it was needed in, for example, ToT-evaluate-Mixtral notebook in the generate_and_check_answers function in the second if statement.

# Code adapted from: pandas, 2024. pandas.isna (v.2.2) [Online]. 
# Available from: https://pandas.pydata.org/docs/reference/api/pandas.isna.html#pandas-isna [Accessed 15 October 2024].
pd.isna(dataset_record.generated_answer) == True
#
