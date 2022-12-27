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
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
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




### Data Files



<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Files

To generate "historical" data from baseline controller, 

```
$ python simulate.py
```

For **Offline Pretraining**, 
```
$ python Imit_EP.py
```

For **Online Learning**, 
```
$ python PPO_MPC_EP.py
``` 

```
    .
    ├── ...
    ├── test                    # Test files (alternatively `spec` or `tests`)
    │   ├── benchmarks          # Load and stress tests
    │   ├── integration         # End-to-end, integration tests (alternatively `e2e`)
    │   └── unit                # Unit tests
    └── ...
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Contact
- [Yueyan Gu](mailto:bingqinc@andrew.cmu.edu), PhD student at Virginia Tech, Department of Civil and Environmental Engineering, INFORM Lab.
- [Farrokh Jazizadeh](mailto:marioberges@cmu.edu), Associate Professor at Virginia Tech, Department of Civil and Environmental Engineering, INFORM Lab


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

Copyright (c) 2023 Yueyan Gu

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

Here are some resources that are helpful to the creation of this Project Repository.

* [Choose an Open Source License](https://choosealicense.com)
* [Best-README-Template](https://github.com/othneildrew/Best-README-Template)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
