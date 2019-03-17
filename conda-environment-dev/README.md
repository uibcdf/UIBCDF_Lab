# Exporting 

The list of packages is saved in a file.
We remove those packages installed manually.

```bash
conda env export -n UIBCDF_lab_dev -f uibcdf_lab_dev.yml
head -n -1 uibcdf_lab_dev.yml > tmp.yml
sed -i '/pyrosetta/d' tmp.yml
mv tmp.yml uibcdf_lab_dev.yml
```

The list is uploaded to anaconda

```bash
anaconda login
anaconda upload --user uibcdf uibcdf_lab_dev.yml
anaconda logout
```

# Creating or updating the environment.

The environments can be checked in the [UIBCDF conda channel](http://envs.anaconda.org/uibcdf).

## Create the UIBCDF_lab_dev env.

```bash
conda env create uibcdf/uibcdf_lab_dev
source activate UIBCDF_lab_dev
```

## Update the UIBCDF_lab_dev env.

```bash
conda env update uibcdf/uibcdf_lab_dev
```

