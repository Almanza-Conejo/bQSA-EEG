# AMIGOS Bicomplex Product
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/AMIGOS/bicomplexProduct/images/bicomplexProductAMIGOSgeneral.svg" alt="drawing" width="2000"/>

## The quaternion algebra
The EEG signal processing using the AMIGOS dataset is based on the primitive emotion stimuli, Valence (V), Arousal (A), Dominance (D), and Linking (L). These four emotions are used to classify a robust classification algorithm companding $25$-ML architectures. Previously, we developed the framework [**Emotion recognition in EEG signals using the continuous wavelet transform and CNNs**](https://doi.org/10.1007/s00521-022-07843-9), based on a Convolutional Neural Network (CNN) architecture to classify a Deep Learning model combining these primitive emotions. Taking our [last work](https://doi.org/10.1016/j.engappai.2023.106971) as a reference, we found that *F7*, *P7*, *O1*, and *FC6* are the top four EEG Effective Channels (EC) in this dataset.

Then, we used these four effective channels to perform a quaternion form based on the *Cayley-Dickson* form, as presented in [Quaternion Fourier Transforms for Signal and Image Processing](10.1002/9781118930908). We take the premise that

$$\mathbb{H} = \lbrace q | q = a + b \boldsymbol{i} + c \boldsymbol{j} + d \boldsymbol{k}, \quad \forall \lbrace a, b, c, d \rbrace \in \mathbb{R} \rbrace,$$

and

$$q = \xi_\varsigma(\eta_1, t) + \xi_\varsigma(\eta_2, t)\boldsymbol{i} + \xi_\varsigma(\eta_3, t)\boldsymbol{j} + \xi_\varsigma(\eta_4, t)\boldsymbol{k},$$

where $\xi_\varsigma(\eta_k, t) \in \mathbb{R}$ represents each EC. Then, $q$ is delayed $\Delta \tau = 250$ ms as

$$q = \xi_\varsigma(\eta_1, t_{\omega}-\Delta\tau) + \xi_\varsigma(\eta_2, t_{\omega}-\Delta\tau)\boldsymbol{i} + \xi_\varsigma(\eta_3, t_{\omega}-\Delta\tau)\boldsymbol{j} + \xi_\varsigma(\eta_4, t_{\omega}-\Delta\tau)\boldsymbol{k}, $$


Then, we established a new $p$ quaternion form based on the initial $q$ form, as

$$p =  \xi_\varsigma(\eta_1, t_{\omega}) + \xi_\varsigma(\eta_2, t_{\omega})\boldsymbol{i} + \xi_\varsigma(\eta_3, t_{\omega})\boldsymbol{j}  + \xi_\varsigma(\eta_4, t_{\omega})\boldsymbol{k}$$

Finally, the quaternion product is expressed as

$$q p = \left( q_1p_1 - q_2 p_2, q_2p_1 + q_1 p_2 \right),$$

## The b-QSA signal processing behaviour
According to above, each primary emotion yields a time behaviour. We include the graphs here

### HVHA
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/AMIGOS/bicomplexProduct/images/HVHA_bicomplexProductAMIGOS.svg" alt="drawing" width="2000"/>

### HVLA
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/AMIGOS/bicomplexProduct/images/HVLA_bicomplexProductAMIGOS.svg" alt="drawing" width="2000"/>

### LVHA
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/AMIGOS/bicomplexProduct/images/LVHA_bicomplexProductAMIGOS.svg" alt="drawing" width="2000"/>

### LVLA
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/AMIGOS/bicomplexProduct/images/LVLA_bicomplexProductAMIGOS.svg" alt="drawing" width="2000"/>

