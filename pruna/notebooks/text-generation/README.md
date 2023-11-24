# LLM Optimization
Pruna currently supports txt2img, img2img, inpainting, controlnet, and LoRA optimizations for all stable diffusion models.

## SmasherConfig Documentation

The `SmasherConfig` class is used to configure settings for the image processing pipeline. Here's how to set up and use the `SmasherConfig` object.

### Default Configuration

First, initialize a `SmasherConfig` object:

```python
smasher_config = SmasherConfig()
```

#### Base Configuration Parameters
These parameters need to be set for all stable diffusion pipelines
##### quantizer
If you would like to apply quantization on your LLM please set this field:
```python
smasher_config['quantizer'] = 'bitsandbytes'
```
quantization options:
- bitsandbytes
- huggingface-gptq
- auto-gptq

###### n_quantization_bits (quantizer)
Set the bit precision you want to quantize down to, lower means better gains but slightly wose performance:
```python
smasher_config['n_quantization_bits'] = 4
```

options:
- 4
- 8

##### compiler
If you would like to apply quantization + C compilation, please set the compiler field:
```python
smasher_config['compiler'] = 'ctranslate2_generation'
```
###### n_quantization_bits (compiler)
Set the bit precision you want to quantize down to, lower means better gains but slightly wose performance:
```python
smasher_config['n_quantization_bits'] = 8
```

options:
- 16
- 8
