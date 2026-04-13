# 📁 Módulo 01 — Sistema de Presupuesto en Excel

> *Este no es un template de presupuesto.*
> *Es un modelo de datos financieros construido con lógica de Control de Gestión,*
> *que sienta las bases para un sistema analítico completo.*

---

## ⚡ El punto de partida

Antes de conectar Power BI, antes de escribir una query SQL, hay una pregunta que todo analista de datos debería hacerse:

**¿Están bien estructurados mis datos en origen?**

Este módulo responde esa pregunta aplicándola a un caso real: las finanzas de una familia española — *Los Emigrantes* — con ingresos, gastos fijos, gastos variables y una meta de ahorro mensual.

El modelo no está diseñado para ser bonito. Está diseñado para **escalar**.

---

## 🗂 Estructura del archivo

El libro Excel está organizado como un mini-sistema de información, no como una hoja de cálculo tradicional:

| Hoja | Rol en el modelo | Editable |
|------|-----------------|----------|
| **Instrucciones** | Guía de uso y documentación | No |
| **Categorías** | Tabla de dimensiones — catálogo maestro | Sí |
| **Plan-Patrón** | Entrada de datos — presupuesto de referencia | Sí |
| **Plan2025** | Tabla de hechos — cálculo y consolidación anual | Sí |
| **Dashboard** | Capa de visualización — resumen ejecutivo | No |

> Esta separación entre **dimensiones**, **hechos** y **visualización** no es casual.  
> Es la misma lógica que usaremos en el Módulo 02 cuando construyamos el modelo en estrella.

---

## ⚙️ Funcionalidades implementadas

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

## ▶️ Cómo usar el archivo

1. Abre el archivo y **habilita las macros**
2. Ve a **Plan-Patrón** e introduce tu presupuesto de referencia mensual
3. Pulsa **"Insertar Plan"** para cargar los datos
4. Registra tus gastos reales mes a mes en **Plan2025**
5. Revisa los KPIs — si alguno aparece en rojo, es una señal de alerta
6. Consulta el resumen visual en **Dashboard**

---

## 🧠 Decisiones de diseño — por qué está construido así

Esta sección es la más importante del README.  
Un template cualquiera no explica sus decisiones. Un modelo diseñado con criterio, sí.

**¿Por qué una hoja de Categorías separada?**  
Para tener una única fuente de verdad. Si cambias una categoría, el cambio se propaga automáticamente. Es el mismo principio de una tabla de dimensiones en un modelo analítico.

**¿Por qué los KPIs están en Plan2025 y no en el Dashboard?**  
Porque el cálculo y la visualización son responsabilidades distintas. El Dashboard consume, no calcula. Esto facilita la migración futura a Power BI.

**¿Por qué VBA para los botones?**  
Para automatizar la carga del plan mensual sin que el usuario tenga que copiar y pegar manualmente. Es una decisión de usabilidad, no de complejidad técnica.

**¿Por qué la familia se llama "Los Emigrantes"?**  
Porque el caso de uso está pensado para una familia de origen latinoamericano viviendo en España, con categorías específicas como *Remesas*. Es un caso real, no ficticio genérico.

---

## 📊 Resultado del modelo — datos reales del caso

Con los datos cargados para 2025, el modelo muestra:

| Concepto | Importe Anual | % sobre Ingreso |
|----------|--------------|-----------------|
| Ingreso Total | 33.551 € | 100% |
| Gastos Fijos | 15.600 € | 46.5% ⚠️ |
| Gastos Variables | 12.894 € | 38.4% ⚠️ |
| Ahorro / Utilidad | 5.057 € | 15.1% ✅ |

> La tasa de ahorro del 15% cumple el umbral mínimo de la regla 50/30/20.  
> Los gastos fijos y variables están en zona amarilla — Normal, con margen de mejora.

---

## 🔗 Conexión con los siguientes módulos

Este archivo es el **origen de datos** del sistema completo:

```
Módulo 01 (Excel)
    └── Exportación estructurada
        └── Módulo 02 (Power Query + modelo en estrella)
            └── Medidas DAX
                └── Módulo 03 (Dashboard Plan vs Real)
```

En el Módulo 02 tomaremos los datos de este Excel, los combinaremos con transacciones bancarias reales y construiremos el modelo relacional.

---

## 📺 Vídeo explicativo

📺 **Vídeo 1 de la serie** — *(próximamente disponible)*

En el vídeo se explica:
- Cómo se construyó el modelo desde cero
- Las decisiones de diseño y por qué se tomaron
- Cómo usar el archivo con datos propios
- Qué errores cometí y cómo los resolví

---
## 📥 ¿Problemas para descargar desde GitHub?

Si no estás familiarizado con GitHub, puedes descargarlo directamente desde Google Drive:

👉 [Descargar archivo Excel desde Google Drive](https://drive.google.com/file/d/1o8NZMudJup22gAY8u5-vRahDeFgRlaGM/view?usp=sharing)
---
## 👤 Autor

**Diosvely Pérez Arteaga** — Controller Financiero en transición hacia Data Analytics

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Perfil-0077B5?style=flat&logo=linkedin)](https://www.linkedin.com/in/diosvelyperezarteaga)
[![GitHub](https://img.shields.io/badge/GitHub-Repositorio-181717?style=flat&logo=github)](https://github.com/Diosvely)
