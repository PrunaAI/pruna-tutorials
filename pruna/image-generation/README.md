# Stable Diffusion Optimization
Pruna is able to optimize the state of the art in image generation including for [Stable Diffusion (SD)](https://arxiv.org/abs/2112.10752) and preliminary support for [Consistency models](https://arxiv.org/abs/2303.01469). Our tool enhances txt2img, img2img, inpainting, controlnet, and LoRA optimizations, integrating seamlessly with all stable diffusion models. Dive deeper into the capabilities of SD models, which are pivotal in generating high-fidelity images from textual descriptions. Meanwhile, Consistency models, essential for maintaining coherent attributes in sequential model outputs, are also supported. Explore the full spectrum of Pruna's capabilities to elevate your projects.

## SmasherConfig Documentation

The `SmasherConfig` class is used to configure settings for the image processing pipeline. Here's how to set up and use the `SmasherConfig` object.

### Default Configuration

First, initialize a `SmasherConfig` object:

```python
smasher_config = SmasherConfig()
```

#### Base Configuration Parameters
These parameters need to be set for all stable diffusion pipelines
##### compiler
Always set the compiler to 'diffusers':
```python
smasher_config['compiler'] = 'diffusers'
```
##### max_batch_size
Set the batch size you would like to use after the model is compressed:
```python
smasher_config['max_batch_size'] = 1
```
In case you would like to support a variable batch size up to max_batch_size specify the static_batch parameter to False:
```python
smasher_config['static_batch'] = False
```
##### image_height and image_width
Set the image height and width you would like to use after the model is compressed:
```python
smasher_config['image_height'] = 512
smasher_config['image_width'] = 512
```
In case you would like to support a variable image height and width up to image_height and image_width specify the static_shape parameter to False:
```python
smasher_config['static_shape'] = False
```
##### version
Specify the version of your 
```python
smasher_config['version'] = '1.5'
```
Version options:
- 1.4
- 1.5
- 2.0-base
- 2.0
- 2.1-base
- 2.1
- xl-1.0

#### Inpaint Configuration Parameters
Specify your UNET dimension (default=9):
```python
smasher_config['unet_dim'] = 9
```

#### Controlnet Configuration Paramters
Set controlnet to True:
```python
smasher_config['controlnet'] = True
```

#### Consistency Models
Set scheduler to "LCMScheduler":
```python
smasher_config['scheduler'] = "LCMScheduler"
```