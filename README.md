# Pedalion Role Labeler
A semantic role labeler for Ancient Greek. The role set is the one used by the [Pedalion project](http://en.pedalion.org/). Subjects, accusative objects and clauses are currently not labeled. Accuracy is estimated to be about 75.7%, with large genre differences (lyric and epic poetic texts perform particularly badly).

## Requirements
* [R](https://www.r-project.org/), with package randomForest installed
* [Java Runtime Environment](https://www.java.com/nl/download/)

## Usage

### Step 1: extracting an unlabeled dataset from an AGDT-style treebank
```
cd PRL
java -jar DataProcessor.jar export [XML_OR_DIRECTORY]
```
### Step 2: labeling the dataset
```
RScript PRL.R output.txt
```
### Step 3: importing the labeled dataset back in the XML
```
java -jar DataProcessor.jar import pred_srl.txt [INPUT_XML_OR_DIRECTORY] [OUTPUT_XML_OR_DIRECTORY]
```
### Step 4: annotating the XML with Arethusa
* Set format to "pedalion" in the output xml in \<treebank\>.
* Import the XML in [Arethusa](http://sites.tufts.edu/perseids/instructions/treebanking-instructions/).

## Credits

The labeler has been trained on semantically annotated data from the following sources:
* The [Ancient Greek Dependency Treebanks](https://github.com/PerseusDL/treebank_data), managed by Giuseppe G. A. Celano, Gregory Crane, Bridget Almas and others.
* [Aphthonius' Progymnasmata](https://github.com/polinayordanova/Treebank-of-Aphtonius-Progymnasmata), annotated by Polina Yordanova.
* The [Digital Marmor Parium](http://digitalmarmorparium.org/linguistics.html), annotated by Giuseppe G. A. Celano.
* The [Harrington Trees](https://github.com/perseids-project/harrington_trees), managed by J. M. Harrington.
* The [Pedalion Treebanks](https://github.com/perseids-publications/pedalion-trees/), managed by Toon Van Hal and Alek Keersmaekers. 

It also includes a semantic lexicon partly based on data from the [PROIEL project](https://github.com/proiel/proiel-treebank), managed by Dag Haug and Marius Jøhndal.

## How to cite
This data is available under a [CC BY-NC-SA 4.0 License](https://creativecommons.org/licenses/by-nc-sa/4.0/). Please refer to the following paper when using the labeler or any of the data included:

*(to be added)*
