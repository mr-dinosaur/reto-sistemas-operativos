# Reto: análisis de deserción de empleados y sistemas operativos

Análisis en Pandas de los datos del Hackathon HackerEarth 2020 (deserción de empleados) cruzados con la información del área de TI: sistema operativo de escritorio, sistema operativo móvil y tickets de soporte.

## Objetivo

- Cargar y conjuntar cuatro archivos CSV con Pandas.
- Responder cinco consultas sobre el uso de sistemas operativos.
- Guardar cada resultado en su propia hoja de un archivo `.xlsx`.

## Datos

| Archivo | Contenido |
|---|---|
| `Train.csv` | Empleados (id, edad, nivel educativo, estado civil, etc.) |
| `Test.csv` | Empleados, mismo esquema que `Train.csv` |
| `Train2.csv` | Datos de TI: SO de escritorio, versión, tickets, SO móvil, versión, tickets |
| `Test2.csv` | Datos de TI, mismo esquema que `Train2.csv` |

Los cuatro archivos se leen como datos, no se ejecuta nada de su contenido.

## Metodología

1. Se cargan los cuatro archivos en DataFrames.
2. Se apilan `Train` + `Test` (empleados) y `Train2` + `Test2` (TI).
3. Se unen ambos bloques por el identificador del empleado, conservando todos los registros de empleados (`left join`).
4. Los valores faltantes de SO de escritorio y SO móvil se reemplazan por `"no registrado"`.
5. Se calculan las consultas y se exportan al `.xlsx`.

## Consultas

| Hoja del Excel | Resultado |
|---|---|
| Porcentaje SO escritorio | % de personas con Windows, Mac, Linux o "no registrado" (4 renglones) |
| Porcentaje SO móvil | % de personas con iOS, Android o "no registrado" (3 renglones) |
| Edad promedio | Edad promedio por SO de escritorio |
| Nivel educativo promedio | Nivel educativo promedio por SO de escritorio |
| Total de tickets | Suma de tickets por SO de escritorio |

## Estructura del repositorio

```
.
├── README.md
├── DS_C2_SC3_NOMBRE.ipynb     # Libreta de Google Colab
├── DS_C2_SC3_NOMBRE.xlsx      # Resultados, una hoja por consulta
└── data/
    ├── Train.csv
    ├── Test.csv
    ├── Train2.csv
    └── Test2.csv
```

## Cómo ejecutarlo

1. Abre la libreta en Google Colab.
2. Sube los cuatro CSV al entorno de Colab (o ajusta la ruta de lectura en la primera celda).
3. Ejecuta todas las celdas en orden. Al final se genera el `.xlsx`.

Dependencias: `pandas` y `openpyxl`.

```bash
pip install pandas openpyxl
```

## Notas

- El nivel educativo se promedia sobre su valor numérico tal como viene en los datos.
- Los tickets son solicitudes de soporte de un mes específico.
- El repositorio no contiene credenciales, claves ni datos personales fuera de los CSV del reto.

## Autor

Carlos Alberto Tapia Hernández con Claude Code :)
