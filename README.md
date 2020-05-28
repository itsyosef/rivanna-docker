# rivanna-docker

**Autogenerated - do not edit manually!**  
Run `writeREADME.sh` to update this `README.md`.

This repository contains Dockerfiles for Rivanna.

## Structure

Each Dockerfile should reside in its own directory with a `README.md` of the form:
```
<name and version of main app>
<homepage of main app>
<usage>
```

The first line is reproduced under \"List of Docker images\" in the main `README.md` on GitHub.

Individual `README.md` files are used as the Docker Hub repository description.

Note: We may need to structure this repo as `/app/version/Dockerfile` later.

## Instructions for Contribution

1. Install the following utilities if not on our machine:
    * `docker`
    * `docker-pushrm` - add-on to push `README.md`  
    https://github.com/christian-korneck/docker-pushrm
    * `git`
1. Clone this repository
1. Build and test
    1. Prepare a `Dockerfile`
    1. Build with explicit tag (do not use `latest`): `docker build -t uvarc/<app>:<tag>`  
       Use the app version (and suffix if needed) as the tag
    1. Test locally (or on Rivanna - see below)
1. Write `README.md` for the app
1. Deploy
    1. Login to Docker Hub: `docker login`
    1. Push image to Docker Hub: `docker push uvarc/<app>:<tag>`
    1. Push `README.md` to Docker Hub (in subdirectory): `docker pushrm uvarc/<app>`
    1. Push to GitHub: `git add . && git commit -m "your message" && git push`
    1. Remember to logout: `docker logout`
1. Run on Rivanna
    1. `module load singularity`
    1. `singularity pull docker://uvarc/<app>:<tag>`
    1. To run the default command specified in `ENTRYPOINT`:  
       `./<app>_<tag>.sif`  
       Otherwise:  
       `singularity exec <app>_<tag>.sif <command>` or  
       `singularity shell <app>_<tag>.sif`

## List of Docker images

(Link to Docker Hub repository)

|App|Short Description|Compressed Size|Last Updated (UTC)|By|
|---|---|---:|---|---|
| [hydrator](https://hub.docker.com/r/uvarc/hydrator) | Hydrator 0.0.10 | 178.869 MB | 2020-05-28 22:30:50.776306 | rsdmse |
| [inkscape](https://hub.docker.com/r/uvarc/inkscape) | Inkscape 0.92.4 on Alpine 3.11 | 35.476 MB | 2020-05-28 11:40:21.37022 | rsdmse |

