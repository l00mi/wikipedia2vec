Wikipedia2Vec
=============

[![Fury badge](https://badge.fury.io/py/wikipedia2vec.png)](http://badge.fury.io/py/wikipedia2vec)
[![CircleCI](https://circleci.com/gh/wikipedia2vec/wikipedia2vec.svg?style=svg)](https://circleci.com/gh/wikipedia2vec/wikipedia2vec)

Wikipedia2Vec is a tool used for obtaining embeddings (or vector representations) of words and entities (i.e., concepts that have corresponding pages in Wikipedia) from Wikipedia.
It is developed and maintained by [Studio Ousia](http://www.ousia.jp).

This tool enables you to learn embeddings of words and entities simultaneously, and places similar words and entities close to one another in a continuous vector space.
Embeddings can be easily trained by a single command with a publicly available Wikipedia dump as input.

This tool implements the [conventional skip-gram model](https://en.wikipedia.org/wiki/Word2vec) to learn the embeddings of words, and its extension proposed in [Yamada et al. (2016)](https://arxiv.org/abs/1601.01343) to learn the embeddings of entities.
This tool has been used in several important applications including entity linking ([Yamada et al., 2016](https://arxiv.org/abs/1601.01343), [Eshel et al., 2017](https://arxiv.org/abs/1706.09147)), named entity recognition ([Sato et al., 2017](http://www.aclweb.org/anthology/I17-2017), [Lara-Clares and Garcia-Serrano, 2019](http://ceur-ws.org/Vol-2421/eHealth-KD_paper_6.pdf)), text classification ([Yamada et al., 2019](https://arxiv.org/abs/1909.01259)), paraphrase detection ([Duong et al., 2018](https://ieeexplore.ieee.org/abstract/document/8606845)), knowledge graph completion ([Shah et al., 2019](https://aaai.org/ojs/index.php/AAAI/article/view/4162)), plot analysis of movies ([Papalampidi et al., 2019](https://arxiv.org/abs/1908.10328)), and question answering ([Yamada et al., 2017](https://arxiv.org/abs/1803.08652)).

This tool has been tested on Linux, Windows, and macOS.

An empirical comparison between Wikipedia2Vec and existing embedding tools (i.e., FastText, Gensim, RDF2Vec, and Wiki2vec) is available [here](https://arxiv.org/abs/1812.06280).

The source code of the neural text classification model built upon Wikipedia2Vec is available [here](https://github.com/wikipedia2vec/wikipedia2vec/tree/master/examples/text_classification).

Documentation and pretrained embeddings for 12 languages (English, Arabic, Chinese, Dutch, French, German, Italian, Japanese, Polish, Portuguese, Russian, and Spanish) are available online at [http://wikipedia2vec.github.io/](http://wikipedia2vec.github.io/).

Basic Usage
-----------

Wikipedia2Vec can be installed via PyPI:

```bash
% pip install wikipedia2vec
```

With this tool, embeddings can be learned by running a *train* command with a Wikipedia dump as input.
For example, the following commands download the latest English Wikipedia dump and learn embeddings from this dump:

```bash
% wget https://dumps.wikimedia.org/enwiki/latest/enwiki-latest-pages-articles.xml.bz2
% wikipedia2vec train enwiki-latest-pages-articles.xml.bz2 MODEL_FILE
```

Then, the learned embeddings are written to *MODEL\_FILE*.
Note that this command can take many optional parameters.
Please refer to [our documentation](https://wikipedia2vec.github.io/wikipedia2vec/commands/) for further details.

References
----------

If you use Wikipedia2Vec in a scientific publication, please cite the following paper:

Ikuya Yamada, Akari Asai, Hiroyuki Shindo, Hideaki Takeda, Yoshiyasu Takefuji, [Wikipedia2Vec: An Optimized Tool for Learning Embeddings of Words and Entities from Wikipedia](https://arxiv.org/abs/1812.06280).

```bibtex
@article{yamada2018wikipedia2vec,
  title={Wikipedia2Vec: An Optimized Tool for Learning Embeddings of Words and Entities from Wikipedia},
  author={Yamada, Ikuya and Asai, Akari and Shindo, Hiroyuki and Takeda, Hideaki and Takefuji, Yoshiyasu},
  journal={arXiv preprint 1812.06280},
  year={2018}
}
```

Wikipedia2Vec is an official implementation of the embedding model proposed in the following paper:

Ikuya Yamada, Hiroyuki Shindo, Hideaki Takeda, Yoshiyasu Takefuji, [Joint Learning of the Embedding of Words and Entities for Named Entity Disambiguation](https://arxiv.org/abs/1601.01343).

```bibtex
@inproceedings{yamada2016joint,
  title={Joint Learning of the Embedding of Words and Entities for Named Entity Disambiguation},
  author={Yamada, Ikuya and Shindo, Hiroyuki and Takeda, Hideaki and Takefuji, Yoshiyasu},
  booktitle={Proceedings of The 20th SIGNLL Conference on Computational Natural Language Learning},
  year={2016},
  publisher={Association for Computational Linguistics},
  doi={10.18653/v1/K16-1025},
  pages={250--259}
}
```

The text classification model implemented in [this example](https://github.com/wikipedia2vec/wikipedia2vec/tree/master/examples/text_classification) was proposed in the following paper:

Ikuya Yamada, Hiroyuki Shindo, [Neural Attentive Bag-of-Entities Model for Text Classification](https://arxiv.org/abs/1909.01259).

```bibtex
@article{yamada2019neural,
  title={Neural Attentive Bag-of-Entities Model for Text Classification},
  author={Yamada, Ikuya and Shindo, Hiroyuki},
  booktitle={Proceedings of The 23th SIGNLL Conference on Computational Natural Language Learning},
  year={2019},
  publisher={Association for Computational Linguistics}
}
```

License
-------

[Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)
