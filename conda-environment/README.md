# Exporting 

The list of packages is saved in a file.
We remove those packages installed manually.

```bash
conda env export -n UIBCDF_lab -f uibcdf_lab.yml
sed -i '/prefix/d' uibcdf_lab.yml
sed -i '/pyrosetta/d' uibcdf_lab.yml
mv tmp.yml uibcdf_lab.yml
```

The list is uploaded to anaconda

```bash
anaconda login
anaconda upload --user uibcdf uibcdf_lab.yml
anaconda logout
```

# Creating or updating the environment.

The environments can be checked in the [UIBCDF conda channel](http://envs.anaconda.org/uibcdf).

## Create the UIBCDF_lab env.

```bash
conda env create uibcdf/uibcdf_lab
source activate UIBCDF_lab
```

## Update the UIBCDF_lab env.

```bash
conda env update uibcdf/uibcdf_lab
```

