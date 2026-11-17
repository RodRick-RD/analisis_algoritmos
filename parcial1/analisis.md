P1.1 — Análisis de Algoritmos

a) Cuatro fragmentos

F1:
  - Costo O en el peor caso: $O(n)$
  - Justificación: El ciclo `for` se ejecuta exactamente $n$ veces realizando operaciones elementales de tiempo constante en cada iteración.

F2:
 - Costo O en el peor caso: $O(n^2)$
 - Justificación: Es un ciclo anidado donde el ciclo externo corre $n$ veces y el interno corre en promedio $n/2$ veces, generando $\frac{n(n-1)}{2}$ iteraciones.

F3:
 - Costo O en el peor caso: $O(\log n)$
 - Justificación: En cada iteración la variable $k$ se divide a la mitad ($k = k / 2$), por lo que el ciclo se repite $\log_2 n$ veces.

F4:
 - Costo O en el peor caso: $O(n \log n)$
 - Justificación: El ciclo externo se ejecuta $n$ veces, y por cada iteración de este, el ciclo interno duplica $k$ hasta llegar a $n$, ejecutándose $\log_2 n$ veces.

b) Dos recurrencias (Teorema Maestro de bolsillo)

(i) $T(n) = 3 T(n/2) + n$
- $a = 3$, $b = 2$, $f(n) = n$
- $d = 1 \implies b^d = 2^1 = 2$
- Comparación: $a = 3 > b^d = 2$
- Forma / Solución: Caso 1 del teorema maestro $\implies O(n^{\log_2 3}) \approx O(n^{1.585})$.

(ii) $T(n) = T(n/2) + n^2$
- $a = 1$, $b = 2$, $f(n) = n^2$
- $d = 2 \implies b^d = 2^2 = 4$
- Comparación: $a = 1 < b^d = 4$
- Forma / Solución: Caso 3 del teorema maestro $\implies O(n^2)$ (dominado por $f(n)$).