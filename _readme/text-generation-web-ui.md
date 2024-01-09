## Localhost (Windows 10)

Install [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit), I use `CUDA 12.1.0` refer to [Start Locally](https://pytorch.org/get-started/locally/).

```sh
git clone https://github.com/oobabooga/text-generation-webui
cd text-generation-webui
```

Use [HuggingFace-Download-Accelerator](https://github.com/LetheSec/HuggingFace-Download-Accelerator) download model, liked [tiiuae/falcon-7b-instruct](https://huggingface.co/tiiuae/falcon-7b-instruct).

```sh
mklink /D ...\text-generation-webui\models\models--tiiuae--falcon-7b-instruct ...\models--hadongz--falcon-7b-instruct-gguf
```

```sh
start_windows.bat
```

Open `localhost:7860` → Model Tab → Select `Model` → Select `Model loader` → load

If there is no problem, you will see:

![](_media/text-generation-web-ui_model.png)

If you see errors, good luck for you!