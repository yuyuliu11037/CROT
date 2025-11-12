### Enviroment
```
conda create -n ot
source activate ot
conda install pytorch==2.4.0 torchvision==0.19.0 torchaudio==2.4.0 pytorch-cuda=12.1 -c pytorch -c nvidia
pip install pot anndata scipy wandb scanpy igraph geomloss[full] argparse cvxpy
```

### Data
```
cd data
pip install gdown
# Download data from https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE194122
gdown https://www.ncbi.nlm.nih.gov/geo/download/?acc=GSE194122&format=file&file=GSE194122%5Fopenproblems%5Fneurips2021%5Fcite%5FBMMC%5Fprocessed%2Eh5ad%2Egz
```

### Run experiment
```
python -m imputationot.citeseq.train --wandb_job aux --wandb_name equal_weighting --use_wandb --use_cluster --weights 0.5,0.5
```
