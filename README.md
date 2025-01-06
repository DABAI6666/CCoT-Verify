## Requirements

To install requirements:
```
pip install -r requirements.txt
```

## Dataset

- MOCHEG: You can download dataset [here](Comply with anonymity rules, will be made public after acceptance)..

    For more information on the dataset format and structure, please refer to their Please check their [official repository](Comply with anonymity rules, will be made public after acceptance)..
- Factify: The dataset can be downloaded [here](Comply with anonymity rules, will be made public after acceptance).

    Additional details can be found on their [official website](Comply with anonymity rules, will be made public after acceptance).

- MultiVerify: New Dataset(./MultiVerify Dataset)

### Model CBART
The default version of language model is [CBART](Comply with anonymity rules, will be made public after acceptance)..
We provide the download link of pretrained CBART [link](Comply with anonymity rules, will be made public after acceptance).

## Evaluation
To run the pipeline and evaluate on datasets, run:

```
#LLM Reranker
#Image retrieval
python ir_llms.py --mode=test --media=img --model_name==Salesforce/instructblip-flan-t5-xl --use_llm_score=False --mocheg_result_path=checkpoints/mocheg_img_results/query_result_img.pkl --prompt=Is this image and text query mentioning the same person or topic? answer with yes or no.
#Text retrieval
python ir_llms.py --mode=test --media=txt --model_name==Mistral-7B-OpenOrca --use_llm_score=True --mocheg_result_path=checkpoints/mocheg_txt_results/query_result_txt.pkl --prompt=Is this corpus related to the query? Answer with yes or no.
```

``` 
# Fact verification
python CCoT-Verify.py --media=multimodal --model_name=llava-llama-3-8b --evidence_type='retrieved' --two_level_prompting=True --task1_out=retrieval/output/ir_llms/mocheg/txt 
```

Notes: Due to the large size of the new dataset (over 30GB) and to prevent malicious fork incidents before publication, the complete data and files will be released immediately after the paper is accepted.