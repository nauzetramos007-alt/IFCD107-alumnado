# Autoevaluación y coevaluación · «Primer modelo en producción»

---

## 1. Autoevaluación

**Nombre:** Juanjo

### Repaso rápido
| Pregunta | Mi respuesta |
| :--- | :--- |
| **¿El informe tiene las tres partes y cabe en 4 páginas?** | Sí, tiene las tres partes pero están divididas en 7 puntos y cabe en cuatro páginas |
| **¿La métrica y el umbral están explicados en lenguaje de negocio?** | Sí: ROC-AUC para comparar y coste en euros para decidir el umbral (0,3), comparado con «avisar a todos» y «no avisar nunca». Falta sustituir los importes de ejemplo (100 € / 40 €) por los nuestros |
| **¿Hay evidencia de una llamada a la API (petición y respuesta), sin credenciales?** | A medias: están la petición y la respuesta (probabilidad 0,816, alerta true), sin claves. |
| **¿Explicamos qué variables hemos excluido y por qué?** | Sí: solo id_reserva (identificador); el resto se conoce al reservar y no hay columnas posteriores al hecho. |
| **¿Hemos cerrado y eliminado todos los recursos y lo demostramos?** | No (todavía): falta hacer «Desconectar y eliminar entorno» |
| **¿Hay al menos dos riesgos de IA responsable y una medida?** | Sí: cuatro (datos sintéticos, falsas alertas, sesgos por país/canal, deriva temporal), cada uno con su medida. |
| **¿Otra persona ha revisado el informe con la rúbrica?** | No (todavía): pendiente de la review |

### Puntúate de 1 a 4 en cada criterio de la rúbrica:
| Criterio | Mi puntuación (1–4) | Por qué (una frase) | Qué haría para subir un punto |
| :--- | :---: | :--- | :--- |
| **Corrección técnica** | 3 | Partición temporal, modelo elegido por validación y umbral calculated con costes | Reejecutar el cuaderno completo, aclarar esa diferencia y poner el umbral 0,3 en la API. |
| **Reproducibilidad** | 3 | Documentados versión de AutoGluon, preset, límite de tiempo, partición y semilla. | Pasar la semilla también a AutoGluon para que los resultados no varíen entre ejecuciones. |
| **Análisis y comunicación al cliente** | 3 | Explico el ahorro real y su límite: solo un 11 % mejor que avisar a todos. | Usar nuestros importes reales y añadir el porcentaje de cancelaciones por canal. |
| **IA responsable** | 3 | Cuatro riesgos con medida y una recomendación con límites claros | Medir de verdad el recall y la tasa de alertas por país y canal en lugar de solo proponerlo. |

**Reflexiones adicionales:**
* **Lo que más me costó:** Interpretación de los resultados del leaderboard, porque los modelos de árboles puntuaban muchísimo mejor en la prueba que en validación y eso no tenía sentido, así que tuve que decidir no fiarme de esa tabla.
* **Uso de IA:** He usado IA para redactar el borrador del informe a partir de los resultados del cuaderno, y lo que he comprobado a mano es que las cifras (costes, matriz, ahorro de 2.800 € y 35.580 €) coinciden con la salida del cuaderno.

---

## 2. Coevaluación (durante la review)

* **Trabajo revisado de:** AZUL
* **Revisado por:** Juanjo

### ¿Está lo que pide el reto?
| Entregable (nómbralo) | ¿Está y se entiende? | Comentario breve |
| :--- | :---: | :--- |
| **Informe Sprint 3 · TurisData · Primer modelo en producción_entrega.pdf** | ✔ | Análisis de los datos obtenidos |
| **Notebook Colab (Link)** | ✔ | Cuaderno de notebook donde se hicieron los cálculos |
| **DB Browser** | ✔ | Toma de contacto con la estructura de datos |

### Puntuación (1–4) de quien revisa:
| Criterio | Puntuación | Comentario breve |
| :--- | :---: | :--- |
| **Corrección técnica** | 3 | Siempre se puede mejorar |
| **Reproducibilidad** | 4 | Se hizo varias veces |
| **Análisis y comunicación al cliente** | 3 | Una comunicación precisa y directa para que se entienda |
| **IA responsable** | 4 | No se usaron datos personales que identifiquen a alguien |

* **Lo que está muy bien:** La limpieza de datos y la metodología.
* **Lo que yo cambiaría, y por qué:** El uso de datos sintéticos en vez de usar datos de otras temporadas.
* **Comentario general:** *En muy poco tiempo se pasó de entender los datos a interpretarlos.*
