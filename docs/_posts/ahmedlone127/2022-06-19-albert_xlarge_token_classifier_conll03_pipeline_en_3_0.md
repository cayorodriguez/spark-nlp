---
layout: model
title: ALBERT XLarge CoNNL-03 NER Pipeline
author: John Snow Labs
name: albert_xlarge_token_classifier_conll03_pipeline
date: 2022-06-19
tags: [open_source, ner, token_classifier, albert, conll03, en]
task: Named Entity Recognition
language: en
edition: Spark NLP 4.0.0
spark_version: 3.0
supported: true
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

This pretrained pipeline is built on the top of [albert_xlarge_token_classifier_conll03](https://nlp.johnsnowlabs.com/2021/09/26/albert_xlarge_token_classifier_conll03_en.html) model.

## Predicted Entities



{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/albert_xlarge_token_classifier_conll03_pipeline_en_4.0.0_3.0_1655654378483.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python


pipeline = PretrainedPipeline("albert_xlarge_token_classifier_conll03_pipeline", lang = "en")

pipeline.annotate("My name is John and I work at John Snow Labs.")
```
```scala


val pipeline = new PretrainedPipeline("albert_xlarge_token_classifier_conll03_pipeline", lang = "en")

pipeline.annotate("My name is John and I work at John Snow Labs."))
```
</div>

## Results

```bash


+--------------+---------+
|chunk         |ner_label|
+--------------+---------+
|John          |PER      |
|John Snow Labs|ORG      |
+--------------+---------+
```

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|albert_xlarge_token_classifier_conll03_pipeline|
|Type:|pipeline|
|Compatibility:|Spark NLP 4.0.0+|
|License:|Open Source|
|Edition:|Official|
|Language:|en|
|Size:|206.5 MB|

## Included Models

- DocumentAssembler
- SentenceDetectorDLModel
- TokenizerModel
- AlbertForTokenClassification
- NerConverter
- Finisher