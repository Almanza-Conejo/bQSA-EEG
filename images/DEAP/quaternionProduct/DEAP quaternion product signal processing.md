
# DEAP Quaternion Product
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/quaternionPoduct/images/SEED-V%20quaternion%20product%20general.svg" alt="drawing" width="2000"/>

## The quaternion algebra
The EEG signal processing using the SEED-V dataset is based on the primitive emotion stimuli, Valence (V), Arousal (A), Dominance (D), and Linking (L). These four primitive emotions are used to classify a robust classification algorithm companding $25$-ML architectures. The DEAP dataset contains a sum of $\Xi_{s} \in \mathbb{R}^{44640 \times t}$ EEG signals, $\lbrace \Xi_{s_i} \in \mathbb{R}^{8928 \times t} \rbrace \in \Xi_{s}$ per emotion stimuli. Besides, using the [Minimum Redundance Maximum Relevance algorithm](https://doi.org/10.1142/S0219720005001004) we achieve a top four EEG Effective Channels (EC) subset based on our previous work, [**A channel selection method to find the role of the amygdala in emotion recognition avoiding conflict learning in EEG signals**](https://doi.org/10.1016/j.engappai.2023.106971). As a result, the top four effective channels for SEED-V db are: *FP1*, *CP1*, *CZ*, and *CB2*. The normalized EC score is shown in the following figure.

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/effectiveChannels/ecSEED.svg" alt="drawing" width="2000"/>

Then, we used these four effective channels to perform a quaternion form based on the *Cayley-Dickson* form, as presented in [Quaternion Fourier Transforms for Signal and Image Processing](10.1002/9781118930908). We take the premise that

$$\mathbb{H} = \lbrace q | q = a + b \boldsymbol{i} + c \boldsymbol{j} + d \boldsymbol{k}, \quad \forall \lbrace a, b, c, d \rbrace \in \mathbb{R} \rbrace,$$

and

$$q = \xi_\varsigma(\eta_1, t) + \xi_\varsigma(\eta_2, t)\boldsymbol{i} + \xi_\varsigma(\eta_3, t)\boldsymbol{j} + \xi_\varsigma(\eta_4, t)\boldsymbol{k},$$

where $\xi_\varsigma(\eta_k, t) \in \mathbb{R}$ represents each EC. Then, $q$ is delayed $\Delta \tau = 250$ ms as

$$q = \xi_\varsigma(\eta_1, t_{\omega}-\Delta\tau) + \xi_\varsigma(\eta_2, t_{\omega}-\Delta\tau)\boldsymbol{i} + \xi_\varsigma(\eta_3, t_{\omega}-\Delta\tau)\boldsymbol{j} + \xi_\varsigma(\eta_4, t_{\omega}-\Delta\tau)\boldsymbol{k}, $$


Then, we established a new $p$ quaternion form based on the initial $q$ form, as

$$p =  \xi_\varsigma(\eta_1, t_{\omega}) + \xi_\varsigma(\eta_2, t_{\omega})\boldsymbol{i} + \xi_\varsigma(\eta_3, t_{\omega})\boldsymbol{j}  + \xi_\varsigma(\eta_4, t_{\omega})\boldsymbol{k}$$

Finally, the quaternion product is expressed as

$$q p = \left( q_1p_1 - q_2^\ast p_2, q_2p_1 + q_1^\ast p_2 \right),$$

## The b-QSA signal processing behaviour
According to above, each primary emotion yields a time behaviour. We include the graphs here

### Happy
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/quaternionPoduct/images/HAPPY_quaternionProductSEEDV.svg" alt="drawing" width="2000"/>

### Disgust
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/quaternionPoduct/images/DISGUST_quaternionProductSEEDV.svg" alt="drawing" width="2000"/>

### Neutral
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/quaternionPoduct/images/NEUTRAL_quaternionProductSEEDV.svg" alt="drawing" width="2000"/>

### Fear
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/quaternionPoduct/images/FEAR_quaternionProductSEEDV.svg" alt="drawing" width="2000"/>

### Sad
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/quaternionPoduct/images/SAD_quaternionProductSEEDV.svg" alt="drawing" width="2000"/>
