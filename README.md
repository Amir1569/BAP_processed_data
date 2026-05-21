# BAP_processed_data
This repository contains the preprocessed data of the cities Zurich, Cagliari and Luzern of the UTD19 dataset. The preprocessed data can be used to train multiple models (LSTM, MegaCRN, Graph Wavenet, STDN and HimNet).

The source code is not included in this repository. This repository only contains the processed data files that are too large to include directly in the main code submission.

## Cities

The processed data is provided for three cities:

- Zurich
- Cagliari
- Luzern

Each city folder contains the data required by each model.

```text
preprocessed_data/
├── cagliari_data_processed/
├── luzern_data_processed/
└── zurich_data_processed/

These files are needed to train or evaluate the implemented models:
Historic Average, LSTM, Graph WaveNet, MegaCRN, HimNet and STDN.

## Repository structure

```text
preprocessed_data/
├── cagliari_data_processed/
│   ├── graphwavenet/
│   ├── megacrn/
│   ├── himnet/
│   ├── stdn/
│   └── historic_average/
├── luzern_data_processed/
│   ├── graphwavenet/
│   ├── megacrn/
│   ├── himnet/
│   ├── stdn/
│   └── historic_average/
└── zurich_data_processed/
    ├── graphwavenet/
    ├── megacrn/
    ├── himnet/
    ├── stdn/
    └── historic_average/
```

## Where to copy the files

After downloading this repository, copy the files into the matching folders of the main `BAP_code` project.

### Graph WaveNet

Copy the files from:

```text
<city>_data_processed/graphwavenet/
```

to:

```text
BAP_code/implementation_models/graphwavenet/Graph-WaveNet-master/data/<CITY>/
```

Expected files:

```text
train.npz
val.npz
test.npz
adj_mx.pkl
```

### MegaCRN

Copy the files from:

```text
<city>_data_processed/megacrn/
```

to:

```text
BAP_code/implementation_models/MegaCRN/MegaCRN-main/<CITY>/
```

Expected files:

```text
train.npz
val.npz
test.npz
```

If a city folder also contains a `.parquet` file, keep it in the same folder.

### HimNet

Copy the files from:

```text
<city>_data_processed/himnet/
```

to:

```text
BAP_code/implementation_models/HimNet/HimNet-main/data/<CITY>/
```

Expected files:

```text
data.npz
index.npz
```

### STDN

Copy the files from:

```text
<city>_data_processed/stdn/
```

to:

```text
BAP_code/implementation_models/STDN/STDN-main/STDN-main/data/<CITY>/
```

Expected files:

```text
<CITY>.npz
<CITY>_adj.npy
samples_12_12_3.npz
```

### Historic Average and LSTM

The LSTM baseline uses the same `train.npz`, `val.npz` and `test.npz` files as Graph WaveNet.

The Historic Average baseline also needs the final wide flow matrix. Copy the file from:

```text
<city>_data_processed/historic_average/
```

to the path expected by the script, or update the `raw_file` path in:

```text
BAP_code/implementation_models/historic_average/run_historic_average.py
```

## Notes

- City folder names in the main code are uppercase: `ZURICH`, `CAGLIARI`, `LUZERN`.
- The data is already cleaned, split and formatted for the models.
- Raw UTD19 files are not included here.
- Intermediate preprocessing files are not included to keep the repository smaller.
