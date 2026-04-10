{
  "11": {
    "inputs": {
      "ckpt_name": "v1-5-pruned-emaonly-fp16.safetensors"
    },
    "class_type": "CheckpointLoaderSimple",
    "_meta": {
      "title": "Cargar Punto de Control"
    }
  },
  "12": {
    "inputs": {
      "lora_name": "flux1-pokemon_trainer_sprite_pixelart.safetensors",
      "strength_model": 1,
      "strength_clip": 1,
      "model": [
        "11",
        0
      ],
      "clip": [
        "11",
        1
      ]
    },
    "class_type": "LoraLoader",
    "_meta": {
      "title": "Cargar LoRA"
    }
  },
  "13": {
    "inputs": {
      "text": "realistic, ",
      "clip": [
        "12",
        1
      ]
    },
    "class_type": "CLIPTextEncode",
    "_meta": {
      "title": "Codificar Texto CLIP (Prompt)"
    }
  },
  "14": {
    "inputs": {
      "text": "pokemon, trainer, battle, fire, water",
      "clip": [
        "12",
        1
      ]
    },
    "class_type": "CLIPTextEncode",
    "_meta": {
      "title": "Codificar Texto CLIP (Prompt)"
    }
  },
  "15": {
    "inputs": {
      "seed": 618807423325943,
      "steps": 25,
      "cfg": 8,
      "sampler_name": "euler",
      "scheduler": "simple",
      "denoise": 1,
      "model": [
        "12",
        0
      ],
      "positive": [
        "14",
        0
      ],
      "negative": [
        "13",
        0
      ],
      "latent_image": [
        "16",
        0
      ]
    },
    "class_type": "KSampler",
    "_meta": {
      "title": "KSampler"
    }
  },
  "16": {
    "inputs": {
      "width": 512,
      "height": 512,
      "batch_size": 1
    },
    "class_type": "EmptyLatentImage",
    "_meta": {
      "title": "Imagen Latente Vacía"
    }
  },
  "17": {
    "inputs": {
      "samples": [
        "15",
        0
      ],
      "vae": [
        "11",
        2
      ]
    },
    "class_type": "VAEDecode",
    "_meta": {
      "title": "Decodificación VAE"
    }
  },
  "18": {
    "inputs": {
      "filename_prefix": "ComfyUI",
      "images": [
        "17",
        0
      ]
    },
    "class_type": "SaveImage",
    "_meta": {
      "title": "Guardar Imagen"
    }
  }
}
