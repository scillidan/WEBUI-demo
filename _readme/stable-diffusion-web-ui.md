## Localhost

Install [Python 3.10.6](https://www.python.org/downloads/release/python-3106/).

Install [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit), I use `CUDA 11.8.0` because of [Start Locally](https://pytorch.org/get-started/locally/) but `torch==2.0.1`.

```sh
git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui
cd stable-diffusion-webui
C:\Users\YourName\AppData\Local\Programs\Python\Python310\python.exe -m venv venv
venv\Scripts\activate.bat
```

Install `torch` at first:

```sh
pip install torch==2.0.1
```

Or download `torch-2.0.1+cu118-cp310-cp310-win_amd64.whl` from https://download.pytorch.org/whl/torch/, then:

```sh
pip install torch-2.0.1+cu118-cp310-cp310-win_amd64.whl
```

Then install requirements:

```sh
pip install -r requirements.txt
```

Do something according to the returned information:

```sh
pip install -U numpy
```

Download `tb-nightly-****.whl` frome https://pypi.org/project/tb-nightly/#files.

```sh
pip install tb-nightly-****.whl
```

Download and put some checkpoint (`.safetensors` format) liked [ReV Animated](https://civitai.com/images/1433368), [Voxel XL](https://civitai.com/images/1829332), etc. into `./models/Stable-diffusion`.

Edit `webui-user.bat` line 6:

```sh
set COMMANDLINE_ARGS=--xformers --port 7050
```

```sh
webui-user.bat
```

## Reference

- [Manual Installation](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-NVidia-GPUs#manual-installation)
- [Troubleshooting](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Troubleshooting)
- [Command Line Arguments and Settings](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Command-Line-Arguments-and-Settings)

## Troubleshoot

- [AssertionError: Torch not compiled with CUDA enabled](https://github.com/pytorch/pytorch/issues/30664)
- [[resolved][bug]: Python version mismatch and could not find tb-nightly](https://github.com/invoke-ai/InvokeAI/issues/3560#issuecomment-1689474997)
- [How on earth can I install xformers?](https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/9802#discussioncomment-5894895)