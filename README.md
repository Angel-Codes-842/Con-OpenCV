-----

# Detección Facial en Tiempo Real con OpenCV

Este script de Python utiliza **OpenCV** para realizar detección facial en tiempo real usando la cámara web de tu computadora. Detecta rostros en el feed de video y los marca con un recuadro verde.

-----

## Requisitos

Para ejecutar este script, necesitarás tener instalado **OpenCV** en tu entorno Python.

Puedes instalarlo usando pip:

```bash
pip install opencv-python
```

-----

## Cómo Ejecutar

1.  Asegúrate de tener una cámara web conectada y funcional.

2.  Guarda el código proporcionado en un archivo Python (por ejemplo, `Deteccion de rostros.py`).

3.  Ejecuta el script desde tu terminal:

    ```bash
    python Deteccion de rostros.py
    ```

Una ventana se abrirá mostrando el feed de tu cámara web con los rostros detectados resaltados.

-----

## Uso

  * El script inicializará la cámara web y comenzará a mostrar el video en vivo.
  * Los rostros detectados serán marcados con un **recuadro verde**.
  * Para salir de la aplicación, presiona la tecla **'q'** en tu teclado.

-----

## ¿Cómo funciona?

El script realiza los siguientes pasos:

1.  **Importa OpenCV:** `import cv2`
2.  **Carga el clasificador Haar Cascade:** Utiliza el archivo pre-entrenado `haarcascade_frontalface_default.xml` para detectar rostros frontales. Este archivo es parte de la distribución de OpenCV.
3.  **Inicia la captura de video:** `cv2.VideoCapture(0)` accede a la cámara web predeterminada (generalmente la cámara integrada).
4.  **Bucle principal:**
      * Lee cada fotograma de la cámara (`capture.read()`).
      * Convierte el fotograma a escala de grises (`cv2.cvtColor`). La detección facial a menudo funciona mejor en escala de grises.
      * Aplica el clasificador de rostros (`face_cascade.detectMultiScale`) para encontrar rostros en el fotograma. Los parámetros `scaleFactor` y `minNeighbors` ajustan la precisión de la detección.
      * Para cada rostro detectado, dibuja un **recuadro verde** alrededor de él (`cv2.rectangle`).
      * Muestra el fotograma resultante en una ventana (`cv2.imshow`).
      * Verifica si la tecla **'q'** ha sido presionada para salir del bucle.
5.  **Libera los recursos:** Una vez que el bucle termina, se libera la cámara (`capture.release()`) y se cierran todas las ventanas de OpenCV (`cv2.destroyAllWindows()`).

-----

## Contribuciones

Siéntete libre de contribuir o mejorar este script.

-----
