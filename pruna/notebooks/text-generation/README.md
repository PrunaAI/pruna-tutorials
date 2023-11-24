# LLM Optimization
 Pruna supports an extensive array of Casual Language Models (CasualLM) from the [Hugging Face Transformers library](https://huggingface.co/transformers/). Our optimizations are designed to work fluidly with these powerful models, facilitating the generation of natural language text with unprecedented ease and flexibility. We currently support several compression techniques including quantization and c translation.

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
