# siniestros-futbol-caba

Se realiza para el trabajo práctico de la materia [Laboratorio de Métodos Cuantitativos Aplicados a la Gestión](https://github.com/Datso653/Laboratorio-de-metodos-Cuantitativos-Aplicados-a-la-gestion) (FCE-UBA) un análisis de datos en grupo con el objetivo de responder a la siguiente pregunta:

*¿Se registra un aumento significativo de siniestros viales en la Ciudad de Buenos Aires durante las 12 horas posteriores a la derrota de los equipos más populares de fútbol?*

Se consideran todos los partidos de la Selección Argentina (oficiales y amistosos), River Plate y Boca Juniors entre 2021 y 2025 inclusive (568 partidos), junto con todos los siniestros viales registrados por el Gobierno de la Ciudad de Buenos Aires en los mismos años (49.602 siniestros).

**Respuesta corta:** no. Tras una derrota, los siniestros en las 12 horas siguientes se mantienen en el nivel esperado para ese horario, día de la semana y año (ratio 0,99), y ninguna prueba estadística detecta un aumento significativo.

## El trabajo incluye

- Análisis realizado en Python (Google Colab), en la carpeta `notebook/`
- Informe académico, en la carpeta `informe/`
- Presentación, en la carpeta `presentacion/`

## Notebooks (ejecutar en este orden)

Cada notebook corresponde a un punto de la consigna y tiene el botón *Open in Colab*. Todos leen los datos directamente desde este repositorio.

| Notebook | Consigna | Qué hace |
|---|---|---|
| [`3_1_carga_y_exploracion.ipynb`](notebook/3_1_carga_y_exploracion.ipynb) | 3.1 | Carga las tres bases originales y explora su estructura, cobertura y calidad |
| [`3_2_pregunta_de_investigacion.ipynb`](notebook/3_2_pregunta_de_investigacion.ipynb) | 3.2 | Pregunta, motivación, hipótesis y respuesta encontrada |
| [`3_3_transformaciones_y_resumen.ipynb`](notebook/3_3_transformaciones_y_resumen.ipynb) | 3.3 | Limpieza de las tres bases, cruce partidos × siniestros, resúmenes con `groupby`, pruebas de significación y robustez |
| [`3_4_analisis_grafico.ipynb`](notebook/3_4_analisis_grafico.ipynb) | 3.4 | Cuatro gráficos con su interpretación, exportados a `informe/figuras/` |

## Datos

| Carpeta / archivo | Contenido | Fuente |
|---|---|---|
| `datos/Siniestros Viales 2019 - 2025/` | Bases originales de hechos y víctimas, y notas metodológicas | [Buenos Aires Data — Siniestros viales](https://data.buenosaires.gob.ar/) (Observatorio de Movilidad y Seguridad Vial, GCBA) |
| `datos/Temporadas River - Boca/` | CSV anuales de River y Boca 2021–2025 y las planillas unidas | [FBref](https://fbref.com/) |
| `datos/Resultados Internacionales 1872 - 2026/` | Resultados y tandas de penales de selecciones | [Kaggle — International football results](https://www.kaggle.com/datasets/martj42/international-football-results-from-1872-to-2017) |
| Horarios de la Selección | Hora de inicio de los 67 partidos (cargada en el notebook 3.3) | [Wikipedia — Argentina national football team results (2020–present)](https://en.wikipedia.org/wiki/Argentina_national_football_team_results_(2020%E2%80%93present)) |

Archivos generados por el notebook 3.3 (en `datos/`):

- `hechos_limpio_2021_2025.csv`, `victimas_limpio_2021_2025.csv`, `siniestros_por_hora_2021_2025.csv`: siniestros limpios y serie horaria
- `Temporadas River - Boca/boca_2021_2025.csv`, `river_2021_2025.csv`, `river_boca_2021_2025.csv`: partidos de los clubes con hora argentina y resultado final
- `partidos_seleccion_2021_2025.csv`: partidos de la Selección con hora argentina y resultado final
- `partidos_con_siniestros_12h.csv`: cada partido con sus siniestros observados y esperados en las 12 h posteriores
- `perfil_horario_12h.csv`: siniestros hora por hora tras el partido, según resultado

## Uso de IA

El análisis se desarrolló con asistencia de Claude (Anthropic). Cada notebook indica el prompt utilizado. La interpretación de los resultados y las decisiones metodológicas fueron revisadas por el grupo.
