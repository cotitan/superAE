## Citation
If you use this code for your research, please cite the paper this code is based on:
*Autoencoder as Assistant Supervisor: Improving Text Representation for Chinese Social Media Text Summarization*:

```
@inproceedings{Ma2016superAE,
  title   = {Autoencoder as Assistant Supervisor: Improving Text Representation for Chinese Social Media Text Summarization},
  author  = {Shuming Ma and Xu Sun and Junyang Lin and Houfeng Wang},
  booktitle = {{ACL} 2018},
  year      = {2018}
}
```

## Requirements
* python3.5
* pytorch=0.3.1

## Data Preprocessing
lcsts: If you've got this dataset in xml format, 
1. first extract the source content and summary, save as *.src and *.tgt respectively.
2. run preprocess.py at root dir to preprocess the data, refer to following script:
  ```
  python preprocess.py -train_src data/lcsts/PART_I.src -train_tgt data/lcsts/PART_I.tgt -valid_src data/lcsts/PART_II.src -valid_tgt data/lcsts/PART_II.tgt -save_data data/lcsts/lcsts.low.share
  ```

## Training config
in _lcsts.yaml_, remember to modify _data_ field

## Train
```
CUDA_VISIBLE_DEVICES=0 python train.py -config lcsts.yaml
```
1. You're supposed to run this script in a command line instead of any IDE.
2. _CUDA_VISIBLE_DEVICES_ if optional, remove this to use cpu.
