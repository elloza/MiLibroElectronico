# 2. El paper de Transformers

Este capitulo resume el paper ubicado en la carpeta recursos del proyecto (`recursos/paper_transformers.pdf`):
**Attention Is All You Need** (Vaswani et al., NeurIPS 2017).

## Idea principal

La propuesta central es reemplazar redes recurrentes y convolucionales por un modelo basado solo en atencion.
Ese modelo se llama **Transformer**.

En vez de procesar token a token como un RNN, el Transformer puede procesar todos los tokens en paralelo durante entrenamiento.

## Que problema resolvia

En traduccion automatica y otras tareas de secuencias, los modelos previos:

- eran mas lentos de entrenar por su naturaleza secuencial,
- tenian mas dificultad para capturar dependencias largas,
- y escalan peor cuando la secuencia crece.

El paper muestra que la autoatencion reduce estos limites y mejora calidad + velocidad.

## Componentes clave del Transformer

1. **Self-Attention**: cada token atiende a otros tokens de la misma secuencia.
2. **Scaled Dot-Product Attention**: atencion con producto punto escalado por $\sqrt{d_k}$.
3. **Multi-Head Attention**: varias "cabezas" de atencion en paralelo para capturar relaciones distintas.
4. **Positional Encoding**: como no hay recurrencia, se inyecta informacion de posicion con senos y cosenos.
5. **Bloques Encoder-Decoder**: pilas de capas con atencion, redes feed-forward, residual y layer normalization.

## Resultados del paper

Segun el propio paper:

- supera el estado del arte en WMT14 English-German,
- logra resultados muy fuertes en WMT14 English-French,
- y reduce de forma importante el coste de entrenamiento frente a sistemas anteriores.

## Por que fue tan influyente

Este trabajo cambio el rumbo del aprendizaje profundo para lenguaje y despues para muchas otras areas.
Modelos como BERT, GPT y muchos LLM actuales usan la base conceptual del Transformer.

## Resumen en una frase

El paper demuestra que **la atencion por si sola** puede ser el nucleo de modelos de secuencia mas precisos, paralelizables y escalables que las alternativas recurrentes clasicas.
