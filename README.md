# ¿Supone la Gestión Pasiva una Amenaza para la Eficiencia de los Mercados de Renta Variable?

## Trabajo de Fin de Grado

**Autor:** Héctor Pérez
**Universidad:** Universidad Carlos III de Madrid
**Grado:** Finanzas y Contabilidad
**Fecha:** 2024-2025

---

## Descripción

Este repositorio contiene el análisis cuantitativo del Trabajo de Fin de Grado que investiga el impacto de la gestión pasiva (fondos indexados y ETFs) en la eficiencia de los mercados de renta variable.

El estudio examina tres hipótesis principales:
1. **Impacto en los precios**: ¿Los flujos hacia fondos pasivos afectan a los retornos de las acciones?
2. **Concentración de propiedad**: ¿Cómo ha evolucionado la propiedad de los "Big Three" (BlackRock, Vanguard, State Street)?
3. **Sincronía de retornos**: ¿Ha aumentado la correlación entre acciones individuales y el mercado?

---

## Estructura del Repositorio

```
├── README.md                           # Este archivo
├── documento/                          # Documento del TFG
│   └── Análisis Cuantitativo TFG.docx
│
├── analisis/                           # Notebooks de análisis principal
│   ├── modelo_fama_french/             # Análisis Fama-French 4 factores
│   │   ├── modelo_4factores_semanal.ipynb
│   │   └── analisis_por_empresa/       # Análisis individuales
│   │       ├── apple.ipynb
│   │       ├── amazon.ipynb
│   │       ├── microsoft.ipynb
│   │       ├── google.ipynb
│   │       ├── nvidia.ipynb
│   │       ├── tesla.ipynb
│   │       ├── bank_of_america.ipynb
│   │       └── sp500.ipynb
│   │
│   ├── sincronía_retornos/             # Análisis de sincronía
│   │   ├── stock_return_synchronicity.ipynb
│   │   ├── rentabilidades_por_sector.ipynb
│   │   └── informacion_acciones.ipynb
│   │
│   └── propiedad_institucional/        # Análisis Big Three
│       └── big_three_ownership.ipynb
│
├── datos/                              # Datos utilizados
│   ├── factores_fama_french/           # Factores FF
│   │   ├── factores_semanales_4f.csv
│   │   └── factores_mensuales_3f.csv
│   ├── flujos_etf/                     # Flujos de ETFs
│   │   └── flujos_etf_diarios.xlsx
│   ├── acciones/                       # Datos de acciones
│   │   └── [archivos por ticker]
│   └── resultados/                     # Resultados de regresiones
│       └── [archivos de resultados]
│
├── literatura/                         # Referencias bibliográficas
│   ├── papers/                         # Artículos académicos (PDFs)
│   └── articulos_destacados.txt        # Enlaces a artículos online
│
└── auxiliar/                           # Archivos auxiliares y borradores
    └── [notebooks experimentales]
```

---

## Metodología

### 1. Modelo Fama-French Ampliado (4 Factores)

Se utiliza el modelo de Fama-French de 3 factores ampliado con un factor de flujos de fondos pasivos:

```
Ri - Rf = α + β1(Rm-Rf) + β2(SMB) + β3(HML) + β4(FundFlows) + ε
```

Donde:
- **Ri - Rf**: Exceso de retorno de la acción i
- **Rm - Rf**: Prima de riesgo de mercado
- **SMB**: Factor tamaño (Small Minus Big)
- **HML**: Factor valor (High Minus Low)
- **FundFlows**: Flujos netos hacia fondos pasivos

**Período de análisis**: 2020-2024 (datos semanales)

### 2. Análisis de Sincronía de Retornos

Se mide la sincronía mediante el R² del modelo de mercado:

```
Ri = α + β(Rm) + ε
```

Un R² más alto indica mayor sincronía con el mercado, lo que puede sugerir menor incorporación de información específica de la empresa.

**Períodos comparados**: 1995-1999 vs 2020-2023

### 3. Análisis de Propiedad Institucional

Se analiza la evolución de la propiedad de los "Big Three":
- BlackRock
- Vanguard
- State Street

---

## Requisitos

### Dependencias de Python

```bash
pip install yfinance pandas numpy statsmodels matplotlib seaborn openpyxl
```

### Versiones recomendadas
- Python >= 3.8
- pandas >= 1.3.0
- yfinance >= 0.2.0
- statsmodels >= 0.13.0

---

## Uso

### Ejecutar en Google Colab (Recomendado)

Los notebooks están diseñados para ejecutarse en Google Colab. Simplemente:
1. Abre el notebook en GitHub
2. Haz clic en "Open in Colab"
3. Ejecuta las celdas secuencialmente

### Ejecutar localmente

```bash
# Clonar el repositorio
git clone https://github.com/hectoorperezz/-Supone-la-gesti-n-pasiva-una-amenaza-para-la-eficiencia-de-los-mercados-de-renta-variable-.git

# Instalar dependencias
pip install -r requirements.txt

# Abrir Jupyter
jupyter notebook
```

**Nota**: Algunos notebooks descargan datos de Yahoo Finance, por lo que requieren conexión a internet.

---

## Notebooks Principales

| Notebook | Descripción |
|----------|-------------|
| `modelo_4factores_semanal.ipynb` | Regresión Fama-French 4 factores para el S&P 500 |
| `stock_return_synchronicity.ipynb` | Análisis de sincronía de retornos |
| `big_three_ownership.ipynb` | Evolución propiedad Big Three |

---

## Datos

### Fuentes de datos
- **Yahoo Finance** (via yfinance): Precios históricos de acciones
- **Kenneth French Data Library**: Factores Fama-French
- **ETF.com / Bloomberg**: Flujos de ETFs

### Archivos de datos incluidos

| Archivo | Descripción |
|---------|-------------|
| `factores_semanales_4f.csv` | Factores FF + FundFlows semanales |
| `flujos_etf_diarios.xlsx` | Flujos netos diarios hacia ETFs |

---

## Resultados Principales

Los resultados detallados se encuentran en el documento del TFG. En resumen:

1. **Modelo Fama-French**: [Resumen de hallazgos]
2. **Sincronía de retornos**: [Resumen de hallazgos]
3. **Propiedad institucional**: [Resumen de hallazgos]

---

## Literatura de Referencia

Los principales artículos consultados se encuentran en la carpeta `literatura/`:

- Fama, E. F., & French, K. R. (1993). Common risk factors in the returns on stocks and bonds.
- Gabaix, X., & Koijen, R. S. (2021). In search of the origins of financial fluctuations: The inelastic markets hypothesis.
- Azar, J., Schmalz, M. C., & Tecu, I. (2018). Anticompetitive effects of common ownership.

---

## Licencia

Este proyecto es parte de un Trabajo de Fin de Grado con fines académicos.

---

## Contacto

- **Autor**: Héctor Pérez
- **Email**: [tu-email]
- **LinkedIn**: [tu-linkedin]
