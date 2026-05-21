# BAP_processed_data

This repository provides the preprocessed data files used for the experiments in the BAP project.

The source code is not included in this repository. The main code is provided separately. This repository only serves as a download location for the processed data files, because they are too large to include directly in the main code submission.

## Download

The processed data is available as a ZIP file in the GitHub Releases section.

Download the latest release asset:

```text
BAP_processed_data.zip
```

After downloading, extract the ZIP file. The extracted folder should contain:

```text
preprocessed_data/
├── cagliari_data_processed/
├── luzern_data_processed/
└── zurich_data_processed/
```

## Cities

Processed data is provided for:

- Zurich
- Cagliari
- Luzern

The data is already cleaned, split and formatted for the implemented models.

## Repository structure inside the ZIP

Each city folder contains model-specific data:

```text
<city>_data_processed/
├── graphwavenet/
├── megacrn/
├── himnet/
├── stdn/
└── historic_average/
```

## Where to copy the files

Copy the downloaded files into the matching folders of the main `BAP_code` project.

### Graph WaveNet

Copy:

```text
preprocessed_data/<city>_data_processed/graphwavenet/
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

Copy:

```text
preprocessed_data/<city>_data_processed/megacrn/
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

Some city folders may also contain an additional `.parquet` file. Keep it in the same folder when present.

### HimNet

Copy:

```text
preprocessed_data/<city>_data_processed/himnet/
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

Copy:

```text
preprocessed_data/<city>_data_processed/stdn/
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

The Historic Average baseline also needs the final wide flow matrix. Copy the `.parquet` file from:

```text
preprocessed_data/<city>_data_processed/historic_average/
```

to the path expected by the Historic Average script, or update the `raw_file` path in the script.

## Notes

- Destination city folder names in the main project use uppercase names: `ZURICH`, `CAGLIARI`, `LUZERN`.
- Raw UTD19 files are not included.
- Intermediate preprocessing files are not included.
- The files in this repository are only the processed data files needed to train or evaluate the implemented models.
