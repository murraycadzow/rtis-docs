## Dorado

Dorado is a high-performance, easy-to-use, open source basecaller for Oxford Nanopore reads. 
It needs to be run on a partition/node with **GPU compute/CUDA** support, and is heavily-optimised for Nvidia A100 and H100 GPUs.

Dorado is made available on the cluster as a shared [Apptainer]({{apptainer}}) container image.

You can use the `apptainer/dorado` module to add a convenient alias to running `dorado` within the container:

!!! terminal

    ```bash
    module avail dorado
    module load apptainer/dorado/0.7.1
    # The following is required to use aliases in a non-interactive/SLURM batch script:
    shopt -s expand_aliases
    dorado ....
    ```

Alternatively run with apptainer directly; i.e. to run binaries within the container, prefix any 
command with `apptainer -s run --nv <$APPTAINER_IMG/apptainer_image.sif>`. 

Make sure to specify `--nv` to enable NVIDIA GPU support. e.g. 

!!! terminal

    ```bash
    apptainer -s run --nv $APPTAINER_IMG/dorado-<version>.sif dorado basecaller /models/dna_r10.4.1_e8.2_400bps_hac@v4.1.0 ~/pod5s/
    ```

Also note that `-s / --silent` is required here to suppress the verbose container output that may otherwise contaminate standard output.

* To list the available basecaller models, run

!!! terminal

    ```bash
    $APPTAINER_IMG/dorado-<version>.sif ls -1 /models
    ```

As with all Apptainer containers, take care to qualify the files and paths in the context of the 
container image, i.e. Models are located within the container in `/models/`, and any other files 
and data stored outside the container needs to be in a folder that is bound by Apptainer into the 
container (either by default, such as your `$HOME`, `/scratch` or `/projects`), or 
by explicitely specifying a bind mount with Apptainer's `--bind` option). 

Please refer to the dorado GitHub page for more information regarding running dorado.
[https://github.com/nanoporetech/dorado](https://github.com/nanoporetech/dorado)
