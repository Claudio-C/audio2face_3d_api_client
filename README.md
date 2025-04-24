# Sample Application connecting to Audio2Face-3D NIM locally

A sample Python application to showcase the Audio2Face-3D NIM running on localhost.

## Getting started

Start by creating a python venv using:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Then install the required dependencies:

```bash
pip3 install -r requirements
pip3 install ../../proto/sample_wheel/nvidia_ace-1.2.0-py3-none-any.whl
```

Note: This wheel is compatible with Audio2Face-3D NIM 1.3


```bash
python3 ./nim_a2f_3d_client.py <audio_file.wav> <config.yml>
```

By Default:

```bash
python3 ./nim_a2f_3d_client.py ../../example_audio/Claire_neutral.wav config/config_claire.yml
```

The scripts takes two mandatory parameters, an audio file at format PCM 16 bits and
 a yaml configuration file for the emotions parameters. The script connects to the local
 endpoint at localhost:52000, which doesn't require authentication.

## What does this example do?

1. Reads the audio data from a wav 16bits PCM file
2. Reads emotions and parameters from the yaml configuration file
3. Sends emotions, parameters and audio to the A2F-3D running locally on localhost:52000
4. Receives back blendshapes, audio and emotions
5. Saves blendshapes as animation key frames in a csv file with their name, value
and time codes
6. Same process for the emotion data.
7. Saves the received audio as out.wav (Should be the same as input audio)
