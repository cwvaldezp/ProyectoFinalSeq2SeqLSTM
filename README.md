# 🚀 Neural Machine Translation Seq2Seq LSTM

Proyecto Final — Curso de Aprendizaje Profundo  
Maestría en Inteligencia Artificial — USFQ  

---

## 📌 Descripción

Este proyecto implementa un sistema de **traducción automática neural Inglés → Español** utilizando una arquitectura clásica **Sequence-to-Sequence (Encoder-Decoder) basada en LSTM**, desarrollada completamente en **PyTorch**.

El objetivo principal fue construir una **línea base funcional de traducción automática**, analizar su comportamiento durante el entrenamiento y evaluar su desempeño mediante métricas cuantitativas y análisis cualitativo.

---

## 🧠 Arquitectura del Modelo

- Encoder LSTM
- Decoder LSTM
- Embeddings de 128 dimensiones
- Hidden size = 256
- Dropout = 0.2
- Teacher forcing = 0.3
- Gradient clipping
- Early stopping
- Fine-tuning desde mejor checkpoint

Arquitectura clásica **Seq2Seq sin mecanismo de atención**.

---

## 📊 Dataset

Se utilizó el dataset paralelo **English–Spanish (`spa.txt`)**.

| Split | Número de pares |
|------|----------------|
| Train | 83,055 |
| Validation | 23,730 |
| Test | 11,865 |
| **Total** | **118,650** |

Se aplicó:

- Normalización textual
- Tokenización
- Construcción de vocabularios
- Padding dinámico
- DataLoaders con batch size = 64

---

## ⚙️ Entrenamiento

- Optimizador: Adam  
- Learning Rate inicial: 0.001  
- Máximo 50 épocas  
- Early stopping (patience = 10)  

### 📉 Mejor resultado entrenamiento base

- **Validation Loss:** 3.1956 (Epoch 12)

---

## 🔬 Fine-Tuning

Se realizó fine-tuning desde el mejor checkpoint:

- Learning Rate reducido: 0.0003  
- Patience = 3  

### 📉 Resultado final

| Modelo | Test Loss |
|-------|-----------|
| Base | 3.2492 |
| Fine-Tuned | **3.1942** |

---

## 📈 Métrica BLEU

- **BLEU Score:** 0.1226  

Consistente con modelos Seq2Seq clásicos sin atención.

---

## 🧪 Resultados Cualitativos

✔ Traducciones coherentes en frases simples  
⚠ Repeticiones de palabras  
⚠ Errores de concordancia  
⚠ Dificultades en oraciones largas  

Limitaciones asociadas al **cuello de botella del vector de contexto**.

---

## 🚀 Posibles Mejoras

- Incorporar **Attention Mechanism**
- Encoder Bidireccional
- Beam Search
- Transformers
- Subword Tokenization (BPE)

---

## 🛠 Tecnologías

- Python  
- PyTorch  
- NumPy  
- Matplotlib  
- Jupyter Notebook  

---

## 👨‍🎓 Autor

**Carlos Valdez P.**  
Maestría en Inteligencia Artificial  
Universidad San Francisco de Quito  

---
