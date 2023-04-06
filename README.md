# Text-to-Art-image-Generator
Graduation Project Description 2022

## Introduction
The AI art apps generate images by simply typing a brief description of what we want to see, no matter what we type, the app will generate something visually compelling that matches our prompt in often surprisingly opposite ways. This sort of AI-generated artwork is becoming higher quality and more accessible. Past examples of these sorts of text-to-image models have included research-orientated programs like DALL-E and VQGAN+CLIP, as well as more specialized commercial projects like Art breeder (which is particularly good at creating portraits of fictional beings and people). Generally, programs like these are trained on vision datasets — huge libraries of images that are tagged based on objects and scenery.

## Scope
We focus on model architecture and learning paradigms to learn more about the strengths and weaknesses of generative models applied in text-to-image. We also try to organize these works to show development over the years. Also, we mention top-powered tools and applications that are used at present. Finally, we emphasize existing and future challenges.

## Objectives
Images are more attractive compared to text. Visual aids can deliver information more directly. Visual content grabs the attention and keeps people engaged. Key activities such as presentation, learning, and all involve visual Communication to some degree. If designed well, it offers numerous benefits.

## Generative Models
- Generative models allow to synthesize novel data that is different from the real data but still looks just as realistic. A designer could train a generative model on images of cars and then let the resulting generative AI computationally dream up novel cars with different looks, accelerating the artistic prototyping process.
- There are Four types of generative models, GAN, VAE, Flow-based models, and Diffusion models. They have shown great success in generating high-quality samples, but each has some limitations of its own.
![182920524-381d8414-a61d-48d6-8378-3e10721ac879](https://user-images.githubusercontent.com/63863517/230326745-1982a6db-cda0-4588-aea7-af92ba698d41.png)

## Transformer & Taming transformer 
- Transformer allow us to learning the complex relationships between the inputs, in other words that make them expressive. However, this is computationally expensive for long-range sequences.
- To keep the sequence length small and to harness the expressiveness of the transformer, the taming transformer uses a separate codebook for learned representations (inspired by VQ-VAE).
- Any image can be represented by a spatial collection of codebook entries , where nz is the dimensionality of codes.
- Taming use  VQ-GAN, a variant of the original VQ-VAE that uses a discriminator and perceptual loss to keep good perceptual quality at increased compression rate.
### This is a two-step training architecture design:
- Training the VQ-GAN and learning the quantized codebook.
- Training an autoregressive transformer using the quantized codebook as sequential input to the transformer. 
### 1) Training the VQ-GAN and learning the quantized codebook :
![Training the VQ-GAN](https://user-images.githubusercontent.com/63863517/230320180-351568d6-1ecf-46c1-8209-1120d078c7db.png)
#### Loss funtions of vqGan:
- VQ Loss.
- GAN Loss.
### 2) Train Transformer : 
we represent the images in terms of the codebook-indices of their embeddings. 
![codebook ](https://user-images.githubusercontent.com/63863517/230322079-494f2dd8-90b9-4e97-b38a-05546b5db9a5.png)

- In many images synthesis tasks, a user demands control over the generation process by providing additional information. This information, which we will call c.
- The task is then to learn the likelihood of the sequence given this information c .    
![taming](https://user-images.githubusercontent.com/63863517/230323981-e500795f-aea2-47b5-af71-b3f8e187d3c8.png)
![taming2](https://user-images.githubusercontent.com/63863517/230323984-f6835c51-153f-414e-9bfd-b3cd28e62c2d.png)
### To generate high-resolution images and reduce computational cost, sliding attention can be used instead of full attention.
![high-resolution](https://user-images.githubusercontent.com/63863517/230323973-f0daec96-8411-4647-ba90-17674b5d2197.png)



## Our model
- Based on CLIP + VQGAN from Taming Transformers.
- various CLIP models (incl. multi-language from SBERT).
- optimization with SIREN.

| Command | Description |
| --- | --- |
| `git status` | List all *new or modified* files |
| `git diff` | Show file differences that **haven't been** staged |


## Results (Before & After Optimization)
1. VQGAN_model = "imagenet_f16-16384" , model = "ViT-B/32" , style = "Classicism"
| Prompt | Before | after |
| --- | --- | --- |
| `'cosmic crystals of jelly and fire flowers'` | ![azhar gamela befor](https://user-images.githubusercontent.com/63863517/230329716-cf44b4ca-aef7-47c8-8aad-8ded7bb5cb16.png)
 | ![azhar gamela after](https://user-images.githubusercontent.com/63863517/230329813-41d7fa4b-1376-48af-9724-3b402b52a548.png)
 |

