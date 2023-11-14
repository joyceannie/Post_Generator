# LinkedIn Post Generation Model

The purpose of the project is to finetune a model to generate zero to hero posts on LinkedIn. OpenAI is used to finetune the model. The dataset is created using LnkedIn posts from top entrepreneurial voices like Justin Welsh. 

## Dataset
The raw data collected from LinkedIn is stored in the data folder. Each txt file corresponds to a LinkedIn post by some top voice. As of now, there are only 15 txt files. For better results, we have to collect more data.

## Data Preprocessing
In order to finetune the model using OpenAI, we have to transform the data to the right format. The raw data is converted to the right format using `data_processing.py`. The output of this step is a jsonl file.

## Data Analysis
The data is analyzed using `data_analysis.py`. It checks for format errors, provides basic statistics, and estimates token counts for fine-tuning costs. As of now, there are no errors. The dataset has ~5245 tokens that will be charged for during training. By default, you'll train for 6 epochs on this dataset. By default, you'll be charged for ~31470 tokens. As we add more data, the cost would get higher.

## How To Run

In order to run the scripts, you should have an [openAI](https://openai.com/) key. As of now, openAI is allowing finetuning only with paid accounts. 

Once you have generated your API key, copy it to the `.env` file.
If you are adding more data, run `data_processing.py` to generate the jsonl file, and perform data analysis using `data_analysis.py`. If you are not adding more data, you can skip this step.

Run `fine_tuning.py`  to fine-tune the model. You can perform inferences using the model name from `result/new_model_name.txt`.
