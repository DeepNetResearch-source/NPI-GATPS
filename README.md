# NPI-GATPS
Code for our paper on ncRNA-protein interaction prediction using personalized subgraph selection
# NPI-GATPS: Personalized Subgraph Selection for ncRNA–Protein Interaction Prediction

This repository contains a implementation of the model described in our paper:

**Predicting ncRNA-protein interactions with a graph attention model exploiting personalized subgraphs**

## **Requirements**
Before running the code, make sure you have the following installed:

- Python 3.8+
- PyTorch 
- torch-geometric
- NumPy
- Pandas
- scipy
- scikit-learn
- torch-cluster
- torch-scatter
- torch-sparse
- NetworkX
- tqdm

## Dataset

We use five publicly available datasets:
- NPInter2.0
- RPI7317
- NPInter2.0 lncRNA
- RPI2241
- RPI369

## To preprocess the data:

```
python ./code/data_preprocessing/src/generate_edgelist.py --projectName yourProjectName --interactionDatasetName NPInter2 --createBalanceDataset 0

python ./code/data_preprocessing/node2vec-master/src/main.py --input './code/data_preprocessing/data/graph/yourProjectName/bipartite_graph.edgelist' --output './code/data_preprocessing/data/node2vec_result/yourProjectName/training_0/result.emb'

python ./code/data_preprocessing/src/generate_dataset.py --projectName yourProjectName --interactionDatasetName NPInter2 --fold 0 --noKmer 0 --createBalanceDataset 0

```


## Run the Model

To train the model:

```
python ./code/ps2.py --dataset "NPInter2"

```
