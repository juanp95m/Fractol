<div align="center">
  <a href="README_en.md">🇺🇸 English</a> | <b>🇪🇸 Español</b>
</div>

---

# 🌌 Fract-ol - Renderizador Interactivo de Fractales
Este proyecto es una inmersión gráfica en el mundo de las matemáticas mediante C, enfocado en calcular y visualizar la infinita complejidad de los fractales (Mandelbrot y Julia) usando la librería gráfica **MLX42**.

## 📖 Introducción al Proyecto
Fract-ol ilustra el poder de los números complejos y la optimización en la programación gráfica:

* Calcula si un punto en un plano complejo escapa al infinito o permanece acotado.
* Dependiendo de la velocidad de escape del punto, se le asigna un color dinámico.
* Soporte nativo para renderizar el **Conjunto de Mandelbrot** y el **Conjunto de Julia**.
* Permite interacción en tiempo real: zoom profundo y desplazamiento por el plano.

## 🚀 Compilación e Instrucciones de Uso
Para compilar el proyecto (asegúrate de cumplir las dependencias de MLX42 y GLFW):
```bash
make
```

### Ejecución y Parámetros
```bash
./fractol [tipo_fractal] [parametros_opcionales]
```

* **Mandelbrot**:
  ```bash
  ./fractol mandelbrot
  ```
* **Julia**: (Requiere dos valores decimales para representar el número complejo `c`)
  ```bash
  ./fractol julia <real> <imaginario>
  
  # Ejemplos sorprendentes:
  /fractol julia -0.4 0.6     (spiral)
	./fractol julia 0.285 0.01   (dendrites)
	./fractol julia -0.70176 -0.3842  (lightning)
	./fractol julia -0.835 -0.2321  (dragon)
	./fractol julia -0.8 0.156    (galaxy)
  ```

## 📂 Arquitectura del Proyecto
```text
Fractol/
├── Makefile       # Reglas de compilación automatizadas
├── fractol.h      # Declaraciones, macros y estructuras de datos
├── libft/         # Librería estandarizada propia de 42
├── MLX42/         # Librería gráfica (wrapper de GLFW)
└── *.c            # Archivos fuente (main, render, hooks, math, etc.)
```

## 🎮 Controles Interactivos
El explorador fractal cuenta con las siguientes funcionalidades mapeadas:

* **Ratón (Rueda)**: Realiza Zoom In / Zoom Out centrado en el puntero.
* **Teclas Direccionales (Flechas)**: Desplazamiento (paneo) a lo largo del fractal.
* **Teclado (ESC)**: Finaliza el programa limpiamente.
* **Botón ❌**: Cierra la ventana y libera recursos.

## 🛠️ Aspectos Técnicos
* **Gráficos**: Uso extensivo de MLX42 para inyectar píxeles en un búfer de imagen (Image buffer) en lugar de dibujar píxel por píxel en la ventana, maximizando el rendimiento.
* **Matemáticas Complejas**: Algoritmos eficientes para la iteración de números imaginarios.
* **Manejo de Eventos (Hooks)**: Callbacks precisos para redibujar la pantalla solo cuando el usuario interactúa.
* **Gestión de Memoria**: Aislamiento estricto de recursos y liberación total de texturas y ventanas al salir (sin *memory leaks*).

## 🎯 Metas de Aprendizaje
* Programación de interfaces gráficas básicas en `C`.
* Optimización algorítmica para tareas de renderizado intensivo.
* Gestión de ventanas, eventos y *hooks* asíncronos en MLX42.
* Parseo robusto de argumentos de línea de comandos (incluyendo números en coma flotante).
