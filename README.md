# color-ner

This is a  spaCy NER model for recognizing color entities in text fragments coming from
external resources. The model is trained on the [color_train.jsonl](assets/color_train.jsonl) 
dataset, and tested on the [color_dev.jsonl](assets/color_dev.jsonl) dataset, using 
the [spaCy](https://spacy.io/) library.

The goal of the model is to recognize color entities in text fragments, and assign them
the **COLOR** label. Note: it will recognize *all* color entities in the text fragment, e.g. 
consider the following text fragment:

```bash
"dark bluish red with tins of purple and brown"
```

The model will recognize the following entities:
```bash
"dark bluish red" -> "COLOR"
"purple" -> "COLOR"
"brown" -> "COLOR"
```

The model is deployed to **HuggingFace** model hub, and can be found [here](https://huggingface.co/liubomyrgavryliv/en_colorExtractor).
You can play with it there and test it on your own text fragments.

## Installation

To install the model, run the following command:
```bash
pip install https://huggingface.co/liubomyrgavryliv/en_colorExtractor/resolve/main/en_colorExtractor-any-py3-none-any.whl
```

## Usage

To use the model, run the following command:
```python
# Using spacy.load().
import spacy
nlp = spacy.load("en_colorExtractor")

# Importing as module.
import en_colorExtractor
nlp = en_colorExtractor.load()
```

## Commands

The model is built using the [spaCy](https://spacy.io/) project and config system.
The following commands are available in [project.yml](project.yml) file:
- preprocess 
  - Prepare jsonl train and dev data from raw data and save to spacy format in the [assets](assets) folder
- train
  - train the model and save it to the [training](training) folder
- evaluate
  - evaluate the model on the dev data and save metrics to the [metrics](metrics) folder
- package
  - package the model and save it to the [package](package) folder
- deploy
  - deploy the model to the HuggingFace model hub
- clean
  - clean the project from all the generated files


## Support

This project No. 3007/01/01 has received funding from the European Union´s Horizon 2020 research and innovation programme under the Marie Skłodowska-Curie grant agreement No. 945478.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.