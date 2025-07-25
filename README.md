# Análisis de Hipótesis y Test A/B para Aumento de Ingresos en Tienda Online

## Descripción

Proyecto para priorizar hipótesis de marketing y analizar un test A/B en una tienda online, con el fin de aumentar ingresos. Dividido en: priorización (ICE/RICE) y análisis de resultados (gráficos, estadísticas, decisión final).

## Contexto

Analista de datos evalúa hipótesis y test A/B. Preprocesar datos para eliminar errores (e.g., usuarios duplicados en grupos).

## Datos

- **hypotheses_us.csv**: 9 hipótesis con Reach, Impact, Confidence, Effort.
- **orders_us.csv**: Pedidos (transactionId, visitorId, date, revenue, group).
- **visits_us.csv**: Visitas (date, group, visits).

## Requisitos

- Python 3.x con pandas, numpy, matplotlib, scipy.
- Instalar: `pip install pandas numpy matplotlib scipy`.

## Estructura

### Parte 1: Priorizar Hipótesis
- Calcular ICE = (Impact * Confidence) / Effort; ordenar descendente.
- Calcular RICE = (Reach * Impact * Confidence) / Effort; ordenar descendente.
- Comparar cambios (Reach influye en RICE).

### Parte 2: Análisis Test A/B
- Gráficos: Ingresos/tamaño pedido acumulados, diferencia relativa, conversión diaria.
- Dispersión: Pedidos/usuario, precios pedidos.
- Percentiles: 95/99 para anomalías en pedidos/precios.
- Pruebas estadísticas: Diferencia en conversión/tamaño pedido (crudo/filtrado, Mann-Whitney).
- Decisión: Parar (líder/diferencia nula) o continuar.

## Ejecución

1. Cargar datos en Jupyter Notebook.
2. Preprocesar (eliminar duplicados, convertir fechas).
3. Ejecutar cálculos y gráficos secuencialmente.

## Conclusiones

RICE prioriza por alcance. En A/B, filtrar anomalías para resultados precisos; decidir basado en p-values (<0.05 indica diferencia significativa).

