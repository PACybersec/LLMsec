# 🔍 Auditoría de Vulnerabilidades en LLM con Garak

Proyecto de demostración para identificar vulnerabilidades de **Prompt Injection** en Modelos de Lenguaje Grande (LLMs), alineado con el **OWASP Top 10 for LLM Applications**.

## 🎯 Objetivo

Demostrar la aplicación de herramientas de seguridad ofensiva (**Garak**, desarrollado por LEAP / Georgia Tech) para auditar modelos de lenguaje y detectar vulnerabilidades como:

- **Prompt Injection** (LLM01)
- **Insecure Output Handling** (LLM06)
- Falta de *guardrails* en la entrada/salida

## 🛠️ Tecnologías Utilizadas

- **Garak**: Framework open-source de evaluación de vulnerabilidades en LLMs
- **Python 3.x** con entorno virtual aislado
- **Hugging Face**: Modelo local `facebook/opt-125m` (sin costos de API)
- **CachyOS (Arch Linux)**: Entorno de desarrollo

## 📊 Metodología

1. Despliegue local de un LLM de prueba (`opt-125m`)
2. Ejecución de la *probe* `dan.DAN` (técnica de jailbreaking conocida)
3. Análisis del informe generado por Garak (formato JSON/HTML)
4. Identificación de tasas de éxito en los intentos de inyección

## 🚀 Cómo Reproducir este Proyecto

```bash
# 1. Clonar el repositorio
git clone https://github.com/TU-USUARIO/garak-llm-audit.git
cd garak-llm-audit

# 2. Crear y activar entorno virtual
python -m venv venv
source venv/bin/activate.fish  # o activate para bash/zsh

# 3. Instalar dependencias
pip install --upgrade pip
pip install garak

# 4. Ejecutar la auditoría
garak --model_type huggingface --model_name facebook/opt-125m --probes dan.DAN
```

## 💡 Hallazgos y Próximos Pasos

- Implementar **guardrails de entrada** (ej. NeMo Guardrails, Llama Guard)
- Probar contra modelos con *fine-tuning* de seguridad
- Ampliar el alcance a otras probes de OWASP (data poisoning, model denial of service)

## 📚 Referencias

- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [Garak - LLM Vulnerability Scanner](https://github.com/NVIDIA/garak)
- [Documentación de Hugging Face](https://huggingface.co/docs)

---

**Autor**: Pablo Acosta A. | Máster en Ciberseguridad  
**LinkedIn**:https://www.linkedin.com/in/pablo-acosta-cybersec/ 

