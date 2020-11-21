# Question Answering Predictions

1. [MLQA Predictions](MLQA_prediction_results.json)
2. [SQuAD Predictions](SQuAD_prediction_results.json)

## Predictions
### MLQA Predictions
[MLQA Predictions](MLQA_prediction_results.json)

| Name in File      | Used Dataset for Finetuning       | Used Dataset for Prediction     |
|-------------------|-----------------------------------|---------------------------------|
| original_squad    | SQuADv1.1 Train                   | SQuADv1.1 Dev                   |
| translated_squad  | Translated SQuAD in German        | MLQA dev-context-de-question-de |
| german_mlqa       | MLQA train-context-de-question-de | MLQA dev-context-de-question-de |
| zero_shot_english | -                                 | MLQA dev-context-en-question-en |
| zero_shot_german  | -                                 | MLQA dev-context-de-question-de |

### SQuAD Prediction
[SQuAD Predictions](SQuAD_prediction_results.json)

| Name in File      | Used Dataset for Finetuning       | Used Dataset for Prediction     |
|-------------------|-----------------------------------|---------------------------------|
| original_squad    | SQuADv1.1 Train                   | MLQA dev-context-en-question-en |

## Parameters
- Model: [BERT Base Multilingual Cased](https://github.com/google-research/bert)
- Finetuning Parameters:
  - train_batch_size=32
  - learning-rate=3e-5
  - num_train_epochs=2.0
  - max_seq_length=384
  - doc_stride=128
  - use_tpu=true
- Finetuning: [BERT Function](https://github.com/google-research/bert)
- Evaluation: [MLQA Function](https://github.com/facebookresearch/MLQA)

## Evalutation Results
| Dataset                  | Exact Match | F1        |
|--------------------------|-------------|-----------|
| Original SQuAD           | 81,901608   | 88,947487 |
| Original SQuAD with MLQA | 66,898954   | 80,266104 |
| German SQuAD with MLQA   | 44,140625   | 61,369219 |
| MLQA-de                  | 39,0625     | 54,079560 |
| Zero-Shot in English     | 0,0871080   | 5,5916380 |
| Zero-Shot in German      | 0,1953125   | 5,9733396 |