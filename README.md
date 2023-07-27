# Generate-face-images-from-sketches
In this project we implement the approach that was mentioned in [1](https://arxiv.org/abs/1711.08972).
we try to generate real face images from bad hand drawning.
this approach containes two phases:
1- model phase:
    In this phase we build GAN model and train it on joint images(real face + its sketch that is extracted using XDOG algorithm).
2- completion phase:
    In this phase we use this steps to generate images that match the input sketches:
      - first, we refine initialize the input vector that we will pass to our generator from the previous phase,
      we calculate the Kullback-Leibler divergence between input sketch and generated sketch portion to choose the input vector that generates sketch portion with the lowest KL.
      - second, to acheive more accurate results we optimaize the input vector that we optianed from the previous step using gradient descent.

we test out project on bad hand-drawing images:
1- from this:
![A_try5](https://github.com/doaa-ali-13/Generate-face-images-from-sketches/assets/83879026/0bcc2b44-4a27-49d1-ba01-f59aeb36ff16)  
 we generate this face :
 ![smooth_male_image_15A_try5 png](https://github.com/doaa-ali-13/Generate-face-images-from-sketches/assets/83879026/afc3dc58-5ed1-416a-8b49-ebec103e18c5)

2- from this:
![A_try2](https://github.com/doaa-ali-13/Generate-face-images-from-sketches/assets/83879026/12fb7e85-6501-45ba-8b76-72290f8a423f)
we generate this face:
![smooth_male_image_15A_try2 png](https://github.com/doaa-ali-13/Generate-face-images-from-sketches/assets/83879026/b297be22-6321-4d58-b5fd-5a4600a4b88f)

    
