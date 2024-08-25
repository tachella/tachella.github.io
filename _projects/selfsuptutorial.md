---
layout: page
title: Self-supervised learning for imaging tutorial
description: 
img: assets/img/EUSIPCO24_header_sharp.png
importance: 1
category: work
---
This page contains information about the tutorial on self-supervised learning for imaging, given by [Mike Davies](https://www.eng.ed.ac.uk/about/people/professor-michael-e-davies) and me.
The tutorial is part of the [EUSIPCO 2024 conference](https://eusipcolyon.sciencesconf.org/resource/page/id/28) on the 26/08/2024 in Lyon, France.

**Slides**: The slides of the tutorial will be uploaded here after the conference.

**Code**: We will follow the Google Colab demo in [this link](https://colab.research.google.com/drive/1_dlXdNbgwg5u7_OAl29WiMRMOybnkCIo?usp=sharing).
More self-supervised learning demos can be found on the deepinverse website [here](https://deepinv.github.io/deepinv/auto_examples/index.html#self-supervised-learning).


**Abstract**: This tutorial will cover core concepts and recent advances in the emerging field of self-supervised
learning methods for solving imaging inverse problems with deep neural networks.
Self-supervised learning is a fundamental tool deploying deep learning solutions in scientific and medical
imaging applications where obtaining a large dataset of ground-truth images is very expensive or impossible.
The tutorial will provide a comprehensive summary of different self-supervised methods, 
discuss their theoretical underpinnings and present practical self-supervised imaging applications.

### References
List of references mentioned in the tutorial by topic.

#### Part I: Introduction
- Zbontar, Jure, et al. "fastMRI: An open dataset and benchmarks for accelerated MRI." arXiv preprint arXiv:1811.08839 (2018).
- Ulyanov, Dmitry, Andrea Vedaldi, and Victor Lempitsky. "Deep image prior." Proceedings of the IEEE conference on computer vision and pattern recognition. 2018.
- Jin K. H., McCann M. T., Froustey E., Unser M., Deep convolutional neural network for inverse problems in imaging. IEEE Trans. Im. Proc., 2017.
- Monga V., Li Y., Eldar Y. C., Algorithm unrolling: interpretable, efficient deep learning for signal and image processing. IEEE Sig. Proc. Mag., 2021.
- Y. Zhu et al., "Denoising Diffusion Models for Plug-and-Play Image Restoration," 2023 IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW), Vancouver, BC, Canada, 2023, pp. 1219-1229.

#### Part II: Learning from noisy data

##### Noise2Noise methods
- Mallows, Colin L. "Some comments on Cp." Technometrics 15.4 (1973): 661-675.
- Lehtinen, Jaakko, et al. "Noise2noise: Learning image restoration without clean data." Proceedings of the 35th International Conference on Machine Learning. 2018.

##### SURE methods
- Stein, Charles M. "Estimation of the mean of a multivariate normal distribution." The annals of Statistics (1981): 1135-1151.
- Breiman, Leo. "The little bootstrap and other methods for dimensionality selection in regression: X-fixed prediction error." Journal of the American Statistical Association 87.419 (1992): 738-754.
- Ramani, Sathish, Thierry Blu, and Michael Unser. "Monte-Carlo SURE: A black-box optimization of regularization parameters for general denoising algorithms." IEEE Transactions on image processing 17.9 (2008): 1540-1554.
- Eldar, Yonina C. "Generalized SURE for exponential families: Applications to regularization." IEEE Transactions on Signal Processing 57.2 (2008): 471-481.
- Metzler, Christopher A., et al. "Unsupervised learning with Stein's unbiased risk estimator." arXiv preprint arXiv:1805.10531 (2018).
- Kim, Kwanyoung, and Jong Chul Ye. "Noise2score: tweedies approach to self-supervised image denoising without clean images." Advances in Neural Information Processing Systems 34 (2021): 864-874.
- J. Ma and L. Ping, "Orthogonal AMP," in IEEE Access, vol. 5, pp. 2020-2033, 2017.

##### Noisier2Noise methods
- Moran, Nick, et al. "Noisier2noise: Learning to denoise from unpaired noisy data." Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2020.
- Pang, Tongyao, et al. "Recorrupted-to-recorrupted: Unsupervised deep learning for image denoising." Proceedings of the IEEE/CVF conference on computer vision and pattern recognition. 2021.
- Oliveira, Natalia L., Jing Lei, and Ryan J. Tibshirani. "Unbiased risk estimation in the normal means problem via coupled bootstrap techniques." arXiv preprint arXiv:2111.09447 (2021).
- Oliveira, Natalia L., Jing Lei, and Ryan J. Tibshirani. "Unbiased test error estimation in the poisson means problem via coupled bootstrap techniques." arXiv preprint arXiv:2212.01943 (2022).

##### Noise2Void and cross-validation methods
- Efron, Bradley. "The estimation of prediction error: covariance penalties and cross-validation." Journal of the American Statistical Association 99.467 (2004): 619-632.
- Krull, Alexander, Tim-Oliver Buchholz, and Florian Jug. "Noise2void-learning denoising from single noisy images." Proceedings of the IEEE/CVF conference on computer vision and pattern recognition. 2019.
- Batson, Joshua, and Loic Royer. "Noise2self: Blind denoising by self-supervision." International Conference on Machine Learning. PMLR, 2019.
- Huang, Tao, et al. "Neighbor2neighbor: Self-supervised denoising from single noisy images." Proceedings of the IEEE/CVF conference on computer vision and pattern recognition. 2021.
- Hendriksen, Allard Adriaan, Daniel Maria Pelt, and K. Joost Batenburg. "Noise2inverse: Self-supervised deep convolutional denoising for tomography." IEEE Transactions on Computational Imaging 6 (2020): 1320-1335.

##### Blind spot networks
- Laine, Samuli, et al. "High-quality self-supervised deep image denoising." Advances in Neural Information Processing Systems 32 (2019).
- W Lee, S Son, K M Lee; AP-BSN: Self-Supervised Denoising for Real-World Images via Asymmetric PD and Blind-Spot Network. Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), 2022, pp. 17725-17734

#### Part III: Learning from incomplete operators

- Liu, Jiaming, et al. "RARE: Image reconstruction using deep priors learned without groundtruth." IEEE Journal of Selected Topics in Signal Processing 14.6 (2020): 1088-1099.
- Tachella, Julian, Dongdong Chen, and Mike Davies. "Unsupervised learning from incomplete measurements for inverse problems." Advances in Neural Information Processing Systems 35 (2022): 4983-4995.
- Yaman, Burhaneddin, et al. "Self supervised learning of physics guided reconstruction neural networks without fully sampled reference data." Magnetic resonance in medicine 84.6 (2020): 3172-3191.
- Daras, Giannis, et al. "Ambient diffusion: Learning clean distributions from corrupted data." Advances in Neural Information Processing Systems 36 (2024).
- Gan W. et al., Self-Supervised Deep Equilibrium Models with Theoretical Guarantees and Applications to MRI Reconstruction. IEEE Trans. Comp Imag., 2023.
- C. Millard and M. Chiew, "A Theoretical Framework for Self-Supervised MR Image Reconstruction Using Sub-Sampling via Variable Density Noisier2Noise," in IEEE Transactions on Computational Imaging, vol. 9, pp. 707-720, 2023.

#### Part IV: Equivariant Imaging
- Chen, Dongdong, Julian Tachella, and Mike E. Davies. "Equivariant imaging: Learning beyond the range space." Proceedings of the IEEE/CVF International Conference on Computer Vision. 2021.
- Chen, Dongdong, Julian Tachella, and Mike E. Davies. "Robust equivariant imaging: a fully unsupervised framework for learning to image from noisy and partial measurements." Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2022.
- Scanvic, Jeremy, et al. "Self-supervised learning for image super-resolution and deblurring." arXiv preprint arXiv:2312.11232 (2023).

#### Part V: Identification theory
- Sauer, Tim, James A. Yorke, and Martin Casdagli. "Embedology." Journal of statistical Physics 65 (1991): 579-616.
- Tachella, Julian, Dongdong Chen, and Mike Davies. "Sensing theorems for unsupervised learning in linear inverse problems." Journal of Machine Learning Research 24.39 (2023): 1-45.
- Cramer, Harald; Wold, Herman (1936). "Some Theorems on Distribution Functions". Journal of the London Mathematical Society. 11 (4): 290-294.
-  Bourrier A., Davies M. E., Peleg T., Perez P., Gribonval R. Fundamental Performance Limits for Ideal Decoders in High-Dimensional Linear Inverse Problems. IEEE Trans. Inf. Thy., 2014.

#### Part VI: Perspectives
- Bora, Ashish, Eric Price, and Alexandros G. Dimakis. "AmbientGAN: Generative models from lossy measurements." International conference on learning representations. 2018.
- Hermosilla, Pedro, Tobias Ritschel, and Timo Ropinski. "Total denoising: Unsupervised learning of 3D point cloud cleaning." Proceedings of the IEEE/CVF international conference on computer vision. 2019.
- Tachella, Julian, and Laurent Jacques. "Learning to reconstruct signals from binary measurements." arXiv preprint arXiv:2303.08691 (2023).
- Bellec, Pierre C., and Cun-Hui Zhang. "Second-order Stein: SURE for SURE and other applications in high-dimensional inference." The Annals of Statistics 49.4 (2021): 1864-1903.
- Tachella, Julian, and Marcelo Pereyra. "Equivariant bootstrapping for uncertainty quantification in imaging inverse problems." AISTATS (2024).
