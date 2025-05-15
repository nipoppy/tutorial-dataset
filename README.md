# Nipoppy Tutorial Dataset

This dataset was created to serve as an example dataset for the [Nipoppy tutorials](). 

## Download data

Besides cloning this repo, you can download the data

**via the browser:** Click on the green button "Code" on the right upper corner in this repo and select "Download Zip"

or 

**via the command line:**
```
wget -O tutorial-dataset.zip https://github.com/nipoppy/tutorial-datset/archive/refs/heads/main.zip
```

Unzip once downloaded. 

## Using the data

Following the Nipoppy tutorials, the data is used for different steps in the Nipoppy framework. Commands assume the Nipoppy dataset is called `my-example-study` as instructed in the Nipoppy tutorials. Instructions are given in the order they will appear in the Nipoppy tutorial series. 

### ./manifest.tsv

During the `nipoppy init` tutorial we will create this `manifest.tsv` file. Should you not watch this tutorial or run in any errors related to the `manifest.tsv`, you can use this one. 

### ./reorg

- intented for: [`nipoppy reorg` tutorial]() 
- steps:
    
    1. move the **content** of the `tutorial-dataset/reorg` directory to the `sourcedata/imaging/pre_reorg` directory of your Nipoppy dataset, i.e.: 

    ``` 
    mv tutorial-dataset/reorg/* my-example-study/sourcedata/imaging/pre_reorg
    ``` 
    
    Do this while watching the `nipoppy reorg` video and you are instructed to do so in the tutorial. 

**Note:** Data of one subject was copied in order to create multiple subjects with different modalities for training purposes. Hence, all data stems from one subject. 

### ./bidsify

- intended for: [`nipoppy bidsify` tutorial]()
- steps:

    1. move the `dcm2bids_config.json` to the `code` directory of your Nipoppy dataset, i.e.:


    ```
    mv tutorial-dataset/bidsify/dcm2bids_config.json my-example-study/code
    ```

    2. move the `participants.tsv` as well as the `dataset_description.json` to the `bids` directory of your Nipoppy dataset, i.e.: 

    ``` 
    mv -t my-example-study/bids tutorial-dataset/bidsify/participants.tsv tutorial-dataset/bidsify/dataset_description.json
    ```

### ./process

- intended for: [`nipoppy process` tutorial](), only necessary for users who didn't follow the previous tutorials and want to start with a BIDS dataset. 
- steps: 

    1. move the **content** of `tutorial-dataset/process` to the `bids` directory of your Nipoppy dataset, i.e.:

    ```
    mv tutorial-dataset/process/* my-example-study/bids
    ```

    2. (If you haven't done so for the previous tutorial) move the `participants.tsv` as well as the `dataset_description.json` to the `bids` directory of your Nipoppy dataset, i.e.: 

    ``` 
    mv -t my-example-study/bids tutorial-dataset/process/participants.tsv tutorial-dataset/process/dataset_description.json
    ```

**Note:** `participants.tsv` contains made-up phenotypic data. 

### ./extract

- intended for: [`nipoppy extract` tutorial]()
- steps:

    1. move the **content** of the `tutorial-dataset/extract` directory to the `derivatives` directory of your Nipoppy dataset, i.e.:

    ```
    mv tutorial-dataset/extract/* my-example-study/derivatives
    ```

**Note:** We removed some of the freesurfer output to scale down the size of the repository. Files that are needed for `nipoppy track-processing` and running the `fs_stats` pipeline are still present.

## Acknowledgements

Data is a phantom dataset generated at the University of Arizona on our Siemens Skyra 3T with Syngo MR VE11c software on 2018_02_08. It was retrieved from https://datasets.datalad.org/repronim/heudiconv-tutorial-example/. 

We thank the [Heudiconv Team](https://github.com/nipy/heudiconv) and [Dianne Patterson](https://neuroimaging-core-docs.readthedocs.io/en/latest/pages/heudiconv.html#lesson-3-reproin-py) for making this data available.  