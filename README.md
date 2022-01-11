# Docker Container of jupyterlab
The docker container to work ML.

## Checked environment
- Windows11 on Ryzen 7 2700X and nVidia GTX 1050Ti
- Windows10 (21H2) on Intel i5-10600K and nVidia GTX 750Ti

## How to use
1. Make `.env` and `container.env` file in root directory and set path.
    - `.env` ... environment variables for local path.
        - `DATASET_LOCALDIR` ... The **LOCAL** directory path containing datasets.<br>(example: `D:/datasets`)
        - `DATASET_DIR` ... The remote directory path containing datasets.<br>(example: `/resources/datasets`)
        ```env
        DATASET_LOCALDIR=D:\datasets
        DATASET_DIR=/resources/datasets
        ```

    - `container.env` ... environment vaiables for remote container.
        
2. Launch container with:
    ```sh
    $ docker compose build
    $ docker compose up
    ```

3. Access http://127.0.0.1:8888/lab$token=[token] on your browser!