# Matlab installation with a UNIGE account

## Introduction:
The procedure detailled to install Matlab with a UNIGE licence misses some details which lead to a cumbersome installation. This repo provides a step-by-step installation procedure.

## Downloading the `.iso` file, the licence number, the `installer_input_unige.txt` and the `matlablm_unige.dat` files:
- Download the `.iso` file [here](https://plone.unige.ch/distic/pub/logiciels/matlab/comment-installer-matlab-sur-linux).
- Request a licence number and download the `installer_input_unige.txt` and the `matlablm_unige.dat` [here](https://logiciels.unige.ch/).

## Mount the `.iso` file and copy paste content to another directory:
- Mount the `.iso` file.
- Copy the content to a new file using `rsync`. 

## Modify the `installer_input_unige.txt`:
- Change the `destinationFolder` to
```bash
destinationFolder=/usr/local/MATLAB/R2021b
```
- Specify the correct licence number in the `installer_input_unige.txt` file to:
```bash
fileInstallationKey= your_licence_number
```
- Change the `outputFile` to:
```bash
outputFile=/tmp/mathworks_R2021b.log
```
- Specify the correct `licencePath`:
```bash
licensePath=./matlablm_unige.dat
```
- Comment out all unecessary toolboxes with `#`.

## Run the installation and check installation `log` file:
```bash
 sudo ./install -inputfile ./installer_input_unige.txt
```

## Create an alias to launch Matlab:
in your `.bashrc` or `.zshrc`, add the following alias:

```bash
alias matlab="/usr/local/MATLAB/R2021b/bin/matlab"
```

## Launch Matlab:
Launch Matlab with:
```bash
matlab
```

## Useful commands:
- `xhost +SI:localuser:root` enables modification of the folder
- `rsync -av old_folder new_folder`






