# Signans - The Conversation Tool

In an attempt to maximize inclusion and expand the level of communication between signers and non-signers, this project employs the use of machine learning to translate [American Sign Language](https://www.nidcd.nih.gov/health/american-sign-language) fingerspelling alphabet into text and speech in real-time.

* To load Signans on your project, follow this [tutorial](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/auto_examples/plot_object_detection_saved_model.html).
* To load the Lite version, follow this [tutorial](https://www.tensorflow.org/lite/guide).
* To load the JS version, follow this [tutorial](https://www.tensorflow.org/js/guide/save_load).

* To test Signans on your machine with OpenCV, follow the next steps. 

### 1. Create Virtual Python Environment

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install  [virtualenv](https://virtualenv.pypa.io/en/latest/) and create a virtual environment on your machine.

```bash
pip install virtualenv
python3.8 -m venv signans-python
```

On Windows, run:
```bash
signans-python\Scripts\activate.bat
pip install --upgrade pip
cd signans-python
```

On Unix or MacOS, run:
```bash
source signans-python/bin/activate
pip install --upgrade pip
cd signans-python
```

### 2. Clone Signans and Download Packages 
* Clone Signans GitHub repository:

```bash
git clone https://github.com/brunobpr/Signans
```
* Download [TensorFlow Models](https://www.tensorflow.org/js/models):
```bash
git clone https://github.com/tensorflow/models.git
```
* Install the required packages:
```bash
pip install -r Signans/requirements.txt
```

* Move the models to the python environment:

On Windows, run:
```bash
move "models\research\object_detection" "Lib\site-packages"
move "models\official" "Lib\site-packages"
cd Signans
```

On Unix or MacOS, run:
```bash
mv models/research/object_detection lib/python3.8/site-packages
mv models/official lib/python3.8/site-packages
cd Signans
```

### 3. Run the Script
```bash
python Signans.py
```
Once the video capturing window opens, use the ASL alphabet to finger-spell words or sentences. There are two extra signs, `space` and `dot`. 

* Space (left) means end of the word;
* Dot (right) triggers the text-to-speech function.

[![space-dot-signs](https://i.postimg.cc/fLkHL9zw/Screenshot-2021-05-05-at-22-26-41.png)](https://postimg.cc/mzf3ph1q)


To change the detection speed, run the scrip with the argument --speed or -s: 
```bash
python Signans.py --speed {time in seconds}
```

##### Signans with Google Translator
* To enable Google Translator, you need to set up an [authentication key](https://cloud.google.com/translate/docs/setup).
* Once the authentication key is generated and downloaded, move it to `signans-python/Signans` and rename it as `authentication.json`



At the moment the supported languages are: 
| Language  | Code  |
|:--------: |------:|
|**French** | fr| 
|**Spanish**    |   es|
|**Portuguese**  |    pt |
|**Mandarin**  |    zh|


To change the language, run the scrip with the argument --language or -l 
```bash
python Signans.py --language {code}
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[Apache 2.0](https://choosealicense.com/licenses/apache-2.0/)