<div align="center">
  <h1>Ontología Territorial y Geotensores</h1>
  <h3>Deformación Geotensorial de la Matriz de Bienestar Humano Territorial (MBHT)</h3>
</div>

<br>

Este repositorio aloja la validación empírica y la visualización interactiva del modelo geotensorial aplicado a la **Matriz de Bienestar Humano Territorial (MBHT)** de Chile (Región Metropolitana). Es el resultado de la aplicación práctica de los axiomas establecidos en los tomos I y II de la obra *Ontología Territorial*.

---

## 🔗 Modelo 3D Interactivo
**👉 [Ver el Dashboard Interactivo Aquí](https://[TU-USUARIO].github.io/ontologia-territorial-mbht/)** 

*(Para la mejor experiencia, accede desde un computador. Mantén presionado el **clic derecho** para rotar e inclinar el modelo topológico).*

---

## 🧠 1. Marco Filosófico: La Firma Cognitiva
El modelo se aleja drásticamente de la geografía cuantitativa clásica y la cartografía plana. Se sustenta en los siguientes axiomas ontológicos:

* **Relación antes que Objeto:** El territorio no es un polígono administrativo (comuna) pasivo, es un *colector relacional vivo*.
* **Habitar antes que Medir:** No basta con medir un promedio de bienestar; la experiencia territorial está definida por las fracturas y tensiones de sus dimensiones internas.
* **Memoria antes que Equilibrio:** El territorio guarda en su geometría el rastro de la desigualdad histórica y el poder. El poder es un *deformador geométrico*.

## 📐 2. Fundamentos Matemáticos (La Física Intrínseca)
En este proyecto, la matemática no se utiliza como un lenguaje de reducción estadística, sino como un **abrigo formal** para captar la deformación del espacio. El algoritmo en Python realiza la siguiente secuencia:

### A. El Continuum Geotensorial
Utilizando la técnica de árboles espaciales (`cKDTree`) y un filtro gaussiano bidimensional sobre los datos de la Subsecretaría de Desarrollo Regional (SUBDERE), los valores discretos poblacionales se funden en un fluido ininterrumpido. 

### B. Tensión Local ($\alpha$) como Observable Fundamental
Un territorio puede promediar un índice de bienestar alto, pero si tiene una seguridad excelente y un entorno ambiental degradado, sufre internamente. Calculamos la **varianza estadística** entre las 4 subdimensiones de la MBHT (Ambiental, Seguridad, Social, Accesibilidad) para extraer el Tensor $\alpha$ (Tensión Local).

### C. Fricción Relacional (Los "Muros" Invisibles)
Calculamos los gradientes espaciales del bienestar general ($dx, dy$) y los modulamos por la Tensión ($\alpha$).
La ecuación de la traza del tensor métrico deforma el mapa geométricamente:

```math
Friccion = (1 + \alpha \cdot \nabla BHT_x^2) + (1 + \alpha \cdot \nabla BHT_y^2) - 2
```

El resultado de esta fricción territorial se inyecta directamente como la elevación (eje Z) en la topología. Las zonas rojas que se levantan como muros representan físicamente barreras de fricción severa que quiebran las trayectorias de vida.

## 🛑 3. El Píxel Ontológico (Sistema H3)
Para consolidar la deformación, utilizamos la malla hexagonal **H3**. ¿Por qué un hexágono? Porque preserva la vecindad espacial de forma isométrica (todas las celdas vecinas están a la misma distancia del centro). El hexágono actúa como el **píxel ontológico**, agrupando la tensión sin distorsionarla con las fronteras artificiales del Estado.

## 🛠️ 4. Stack Tecnológico
* **Python:** Lenguaje principal de procesamiento.
* **GeoPandas & SciPy:** Tratamiento espacial y cálculo del continuum mediante *k-d trees* y cálculo de gradientes.
* **H3 (Uber):** Sistema de indexación geoespacial jerárquico.
* **Deck.GL / PyDeck:** Motor de renderizado WebGL para pintar y extruir las deformaciones masivas a 60 FPS directo en el navegador.

---

## 📚 5. Citas y Bibliografía

Al citar o utilizar este modelo interactivo, por favor hacer referencia a las siguientes obras fundamentales:

1. **Treimun Ríos, J. (2025).** *Ontología Territorial y Geotensores: El Territorio como devenir, tensión y posibilidad.* Tomo I (v1.1). CC BY 4.0. DOI: [10.5281/zenodo.17444604](https://doi.org/10.5281/zenodo.17444604)
2. **Treimun Ríos, J. (2026).** *Ontología Territorial: Geotensores y la Física Intrínseca del Territorio.* Tomo II (v1.0). Centro de Inteligencia Territorial, Universidad Adolfo Ibáñez. DOI: [10.5281/zenodo.21208216](https://doi.org/10.5281/zenodo.21208216)
3. **Subsecretaría de Desarrollo Regional y Administrativo [SUBDERE]. (2017).** *Matriz de Bienestar Humano Territorial (MBHT)*. Santiago, Chile. [https://plataformabht.subdere.gov.cl/](https://plataformabht.subdere.gov.cl/)
