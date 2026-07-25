# Laboratorio 1 — Series de Tiempo (CC3084 Data Science, UVG, Sem. II 2026)

Análisis de series de tiempo del **ingreso de viajeros internacionales a Guatemala**
(ene-2009 a jun-2026). Datos de uso exclusivamente académico.

## Categorías seleccionadas
Además de la **serie total obligatoria** (definida como `Turista + Excursionista`, la versión
consistente en todo el período), se eligieron dos categorías de análisis:
- **Vías de ingreso** (Aérea, Terrestre, Marítima)
- **Países de residencia** (top-3 acumulado)

## Orden de los notebooks

| Orden | Archivo | Contenido | 
|-------|---------|-----------|
| **1** | `Lab1_Series_Tiempo.ipynb` | EDA general (compartido) + series **Total** y **Vías** |
| **2** | `Lab1_Series_Paises.ipynb` | Series por **País** (El Salvador, EE. UU., Honduras) |

> **Empezar por el Notebook 1**: contiene el análisis exploratorio general (calidad de datos,
> pandemia, quiebres metodológicos) que da contexto al Notebook 2.

## Estado de avance

- [x] Análisis exploratorio general (Notebook 1)
- [x] Series **Total** y **Vía Aérea**: construcción, descomposición, estacionariedad (var. + media)
- [x] Series **Terrestre** y **Marítima** (Notebook 1)
- [x] Series por **País** (Notebook 2): análisis + estacionariedad
- [x] Modelado (ARIMA/SARIMA, Prophet, Holt-Winters, suav. exponencial, seasonal naive) — todas las series
- [x] Partición 70/30, predicción y métricas (MAE, RMSE, AIC, BIC) — todas las series
- [x] Análisis comparativo con evidencia estadística (ejercicio 5, Notebook 2)
- [ ] Redacción y exportación del informe final sin código a PDF

## Nota metodológica: top-3 de países

El top-3 literal por acumulado incluía "Guatemala", pero corresponde a **residentes guatemaltecos
retornando** (no es un mercado de residencia extranjero) y su serie se **corta en 2022** por el
cambio de granularidad de la variable `País` desde 2023. Por eso se excluye y se usa el siguiente:
**El Salvador, Estados Unidos de América y Honduras** (mercados extranjeros con series completas).

## Cómo ejecutar

```bash
python -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install numpy pandas matplotlib seaborn statsmodels scikit-learn openpyxl
pip install pmdarima prophet         # para la fase de modelado
```
Luego abrir los notebooks con Jupyter y ejecutarlos de arriba hacia abajo. El archivo de datos
`Base_Migracion_2009-2026jun.xlsx` debe estar en la raíz del repositorio.

Los dos notebooks están guardados con todas sus celdas ejecutadas, incluyendo tablas de métricas,
pruebas estadísticas y gráficas. El análisis comparativo y las recomendaciones para INGUAT se
encuentran al final del Notebook 2.
