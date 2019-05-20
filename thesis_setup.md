# Repos
## Clone them

```
g clone git@github.com:zaccharieramzi/understanding-unets.git && \
g clone git@github.com:zaccharieramzi/local-machine-setup.git && \
g clone git@github.com:zaccharieramzi/learned_primal_dual.git && \
g clone git@github.com:zaccharieramzi/odl.git && \
g clone git@github.com:zaccharieramzi/ModOpt.git && \
g clone git@github.com:zaccharieramzi/pysap-mri.git && \
g clone git@github.com:zaccharieramzi/pysap.git &&\
g clone https://github.com/CEA-COSMIC/pysap-astro.git
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
pip install -r ~/workspace/local-machine-setup/python_science_reqs.txt
```

## Sparse2d
```
echo '# sparse2d
export PATH=$PATH:$HOME/workspace/pysap/build/' >> ~/.zshrc
```

## Learned Primal Dual
```
deactivate &&\
cd ~/workspace/learned_primal_dual &&\
mkvenv &&\
cdvenv . &&\
pip install -e . &&\
```
