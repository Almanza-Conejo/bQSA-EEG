# EEG scaled behaviour

After the Wavelet Denoised (WD), we perform a scaling function to modify the magnitude of WD-EEG. The entry EEG signal is processed following a min-max criteria as:

$$\xi_\varsigma(t) = \xi_\psi(t) - \frac{\underset{}{\min}\left(\xi_\psi(t)\right)}{\underset{}{\max}\left(\xi_\psi(t)\right) - \underset{}{\min}\left(\xi_\psi(t)\right)},$$

where $\xi_\psi(t)$ represents the WD-EEG and $\xi_\varsigma(t)$ the scaled EEG. The emotions time behaviour is represented in the following figure

<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/scalledBehaviour/SEED-V%20scaled%20general.svg" alt="drawing" width="2000"/>

## Happy
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/scalledBehaviour/HAPPY_scaledSEEDV.svg" alt="drawing" width="2000"/>

## Disgust
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/scalledBehaviour/Disgust_scaledSEEDV.svg" alt="drawing" width="2000"/>

## Neutral
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/scalledBehaviour/NEUTRAL_scaledSEEDV.svg" alt="drawing" width="2000"/>

## Fear
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/scalledBehaviour/FEAR_scaledSEEDV.svg" alt="drawing" width="2000"/>

## Sad
<img src="https://github.com/Almanza-Conejo/bQSA-EEG/blob/main/images/SEED-V/scalledBehaviour/SAD_scaledSEEDV.svg" alt="drawing" width="2000"/>
