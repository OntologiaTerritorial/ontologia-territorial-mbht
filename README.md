<div align="center">
  <h1>Ontología Territorial y Geotensores</h1>
  <h3>Deformación Geotensorial de la Matriz de Bienestar Humano Territorial (MBHT)</h3>
</div>

<br>

Este repositorio aloja la validación empírica y la visualización interactiva del modelo geotensorial aplicado a la **Matriz de Bienestar Humano Territorial (MBHT)** de Chile. Es el resultado de la aplicación práctica de los axiomas establecidos en los tomos I y II de la obra *Ontología Territorial*.

---

## 🔗 Modelo 3D Interactivo
**👉 [Ver el Dashboard Interactivo Aquí](https://[TU-USUARIO].github.io/ontologia-territorial-mbht/)** 

*(Para la mejor experiencia, accede desde un computador. Mantén presionado el **clic derecho** para rotar e inclinar el modelo topológico).*

---

## 1. La Base Empírica: Matriz de Bienestar (MBHT)
Antes de deformar el espacio, debemos entender qué estamos midiendo. La **Matriz de Bienestar Humano Territorial (MBHT)**, desarrollada por la SUBDERE, busca ir más allá de los índices de pobreza clásicos midiendo las condiciones estructurales del habitar a través de cuatro dimensiones fundamentales:

1. **Dimensión Ambiental:** Calidad del entorno, áreas verdes, contaminación.
2. **Dimensión de Seguridad:** Exposición a delitos, percepción de riesgo, vulnerabilidad física.
3. **Dimensión Social:** Cohesión, hacinamiento, calidad de la vivienda.
4. **Dimensión de Accesibilidad:** Distancia a servicios críticos, transporte, educación y salud.

El enfoque tradicional de la política pública suele reducir estas cuatro dimensiones a un **promedio simple** (el Índice BHT) y pintarlo sobre el mapa de las comunas. Sin embargo, un "promedio" oculta el desgarro de la experiencia urbana. Un barrio con excelente accesibilidad pero con niveles críticos de delincuencia puede "promediar" un bienestar aceptable, encubriendo una fractura profunda en la experiencia del habitar cotidiano. 

Para revelar estas fracturas ocultas, debemos abandonar la estadística simple y pasar a la física espacial.

---

## 2. El Salto Filosófico: La Firma Cognitiva
El modelo se aleja drásticamente de la geografía cuantitativa clásica sustentándose en los siguientes axiomas ontológicos:

* **Relación antes que Objeto:** El territorio no es un polígono administrativo (comuna) pasivo, es un *colector relacional vivo*.
* **Habitar antes que Medir:** No basta con medir un promedio de bienestar; la experiencia territorial está definida por las tensiones de sus dimensiones internas.
* **Memoria antes que Equilibrio:** El territorio guarda en su geometría el rastro de la desigualdad y el poder. El poder actúa como un *deformador geométrico*.

---

## 3. Desarrollo Matemático: La Física Intrínseca del Territorio
Para capturar esta firma cognitiva, utilizamos la matemática tensorial no como una herramienta de reducción, sino como un **abrigo formal** capaz de preservar la complejidad.

### A. El Campo Escalar Continuo ($W$)
El algoritmo primero transforma los datos de los polígonos discretos en un **campo escalar continuo** $W(x, y)$ mediante algoritmos de vecindad espacial (*k-d tree*) y convolución gaussiana. El territorio deja de tener "fronteras administrativas" y se vuelve una superficie continua donde cada coordenada $(x, y)$ posee un valor de bienestar $W$.

### B. El Gradiente Espacial ($\nabla W$)
En el espacio continuo, el gradiente apunta en la dirección de la máxima pendiente. Calculamos las derivadas parciales del bienestar respecto a la longitud ($x$) y la latitud ($y$):

```math
\nabla W = \left( \frac{\partial W}{\partial x}, \frac{\partial W}{\partial y} \right)
```
**Interpretación:** Si $\frac{\partial W}{\partial x}$ es muy alto, significa que al caminar pocos metros se cruza una "frontera invisible" de desigualdad masiva (un choque severo de realidades vecinas).

### C. El Tensor de Tensión Local ($\alpha$)
El gradiente por sí solo mide desigualdad material, pero no la fractura de la interioridad del territorio. Introducimos $\alpha$, calculado como la **varianza estadística** entre las 4 dimensiones de la MBHT en cada coordenada específica:

```math
\alpha(x,y) = \text{Var}(D_{amb}, D_{seg}, D_{soc}, D_{acc})
```
**Interpretación:** $\alpha$ mide la *fractura del habitar*. Si un barrio tiene buena accesibilidad pero sufre balaceras diarias, la varianza dimensional se dispara. El territorio está internamente en conflicto.

### D. La Deformación del Tensor Métrico ($g_{ij}$)
Asumimos que el territorio pasivo tiene una métrica euclidiana ($g_{xx}=1, g_{yy}=1$). Pero la suma de la desigualdad exterior ($\nabla W$) y la fractura interior ($\alpha$) *deforma* la geometría del espacio, al igual que la masa deforma el espacio-tiempo en la relatividad general. 

El nuevo tensor métrico deformado se define como:
```math
g_{xx} = 1 + \alpha \left( \frac{\partial W}{\partial x} \right)^2 
```
```math
g_{yy} = 1 + \alpha \left( \frac{\partial W}{\partial y} \right)^2 
```

### E. La Fricción Relacional (Los Muros Invisibles)
Para visualizar esto en un mapa 3D (un observable escalar), extraemos la **Traza** del tensor métrico y le restamos la traza del espacio plano original ($1+1=2$):

```math
\text{Friccion} = (g_{xx} + g_{yy}) - 2 = \alpha \left[ \left( \frac{\partial W}{\partial x} \right)^2 + \left( \frac{\partial W}{\partial y} \right)^2 \right] = \alpha |\nabla W|^2
```

**Conclusión Física:** Esta ecuación nos dice que la "barrera territorial" (el muro rojo del modelo 3D) solo se levanta si existen ambas condiciones a la vez: un choque de realidades vecinas ($|\nabla W|^2 > 0$) potenciado por una fractura interna del bienestar en ese mismo lugar ($\alpha > 0$). El resultado es la Fricción Territorial.

---

## 4. El Píxel Ontológico (Sistema H3)
Para proyectar la fricción en la web, utilizamos la malla hexagonal **H3** desarrollada por Uber. ¿Por qué un hexágono? Porque preserva la vecindad espacial de forma isométrica (todas las celdas vecinas están a la misma distancia del centro). El hexágono actúa como el **píxel ontológico**, agrupando la tensión geométrica sin distorsionarla con grillas cuadradas ni límites administrativos, honrando el Axioma 1 de la teoría.

## 5. Stack Tecnológico
* **Python:** Lenguaje principal de procesamiento estadístico.
* **GeoPandas & SciPy:** Tratamiento espacial de las bases MBHT, árboles de vecindad y derivadas parciales espaciales.
* **H3 (Uber):** Sistema de indexación geoespacial jerárquico.
* **Deck.GL / PyDeck:** Motor de renderizado WebGL para pintar y extruir las deformaciones tensoriales masivas directo en la nube.

---

## 📚 6. Citas y Bibliografía

Al citar o utilizar este modelo interactivo, por favor hacer referencia a las siguientes obras fundamentales:

1. **Treimun Ríos, J. (2025).** *Ontología Territorial y Geotensores: El Territorio como devenir, tensión y posibilidad.* Tomo I (v1.1). CC BY 4.0. DOI: [10.5281/zenodo.17444604](https://doi.org/10.5281/zenodo.17444604)
2. **Treimun Ríos, J. (2026).** *Ontología Territorial: Geotensores y la Física Intrínseca del Territorio.* Tomo II (v1.0). Centro de Inteligencia Territorial, Universidad Adolfo Ibáñez. DOI: [10.5281/zenodo.21208216](https://doi.org/10.5281/zenodo.21208216)
3. **Subsecretaría de Desarrollo Regional y Administrativo [SUBDERE]. (2017).** *Matriz de Bienestar Humano Territorial (MBHT)*. Santiago, Chile. [https://plataformabht.subdere.gov.cl/](https://plataformabht.subdere.gov.cl/)
