P1.3 — Elegir

Contexto Hospitalario
- $n = 300.000$ números de historia clínica.
- Consultas diarias = $5.000$.
- Restricción: Memoria limitada (no se puede duplicar el listado).

Costos Totales con Números

opción 1 (Recorrido lineal en cada consulta):
   - Costo por consulta: $O(n) = 300.000$ operaciones.
   - Costo total de 5.000 consultas: $5.000 \times 300.000 = \mathbf{1.500.000.000 \text{ operaciones}}$.

opción 2 (Ordenar una vez en la mañana $O(n \log n)$ + Búsqueda Binaria $O(\log n)$):
   - Ordenamiento inicial: $300.000 \times \log_2(300.000) \approx 300.000 \times 18,19 \approx 5.457.000$ operaciones.
   - 5.000 búsquedas binarias: $5.000 \times \log_2(300.000) \approx 5.000 \times 19 \approx 95.000$ operaciones.
   - Costo total diario: $5.457.000 + 95.000 = \mathbf{5.552.000 \text{ operaciones}}$.

opción 3 (Ordenar con algoritmo cuadrático $O(n^2)$ + Búsqueda binaria):
   - Ordenamiento inicial: $(300.000)^2 = \mathbf{90.000.000.000 \text{ operaciones}}$ (inviable).

Elección
La opción elegida es la Opción 2. Reduce drásticamente el costo operativo diario de 1.500 millones a apenas 5,5 millones de operaciones, cumpliendo con la restricción de no duplicar memoria al ordenar in-place.

Umbral de Cambio de Opinión
Igualando los costos totales en función del número de consultas $C$:
$$C \times n = n \log_2 n + C \log_2 n$$
$$C(300.000 - 18,19) = 5.457.000 \implies C \approx 18,19$$
Cambiaría de opinión a partir de las 19 consultas. Si el hospital hiciera menos de 19 consultas al día, el ordenamiento matutino dejaría de compensar; sin embargo, con 5.000 consultas diarias, la Opción 2 es abrumadoramente superior.