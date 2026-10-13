# Guía Paso a Paso: Instalación y Configuración de Ollama

Esta guía detalla cómo instalar Ollama en tu computadora y preparar los modelos locales para controlar tu animatrónico de forma gratuita y sin conexión a internet.

---

## Paso 1: Instalación de Ollama

### En Windows:
1. Entra a la página oficial: **[ollama.com](https://ollama.com/)**
2. Haz clic en el botón **"Download for Windows"**.
3. Ejecuta el archivo descargado (`OllamaSetup.exe`) y sigue los pasos del asistente de instalación.
4. Una vez instalado, Ollama se ejecutará automáticamente en segundo plano (aparecerá un ícono de una llama en la bandeja del sistema, cerca del reloj).

### En Linux (Ubuntu / Debian):
Abre tu terminal y ejecuta el siguiente script oficial de instalación:
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

---

## Paso 2: Descarga del Modelo Local (`gemma2:2b`)

Para que tu sistema pueda procesar texto localmente, debes descargar los pesos del modelo recomendado (`gemma2:2b`).

1. Abre tu terminal (CMD, PowerShell o terminal de Linux).
2. Ejecuta el siguiente comando para descargar y probar el modelo:
   ```bash
   ollama run gemma2:2b
   ```
3. Espera a que termine la descarga (el indicador de porcentaje llegará al 100%). Una vez que aparezca la línea de comandos interactiva del modelo, puedes escribir `/bye` para salir. El modelo ya habrá quedado guardado permanentemente en tu disco.

---

## Paso 3: Verificación del Servicio Local

Ollama corre de manera predeterminada como un servidor local en el puerto `11434` (`http://localhost:11434`). 

* **No necesitas** tener ninguna ventana de terminal ejecutando comandos de Ollama mientras corre tu script principal de Python; el servicio en segundo plano atiende las peticiones automáticamente.

---

## Paso 4: Integración con tu Script de Python

Asegúrate de tener instalada la librería oficial de Ollama para Python ejecutando en tu terminal:
```bash
pip install ollama
```

Y utiliza la estructura basada en la función `ollama.chat()` dentro de tu bucle de control para enviar la voz transcrita y recibir de regreso el JSON estructurado para tus servomotores.