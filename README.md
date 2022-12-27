<a name="readme-top"></a>

# DEGAN

This is the code repository for **DEGAN** (**D**ensity **E**stimation **G**enerative **A**dversarial **N**etwork).

Users of this repo can conduct training and configuring Generative Adversarial Network (GAN) through the DEGAN framework for detecting anomalies on new time series. 

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#introduction">Introduction</a>
      <ul>
        <li><a href="#framework">Framework</a></li>
        <li><a href="#time-series">Time Series</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#required-packages">Required Packages</a></li>
        <li><a href="#demo-project">Demo Project</a></li>
        <li><a href="#sample-dataset">Sample Dataset</a></li>
      </ul>
    </li>
    <li><a href="#files">Files</a></li>
    <li><a href="#publication">Publication</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>


## Introduction
**DEGAN** is an unsupervised Generative Adversarial Network (GAN)-based anomaly detection framework. 

### Framework  

The framework contains three main components: GAN training, _**D**_ model selection, and anomaly detection. It makes use of the information contained in normal time series (processed using a sliding window method) during GAN training and _**D**_ model selection, enabling a validated _**D**_ model to be an independent anomaly detector after training for a given system. 

In the anomaly detection component, kernel density estimation is used to assign a probability distribution to the suspicious data points identified by the selected _**D**_ model and identify the areas with the highest probability of being anomalies.

<img src="https://github.com/Test1122th/test1/blob/main/imgs/degan_framework.png" width="800" height="650" />

### Time Series

The DEGAN framework centers around repeated time series acquired to monitor the temporal variation in the operation of a given system. These time series reflect the performance of the system and the goal is to identify when/where an anomalous event is observed. 

The example below shows an overall process of using repeated time series data for training, validation and testing in DEGAN, where _TSA_ is training data, _TSB_ is validation data and _TSC_ is testing data. 

<img src="https://github.com/Test1122th/test1/blob/main/imgs/time_series.png" width="600" height="450" />

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Getting Started

### Required Packages

The following main packages were used：   
[numpy](https://numpy.org/install/) / [random](https://docs.python.org/3/library/random.html) / [tensorflow](https://www.tensorflow.org/install) / [matplotlib](https://matplotlib.org/stable/users/installing/index.html)

Other packages can be referred in [requirements](requirements.txt).

This file may be used to create an environment using:
```
$ conda create --name <env> --file <this file>
# platform: osx-arm64
```

### Demo Project

[Demo.ipynb](demo.ipynb) is an example of how to apply the DEGAN framework with your own time series datasets.

To test and use the framework, you may get a local copy up and running the example steps in the demo file.


### Sample Dataset

The sample dataset is aquired from a building energy anomaly data (Link here). For the general usage of the project, the original sample data was simply pre-processed into the following datasets:

```
    ├── Data                           # Data files
    │   ├── testing time series.csv        # testing time series data
    │   ├── testing.csv                    # testing data
    │   ├── training.csv                   # training data
    │   └── val.csv                        # validation data
    └── ...
```

Users of this framework can organize their dataset following the similar structure.


<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Files

The main functions of the DEGAN Demo are in the folder [DEGAN](https://github.com/Test1122th/test1/tree/main/DEGAN).


To **generative adversarial network (GAN)** , including building the generator and the discriminator model to combining the two, setting their trainability, generating sample random noise, training and saving the trained discriminator models, refer to:

```
$ python Conv1D_GAN.py
```

To use the discriminator model to **evaluate the testing inspection** making use of the saved discriminator model, refer to:
```
$ python evaluate.py
```

To test the time series data using the trained discriminator from the generative adversarial network, and **calculate the performance metrics** (Precision, Recall, F1) across the testing data, refer to:
```
$ python test.py
``` 

To **train and validate the Generative Adversarial Network** on the time series, and extracte the discriminator model to be used for testing, refer to:
```
$ python train_val.py
``` 

To look into the **helper functions** that perform part of the computations in other functions, refer to:
```
$ python utils.py
``` 

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Publication

Further details of the framework is introduced in this paper:
[DEGAN: Time Series Anomaly Detection using Generative Adversarial Network Discriminators and Density Estimation](https://arxiv.org/abs/2210.02449). 

If you find this framework helpful to your research, please cite it with the following reference:

```
@article{gu2022degan,
  title={DEGAN: Time Series Anomaly Detection using Generative Adversarial Network Discriminators and Density Estimation},
  author={Gu, Yueyan and Jazizadeh, Farrokh},
  journal={arXiv preprint arXiv:2210.02449},
  year={2022}
}
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

**MIT License**

Copyright (c) 2023 NAME HERE

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contact

[Yueyan Gu](https://yueyangu.github.io/aboutme/) - yueyangu@vt.edu
- PhD student at Virginia Tech, Department of Civil and Environmental Engineering, INFORM Lab

[Farrokh Jazizadeh](https://www.inform-lab.org/farrokh-jazizadeh) - jazizade@vt.edu
- Associate Professor at Virginia Tech, Department of Civil and Environmental Engineering, INFORM Lab


<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

Here are some resources that are helpful to the creation of this Project Repository.

* [Choose an Open Source License](https://choosealicense.com)
* [Best-README-Template](https://github.com/othneildrew/Best-README-Template)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
