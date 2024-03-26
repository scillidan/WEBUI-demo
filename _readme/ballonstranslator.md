## Localhost

Install Python 3.11. I used [Python 3.11.8](https://www.python.org/downloads/release/python-3118/).

```sh
where python
...\python.exe -m venv venv
venv\Scripts\activate.bat
```

Edit `requirements.txt`:

```
# torch
# torchvision
```

```sh
pip install -r requirements.txt
```

Install [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit), I use `CUDA 11.8.0`. Check it:

```sh
echo %CUDA_PATH%
echo %CUDA_PATH_V11_8%
```

Downloads `torch-2.2.1+cu118-cp311-cp311-win_amd64.whl` from https://download.pytorch.org/whl/torch.

```sh
python3 -m pip install ...\torch-2.2.1+cu118-cp311-cp311-win_amd64.whl
python3 -m pip install torchvision
```

```sh
python3 launch.py
```