This repository contains the container in a .sif file based on nvcr.io/hpc/lammps:patch_15Jun2023 NGC container for running LAMMPS on GPU. The container was modified to run on Nvidia RTX 40 series GPU, since the sm89 (Ada Lovelace) architecture is not supported by this container.

The modification procedure was quite simple and you can DIY on a Docker image, by running it on -it mode and going to /usr/local/lammps directory. There you will find 5 directories, each one for a different supported GPU architecture. All you gotta do is mv the "sm86" directory as "sm89". Keep the container running, find its ID with "docker ps" and then "docker commit <modified_container_id> <modified_image_name>". Now you can run your simulations from this image in a RTX 40 series GPU.

You can do the same procedure with Singularity, by building an image with --sandbox mode, modifying the same way as explained above, and the building an image from the directory.

PS: An error might show, but the simulation goes on normally after that.
PS2: I was hoping to upload the .sif image here, but it's too large.

Hope this helps! :D
