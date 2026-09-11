# Python Fundamentals & Algorithmic Problem Solving

Ejercicios de algoritmia y estructuras de datos en Python puro.
Repositorio estructurado de fundamentos algorítmicos, estructuras de datos nativas y simulaciones de lógica discreta en Python puro.

---

## 📂 Módulos y Lógica de Implementación

### 1. `01_sequences_and_strings/time_series_streaks.py`
Manejo de secuencias de eventos y análisis de series continuas en tiempo lineal.

* **`maximo_clientes_concurrencia(registro: str) -> int`**
  * **Propósito:** Calcula el pico máximo de concurrencia simultánea en un recinto a partir de una cadena de texto de eventos (`'e'` = entrada, `'s'` = salida).
  * **Lógica:** Recorre la cadena carácter por carácter, incrementando el contador en `'e'` y decrementándolo en `'s'` (sin bajar de 0). En cada paso evalúa si se supera el récord histórico.
  * **Complejidad:** $O(n)$ tiempo, $O(1)$ memoria.

* **`racha_maxima_positiva(secuencia: str) -> int`**
  * **Propósito:** Encuentra la longitud de la racha continua más larga de balances positivos (`'+'`).
  * **Lógica:** Mantiene un contador acumulativo que suma 1 por cada `'+'` y se reinicia inmediatamente a 0 al encontrar un `'-'`.
  * **Complejidad:** $O(n)$ tiempo, $O(1)$ memoria.

---

### 2. `02_data_structures/choir_resource_allocator.py`
Modelado relacional, agregación y verificación de capacidad usando diccionarios y listas.

* **`compilar_censo_coral(cantantes: list) -> dict`**
  * **Propósito:** Agrupa una lista de tuplas `(nombre, voz, es_solista)` en un censo estructurado por cuerda: `{"soprano": [total, solistas], ...}`.
  * **Lógica:** Inicializa las cuatro cuerdas estándar en `[0, 0]` para garantizar consistencia de claves y acumula los conteos iterando sobre la nómina.
  * **Complejidad:** $O(n)$ tiempo, $O(1)$ espacio auxiliar.

* **`es_obra_representable(censo_disponible: dict, requisitos_obra: dict) -> bool`**
  * **Propósito:** Evalúa si el personal disponible cubre los requisitos mínimos (totales y solistas) para interpretar una obra.
  * **Lógica:** Compara cuerda por cuerda; si falta una cuerda requerida o la disponibilidad es menor al requisito, retorna `False` inmediatamente (*fail-fast*).

---

### 3. `03_matrices_and_grids/manual_matrix_search.py`
Indexación y búsqueda en cuadrículas bidimensionales.

* **`buscar_coordenadas_multiples(matriz: list, elementos_busqueda: list) -> dict`**
  * **Propósito:** Localiza todas las posiciones `(fila, columna)` de una lista de elementos dentro de una matriz rectangular.
  * **Lógica:** Recorre la matriz celda por celda con bucles anidados (`i`, `j`). Si el valor actual está en los objetivos, añade la tupla de coordenadas al diccionario de resultados.
  * **Complejidad:** $O(R \times C)$ tiempo (donde $R$ = filas y $C$ = columnas).

---

### 4. `04_math_and_simulations/caffeine_decay.py`
Modelado iterativo de decaimiento temporal discreto.

* **`tiempo_desintegracion_cafeina(tazas: int, umbral_mg: float = 10.0, mg_por_taza: float = 98.0) -> int`**
  * **Propósito:** Estima las horas necesarias para que la concentración de cafeína en el cuerpo descienda por debajo de un umbral seguro.
  * **Lógica:** Aplica una vida media de 5 horas dividiendo la concentración a la mitad en cada ciclo `while` hasta alcanzar o superar el umbral.
  * **Complejidad:** $O(\log(\text{dosis total}))$.

---

## 🧪 Ejecución de Pruebas

Para validar el funcionamiento del conjunto de funciones:

```powershell
pip install -r requirements-dev.txt
python -m pytest -v