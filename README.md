# SDSP Task2 Reproducible Research - MemStream
This repo is about Task 2 of PUCRS course: Scalable Data Stream Processing. In this task, we should apply some of the methods that we learn or we can reproduce a research. I chose to reproduce the MemStream method for Anomaly Detection in Data Streams with anomalies and concept drift. The links to the original paper and the authors repository are below (with MemStream implementation and datasets that were used):

* Original Paper: https://dl.acm.org/doi/pdf/10.1145/3485447.3512221
* MemStream Repo: https://github.com/Stream-AD/MemStream?tab=readme-ov-file

## Conda ENV
```
conda create --name data_env python==3.8.0
conda activate data_stream
pip install -r requirements.txt
```

## Scripts

* `script_table2.ipynb`: notebook to run the different methods in all datasets that reproduce Table 2 of the paper.
* `script_table3.ipynb`: notebook to run the different methods in all datasets that reproduce Table 3 of the paper.
* `script_table4.ipynb`: notebook to run the different methods in all datasets that reproduce Table 4 of the paper.


## Results

* **Table 2**: MemStream outperforms the different streaming methods for most of the datasets tested. However, the value of AUC-ROC reproduced for Mammography dataset was lower than the value computed on the original paper. Also, there were discrepancies for all other methods tested (except LODA).
* **Table 3**: Similar to Table 2, the value of AUC-PR has discrepancies for most methods tested. Also, MemStream outperforms including on the computation time. Also, it is notable the difference on time for iForestASD that this reproduction was way faster than the time reported on the original paper.
* **Table 4**: Increasing the memory size of MemStream for the NSL-Dataset has a tendency to improve the values of AUC-ROC. The reproduced values were very close to the ones computed on the original paper. Also, the new memory length tested, 2³, had a very good value of AUC-ROC. 


## Conclusion
* The paper’s conclusion that MemStream outperforms most methods was reproduced and confirmed by this work.
* It was not possible to reproduce the exact values reported:
    * The repository available for MemStream has the `SEED` used for the experiments, but it didn’t match the values of all the methods used.
    * Also, there isn’t a repository of all the experiments for all the methods tested. 
* Using a sample of data can be an option to approximate the real metric value for all data, including the possibility to run the experiment for methods that couldn’t support the size of the dataset (e.g.: LODA with dataset UNSW).
