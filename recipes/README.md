## Using this conda recipe
This conda recipe compiles and installs HipSTR. It is designed to be run by the [bioconda.yml GitHub action workflow](../.github/workflows/bioconda.yml). The workflow will generate relocatable binaries for any commit to main or a PR that targets main. You can download and test any of the binaries by navigating to the Actions tab and scrolling down to the bottom of each summary:

https://github.com/gymrek-lab/HipSTR2/actions/workflows/bioconda.yml

<img width="2264" height="1648" alt="HipSTR2 artifacts" src="https://github.com/user-attachments/assets/0c7a7def-6bcc-4b75-a4b9-a6299cfe3784" />

Please note that these binaries will only work in an environment where the newest version of `htslib` is installed and discoverable through `$LD_LIBRARY_PATH`. To create such an environment with conda, for example, you can execute the following:

```
chmod u+x HipSTR
conda create -y -n htslib -c conda-forge -c bioconda 'htslib'
conda activate htslib
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:${CONDA_PREFIX}/lib"
./HipSTR --help
```
