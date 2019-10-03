# Mendeley
## Install
```
sudo apt-get install mendeleydesktop
```

## Papers directory
```
cd ~/workspace &&\
mkdir mendeley_papers
```

# Repos

## Gitlab
```
cat ~/.ssh/id_rsa.pub &&\
open https://gitlab.inria.fr/profile/keys
```


## Clone them

```
cd ~/workspace &&\
g clone git@github.com:zaccharieramzi/understanding-unets.git && \
g clone git@github.com:zaccharieramzi/local-machine-setup.git && \
g clone git@github.com:zaccharieramzi/learned_primal_dual.git && \
g clone git@github.com:zaccharieramzi/odl.git && \
g clone git@github.com:zaccharieramzi/ModOpt.git && \
g clone git@github.com:zaccharieramzi/pysap-mri.git && \
g clone git@github.com:zaccharieramzi/pysap.git &&\
g clone git@github.com:zaccharieramzi/fastmri-reproducible-benchmark.git &&\
g clone https://github.com/CEA-COSMIC/pysap-astro.git &&\
g clone git@gitlab.inria.fr:parietal/parietal-wiki.git &&\
g clone git@github.com:zaccharieramzi/thesis-figures.git
```

## Set the original repo
```
cd learned_primal_dual &&\
g remote add upstream https://github.com/adler-j/learned_primal_dual &&\
cd ../odl &&\
g remote add upstream https://github.com/odlgroup/odl &&\
cd ../ModOpt &&\
g remote add upstream https://github.com/CEA-COSMIC/ModOpt &&\
cd ../pysap-mri &&\
g remote add upstream https://github.com/CEA-COSMIC/pysap-mri &&\
cd ../pysap &&\
g remote add upstream https://github.com/CEA-COSMIC/pysap
```

# Environments

## Pysap
```
cd ~/workspace/pysap &&\
mkvenv &&\
cdvenv . &&\
pip install numpy cython pybind11 &&\
export CPLUS_INCLUDE_PATH=/usr/include/python3.6m &&\
sudo apt install -y libnfft3-dev &&\
pip install git+https://github.com/pyNFFT/pyNFFT &&\
pip install -e ../pysap-mri &&\
pip install -e ../pysap-astro &&\
pip install -e ../ModOpt &&\
pip install -e .
```

## Pysap-mri
```
deactivate &&\
cd ~/workspace/pysap-mri &&\
mkvenv &&\
cdvenv . &&\
pip install -e . &&\
pip install numpy cython pybind11 &&\
export CPLUS_INCLUDE_PATH=/usr/include/python3.6m &&\
pip install git+https://github.com/pyNFFT/pyNFFT &&\
pip install -e ../ModOpt &&\
pip install -e ../pysap-astro &&\
pip install -e ../pysap &&\
pip install -r ~/workspace/local-machine-setup/python_science_reqs.txt &&\
jnb_ext &&\
pip install pyqt5
```

## Sparse2d
```
echo '# sparse2d
export PATH=$PATH:$HOME/workspace/pysap/build/temp.linux-x86_64-3.6/extern/bin/' >> ~/.zshrc
```

## ModOpt
```
deactivate &&\
cd ~/workspace/ModOpt &&\
mkvenv &&\
cdvenv . &&\
pip install -e . &&\
pip install astropy
```

## CUDA & affiliates
Taken from: https://www.tensorflow.org/install/gpu (adapt if not ubuntu1604)
```
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/extras/CUPTI/lib64 &&\
sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub &&\
wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_9.1.85-1_amd64.deb &&\
sudo apt install ./cuda-repo-ubuntu1604_9.1.85-1_amd64.deb &&\
wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1604/x86_64/nvidia-machine-learning-repo-ubuntu1604_1.0.0-1_amd64.deb &&\
sudo apt install ./nvidia-machine-learning-repo-ubuntu1604_1.0.0-1_amd64.deb &&\
sudo apt update &&\
sudo mkdir /usr/lib/nvidia &&\
sudo apt-get install --no-install-recommends nvidia-410 &&\
sudo apt install cuda9.0 cuda-cublas-9-0 cuda-cufft-9-0 cuda-curand-9-0 \
    cuda-cusolver-9-0 cuda-cusparse-9-0 libcudnn7=7.2.1.38-1+cuda9.0 \
    libnccl2=2.2.13-1+cuda9.0 cuda-command-line-tools-9-0 &&\
sudo apt update &&\
sudo apt install libnvinfer4=4.1.2-1+cuda9.0 &&\
reboot
```

## Learned Primal Dual
```
deactivate &&\
cd ~/workspace/learned_primal_dual &&\
mkvenv &&\
cdvenv . &&\
pip install -r requirements.txt &&\
sudo apt-get install build-essential libtool autoconf automake libboost-dev &&\
cd ../ &&\
g clone git@github.com:astra-toolbox/astra-toolbox.git &&\
cd astra-toolbox/build/linux &&\
sh autogen.sh &&\
sh configure --with-cuda=/usr/local/cuda \
            --with-python=python \
            --with-install-type=module &&\
make &&\
make install &&\
pip install numpy cython pybind11 &&\
export CPLUS_INCLUDE_PATH=/usr/include/python3.6m &&\
pip install git+https://github.com/pyNFFT/pyNFFT &&\
pip install https://github.com/adler-j/adler/archive/master.zip &&\
jnb_ext
```

## Understanding U-Nets
```
deactivate &&\
cd ~/workspace/understanding-unets &&\
mkvenv &&\
cdvenv . &&\
pip install -r requirements.txt &&\
jnb_ext
```

## Singularity
```
sudo apt-get install libarchive-dev &&\
g clone https://github.com/sylabs/singularity.git &&\
cd singularity &&\
g fetch --all &&\
gco 2.6.1 &&\
sh autogen.sh &&\
sh configure --prefix=/usr/local &&\
make &&\
sudo make install
```


## FastMRI challenge
```
deactivate &&\
cd ~/workspace/fastmri-reproducible-benchmark &&\
mkvenv &&\
cdvenv .&&\
pip install -r ../local-machine-setup/python_science_reqs.txt
```
