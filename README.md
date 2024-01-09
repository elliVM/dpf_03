# DPF_03

Holds a customized lexical tokenizer as a Spark UDF and a bloom filter aggregator.
Used to tokenize spark string columns and to aggregate columns into a bloom filter with configurable filter size selection.

## Features

### TokenizerUDF

Spark UDF that will tokenize incoming string value and returns it as a list of byte arrays.
Tokenization rules are set in blf_01.

### ByteArrayListAsStringListUDF

Spark UDF that converts results from TokenizerUDF into a list of strings.

### BloomFilterAggregator

Custom spark aggregator that aggregates a column string tokens into a single bloom filter and
returns the bytes of the resulting filter that can be processed.

Filter size is selected by giving the aggregator a name of a spark colum that holds an estimated value of tokens and a map 
with a configuration values used by the spark bloom filter implementation (expected number of items, false positive probability).


## Documentation

See the official documentation on https://docs.teragrep.com[docs.teragrep.com].

## Limitations

Compatible with Java version 1.8 other versions might not work

## How to [compile/use/implement]

See tests for how to apply and import into a spark project

## Contributing

You can involve yourself with our project by https://github.com/teragrep/dpf_03/issues/new/choose[opening an issue] or submitting a pull request. 

Contribution requirements:

. *All changes must be accompanied by a new or changed test.* If you think testing is not required in your pull request, include a sufficient explanation as why you think so.
. Security checks must pass
. Pull requests must align with the principles and http://www.extremeprogramming.org/values.html[values] of extreme programming.
. Pull requests must follow the principles of Object Thinking and Elegant Objects (EO).

Read more in our https://github.com/teragrep/teragrep/blob/main/contributing.adoc[Contributing Guideline].

### Contributor License Agreement

Contributors must sign https://github.com/teragrep/teragrep/blob/main/cla.adoc[Teragrep Contributor License Agreement] before a pull request is accepted to organization's repositories. 

You need to submit the CLA only once. After submitting the CLA you can contribute to all Teragrep's repositories. 
