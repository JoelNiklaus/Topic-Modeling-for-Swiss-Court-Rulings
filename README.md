# Topic modeling of Swiss Court Rulings
### Research Center for Digital Sustainability (RCDS)
--

Renato Rao, Marius Asadauskas, Dominik Ummel


When performing various analysis on Court Rulings the vast amount of available data makes the analysis rather complex and time consuming. Therefore the goal of the project was to perform topic modeling over a multilingual dataset of Swiss Court Rulings to group the Rulings into meaningful topics, so that analysis can be done on these groupings.

This repository contains the colab notebook to traing the topic models. Furthermore, it contains the resulting visualizations and evaluations.

## Dataset generation

The dataset sizes are approximately:
- Germam: 5GB
- French: 3GB
- Italian: .5GB

To generate the dataset on the sandbox (kindly provided by RCDS) run:

```
psql -d scrc -U readonly  -c "\copy de(id,court,language,title,header,text,html_url,date) TO 'train_de.csv' DELIMITER ';' CSV HEADER;"
```
```
psql -d scrc -U readonly  -c "\copy fr(id,court,language,title,header,text,html_url,date) TO 'train_fr.csv' DELIMITER ';' CSV HEADER;"
```
```
psql -d scrc -U readonly  -c "\copy it(id,court,language,title,header,text,html_url,date) TO 'train_it.csv' DELIMITER ';' CSV HEADER;"
```

**Important: Characters such as `ü` are stored as `u + ¨` and not `ü`, so the dataset needs to be normalized**


## Colab Notebook
For an interactive session in the browser the jupyter notebook can be seen here:

https://drive.google.com/file/d/1pLeBaMzvvfXjjnsjTtw_sPvdpUWzIQkl/view?usp=sharing

## Model download

The trained BERTopic model (~3GB) can be downloaded here:
https://drive.google.com/file/d/1fSAjlctonmHIN37iL0vFcesZc5MMQTt_/view?usp=sharing

