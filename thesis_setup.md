# Repos
## Clonte them

```shell
g clone git@github.com:zaccharieramzi/understanding-unets.git && \
g clone git@github.com:zaccharieramzi/local-machine-setup.git && \
g clone git@github.com:zaccharieramzi/learned_primal_dual.git && \
g clone git@github.com:zaccharieramzi/odl.git && \
g clone git@github.com:zaccharieramzi/ModOpt.git && \
g clone git@github.com:zaccharieramzi/pysap-mri.git && \
g clone git@github.com:zaccharieramzi/pysap.git
```

## Set the original repo
```shell
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
