---
layout: model
title: Norwegian Bokmål BertForSequenceClassification Large Cased model (from thusken)
author: John Snow Labs
name: bert_classifier_nb_large_user_needs
date: 2022-09-20
tags: [bert, sequence_classification, classification, open_source, nb]
task: Text Classification
language: nb
edition: Spark NLP 4.2.0
spark_version: 3.0
supported: true
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained BertForSequenceClassification model, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP. `nb-bert-large-user-needs` is a Norwegian Bokmål model originally trained by `thusken`.

## Predicted Entities

`need_update`, `need_trend`, `need_perspective`, `need_divert`, `need_inspire`, `need_educate`

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/bert_classifier_nb_large_user_needs_nb_4.2.0_3.0_1663668274042.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python
documentAssembler = DocumentAssembler() \
        .setInputCol("text") \
        .setOutputCol("document")

tokenizer = Tokenizer() \
    .setInputCols("document") \
    .setOutputCol("token")

sequenceClassifier_loaded = BertForSequenceClassification.pretrained("bert_classifier_nb_large_user_needs","nb") \
    .setInputCols(["document", "token"]) \
    .setOutputCol("class")

pipeline = Pipeline(stages=[documentAssembler, tokenizer,sequenceClassifier_loaded])

data = spark.createDataFrame([["PUT YOUR STRING HERE"]]).toDF("text")

result = pipeline.fit(data).transform(data)
```
```scala
val documentAssembler = new DocumentAssembler() 
          .setInputCol("text") 
          .setOutputCol("document")

val tokenizer = new Tokenizer() 
    .setInputCols(Array("document"))
    .setOutputCol("token")

val sequenceClassifier_loaded = BertForSequenceClassification.pretrained("bert_classifier_nb_large_user_needs","nb") 
    .setInputCols(Array("document", "token")) 
    .setOutputCol("class")

val pipeline = new Pipeline().setStages(Array(documentAssembler, tokenizer,sequenceClassifier_loaded))

val data = Seq("PUT YOUR STRING HERE").toDF("text")

val result = pipeline.fit(data).transform(data)
```
</div>

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|bert_classifier_nb_large_user_needs|
|Compatibility:|Spark NLP 4.2.0+|
|License:|Open Source|
|Edition:|Official|
|Input Labels:|[document, token]|
|Output Labels:|[class]|
|Language:|nb|
|Size:|1.3 GB|
|Case sensitive:|true|
|Max sentence length:|256|

## References

- https://huggingface.co/thusken/nb-bert-large-user-needs
- https://www.linkedin.com/pulse/five-lessons-i-learned-while-digitally-changing-bbc-world-shishkin/