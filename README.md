# Hulk

Ansible plays for turning my gaming rig into a machine learning beast.

Tested against Ubuntu Server 22.04.2 LTS, with a 3080.

*   Provision with `make hulk-out`.
*   Run workloads from another machine with:
    *   ```shell
        $ docker -H ssh://ross@hulk \
            run --rm --runtime=nvidia --gpus=all \
            nvidia/cuda:12.1.0-base-ubuntu22.04 nvidia-smi
    *   ```shell
        $ docker context create hulk --docker "host=ssh://ross@hulk"
        $ docker context use hulk
        $ docker run --rm --gpus=all --runtime=nvidia nvidia/cuda:12.1.0-base-ubuntu22.04 nvidia-smi
        ```
    *   ```shell
        $ docker run --rm -p 0.0.0.0:80:80 -d nginx
        $ curl http://hulk/
        <!DOCTYPE html>
        <html>
        <head>
        <title>Welcome to nginx!</title>
        [...]
         ```
