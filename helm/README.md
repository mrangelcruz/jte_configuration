# POSTGRES 16 DOCKER IMAGE 

1> pull image

    docker pull bitnamilegacy/postgresql:16.6.0-debian-12-r2

2> save image as tar (shold save this to Artifactory)

    docker image save \
    bitnamilegacy/postgresql:16.6.0-debian-12-r2 \
    -o tar_files/postgresql-16.6.0-debian-12-r2.tar

3> load tar file and import to k3d

    docker load -i tar_files/postgresql-16.6.0-debian-12-r2.tar

    k3d image import \
    tar_files/postgresql-16.6.0-debian-12-r2.tar \
    --cluster devcluster
