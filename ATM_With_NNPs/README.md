# ATM wit NNPs
## Summary
Here you can find the input files used in our study of RBFE with NNPs. We used the inputs from the paper of [Wang _et al_](https://pubs.acs.org/doi/10.1021/ja512751q) and [Schindler _et al_](https://pubs.acs.org/doi/10.1021/acs.jcim.0c00900).

## Installation and Usage
To install the specific version required to be able to run ATM with ANI2x please refer to our [fork with the necessary changes](https://github.com/compsciencelab/AToM-OpenMM)
> [!WARNING]
> Please realize that for NNP calculations the installation of [`opennmm-ml`](https://github.com/openmm/openmm-ml) and [`nnpops`](https://github.com/openmm/NNPOps) is required.
>
> You can install them with:
> ```
> mamba install -c conda-forge openmm-ml
> mamba install -c conda-forge nnpops
>```
## Folder structure
### For every system
```
-complexes: build of each of the complex systems for every ligand pair
```
To run each calculation:
First equilibrate the system:

```
rbfe_structprep.py ligand_pair.cntl
```
And once the system is successfully equilibrated you can run production:

```
rbfe_explicity.py ligand_pair.cntl
```

> [!IMPORTANT]
>If you wish to run that same ligand pair without NNP mode just delete the following line from the `.cntl` file:
> 
>```
> NNP_MODEL = ani2x
>```

> [!NOTE]
> We had to rename the ligands since our tool to prepare them, Parameterize, only accepts 3 character ligand names (otherwise it defaults to MOL). In most cases our convention was:
> ```
> m + 2 last characters of the ligand name:
> Example: 1h1r ⟶ m1r
> ```
> In the file [`Ligand_Renames.csv`](https://github.com/compsciencelab/ATM_benchmark/blob/main/ATM_With_NNPs/Ligand_Renames.csv) you can find the corresponding ligand names to their original ones.
## Citation
[Enhancing Protein-Ligand Binding Affinity Predictions using Neural Network Potentials](https://arxiv.org/abs/2401.16062)
