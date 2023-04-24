# Decoupled-Unbiased-Teacher


#### Installation 

Please check [INSTALL.md](INSTALL.md) for installation instructions.

#### Data Preparation

1. Download datasets from the following sources:

    Source Domain:
    [CVC-ClinicDB](https://polyp.grand-challenge.org/CVCClinicDB/)
    Target Domain:
    [Abnormal Symptoms](https://endoscopy.selab.hcmus.edu.vn/)

2. To use our preprocessed data, please refer to [Source data Google Drive](https://drive.google.com/drive/folders/1A3HEVZjWEtR3h7_SPwixDfP9oz43POhc?usp=share_link) and [Target data Google Drive](https://drive.google.com/file/d/1NQC-xc7GB-mp9Zhq6lwH9kid4_NtPImF/view?usp=sharing)

3. Change the dataset dir in [here](fcos_core/config/paths_catalog.py).

#### Training

The following command line controls different stages of training:

```bash
# Stage 1: Train the source only model
python tools/train_net_mcd.py --config-file configs/sf/source_only.yaml SOLVER.SFDA_STAGE 1

# Stage 2: Train the model with DUT on Abnormal Symptoms dataset
python tools/train_net_mcd.py --config ./configs/sf/dut_hcmus.yaml OUTPUT_DIR outputs/dut_hcmus
```

#### Acknowledgement

The code is based on [FCOS](https://github.com/tianzhi0549/FCOS). For enquiries please contact 1155195604@link.cuhk.edu.hk.
