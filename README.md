# My DVC Repository

This repository uses [Data Version Control (DVC)](https://dvc.org/) to track and version large datasets. The actual data is stored in a Google Cloud Storage (GCS) bucket.

## Prerequisites

- [DVC](https://dvc.org/doc/install)
- [Google Cloud SDK](https://cloud.google.com/sdk/docs/install)

## Setup

1. Clone this repository:

```bash
git clone https://github.com/visanth-oxd/dvc-repo.git
cd dvc-repo
dvc pull

```

## Versioning Data with DVC

DVC tracks changes in data in a way that's similar to how Git tracks changes in code. When you modify a dataset that's tracked by DVC and run `dvc add` for that dataset, DVC calculates a new checksum for the dataset. This checksum is stored in the corresponding `.dvc` file.

When you commit the changes to the `.dvc` file with Git and push it to your repository, you're effectively creating a new version of your data. Other people can then use `dvc checkout` to retrieve the version of the data that matches the current Git branch.

To create a new version of a dataset, follow these steps:

1. Modify your dataset.
2. Run `dvc add your-dataset` to track the changes.
3. Run `git add your-dataset.dvc` to stage the changes.
4. Run `git commit -m "Update dataset"` to commit the new version.
5. Run `dvc push` to upload the new version of the data to the DVC remote.

Remember to replace `your-dataset` with the actual name of your dataset.