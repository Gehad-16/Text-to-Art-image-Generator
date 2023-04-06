# Text-to-Art-image-Generator
Graduation Project Description 2022

## Introduction
The AI art apps generate images by simply typing a brief description of what we want to see, no matter what we type, the app will generate something visually compelling that matches our prompt in often surprisingly opposite ways. This sort of AI-generated artwork is becoming higher quality and more accessible. Past examples of these sorts of text-to-image models have included research-orientated programs like DALL-E and VQGAN+CLIP, as well as more specialized commercial projects like Art breeder (which is particularly good at creating portraits of fictional beings and people). Generally, programs like these are trained on vision datasets — huge libraries of images that are tagged based on objects and scenery.

## Scope
We focus on model architecture and learning paradigms to learn more about the strengths and weaknesses of generative models applied in text-to-image. We also try to organize these works to show development over the years. Also, we mention top-powered tools and applications that are used at present. Finally, we emphasize existing and future challenges.

## Objectives
Images are more attractive compared to text. Visual aids can deliver information more directly. Visual content grabs the attention and keeps people engaged. Key activities such as presentation, learning, and all involve visual Communication to some degree. If designed well, it offers numerous benefits.

## Generative Models
Generative models allow to synthesize novel data that is different from the real data but still looks just as realistic. A designer could train a generative model on images of cars and then let the resulting generative AI computationally dream up novel cars with different looks, accelerating the artistic prototyping process.
There are Four types of generative models, GAN, VAE, Flow-based models, and Diffusion models. They have shown great success in generating high-quality samples, but each has some limitations of its own.

## Transformer & Taming transformer 
- Transformer allow us to learning the complex relationships between the inputs, in other words that make them expressive. However, this is computationally expensive for long-range sequences.
- To keep the sequence length small and to harness the expressiveness of the transformer, the taming transformer uses a separate codebook for learned representations (inspired by VQ-VAE).
- Any image can be represented by a spatial collection of codebook entries , where nz is the dimensionality of codes.
- Taming use  VQ-GAN, a variant of the original VQ-VAE that uses a discriminator and perceptual loss to keep good perceptual quality at increased compression rate.
### This is a two-step training architecture design:
- Training the VQ-GAN and learning the quantized codebook.
- Training an autoregressive transformer using the quantized codebook as sequential input to the transformer. 
#### 1) Training the VQ-GAN and learning the quantized codebook.



## Our model
Based on CLIP + VQGAN from Taming Transformers.
various CLIP models (incl. multi-language from SBERT).
optimization with SIREN

![gg](https://user-images.githubusercontent.com/63863517/230315975-141e526a-5763-48b0-b290-bcc205e81763.png)



## Results (Before & After Optimization)
