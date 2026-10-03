# Regresión Logística — Online Shoppers Purchasing Intention

Clasificación binaria de la variable `Revenue` (compra / no compra) sobre el
conjunto de datos *Online Shoppers Purchasing Intention* (UCI, id 468, licencia
CC BY 4.0). Las variables de entrada son las 17 restantes (numéricas y
categóricas: `Month`, `VisitorType`, `Weekend`).

## Estructura

```
.
├── data/
│   └── online_shoppers_intention.csv
├── notebooks/
│   └── regresion_logistica.ipynb
├── reports/
│   ├── figures/          # figuras generadas por el notebook
│   └── metricas.csv      # métricas por escenario
├── requirements.txt
└── README.md
```

## Instalación

```bash
pip install -r requirements.txt
```

## Uso

El notebook usa rutas relativas (`../data/...`, `../reports/...`) por lo que
debe ejecutarse desde la carpeta `notebooks/`.

```bash
cd notebooks
jupyter notebook regresion_logistica.ipynb
```

En Google Colab, sube la carpeta completa conservando esta estructura y abre el
notebook desde `notebooks/`.

## Notas

- La variable objetivo `Revenue` se convierte a 0 (no compra) / 1 (compra).
- Modelo base: `Pipeline` con `ColumnTransformer` (`StandardScaler` +
  `OneHotEncoder`) y `LogisticRegression(max_iter=1000)`.
- Se explora el umbral de decisión (0.30, 0.50, 0.60) y un experimento con
  `class_weight="balanced"`.
- Todas las figuras se guardan en `reports/figures/` y las métricas de cada
  escenario en `reports/metricas.csv`.
