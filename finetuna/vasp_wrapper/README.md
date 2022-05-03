# FINETUNA VASP Input Wrapper
This module is for running `FINETUNA` with just VASP input files. All you need is a folder with VASP `INCAR`, `POTCAR`, `POSCAR`, `KPOINTS`.
## How to use
- Install via `pip`

    ```sh
        pip install git+https://github.com/ulissigroup/finetuna.git
    ```
    
- All pre-trained OCP models can be found [here](https://github.com/Open-Catalyst-Project/ocp/blob/main/MODELS.md). We recommend download [GemNet-dT all](https://dl.fbaipublicfiles.com/opencatalystproject/models/2021_08/s2ef/gemnet_t_direct_h512_all.pt), and use it for `FINETUNA`.
    
- Usage
    - Copy [sample_config.yml](https://github.com/ulissigroup/finetuna/blob/master/finetuna/vasp_wrapper/sample_config.yml) to your own working directory
    - Add the path to GemNet-dT checkpoint to [`ocp` `checkpoint_path_list`](https://github.com/ulissigroup/finetuna/blob/master/finetuna/vasp_wrapper/sample_config.yml#L69)
    - Run `FINETUNA` by
    ```sh
        cd /path/to/vasp/input/folder
        finetuna_wrap.py -c /path/to/config/file
    ```
        or
    ```sh
        finetuna_wrap.py -c /path/to/config/file -p /path/to/vasp/input/folder
    ```