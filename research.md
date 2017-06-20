---
layout: page1col
title: Research
permalink: /research/
---
<header class="post-header">
<style type="text/css">
p.intro {text-indent:1em; font-size:0.9em}
</style>
</header>

*Preprints:*

--------

**Learning classification and regression models for data with drift based on transfer samples** ([pdf](\papers\preprint_TMTL.pdf), [Matlab code](/codes/matlab/tmtl.zip))  
**Ke Yan**, David Zhang, and Yong Xu 

<p class="intro">We aim to compensate the two largest influential factors in e-nose applications: instrumental variation and time-varying drift. The transfer-sample-based multitask learning (TMTL) algorithm defines each device or time period as a domain, then learns a prediction model for each domain. Two paradigms, parallel and serial transfer, are designed according to the prior knowledge of the two influential factors. A dynamic model strategy is also proposed to handle continuous sample stream in the MTL framework. <!--In the bottom figure, each circle is a sample; Each Cylinder is a group of transfer samples, which also corresponds to a model; Arrows indicate the model similarity relationships.--></p>

<!--<div align="center"><img title="Model similarity priors in transfer-sample-based multitask learning (TMTL)" src="/images/research/tmtl.png" width="40%" height="40%" alt="Model similarity priors in transfer-sample-based multitask learning (TMTL)" /></div>-->


--------

*Published:*

--------

**Learning Domain-Invariant Subspace Using Domain Features and Independence Maximization** ([pdf](\papers\17_TCyb_MIDA.pdf), [Matlab code](http://www.mathworks.com/matlabcentral/fileexchange/56645-maximum-independence-domain-adaptation--mida-), [domain adaptation toolbox](http://yanke23.com/articles/research/2016/04/17/A-domain-adaptation-matlab-toolbox.html))  
**Ke Yan**, Lu Kou, and David Zhang  
Accepted by *Cybernetics, IEEE Transactions on* (IF = 4.943), <span class="type1">2017</span>.
<p class="intro">Maximum independence domain adaptation (MIDA) is proposed to learn a domain-invariant subspace. It can be applied in all kinds of domain adaptation problems, including discrete or continuous distributional change, supervised/semi-supervised/unsupervised, multiple domains, classification or regression, etc. We first design "domain features", then maximize the independence between them and the learned features.</p>
<div align="center"><img title="Effect of MIDA" src="/images/research/mida.png" width="90%" alt="Effect of MIDA" /></div>
<p></p>

--------

**Correcting instrumental variation and time-varying drift: a transfer learning approach with autoencoders** ([pdf](\papers\preprint_DCAE.pdf), [Python code](https://github.com/viggin/yan-autoencoder))  
**Ke Yan** and David Zhang  
*IEEE Trans. on Instrumentation and Measurement* (IF = 1.790), <span class="type1">2016</span>.

<p class="intro">Drift correction autoencoder (DCAE) is proposed to correct instrumental variation and time-varying drift. We enhance the structure and objective function of the original autoencoder, so that the two factors can be explicitly modeled and compensated. A drift-corrected and discriminative representation of the original data is thus learned.</p>

<div align="center"><img title="The structure of Drift Correction Autoencoder (DCAE)" src="/images/research/dcae.png" width="50%" height="50%" alt="The structure of drift correction autoencoder (DCAE)" /></div>

--------

**Calibration transfer and drift compensation of e-noses via coupled task learning** ([pdf](\papers\16_SNB_TCTL.pdf), [Matlab code](http://www.mathworks.com/matlabcentral/fileexchange/54558-transfer-sample-based-coupled-task-learning--tctl-))  
**Ke Yan** and David Zhang  
*Sensors and Actuators B: Chemical* (IF = 4.097), <span class="type1">2015</span>.

<p class="intro">The preliminary version of TMTL with only 2 tasks. The key idea is to align the transfer samples at the model level.</p>

--------

**Improving the transfer ability of prediction models for electronic noses** ([pdf](\papers\15_SNB_WPDS-SEMI.pdf), [Matlab code](http://www.mathworks.com/matlabcentral/fileexchange/52187-feature-weighted-logistic-regression--ridge-regression--svm-and-svr))  
**Ke Yan** and David Zhang  
*Sensors and Actuators B: Chemical* (IF = 4.097), <span class="type1">2015</span>.
 
<p class="intro">A novel variable standardization method and a regularization strategy, windowed piecewise direct standardization (WPDS) and standardization-error-based model improvement (SEMI), are proposed to deal with instrumental variation.</p>

--------

**Feature selection and analysis on correlated gas sensor data with recursive feature elimination** ([pdf](\papers\15_SNB_SVM-RFE-CBR.pdf), [Matlab code](https://cn.mathworks.com/matlabcentral/fileexchange/50701-feature-selection-with-svm-rfe))  
**Ke Yan** and David Zhang  
*Sensors and Actuators B: Chemical* (IF = 4.097), <span class="type1">2015</span>.

<p class="intro">Introducing correlation bias reduction (CBR), an improvement to the feature selection algorithm SVM-RFE for correlated features.</p>

--------

**Design of a breath analysis system for diabetes diagnosis and blood glucose level prediction** ([pdf](\papers\14_TBME_system.pdf))  
**Ke Yan**, David Zhang, Darong Wu, Hua Wei, and Guangming Lu  
*IEEE Trans. on Biomedical Engineering* (IF = 2.347), <span class="type1">2014</span>. 
<p class="intro">The hardware and software of an e-nose-based system are introduced.</p>
<div align="center">
	<img title="Breath analysis procedure" src="/images/research/breath_analysis_procedure.jpg" width="80%" height="80%" alt="Breath analysis procedure" />
</div>

--------

**Blood glucose prediction by breath analysis system with feature selection and model fusion** ([pdf](\papers\14_EMBC_BGL.pdf))  
**Ke Yan** and David Zhang  
*36th Annual Intl. Conf. of the IEEE Engineering in Medicine and Biology Society (EMBC)*, Chicago, <span class="type1">2014</span>, oral presentation  
<p class="intro">Predicting the blood glucose of 203 breath samples, mean relative absolute error = 20.69%.</p>

--------

**Sensor evaluation in a breath analysis system** ([pdf](\papers\14_ICMB_sensorEval.pdf))  
**Ke Yan** and David Zhang  
*Intl. Conf. Medical Biometrics (ICMB)*, Shenzhen, <span class="type1">2014</span>

--------

**A novel breath analysis system for diabetes diagnosis** ([pdf](\papers\12_ICCH_system.pdf))  
**Ke Yan** and David Zhang  
*Intl. Conf. Computerized Healthcare (ICMB)*, Hong Kong, <span class="type1">2012</span>

--------

**Gabor Surface Feature for face recognition** ([pdf](\papers\11_ACPR_GSF.pdf), [Matlab code](http://www.mathworks.com/matlabcentral/fileexchange/50697-gabor-surface-feature-for-face-recognition), [OpenCV code](https://github.com/viggin/facerecog))  
**Ke Yan**, Youbin Chen and David Zhang  
*1st Asian Conference on Pattern Recognition (ACPR)*, Beijing, <span class="type1">2011</span>  
<p class="intro">An improvement to the Gabor+LBP feature. Good performance on FERET dataset.</p>

--------
Patent: **An exhaled gas detection system (in Chinese)**, Pending  
**一种呼出气体的检测系统** ([link](http://www.google.com/patents/CN103245705A?cl=zh))  
张大鹏, **闫轲**, 卢光明  
*公开中, 公开号 CN103245705 A*
