# WhiteBox - Part1 

The White Box Project is a project that introduces many ways to solve the part of the black box of machine learning. In this part, i've introduced and experimented with ways to interpret and evaluate models in the field of image. 

I shared Korean versions for each reference to study methodology and English. Please refer to the reference.  
참고 자료별로 영어공부겸 한국어로 번역한 자료가 있습니다.

***Keywords** : `Explainable AI`, `XAI`, `Interpretable AI`, `Attribution Method`, `Saliency Map`*

# Requirements
```
pytorch >= 1.2.0
torchvision == 0.4.0
```

# How to Run
**Model Train**
```
python main.py --train --target=['mnist','cifar10']
```

**Model Selectivity Evaluation**
```
python main.py --eval --target=['mnist','cifar10'] --method=['VGB','IB','IG','GB','GC','GB-GC','DeconvNet']
```

# Dataset
- MNIST
- CIFAR-10

# Saliency Maps
**Attribution Methods**
- [Vanilla Backpropagation (VBP)](https://github.com/bllfpc/WhiteBox-Part1/blob/master/notebook/%5BAttribution%5D%20-%20Vanilla%20Backpropagation%20%26%20SmoothGrad.ipynb)
- Input x Backpropagation (IB)
- [DeconvNet](https://github.com/bllfpc/WhiteBox-Part1/blob/master/notebook/%5BAttribution%5D%20-%20DeconvNet%20%26%20SmoothGrad.ipynb) [1]
- [Guided Backpropagation (GB)](https://github.com/bllfpc/WhiteBox-Part1/blob/master/notebook/%5BAttribution%5D%20-%20Guided%20Backpropagation%20%26%20Guided%20GradCam%20%26%20SmoothGrad.ipynb) [2]
- [Integrated Gradients (IG)](https://github.com/bllfpc/WhiteBox-Part1/blob/master/notebook/%5BAttribution%5D%20-%20Integrated%20Gradients%20%26%20SmoothGrad.ipynb) [3]
- [Grad-CAM (GC)](https://github.com/bllfpc/WhiteBox-Part1/blob/master/notebook/%5BAttribution%5D%20-%20GradCAM%20%26%20SmoothGrad.ipynb) [4]
- [Guided Grad-CAM (GB-GC)](https://github.com/bllfpc/WhiteBox-Part1/blob/master/notebook/%5BAttribution%5D%20-%20Guided%20Backpropagation%20%26%20Guided%20GradCam%20%26%20SmoothGrad.ipynb) [4]

**Ensemble Methods**
- SmoothGrad (SG) [5]
- SmoothGrad-Squared (SG-SQ) [6]
- SmoothGrad-VAR (SG-VAR) [6]

# Evaluation Methods
- Coherence
- Selectivity
- ROAR [6]
- KAR [6]

# Experiments
## Model Architecture & Performance

Architecture | MNIST | CIFAR-10
---|---|---
<img src="https://github.com/bllfpc/WhiteBox/blob/master/images/models/simple_cnn_architecture.png" alt="simple_cnn_architecture" width="200"/> | ![](https://github.com/bllfpc/WhiteBox/blob/master/images/results/mnist_acc_loss_plot.png) | ![](https://github.com/bllfpc/WhiteBox/blob/master/images/results/cifar10_acc_loss_plot.png)

# Results
## Coherence
**MNIST**  
![](https://github.com/bllfpc/WhiteBox/blob/master/images/results/coherence_mnist.jpg)

**CIFAR-10**  
![](https://github.com/bllfpc/WhiteBox/blob/master/images/results/coherence_cifar10.jpg)

## Selectivity
**MNIST**  
![](https://github.com/bllfpc/WhiteBox/blob/master/images/results/score_acc_change_mnist.jpg)

**CIFAR-10**  
![](https://github.com/bllfpc/WhiteBox/blob/master/images/results/score_acc_change_cifar10.jpg)

# Reference
- [1] Zeiler, M. D., & Fergus, R. (2014, September). [Visualizing and understanding convolutional networks](https://arxiv.org/abs/1311.2901). In European conference on computer vision (pp. 818-833). Springer, Cham. ([Korean version](https://www.notion.so/tootouch/Visualizing-and-Understanding-Convolutional-Networks-4f396791212846439881575513271407))

- [2] Springenberg, J. T., Dosovitskiy, A., Brox, T., & Riedmiller, M. (2014). [Striving for simplicity: The all convolutional net](https://arxiv.org/abs/1412.6806). arXiv preprint arXiv:1412.6806. 

- [3] Sundararajan, M., Taly, A., & Yan, Q. (2017, August). [Axiomatic attribution for deep networks](https://arxiv.org/pdf/1703.01365.pdf). In Proceedings of the 34th International Conference on Machine Learning-Volume 70 (pp. 3319-3328). JMLR. org.

- [4] Selvaraju, R. R., Cogswell, M., Das, A., Vedantam, R., Parikh, D., & Batra, D. (2017). [Grad-cam: Visual explanations from deep networks via gradient-based localization](https://arxiv.org/abs/1610.02391). In Proceedings of the IEEE International Conference on Computer Vision (pp. 618-626). ([Korean version](https://www.notion.so/tootouch/Grad-CAM-Visual-Explanations-from-Deep-Networks-via-Gradient-based-Localization-504a3f7a58fd4c3eafdc26258befd643))

- [5] Smilkov, D., Thorat, N., Kim, B., Viégas, F., & Wattenberg, M. (2017). [Smoothgrad: removing noise by adding noise](
https://arxiv.org/abs/1706.03825). arXiv preprint arXiv:1706.03825. ([Korean version](https://www.notion.so/tootouch/SmoothGrad-removing-noise-by-adding-noise-18d13aeff8c34bafa61a749720576c1b))

- [6] Hooker, S., Erhan, D., Kindermans, P. J., & Kim, B. (2018). [Evaluating feature importance estimates](https://arxiv.org/abs/1806.10758). arXiv preprint arXiv:1806.10758. ([Korean version](https://www.notion.so/tootouch/Evaluating-Feature-Importance-Estimates-301ba24f929742a69104a2b67fdd0d89))
