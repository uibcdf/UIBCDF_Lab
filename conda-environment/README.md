http://docs.anaconda.com/anaconda-cloud/user-guide/tasks/work-with-environments/    

conda env export -n UIBCDF_lab -f uibcdf_lab.yml
head -n -1 uibcdf_lab.yml > tmp.yml
sed -i '/pyrosetta/d' tmp.yml
mv tmp.yml uibcdf_lab.yml


anaconda login
anaconda upload --user uibcdf uibcdf_lab.yml
anaconda logout

http://envs.anaconda.org/uibcdf

conda env create uibcdf/uibcdf_lab
source activate UIBCDF_lab

conda env update uibcdf/uibcdf_lab
