# DEAP b-QSA
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/bicomplexProduct/images/DEAPbqsatimegeneral.svg" alt="drawing" width="2000"/>

The b-QSA is an effective algorithm proposed for our **"Feature Signal Processing for Emotion Recognition Based on Bi-Complex Quaternion Signal Analysis"** framerowk.
This MD file is a short version of the AMIGOS b-QSA signal processing to present the missed figures in our paper-work.

## Time behaviour
The DEAP is an emotion recognition EEG dataset to classify primitive emotions: Valence (V) and Arousal (A). Here, we propose a
High- or Low-Valence (HV/LV) and High- or Low-Arousal (HA/LA) combination, making that targets up to a four-target space (HVHA, HVLA, LVHA, LVLA).
Normalized EEG raw has a time-domain representation as follows.

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/AMIGOS/timeBehaviour/AMIGOS%20time%20behaviour%20general.svg" alt="drawing" width="2000"/>

For high-resolution images, please visit our [AMIGOS time behaviour](https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/AMIGOS/timeBehaviour/timeBehaviourEEG.md) section.
For details, please go to our manuscript PDF.

## Escalled EEG

Same as in SEED-V escalled pattern, once obtained the Wavelet Denoised EEG (WD-EEG) we perform a scalation function based on the following criteria:

$$\xi_\varsigma(t) = \xi_\psi(t) - \frac{\underset{}{\min}\left(\xi_\psi(t)\right)}{\underset{}{\max}\left(\xi_\psi(t)\right) - \underset{}{\min}\left(\xi_\psi(t)\right)},$$

yielding the following scaled EEG time behaviour, represented as $\xi_{\zeta}\left(t\right)$.

## Effective channels

AMIGOS dataset contains a sum of $\Xi_{s} \in \mathbb{R}^{40960 \times t}$ EEG signals. Besides, using the [Minimum Redundance Maximum Relevance algorithm](https://doi.org/10.1142/S0219720005001004) we achieve a top four EEG Effective Channels (EC) subset based on our previous work, [**A channel selection method to find the role of the amygdala in emotion recognition avoiding conflict learning in EEG signals**](https://doi.org/10.1016/j.engappai.2023.106971). As a result, the top four effective channels for AMIGOS db are: *AF3*, *P7*, *T8*, and *O1*. The normalized EC score is shown in the following figure.

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/effectiveChannels/ecDEAP.svg" alt="drawing" width="2000"/>

## The quaternion algebra
Once these four effective channels are achieved, we perform a quaternion based on the *Cayley-Dickson* form, as presented in [Quaternion Fourier Transforms for Signal and Image Processing](10.1002/9781118930908). We take the premise that

$$\mathbb{H} = \lbrace q | q = a + b \boldsymbol{i} + c \boldsymbol{j} + d \boldsymbol{k}, \quad \forall \lbrace a, b, c, d \rbrace \in \mathbb{R} \rbrace,$$

and

$$q = \xi_\varsigma(\eta_1, t) + \xi_\varsigma(\eta_2, t)\boldsymbol{i} + \xi_\varsigma(\eta_3, t)\boldsymbol{j} + \xi_\varsigma(\eta_4, t)\boldsymbol{k},$$

where $\xi_\varsigma(\eta_k, t) \in \mathbb{R}$ represents each EC. Then, $q$ is delayed $\Delta \tau = 250$ ms as

$$q = \xi_\varsigma(\eta_1, t_{\omega}-\Delta\tau) + \xi_\varsigma(\eta_2, t_{\omega}-\Delta\tau)\boldsymbol{i} + \xi_\varsigma(\eta_3, t_{\omega}-\Delta\tau)\boldsymbol{j} + \xi_\varsigma(\eta_4, t_{\omega}-\Delta\tau)\boldsymbol{k}, $$


Then, we established a new $p$ quaternion form based on the initial $q$ form, as

$$p =  \xi_\varsigma(\eta_1, t_{\omega}) + \xi_\varsigma(\eta_2, t_{\omega})\boldsymbol{i} + \xi_\varsigma(\eta_3, t_{\omega})\boldsymbol{j}  + \xi_\varsigma(\eta_4, t_{\omega})\boldsymbol{k}$$

Finally, the quaternion product is expressed as

$$q p = \left( q_1p_1 - q_2^{\ast} p_2, q_2p_1 + q_1^{\ast} p_2 \right),$$

meanwhile, the bicomplex product is expressed as,

$$q \odot p = \left( q_1p_1 - q_2 p_2, q_2p_1 + q_1 p_2 \right),$$

then, we expressed the quaternion as

$$\boldsymbol{q} \equiv
    \begin{cases}
        q p &= \left( q_1p_1 - q_2^\ast p_2, q_2p_1 + q_1^\ast p_2 \right),  \\
        q \odot p &= \left( q_1p_1 - q_2 p_2, q_2p_1 + q_1 p_2 \right), 
    \end{cases}$$

## The $q p$ quaternion product
### $qp$ signal behaviour
According to above, each primary emotion yields a b-QSA time behaviour. We include the time-domain figures here

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/quaternionProduct/images/DEAPquaternionProduct.svg" alt="drawing" width="2000"/>

### $qp$ feature extraction

An statistical feature extraction is performed using the $\mu, \sigma$, and $\sigma^2$, according to the following criteria

$$\sigma^2(\boldsymbol{q}) = {\frac{N}{N-1}} {\mathbb{E} \lbrace \left(\boldsymbol{qp} - \mathbb{E}\lbrace\boldsymbol{qp}\rbrace \right)^2 \rbrace },$$

where $E\lbrace\boldsymbol{q}\rbrace$ is the expected value of $\boldsymbol{q}$, denoted by $\mu$. Statistical feature space is presented here. Figures are downsampled to reduce file sizes.

#### $\boldsymbol{\mathfrak{Re}}\lbrace qp\left(a,c\boldsymbol{i}\right)\rbrace$

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/featureExtraction/DEAP_AXIS_quaternionProduct_features_q1real.png-1.png" alt="drawing" width="2000"/>

#### $\boldsymbol{\mathfrak{Im}}\lbrace qp\left(a,c\boldsymbol{i}\right)\rbrace$

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/featureExtraction/DEAP_AXIS_quaternionProduct_features_q1imag.png-1.png" alt="drawing" width="2000"/>

#### $\boldsymbol{\mathfrak{Re}}\lbrace qp\left(b,d\boldsymbol{i}\right)\rbrace$

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/featureExtraction/DEAP_AXIS_quaternionProduct_features_q2real.png-1.png" alt="drawing" width="2000"/>

#### $\boldsymbol{\mathfrak{Im}}\lbrace qp\left(b,d\boldsymbol{i}\right)\rbrace$

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/featureExtraction/DEAP_AXIS_quaternionProduct_features_q2imag.png-1.png" alt="drawing" width="2000"/>

## The $q \odot p$ bicomplex product signal behaviour

Hence, bicomplex product shows a time-domain signal behaviour as

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/bicomplexProduct/images/DEAPbqsatimegeneral.svg" alt="drawing" width="2000"/>

## $q \odot p$ feature extraction

As in the quaternion product feature extraction, bicomplex product is performed by computing $\mu, \sigma$, and $\sigma^2$ with the 

$$\sigma^2(\boldsymbol{q}) = {\frac{N}{N-1}} {\mathbb{E} \lbrace \left(\boldsymbol{q \odot p} - \mathbb{E}\lbrace\boldsymbol{q \odot p}\rbrace \right)^2 \rbrace },$$

then, statistical feature space for bicomplex product is presented in the subsequent images.

#### $\boldsymbol{\mathfrak{Re}}\lbrace q \odot p\left(a,c\boldsymbol{i}\right)\rbrace$

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/featureExtraction/DEAP_AXIS_bicomplexProduct_features_q1real.png-1.png" alt="drawing" width="2000"/>

#### $\boldsymbol{\mathfrak{Im}}\lbrace q \odot p\left(a,c\boldsymbol{i}\right)\rbrace$

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/featureExtraction/DEAP_AXIS_bicomplexProduct_features_q1imag.png-1.png" alt="drawing" width="2000"/>

#### $\boldsymbol{\mathfrak{Re}}\lbrace q \odot p\left(b,d\boldsymbol{i}\right)\rbrace$

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/featureExtraction/DEAP_AXIS_bicomplexProduct_features_q2real.png-1.png" alt="drawing" width="2000"/>

#### $\boldsymbol{\mathfrak{Im}}\lbrace q \odot p\left(b,d\boldsymbol{i}\right)\rbrace$

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/DEAP/featureExtraction/DEAP_AXIS_bicomplexProduct_features_q2imag.png-1.png" alt="drawing" width="2000"/>
