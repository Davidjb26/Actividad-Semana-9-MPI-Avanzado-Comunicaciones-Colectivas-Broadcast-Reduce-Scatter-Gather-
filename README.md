## Actividad: Comunicaciones Colectivas en MPI (Broadcast y Reduce) con Python (`mpi4py`)

Repositorio correspondiente a la actividad de **MPI Avanzado: Comunicaciones Colectivas**, enfocado en la implementación de un programa paralelo para el cálculo distribuido del promedio de valores aleatorios utilizando la biblioteca `mpi4py`.

---

## 📋 Descripción de la Actividad
El objetivo principal de esta práctica es comprender, implementar y analizar el comportamiento de las operaciones de comunicación colectiva en un entorno de memoria distribuida (modelo SPMD). El programa desarrollado realiza los siguientes pasos:
1. **Inicialización del entorno MPI** y obtención de identificadores de procesos (`rank` y `num_procs`).
2. **Difusión (Broadcast)** del tamaño de la muestra ($N$) desde el proceso raíz hacia todos los nodos.
3. **Generación local e independiente** de números pseudoaleatorios y cálculo de una suma parcial por cada proceso.
4. **Reducción global (`Reduce`)** para unificar todas las sumas parciales en el proceso coordinador (`rank 0`).
5. **Cálculo del promedio global** y re-difusión del resultado final a toda la red mediante `Broadcast`.
6. **Visualización y validación** de los resultados en cada nodo del sistema.

---

## 🛠️ Requisitos e Instalación en Google Colab
Dado que Google Colab no incluye por defecto un runtime de computación paralela, se deben seguir los siguientes pasos distribuidos en celdas:

### 1. Celda de Aprovisionamiento (Instalación de Dependencias)
```python
!apt-get update
!apt-get install -y openmpi-bin libopenmpi-dev
!pip install mpi4py
```
