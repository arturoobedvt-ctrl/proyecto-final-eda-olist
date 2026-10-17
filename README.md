# Proyecto Final: Pipeline de Limpieza y EDA (Olist)

Proyecto final de **Ciencia de Datos**. Pipeline completo de extracción, limpieza, transformación y
análisis exploratorio con **pandas** y **numpy**, trabajado en equipo con *Feature Branch Workflow* en GitHub.

## Objetivo

Limpiar y analizar el e-commerce brasileño de Olist para responder tres preguntas de negocio:

1. ¿Qué categorías de producto generan más ingreso?
2. ¿El retraso en la entrega baja la calificación que da el cliente?
3. ¿Cómo varían las ventas por mes y por estado?

## Dataset

**Brazilian E-Commerce Public Dataset by Olist** (Kaggle):
<https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce>

- Pedidos reales de 2016 a 2018 en un marketplace de Brasil.
- Tabla principal (pedidos + ítems): 112,650 filas y 14 columnas, con variables numéricas, categóricas y fechas.
- Tablas secundarias para el `merge`: productos, clientes y reseñas.

### Archivos que deben estar en `data/`

Los CSV no se suben al repositorio (están en `.gitignore`). Descárgalos de Kaggle (requiere cuenta gratuita)
y colócalos en la carpeta `data/`:

- `olist_orders_dataset.csv`
- `olist_order_items_dataset.csv`
- `olist_products_dataset.csv`
- `olist_customers_dataset.csv`
- `olist_order_reviews_dataset.csv`

## Instalación y ejecución

Requiere **Python 3.11 o superior**.

```bash
# 1. Crear y activar un entorno virtual
python -m venv .venv
.venv\Scripts\activate          # Windows
# source .venv/bin/activate     # Linux / macOS

# 2. Instalar dependencias
pip install -r requirements.txt

# 3. Ejecutar el notebook de principio a fin
python -m nbconvert --to notebook --execute --inplace Proyecto_Final_EDA.ipynb
```

Para abrirlo de forma interactiva: `pip install notebook` y luego `jupyter notebook Proyecto_Final_EDA.ipynb`.

## Estructura del repositorio

```
.
├── README.md
├── requirements.txt
├── .gitignore
├── data/                      # CSV de Olist (no se suben)
└── Proyecto_Final_EDA.ipynb   # Notebook final
```

## Estructura del notebook

1. Encabezado y contexto del proyecto
2. Importación de librerías y configuración
3. Carga e inspección inicial
4. Limpieza y preprocesamiento (4.1 nulos, 4.2 duplicados, 4.3 casteo, 4.4 texto)
5. Enriquecimiento e ingeniería de características (merge, numpy, outliers)
6. EDA y respuestas a las 3 preguntas
7. Conclusiones finales

## Flujo de trabajo en Git

Ramas por integrante (sin commits directos a `main`), commits semánticos y Pull Requests con revisión cruzada:

| Rama | Responsable | Secciones | Revisa |
|---|---|---|---|
| `feature/carga-y-nulos` | Arturo Obed Velázquez Téllez | 1, 2, 3 y 4.1 | Ángel de Jesús González Molina |
| `feature/duplicados-casteo-texto` | Ángel de Jesús González Molina | 4.2, 4.3 y 4.4 | Antonia Martínez Santos |
| `feature/merge-numpy-outliers` | Antonia Martínez Santos | 5 | José Carlos Hernández Ballado |
| `feature/eda-conclusiones` | José Carlos Hernández Ballado | 6 y 7 | Arturo Obed Velázquez Téllez |

Las ramas están encadenadas (cada una parte de la anterior), por lo que los PR se integran **en orden**.

## Equipo

- Arturo Obed Velázquez Téllez
- Ángel de Jesús González Molina
- Antonia Martínez Santos
- José Carlos Hernández Ballado
