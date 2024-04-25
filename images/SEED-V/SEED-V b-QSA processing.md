# SEED-V b-QSA
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/bicomplexProduct/images/bicomplexProductSEEDVgeneral.svg" alt="drawing" width="2000"/>

The b-QSA is an effective algorithm proposed for our **"Feature Signal Processing for Emotion Recognition Based on Bi-Complex Quaternion Signal Analysis"** framerowk.
This MD file is a short version of the SEED-V b-QSA signal processing to present the missed figures in our paper-work.

## Time behaviour
The SEED-V is an emotion recognition EEG dataset to classify five primary emotions: happy, disgust, neutral, fear, and sad.
Normalized EEG raw has a time-domain representation as follows.

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/timeBehaviour/images/SEED-V%20time%20general.svg" alt="drawing" width="2000"/>

For high-resolution images, please visit our [SEED-V time behaviour](https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/timeBehaviour/timeBehaviourEEG.md) section.
For details, please go to our manuscript PDF.

## Escalled EEG

One obtained the Wavelet Denoised EEG (WD-EEG) we perform a scalation function based on the following criteria:

$$\xi_\varsigma(t) = \xi_\psi(t) - \frac{\underset{}{\min}\left(\xi_\psi(t)\right)}{\underset{}{\max}\left(\xi_\psi(t)\right) - \underset{}{\min}\left(\xi_\psi(t)\right)},$$

yielding the following scaled EEG time behaviour, represented as $\xi_{\zeta}\left(t\right)$.

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/scalledBehaviour/SEED-V%20scaled%20general.svg" alt="drawing" width="2000"/>

For high-resolution images, please visit our [SEED-V scaled behaviour](https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/scalledBehaviour/SEED-V%20b-QSA%20scaled%20processing.md) section.
For details, please go to our manuscript PDF.

## Effective channels



## The quaternion algebra
The EEG signal processing using the SEED-V dataset is based on five primary emotions (Happy, Surprise, Neutral, Disgust, and Sad). These five emotions are used to classify a robust classification algorithm companding $25$-ML architectures. Based on our previous work, [**A channel selection method to find the role of the amygdala in emotion recognition avoiding conflict learning in EEG signals**](https://doi.org/10.1016/j.engappai.2023.106971), we found that *FCZ*, *CP4*, *FC5*, and *P1*, are the top four EEG Effective Channels (EC) in this dataset.

Then, we used these four effective channels to perform a quaternion form based on the *Cayley-Dickson* form, as presented in [Quaternion Fourier Transforms for Signal and Image Processing](10.1002/9781118930908). We take the premise that

$$\mathbb{H} = \lbrace q | q = a + b \boldsymbol{i} + c \boldsymbol{j} + d \boldsymbol{k}, \quad \forall \lbrace a, b, c, d \rbrace \in \mathbb{R} \rbrace,$$

and

$$q = \xi_\varsigma(\eta_1, t) + \xi_\varsigma(\eta_2, t)\boldsymbol{i} + \xi_\varsigma(\eta_3, t)\boldsymbol{j} + \xi_\varsigma(\eta_4, t)\boldsymbol{k},$$

where $\xi_\varsigma(\eta_k, t) \in \mathbb{R}$ represents each EC. Then, $q$ is delayed $\Delta \tau = 250$ ms as

$$q = \xi_\varsigma(\eta_1, t_{\omega}-\Delta\tau) + \xi_\varsigma(\eta_2, t_{\omega}-\Delta\tau)\boldsymbol{i} + \xi_\varsigma(\eta_3, t_{\omega}-\Delta\tau)\boldsymbol{j} + \xi_\varsigma(\eta_4, t_{\omega}-\Delta\tau)\boldsymbol{k}, $$


Then, we established a new $p$ quaternion form based on the initial $q$ form, as

$$p =  \xi_\varsigma(\eta_1, t_{\omega}) + \xi_\varsigma(\eta_2, t_{\omega})\boldsymbol{i} + \xi_\varsigma(\eta_3, t_{\omega})\boldsymbol{j}  + \xi_\varsigma(\eta_4, t_{\omega})\boldsymbol{k}$$

Finally, the bicomplex product is expressed as

$$q p = \left( q_1p_1 - q_2 p_2, q_2p_1 + q_1 p_2 \right),$$

## The b-QSA signal processing behaviour
According to above, each primary emotion yields a time behaviour. We include the graphs here

### Happy
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/bicomplexProduct/images/HAPPY_bicomplexProductSEEDV.svg" alt="drawing" width="2000"/>

### Disgust
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/bicomplexProduct/images/DISGUST_bicomplexProductSEEDV.svg" alt="drawing" width="2000"/>

### Neutral
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/bicomplexProduct/images/NEUTRAL_bicomplexProductSEEDV.svg" alt="drawing" width="2000"/>

### Fear
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/bicomplexProduct/images/FEAR_bicomplexProductSEEDV.svg" alt="drawing" width="2000"/>

### Sad
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/bicomplexProduct/images/SAD_bicomplexProductSEEDV.svg" alt="drawing" width="2000"/>
