Lámpara Interactiva — Interfaz Sinestésica & Web Audio / Web Serial

Lienzo de arte sinestésico y aplicación web modular que traduce audio ambiental en tiempo real y perfiles emocionales en color, controlando de manera bidireccional una tira LED NeoPixel física a través de la API Web Serial y Arduino.

💡 Descripción General del Proyecto

Este proyecto explora la intersección entre el diseño computacional, la electrónica aplicada y la interacción humano-computador. La aplicación web analiza el flujo de audio del entorno (capturado por micrófono), clasifica la atmósfera acústica mediante un motor heurístico de energía, brillo y transitorios de graves, y genera dinámicas visuales de partículas en un canvas HTML5 junto con una Rosa Cromática interactiva.

Simultáneamente, transmite los valores RGB y los modos de transición seleccionados directamente a un microcontrolador físico mediante comunicación serial a 9600 baudios.

🛠️ Especificaciones de la Lámpara Física & Prototipado

El desarrollo del hardware y la carcasa física se estructuró bajo un riguroso proceso de prototipado iterativo y diseño paramétrico:

Microcontrolador: Arduino Uno.

Sistema lumínico: Tira de LEDs direccionables WS2812B conectada al pin digital PWM ~6 de Arduino.

Prototipado electrónico: Montaje inicial y validación de pulsos en protoboard de 30 filas, utilizando etapas de temporización y filtrado de corriente con capacitores de desacoplamiento para evitar caídas de tensión en los transitorios de brillo.

Estructura y Envolvente (Fabricación Digital): Diseño volumétrico enfocado en optimización de materiales. Prototipado de piezas estructurales preparadas en Rhino 8 para corte láser de precisión (material MDF de 3mm), ensambladas y selladas con adhesivo cianoacrilato.

Interfaz de Control Local: Integración de potenciómetro físico y matriz de pulsos lumínicos para emular dinámicas de ondas de marea ("Marea").

✨ Características Principales

Análisis Sinestésico en Tiempo Real: Captura de audio ambiental con umbrales de sensibilidad configurables y supresión de ruido.

Rosa Cromática Interactiva: Anillo de 12 sectores cromáticos normalizados con control de selección libre o guiado por emociones.

Efectos Lumínicos Modulares:

Suave (Fade): Interpolación exponencial fluida de color.

Pulso (Beat): Reacción rítmica directa a los graves (bass).

Marea (Chaser): Olas de desplazamiento horizontal.

Respiración (Breath) y Estrellas (Sparkle).

Conectividad Web Serial: Comunicación nativa con placas Arduino para sincronización de hardware sin drivers intermedios.

Detección Dinámica de Género Musical: Consulta asíncrona optimizada con caché local a la API de iTunes para afinar la matriz emotiva según el flujo acústico.

Soporte de Temas (Automático / Día / Noche): Adaptación visual según la hora local del sistema.

🚀 Instalación y Uso Local

Al preferir arquitecturas autocontenidas y livianas sin dependencias externas pesadas:

Clona este repositorio en tu equipo:

git clone https://github.com/tu-usuario/lampara-interactiva.git


Abre la carpeta del proyecto en tu entorno de desarrollo (por ejemplo, Visual Studio Code).

Levanta un servidor local liviano utilizando la extensión Live Server de VS Code para asegurar el correcto funcionamiento de los contextos seguros (localhost o https) requeridos por las APIs de Web Audio y Web Serial.

Conecta tu Arduino Uno con el sketch correspondiente cargado en el puerto serial.

🔌 Protocolo de Comunicación Serial

La aplicación web envía tramas de texto plano terminadas en salto de línea (\n) con la siguiente estructura:

RGB:R,G,B,EFECTO,VELOCIDAD\n


R, G, B: Valores enteros de 0 a 255.

EFECTO: Patrón lumínico activo (fade, pulse, wave, breath, sparkle).

VELOCIDAD: Factor multiplicador flotante (ej. 1.0).

📐 Stack Tecnológico

Frontend: HTML5 Canvas, CSS3 Custom Properties, JavaScript ES6+ (Vanilla).

Audio Processing: Web Audio API (AnalyserNode, getByteFrequencyData).

Hardware & Firmware: Arduino IDE, C++, FastLED / Adafruit NeoPixel (para WS2812B).

Diseño & CAD: Rhinoceros 8 (Modelado paramétrico y optimización de corte láser).
