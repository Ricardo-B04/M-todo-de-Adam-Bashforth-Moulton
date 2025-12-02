# Método de Adams-Bashforth-Moulton (4to Orden)

Implementación del método numérico **Predictor-Corrector Adams-Bashforth-Moulton** de 4to orden para resolver Problemas de Valor Inicial (PVI).

## Problema Resuelto

Se resuelve la ecuación diferencial ordinaria:

$$\frac{dy}{dt} = (t - y)^2, \quad y(0) = 0$$

Con solución analítica:

$$y(t) = t - \tanh(t)$$

## Contenido del Notebook

1. **Introducción y Solución Analítica**: Derivación paso a paso de la solución exacta usando sustitución.
2. **Método Numérico**: Explicación teórica del esquema Predictor-Corrector (AB4/AM4).
3. **Pseudocódigo**: Algoritmo detallado incluyendo la fase de arranque con RK4.
4. **Implementación en Python**: Código modular y documentado.
5. **Visualización**: Gráficas de comparación y análisis de error.
6. **Conclusión**: Análisis de precisión, estabilidad y eficiencia.

## Requisitos

```bash
pip install -r requirements.txt
```

### Dependencias
- `numpy`
- `matplotlib`

## Uso

### En VS Code
Abre el archivo `adams_bashforth_moulton.ipynb` directamente en VS Code con la extensión de Jupyter.

### En Jupyter Notebook
```bash
pip install jupyter
jupyter notebook adams_bashforth_moulton.ipynb
```

### En JupyterLab
```bash
pip install jupyterlab
jupyter lab adams_bashforth_moulton.ipynb
```

## Método Numérico

### Predictor (Adams-Bashforth 4 pasos)
$$y_{n+1}^P = y_n + \frac{h}{24} (55 f_n - 59 f_{n-1} + 37 f_{n-2} - 9 f_{n-3})$$

### Corrector (Adams-Moulton 3 pasos)
$$y_{n+1} = y_n + \frac{h}{24} (9 f(t_{n+1}, y_{n+1}^P) + 19 f_n - 5 f_{n-1} + f_{n-2})$$

### Arranque
Se utiliza **Runge-Kutta de 4to orden (RK4)** para calcular los primeros 3 valores ($y_1, y_2, y_3$).

## Resultados

El método ABM4 logra errores del orden de $10^{-8}$ con paso $h = 0.05$, confirmando la precisión de 4to orden ($O(h^4)$).

## Autor

Ricardo B.

## Licencia

Este proyecto es de uso educativo para el curso de **Modelación de Sistemas con Ecuaciones Diferenciales**.
