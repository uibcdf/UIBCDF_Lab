http://docs.anaconda.com/anaconda-cloud/user-guide/tasks/work-with-environments/    

conda env export -n UIBCDF_lab_env -f uibcdf_lab_dev.yml
head -n -1 uibcdf_lab_dev.yml > tmp.yml
mv tmp.yml uibcdf_lab_dev.yml


anaconda login
anaconda upload --user uibcdf uibcdf_lab_dev.yml
anaconda logout

http://envs.anaconda.org/uibcdf

conda env create uibcdf/uibcdf_lab_dev
source activate UIBCDF_lab_dev

conda env update uibcdf/uibcdf_lab_dev
