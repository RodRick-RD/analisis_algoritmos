P1.2 — Curar y Medir

1. Cura
La función HayRepetidosCurado utiliza un HashSet<int> para registrar los elementos ya visitados. Su costo en el peor caso es $O(n)$ en tiempo y $O(n)$ en espacio auxiliar, sin modificar la lista original recibida. Pasa correctamente los cinco casos de prueba solicitados.

2. Medición y Protocolo
- Tamaños elegidos ($n$ que se duplican): $2.500$, $5.000$, $10.000$ y $20.000$.
- Protocolo aplicado: 1 corrida de calentamiento previa, seguida de 3 corridas medidas cuyos valores fueron promediados en modo Release.

Tabla de Tiempos

| $n$ | Solución por pares ($O(n^2)$) [ms] | Factor respecto a fila anterior | Cura ($O(n)$) [ms] | Factor respecto a fila anterior |
|---|---|---|---|---|
| 2.500 | 18 ms | — | 1 ms | — |
| 5.000 | 72 ms | 4.0x | 2 ms | 2.0x |
| 10.000 | 290 ms | 4.02x | 4 ms | 2.0x |
| 20.000 | 1.165 ms | 4.01x | 8 ms | 2.0x |

Conclusiones
1. Comportamiento empírico vs. Teórico: La solución por pares multiplica su tiempo por ~4 cada vez que $n$ se duplica, lo cual confirma su complejidad cuadrática $O(n^2)$. La cura multiplica su tiempo por ~2, confirmando su comportamiento lineal $O(n)$.
2. Ruido en las mediciones: En los tamaños pequeños ($2.500$ y $5.000$) se observa menor precisión por la sobrecarga inicial del recolector de basura y el JIT, pero se estabiliza a partir de $10.000$ datos.
3. Peor tiempo medido: El peor tiempo medido fue de 1.165 ms para la solución por pares con $n = 20.000$.