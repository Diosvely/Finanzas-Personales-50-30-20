# Módulo 02 — Modelo en Estrella con Power Query y Power Pivot

ETL completo desde extractos bancarios de CaixaBank hasta 
un modelo dimensional en estrella listo para análisis.

---

## Qué construimos en este módulo

Partimos de dos archivos CSV del banco y los transformamos 
en un modelo analítico relacional con Power Query y Power Pivot.

El resultado: un sistema que se actualiza solo cada mes 
cuando llega un nuevo extracto bancario.

---

## Arquitectura del modelo

**2 Tablas de Hechos:**
- `FactReales` — transacciones bancarias reales
- `FactPresupuesto` — plan mensual por categoría

**4 Dimensiones:**
- `dimCalendario` — inteligencia de tiempo
- `dimCategorias` — clasificación de gastos e ingresos
- `dimConceptos` — mapeo de conceptos bancarios
- `dimCliente` — titulares de las cuentas

---

## Conceptos clave explicados en el video

- Por qué el modelo en estrella supera a las tablas planas
- Parámetros de ruta para hacer el archivo portátil
- Tabla de mapeo como fuente de verdad para categorías
- Granularidad: por qué los reales y el presupuesto 
  tienen distinto nivel de detalle
- Funciones personalizadas en M para automatizar el unpivot
- Checklist de conceptos para garantizar calidad del dato

---

## Archivo disponible

El archivo completo del proyecto estará disponible 
al publicar el Módulo 03 (video final de la serie).

📥 Mientras tanto, puedes descargar el Módulo 01 aquí:
[Módulo 01 — Sistema de Presupuesto en Excel](https://github.com/Diosvely/Finanzas-Personales-50-30-20/tree/main/01-Presupuestos)

---

## Tecnologías

Excel · Power Query · Lenguaje M · Power Pivot · 
Modelado dimensional

---

## Autor

**Diosvely Pérez Arteaga** — Controller de Gestión 
con perfil técnico

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Perfil-0077B5?style=flat&logo=linkedin)](https://www.linkedin.com/in/diosvelyperezarteaga)
[![GitHub](https://img.shields.io/badge/GitHub-Repositorio-181717?style=flat&logo=github)](https://github.com/Diosvely)
