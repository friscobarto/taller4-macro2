# Taller 4: Hechos Estilizados Macroeconómicos
**Macroeconomía 2 — Universidad de los Andes**  
**Profesor:** Fernando Jaramillo  
**Fecha:** Marzo 2026

---

## Descripción
Este repositorio replica los hechos estilizados de la economía colombiana
siguiendo la metodología de Uribe & Schmitt-Grohé (2017) en *Open Economy
Macroeconomics*. Se analizan dos períodos: 1994–2007 (Base 1994) y
2005–2025 (Base 2015), usando datos trimestrales del Banco de la República.

## Estructura del proyecto
```
taller4-macro2/
├── data/              ← Archivos Excel del BanRep (no incluidos en el repo)
├── outputs/           ← Gráficos generados por el notebook
├── taller4.ipynb      ← Notebook principal
├── requirements.txt   ← Dependencias de Python
└── README.md
```

## Datos
Los datos deben descargarse manualmente del portal de Series Estadísticas
Históricas del Banco de la República:
👉 https://www.banrep.gov.co/es/estadisticas/series-estadisticas-historicas

Descargar **PIB por demanda**, frecuencia trimestral, y guardar en `data/`:
| Archivo | Base | Tipo | Período |
|---|---|---|---|
| `constante-1994.xlsx` | 1994 | Precios constantes | 1994–2007 |
| `corriente-1994.xlsx` | 1994 | Precios corrientes | 1994–2007 |
| `constante-2015.xlsx` | 2015 | Precios constantes | 2005–2025 |
| `corriente-2015.xlsx` | 2015 | Precios corrientes | 2005–2025 |

## Metodología
1. **Relaciones de largo plazo:** ratios X/PIB en precios corrientes
2. **Transformación logarítmica:** x_t = ln(X_t)
3. **Filtro Hodrick-Prescott** (λ = 1600) para extraer el componente cíclico
4. **Hechos estilizados:**
   - Volatilidad del PIB (desviación estándar del ciclo)
   - Volatilidades relativas al PIB
   - Ciclicidad (correlación con el PIB)
   - Persistencia (autocorrelación de orden 1)

## Reproducibilidad
Crear entorno virtual e instalar dependencias:
```bash
python -m venv venv --without-pip
venv\Scripts\activate
python -m ensurepip --upgrade
pip install -r requirements.txt
```
Luego abrir `taller4.ipynb` en VSCode y ejecutar todas las celdas.

## Resultados principales
| | Base 1994 | Base 2015 |
|---|---|---|
| Volatilidad PIB | 1.72% | 2.78% |
| Comp. más volátil | Inversión (6.4x) | Inversión (2.6x) |
| Comp. más persistente | Consumo (0.899) | Importaciones (0.715) |
| Exportaciones | Acíclicas | Procíclicas |

## Referencia
Uribe, M., & Schmitt-Grohé, S. (2017). *Open Economy Macroeconomics*.
Princeton University Press.
```
