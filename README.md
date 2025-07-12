# Traductor-Voz-Texto

![Python](https://img.shields.io/badge/python-3.9%2B-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

Aplicación de traducción **voz ↔ texto** en tiempo real.  
Permite hablar al micrófono y escuchar el resultado traducido (opcionalmente con tu propia voz clonada), o introducir texto y obtener la traducción hablada/escrita.

---

## 🚀 Funciones principales
- Reconocimiento de voz (SpeechRecognition + micrófono local).
- Detección y traducción automática de idioma (Googletrans 4.* async).
- Síntesis de voz:
  - Voces estándar (gTTS).
  - Clonación de voz local “zero-shot” (Coqui XTTS v2 opcional).
- Modo CLI y Notebook.
- Compatible con Windows / Linux, CPU o GPU.

---

## 📸 Demo rápida

| Grabación | Traducción | Re-síntesis |
|-----------|------------|-------------|
| ![demo-gif](docs/demo.gif) | “Hello, how are you?” → “Hola, ¿cómo estás?” | ![audio badge](docs/audio_badge.svg) |

---

## 🏗️ Arquitectura

```text
┌──────────┐   audio    ┌─────────────────┐   texto  ┌─────────────┐   texto    ┌──────────┐
│ Micrófono├──────────▶│ SpeechRecognition├────────▶│ Googletrans │──────────▶│   TTS    │
└──────────┘            └─────────────────┘          └─────────────┘            └──────────┘
                        (voi­ce->text)               (lang detect & translate)      (text->speech)