# Análisis de Ventas – Superstore

Análisis exploratorio del dataset Superstore para identificar patrones de ventas, rentabilidad por categoría/región y el impacto de los descuentos sobre las ganancias.

## Dataset

- **Archivo**: `Superstore.csv`
- **Registros**: 9.994 filas
- **Período**: enero 2011 – diciembre 2014
- **Columnas clave**: `Sales`, `Profit`, `Discount`, `Category`, `Sub-Category`, `Region`, `Order Date`
- **Fuente original del dataset**: Kaggle (https://www.kaggle.com/datasets/ishanshrivastava28/superstore-sales)

## Requisitos

```
pandas 3.0.1
matplotlib 3.10.9
seaborn 0.13.2
jupyter 7.4.5

```

## Instalación:

```bash
pip install pandas matplotlib seaborn jupyter
```

## Uso

1. Colocar `Superstore.csv` en la misma carpeta que el notebook.
2. Abrir `Superstore.ipynb` y ejecutar todas las celdas en orden.

## Estructura del análisis

1. **Carga y limpieza**: verificación de nulos, duplicados y conversión de fechas.
2. **Ventas y rentabilidad por categoría/sub-categoría**: incluye margen (`Profit/Sales`), no solo valores absolutos.
3. **Rentabilidad por región y ciudad**.
4. **Evolución temporal de ventas** (estacionalidad mensual).
5. **Descuentos vs. ganancia**: boxplot por nivel de descuento y cruce descuento-categoría para identificar dónde se concentran las pérdidas.
6. **Top/bottom productos por rentabilidad**.
7. **Detección de outliers** en ganancia (método IQR).

## Hallazgos principales

- Ventas totales: **$2,297,200.86** | Ganancia total: **$286,397.02** | Margen general: **12.5%**
- **Technology** es la categoría más rentable en términos absolutos; **Furniture** tiene ventas comparables a Office Supplies pero rentabilidad mucho menor.
- **Tables** y **Bookcases** son las únicas sub-categorías con ganancia negativa acumulada.
- **West** es la región más rentable, seguida de East; Central y South quedan bastante por debajo.
- A partir de un descuento de **0.3** la mediana de ganancia se vuelve negativa: no es una relación lineal suave sino un quiebre claro.
- Existe una categoría específica que concentra la mayoría de las pérdidas asociadas a descuentos altos (ver notebook, sección de cruce descuento-categoría).

## Conclusión

El volumen de ventas no es un buen proxy de rentabilidad: hay categorías y sub-categorías con ventas altas pero ganancia baja o negativa. La política de descuentos actual, especialmente a partir de 0.3, está asociada con pérdidas sistemáticas y debería revisarse por categoría en lugar de aplicarse de forma uniforme.

## Archivos

- `Superstore.ipynb` — notebook con el análisis completo
- `Superstore.csv` — dataset original
- `requirements.txt` — versiones fijadas de las librerías usadas (pandas, matplotlib, seaborn, jupyter)
- `images/` — gráficos exportados del notebook, referenciados en este README
- `README.md` — este archivo

## Elaboración
Nicolas Rivera | 2026
