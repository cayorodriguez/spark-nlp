---
layout: model
title: XLM-RoBERTa Base NER Pipeline
author: John Snow Labs
name: xlm_roberta_base_token_classifier_ontonotes_pipeline
date: 2022-04-21
tags: [open_source, ner, token_classifier, xlm_roberta, ontonotes, xlm, en]
task: Named Entity Recognition
language: en
edition: Spark NLP 3.4.1
spark_version: 3.0
supported: true
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

This pretrained pipeline is built on the top of [xlm_roberta_base_token_classifier_ontonotes](https://nlp.johnsnowlabs.com/2021/10/03/xlm_roberta_base_token_classifier_ontonotes_en.html) model.

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/xlm_roberta_base_token_classifier_ontonotes_pipeline_en_3.4.1_3.0_1650542464092.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python
pipeline = PretrainedPipeline("xlm_roberta_base_token_classifier_ontonotes_pipeline", lang = "en")

pipeline.annotate("My name is John and I have been working at John Snow Labs since November 2020.")
```
```scala
val pipeline = new PretrainedPipeline("xlm_roberta_base_token_classifier_ontonotes_pipeline", lang = "en")

pipeline.annotate("My name is John and I have been working at John Snow Labs since November 2020.")
```
</div>

## Results

```bash
+--------------+---------+
|chunk         |ner_label|
+--------------+---------+
|John          |PERSON   |
|John Snow Labs|ORG      |
|November 2020 |DATE     |
+--------------+---------+
```

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|xlm_roberta_base_token_classifier_ontonotes_pipeline|
|Type:|pipeline|
|Compatibility:|Spark NLP 3.4.1+|
|License:|Open Source|
|Edition:|Official|
|Language:|en|
|Size:|858.4 MB|

## Included Models

- DocumentAssembler
- SentenceDetectorDLModel
- TokenizerModel
- XlmRoBertaForTokenClassification
- NerConverter
- Finisher