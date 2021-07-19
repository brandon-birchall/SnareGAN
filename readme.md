# SnareGAN

Using Deep Convolution Generative Adversarial Networks to generate snare drum sounds

# Results

After 30 Epochs (Around 20 minutes of training on Google Colab with GPU Acceleration) the model clearly shows similarities with an actual snare sound:

*Coloured images show short-time fourier transform output*

## Generated Snare sound

![Final output](https://user-images.githubusercontent.com/47565873/126161264-82d4f615-180a-4729-87f9-82e11e33098a.png)

## Actual Snare sound from dataset

![CorrectOutput](https://user-images.githubusercontent.com/47565873/126161195-6494c8cc-b007-42af-aadc-a6d7f2c7860f.png)

## Discussion of results

Clearly, the model has learned that a snare sound typically has a transient (The initial peak), however in this example has placed two transients. This could be due to examples in the dataset with two transients.

Additionally, the STFT analysis shows strong similarities. With the initial first peak and subsequent tail noise.

However, there is no smooth tail, it is fairly abrubt. Additionally, on listening to the output, it sounds 'squeeky' with a noticable wet sounding noise. 

# Further work

The losses were tracked during training:

![Losses at Epoch 30](https://user-images.githubusercontent.com/47565873/126162030-06d4a155-34b3-49a9-b763-80e859a44ff3.png)


As you can see, the loss of the discriminator is converging to zero, however not-so in a fast/reliable manner. This may imply that a different discriminator design is needed. It is unknown due to lack of resources whether this model would produce better results given more training, although there is a good chance that as the loss for the discriminator decreased, eventually it would start to increase as the generator improves. 

# Usage
Click on 'SnareGAN.ipynb' to view to notebook
