# Módulo 01 — Sistema de Presupuesto en Excel

Modelo de datos financieros construido con lógica de Control de Gestión, que sienta las bases para un sistema analítico completo.

---

## El punto de partida

Antes de conectar Power BI, antes de escribir una consulta SQL, hay una pregunta fundamental:

**¿Están bien estructurados mis datos en origen?**

Este módulo responde esa pregunta aplicándola a un caso real: las finanzas de una familia española — **Los Emigrantes** — con ingresos, gastos fijos, gastos variables y una meta de ahorro mensual.

El modelo no está diseñado para ser bonito. Está diseñado para escalar.

---

## Estructura del archivo

El libro Excel está organizado como un minisistema de información, no como una hoja de cálculo tradicional:

| Hoja | Rol en el modelo | Editable |
|------|-----------------|----------|
| Instrucciones | Guía de uso y documentación | No |
| Categorías | Tabla de dimensiones — catálogo maestro | Sí |
| Plan-Patrón | Entrada de datos — presupuesto de referencia | Sí |
| Plan2025 | Tabla de hechos — cálculo y consolidación anual | Sí |
| Panel | Capa de visualización — resumen ejecutivo | No |

Esta separación entre **dimensiones**, **hechos** y **visualización** no es casual. Es la misma lógica que se aplica en el Módulo 02 con el modelo en estrella.

---

## Funcionalidades implementadas

### Modelo de datos

- Categorías normalizadas con lista desplegable concatenada (`Tipo - Categoría (Descripción)`)
- `BUSCARX` para clasificación automática desde la tabla de dimensiones
- Sin duplicidad de información entre hojas

### Cálculo y análisis

- Presupuesto mensual y anual con acumulados YTD automáticos
- 5 KPIs financieros con umbrales definidos:

| KPI | Verde (Óptimo) | Amarillo (Precaución) | Rojo (Alerta) |
|-----|---------------|----------------------|---------------|
| Ganancia / Ingreso | > 15% | 10–15% | < 10% |
| Gasto Fijo / Ingreso | < 45% | 45–50% | > 50% |
| Gasto Variable / Ingreso | < 35% | 35–40% | > 40% |
| Vivienda / Ingreso | < 30% | 30–35% | > 35% |
| Alimentación / Ingreso | < 15% | 15–25% | > 25% |

- Formato condicional automático (semáforo verde / amarillo / rojo)
- `SI.ERROR` en todos los KPIs para gestión de datos vacíos

### Automatización

- Botón **"Insertar Plan"** — carga el Plan-Patrón al modelo mensual con VBA
- Botón **"Limpiar Plan"** — resetea los datos de entrada

---

## Cómo usar el archivo

1. Abre el archivo y habilita las macros
2. Ve a **Plan-Patrón** e introduce tu presupuesto de referencia mensual
3. Pulsa **"Insertar Plan"** para cargar los datos
4. Registra tus gastos reales mes a mes en **Plan2025**
5. Revisa los KPIs — si alguno aparece en rojo, es una señal de alerta
6. Consulta el resumen visual en **Panel**

---

## Decisiones de diseño

Esta sección es la más importante del README. Un template cualquiera no explica sus decisiones. Un modelo diseñado con criterio, sí.

### ¿Por qué una hoja de Categorías separada?

Para tener una única fuente de verdad. Si cambias una categoría, el cambio se propaga automáticamente. Es el mismo principio de una tabla de dimensiones en un modelo analítico.

### ¿Por qué los KPIs están en Plan2025 y no en el Panel?

Porque el cálculo y la visualización son responsabilidades distintas. El Panel consume, no calcula. Esto facilita la migración futura a Power BI.

### ¿Por qué VBA para los botones?

Para automatizar la carga del plan mensual sin que el usuario tenga que copiar y pegar manualmente. Es una decisión de usabilidad, no de complejidad técnica.

### ¿Por qué la familia se llama "Los Emigrantes"?

Porque el caso de uso está pensado para una familia de origen latinoamericano viviendo en España, con categorías específicas como **Remesas**. Es un caso real, no ficticio genérico.

---

## Resultados del modelo

Con los datos cargados para 2025, el modelo muestra:

| Concepto | Importe Anual | % sobre Ingreso |
|----------|--------------|-----------------|
| Ingreso Total | 33.551 € | 100% |
| Gastos Fijos | 15.600 € | 46,5% ⚠️ |
| Gastos Variables | 12.894 € | 38,4% ⚠️ |
| Ahorro / Utilidad | 5.057 € | 15,1% ✅ |

La tasa de ahorro del 15% cumple el umbral mínimo de la regla 50/30/20. Los gastos fijos y variables están en zona amarilla — normal, con margen de mejora.

---

## Metodología: regla 50/30/20

| Categoría | Límite | En este modelo |
|-----------|--------|----------------|
| Gastos Fijos | ≤ 50% | Vivienda, suministros, seguros, financiación |
| Gastos Variables | ≤ 30% | Alimentación, ocio, transporte, compras |
| Ahorro / Utilidad | ≥ 20% | Lo que queda después de vivir bien |

Cada módulo del proyecto valida si el comportamiento financiero real cumple estos umbrales.

---

## Conexión con los siguientes módulos

```
Módulo 01 (Excel)
    └── Exportación estructurada
        └── Módulo 02 (Power Query + modelo en estrella)
            └── Medidas DAX
                └── Módulo 03 (Dashboard Plan vs Real)
```

En el Módulo 02 se toman los datos de este Excel, se combinan con transacciones bancarias reales y se construye el modelo relacional.

---

## Tecnologías

Excel · VBA · BUSCARX · Formato condicional · Diseño de modelo de datos

---

## Descarga

Si no estás familiarizado con GitHub, puedes descargar el archivo directamente desde Google Drive:

👉 [Descargar archivo Excel desde Google Drive](https://drive.google.com/file/d/1o8NZMudJup22gAY8u5-vRahDeFgRlaGM/view?usp=sharing)

---

## Autor

**Diosvely Pérez Arteaga** — Controller de Gestión con perfil técnico

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Perfil-0077B5?style=flat&logo=linkedin)](https://www.linkedin.com/in/diosvelyperezarteaga)
[![GitHub](https://img.shields.io/badge/GitHub-Repositorio-181717?style=flat&logo=github)](https://github.com/Diosvely)



