# Docker Container of jupyterlab
The docker container to work ML.

## Requirements
- Docker 19.03~ (GPU supported)
- Cuda-GPU device and driver (This container uses CUDA 11.3.1)
- Windows10 (21H2) or Windows11 (supports GPU computing for WSL)

## Checked environment
- Windows11 on Ryzen 7 2700X and nVidia GTX 1050Ti
- Windows10 (21H2) on Intel i5-10600K and nVidia GTX 750Ti

## How to use
1. Make `.env` and `container/.env` file in root directory and set path.
    - `.env` ... environment variables for local path.
        - `DATASET_LOCALDIR` ... The **LOCAL** directory path containing datasets.<br>(example: `D:/datasets`)
        - `DATASET_DIR` ... The remote directory path containing datasets.<br>(example: `/resources/datasets`)
        - `GITHUB_CREDENTIAL` ... The github credential. optional value.<br>(example: [https://your_username:your_token@github.com]<br> The github token is contain allowance to access repositories.
        - `GIT_NAME` ... The git option `user.name`.
            ```sh
            $ git config --global user.name $GIT_NAME
            ```
        - `GIT_MAIL` ... The git option `user.email`.
            ```sh
            $ git config --global user.email $GIT_MAIL
            ```
        
        ```sh
        $ cat .env
        DATASET_LOCALDIR=D:\datasets
        DATASET_DIR=/resources/datasets
        ...
        ```

    - `container/.env` ... environment vaiables for remote container (API tokens, and so on...).
        
2. Launch container with:
    ```sh
    $ docker compose build # WAIT FOR A WHILE
    $ docker compose up
    ```

3. Access http://127.0.0.1:8888/lab$token=[token] on your browser!