
# Vacunación COVID-19 — Teoría de Conjuntos (C#)

Este proyecto genera datos ficticios de una campaña de vacunación contra COVID-19 y aplica **operaciones de teoría de conjuntos** para obtener los siguientes listados:

- Ciudadanos que **no se han vacunado**.
- Ciudadanos que han recibido **ambas dosis** (aparecen en Pfizer y AstraZeneca).
- Ciudadanos que recibieron **solo Pfizer**.
- Ciudadanos que recibieron **solo AstraZeneca**.

## Requisitos cumplidos
- Conjunto de **500** ciudadanos (`Ciudadano 1` ... `Ciudadano 500`).
- Conjunto de **75** vacunados con **Pfizer** (selección aleatoria reproducible).
- Conjunto de **75** vacunados con **AstraZeneca** (selección aleatoria reproducible).
- Resolución **exclusivamente en C#** usando `HashSet<T>` y operaciones de conjuntos: **Unión, Intersección, Diferencia, Complemento**.
- Exportación de resultados a **CSV** dentro de la carpeta `output/` al ejecutar.

## Cómo ejecutar

1. Instala **.NET SDK 8.0** o superior: <https://dotnet.microsoft.com/download>
2. Clona este repositorio y ve a la carpeta del proyecto:
   ```bash
   cd VacunacionCOVID/VacunacionCOVID
   dotnet run
   ```
3. Revisa la salida en consola y los archivos generados en `VacunacionCOVID/output/`.

> **Nota:** El experimento es **reproducible** porque el generador aleatorio usa una **semilla fija**. Si quieres otra simulación, cambia el valor de `seed` en `Program.cs`.

## Explicación (teoría de conjuntos)

- **U (Universo)**: conjunto de los 500 ciudadanos.
- **P (Pfizer)**: conjunto de los vacunados con Pfizer (75 elementos).
- **A (AstraZeneca)**: conjunto de los vacunados con AstraZeneca (75 elementos).

Con esto:
- **No vacunados** = `U − (P ∪ A)`
- **Ambas dosis** = `P ∩ A`
- **Solo Pfizer** = `P − A`
- **Solo AstraZeneca** = `A − P`

Implementado con LINQ sobre `HashSet<T>`: `Union`, `Intersect`, `Except`.

## Estructura
```
VacunacionCOVID/
 └─ VacunacionCOVID/
    ├─ VacunacionCOVID.csproj
    ├─ Program.cs
    └─ output/           # Se crea al ejecutar; contiene CSVs
```

## Licencia
Este código se entrega para uso académico. Se prohíbe su redistribución con fines de plagio.
