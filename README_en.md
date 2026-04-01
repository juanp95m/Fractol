<div align="center">
  <b>🇺🇸 English</b> | <a href="README.md">🇪🇸 Español</a>
</div>

---

# 🌌 Fract-ol - Interactive Fractal Renderer
This project is a graphical plunge into the realm of mathematics using C, focused on calculating and visualizing the infinite complexity of fractals (Mandelbrot and Julia) using the **MLX42** graphic library.

## 📖 Project Introduction
Fract-ol illustrates the power of complex numbers and optimization in computer graphics:

* Calculates whether a point in a complex plane escapes to infinity or remains bounded.
* Points are colored dynamically depending on their iteration escape velocity.
* Native support for rendering the **Mandelbrot Set** and the **Julia Set**.
* Real-time interaction: deep zooming and seamless panning across the mathematical plane.

## 🚀 Compilation and Usage
To build the project (ensure MLX42 / GLFW dependencies are met):
```bash
make
```

### Execution and Parameters
```bash
./fractol [fractal_type] [optional_parameters]
```

* **Mandelbrot**:
  ```bash
  ./fractol mandelbrot
  ```
* **Julia**: (Requires two floating-point values representing the complex number `c`)
  ```bash
  ./fractol julia <real> <imaginary>
  
  # Stunning examples:
/fractol julia -0.4 0.6     (spiral)
	./fractol julia 0.285 0.01   (dendrites)
	./fractol julia -0.70176 -0.3842  (lightning)
	./fractol julia -0.835 -0.2321  (dragon)
	./fractol julia -0.8 0.156    (galaxy)
  ```

## 📂 Project Architecture
```text
Fractol/
├── Makefile       # Automated compilation rules
├── fractol.h      # Declarations, macros, and core data structures
├── libft/         # Custom 42 standard C library
├── MLX42/         # Graphics library (GLFW wrapper)
└── *.c            # Source code (main, rendering, hooks, math, etc.)
```

## 🎮 Interactive Controls
The fractal explorer implements the following keybinds and mouse events:

* **Mouse Wheel**: Zoom In/Out targeted at the cursor's coordinates.
* **Arrow Keys**: Pan/Move around the continuous fractal map.
* **ESC Key**: Cleanly exit the program.
* **Window ❌ Button**: Safely close window and free all resources.

## 🛠️ Technical Aspects
* **Graphics Rendering**: Heavy use of MLX42 to inject pixels into an image buffer instead of putting pixels straight to the window, maximizing performance.
* **Complex Math**: Highly optimized recursive/iterative algorithms for complex coordinates mapping.
* **Event Handling (Hooks)**: Dedicated callbacks to redraw the image buffer only upon user interaction.
* **Memory Management**: Strict resource confinement and safe destruction on exit (zero memory leaks).

## 🎯 Learning Objectives
* Basic Graphical User Interface programming in `C`.
* Algorithmic optimization for computationally heavy loop iterations.
* Window and asynchronous event/hook management in MLX42.
* Robust parsing of command-line arguments (including floating-point numbers structure).
