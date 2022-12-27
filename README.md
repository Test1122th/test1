# DEGAN

This is the code repository for **DEGAN** (**D**ensity **E**stimation **G**enerative **A**dversarial **N**etwork).

Users of this repo can conduct training and configuring Generative Adversarial Network (GAN) through the DEGAN framework for detecting anomalies on new time series. 


## Description
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


## Install Required Packages

The following main packages were used：   
[numpy](https://numpy.org/install/) / [random](https://docs.python.org/3/library/random.html) / [tensorflow](https://www.tensorflow.org/install) / [matplotlib](https://matplotlib.org/stable/users/installing/index.html)

Other packages can be referred in [requirements](requirements.txt).

This file may be used to create an environment using:
```
$ conda create --name <env> --file <this file>
# platform: osx-arm64
```

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

## Contact
- [Bingqing Chen](mailto:bingqinc@andrew.cmu.edu), PhD Candidate at Carnegie Mellon University, Department of Civil and Environmental Engineering, Intelligent Infrastructure Research Laboratory (INFERLab).
- [Mario Berges](mailto:marioberges@cmu.edu), Professor at Carnegie Mellon University, Department of Civil and Environmental Engineering, INFERLab


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


## License
