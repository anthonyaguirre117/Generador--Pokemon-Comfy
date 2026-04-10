
# **Comfy-Tony: Generador de Imágenes Estilo Pokemon Retro** <img width="250" height="250" alt="188987" src="https://github.com/user-attachments/assets/f15f614d-472e-43be-97d4-2828b4df40df" /><img width="250" height="250" alt="Poké_Ball_icon svg" src="https://github.com/user-attachments/assets/266ef622-d26d-42e3-9fe7-66c2297ce053" />


¡Bienvenido a **Comfy-Tony**! Este repositorio contiene un flujo de trabajo optimizado para **ComfyUI**. Está diseñado para generar ilustraciones de alta calidad con un estilo retro/anime (específicamente enfocado en la temática de entrenadores Pokémon), utilizando Inteligencia Artificial generativa.

Este proyecto fue creado como una implementación técnica demostrando la conexión lógica de nodos, modelos base y modificadores de estilo (LoRAs).

#Qué hace este flujo?
El sistema toma instrucciones de texto en inglés (Prompts) y procesa la información a través del modelo Stable Diffusion 1.5. Utiliza un KSampler configurado con el algoritmo Euler para renderizar la imagen en 25 pasos, garantizando un balance ideal entre velocidad y detalle visual.

---

#**Requisitos Previos (Modelos necesarios)**

Para que este flujo funcione en tu máquina local o entorno en la nube, la IA necesita sus "ingredientes". Asegúrate de descargar y colocar los siguientes archivos en sus carpetas correspondientes dentro de tu instalación de ComfyUI:

1. **Checkpoint (Modelo Base):** * Archivo: `v1-5-pruned-emaonly-fp16.safetensors` (o cualquier equivalente SD 1.5).
   * Ruta: `ComfyUI/models/checkpoints/`
2. **LoRA (Modificador de Estilo):**
   * Archivo: *[Pokemon Trainer Sprite PixelArt.safetensors]*
   * Ruta: `ComfyUI/models/loras/`

---

#**Instrucciones de Uso**

Puedes ejecutar este flujo de manera local o a través de un servidor en la nube (como RunPod o plataformas similares).

### **Opción A: Ejecución Local**
1. Clona este repositorio o descarga el archivo `flujo_comfy_tony.json`.
2. Inicia tu servidor local de ComfyUI.
3. Arrastra y suelta el archivo `.json` directamente sobre la interfaz web de ComfyUI en tu navegador. Los nodos se conectarán automáticamente.
4. Verifica que los nodos **"Cargar Punto de Control"** y **"Cargar LoRA"** tengan seleccionados los modelos correctos.
5. Modifica los textos (cajas verde y roja) con tus propias ideas y presiona **Queue Prompt**.

### **Opción B: Ejecución en la Nube (Cloud)**
1. Inicia tu entorno de ComfyUI virtual.
2. Sube los modelos (Checkpoint y LoRA) utilizando el administrador de archivos de tu servidor a las rutas mencionadas arriba.
3. Haz clic en el botón **Load** en el menú de ComfyUI y selecciona el archivo `.json` de este repositorio.
4. ¡Genera tu imagen!

---

![comfy-tony](https://github.com/user-attachments/assets/e6257f5c-ad5d-4b2c-b393-df86fe7a619a)



## **Estructura Técnica del JSON**
Para los desarrolladores interesados en la API, el archivo JSON de este repositorio estructura el flujo de la siguiente manera:
* **Nodos 11 y 12:** Inicialización de pesos matemáticos (Checkpoint + LoRA).
* **Nodos 13 y 14:** Codificación CLIP para el procesamiento del Lenguaje Natural (Prompts).
* **Nodo 15:** Motor KSampler (Seed dinámica, CFG: 8, Pasos: 25, Denoise: 1.0).
* **Nodos 16, 17 y 18:** Definición del espacio latente (512x512), decodificación VAE y exportación final a PNG.

---
**Anthony Aguirre**
