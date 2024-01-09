## Localhost

```sh
git clone https://huggingface.co/spaces/aadnk/faster-whisper-webui
cd faster-whisper-webui
```

Edit `requirements-fasterWhisper.txt`:  

```sh
torch==2.0.1
torchaudio==2.0.2
pyannote.audio==3.0.1
```

```sh
python310 -m venv venv
venv\Scripts\activate.bat
pip install -r requirements-fasterWhisper.txt
```

A useless step to check:

```sh
pip install torch===2.0.1 torchaudio===2.0.2 pyannote.audio===3.0.1 -f https://download.pytorch.org/whl/torch_stable.html
```

```sh
git clone https://github.com/Temmie-Flakes/Simple_Speech_Recognition
cd Simple_Speech_Recognition
```

Imitate `RunBaseModel.bat` and Write your `.bat` liked:

```
venv\Scripts\python.exe Open_WebUI.py --cache-dir "modelsCache" --repo-id "guillaumekln/faster-whisper-medium"

PAUSE
```

Run your `.bat`. Then wait for the download to complete.

Add local-models into `config.json5` liked:

```json
"models": [
  {
    "name": "local-medium",
    "url": "...\\Simple_Speech_Recognition\\modelsCache\\faster-whisper-medium",
    "type": "filesystem"
  },
]
```

According to your needs, edit some arguments of `config.json5` liked:

```
"input_audio_max_duration": 600, // → -1
"server_port": 7860,
"whisper_implementation": "faster-whisper",
"default_model_name": "medium", // → "local-medium"
"vad_parallel_devices": "", // → "0"
"auto_parallel": false, // → true
"output_dir": null, // → "D:/home"
"language": null, // → "Chinese"
```

Used as cli liked:

```sh
python cli.py --whisper_implementation "faster-whisper" --vad "silero-vad" --auto_parallel true --vad_parallel_devices "0" --model "local-medium" --language "Chinese" --initial_prompt="对于普通话句子，以中文简体输出" --diarization_num_speakers 1 --output_dir "D:\home" yourvoice.mp3
```

Start with webui:

```sh
python.exe app.py --input_audio_max_duration -1 --server_name 127.0.0.1 --server_port 7830 --whisper_implementation "faster-whisper" --default_model_name "local-medium" --vad_parallel_devices "0" --auto_parallel true --output_dir "D:/home" 
```

Then Open `http://localhost:7830/`.

Refer to [whisper_VAD模型的区别及用途](https://sharegpt.com/c/VzJhWpV), the Coding Wizard(gpt-3.5-turbo)'s suggestion——You can try transcribing audiobook with `Silero-VAD-Expand-Into-Gaps`. And try transcribing with `Silero-VAD-Skip-Gaps`.

## Reference

- [Running Locally](https://huggingface.co/spaces/aadnk/faster-whisper-webui/blob/main/README.md#running-locally)
- [Enabling custom Japanese model](https://huggingface.co/spaces/aadnk/faster-whisper-webui/discussions/5)
- [services.py](https://github.com/usoonees/logseq-whisper-subtitles-server/blob/main/logseq_whisper_subtitles_server/services.py)

## Troubleshoot

- [Segmentation Fault when loading pyannote/speaker-diarization-3.0 in rockylinux9/python3 environment](https://github.com/pyannote/pyannote-audio/issues/1499)