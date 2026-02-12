# Caso 2 – Análisis de Órdenes de Compra
Proyecto aplicado a Logística, Operaciones y Análisis de Datos.

---

## Índice

1. [Objetivo del Caso](#objetivo-del-caso)
2. [Dataset](#dataset)
3. [Tablas Dinámicas](#tablas-dinámicas)
4. [Visualizaciones](#visualizaciones)
5. [Conclusiones](#conclusiones)
6. [Herramientas Utilizadas](#herramientas-utilizadas)
7. [Archivos del Proyecto](#archivos-del-proyecto)

---

## Objetivo del Caso

Analizar el desempeño de proveedores, categorías de productos y estados de órdenes de compra en un pequeño dataset, permitiendo:

- Evaluar costos totales por proveedor y categoría  
- Identificar retrasos, cancelaciones y entregas  
- Visualizar información clave para apoyar decisiones operativas y de compras  

Roles relacionados: Analista de Logística / Inventarios, Operaciones, Abastecimiento, Datos/E-commerce.

---

## Dataset

Dataset original de 4 órdenes de compra:

| OC_ID | Fecha_OC | Proveedor | Producto | Categoria | Cantidad | Costo_Unit | Fecha_Entrega | Estado |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| OC001 | 02/01/2024 | Proveedor ABC | Mouse USB | Periféricos | 100 | 10 | 06/01/2024 | Entregado |
| OC002 | 03/01/2024 | proveedor abc | Teclado | Periféricos | 50 | 15 | 10/01/2024 | Retrasado |
| OC003 | 05/01/2024 | Proveedor XYZ | Monitor 24" | Monitores | 20 | 200 | 12/01/2024 | Entregado |
| OC004 | 06/01/2024 | Proveedor 123 | Laptop | Computo | 10 | 700 | 20/01/2024 | Cancelado |

Dataset Limpio

| OC_ID | Fecha_OC   | Proveedor      | Producto     | Categoria   | Cantidad | Costo_Unit | Fecha_Entrega | Estado      | Costo total |
|-------|------------|----------------|------------|------------|----------|------------|---------------|------------|------------|
| OC001 | 02/01/2024 | Proveedor ABC  | Mouse USB   | Periféricos| 100      | 10         | 06/01/2024    | Entregado  | 1000       |
| OC002 | 03/01/2024 | Proveedor ABC  | Teclado     | Periféricos| 50       | 15         | 10/01/2024    | Retrasado  | 750        |
| OC003 | 05/01/2024 | Proveedor XYZ  | Monitor 24" | Monitores  | 20       | 200        | 12/01/2024    | Entregado  | 4000       |
| OC004 | 06/01/2024 | Proveedor 123  | Laptop      | Computo    | 10       | 700        | 20/01/2024    | Cancelado  | 7000       |

> La columna `Costo total` se calculó como `Cantidad × Costo_Unit`.

---

## Tablas Dinámicas

**1. Costo total por proveedor** (solo Entregado y Retrasado)

| Proveedor     | Costo total |
|---------------|------------|
| Proveedor ABC | 1750       |
| Proveedor XYZ | 4000       |
| **Total**     | 5750       |

**2. Cantidad de órdenes por estado**

| Estado      | Cantidad |
|------------|----------|
| Cancelado  | 1        |
| Entregado  | 2        |
| Retrasado  | 1        |
| **Total**  | 4        |

**3. Costo total por categoría** (sin órdenes canceladas)

| Categoria   | Costo total |
|------------|------------|
| Monitores  | 4000       |
| Periféricos| 1750       |
| **Total**  | 5750       |

---

## Visualizaciones

- **Costo total por proveedor** → Columnas  
  ![Costo Total por Proveedor](images/costo_proveedor.png)

- **Fecha de pedido vs Fecha de entrega** → Línea  
  ![Fechas Pedido vs Entrega](images/fechas_linea.png)

- **Distribución de estados de órdenes** → Circular  
  ![Estados de Órdenes](images/estados_circular.png)

> Estas visualizaciones permiten identificar rápidamente proveedores más relevantes, eficiencia de entrega y proporción de estados de órdenes.

---

## Conclusiones

1. El proveedor con mayor inversión es **Proveedor XYZ** (4000).  
2. Se registraron **2 órdenes entregadas, 1 retrasada y 1 cancelada**, permitiendo priorizar seguimiento operativo.  
3. La categoría de mayor costo total es **Monitores** (4000).  
4. La visualización de fechas permite evaluar la eficiencia de entrega y detectar retrasos.  
5. Filtrar por estado de orden es clave para reportes financieros y operativos.

---

## Herramientas Utilizadas

- Excel Online  
- Tablas dinámicas  
- Funciones de agregación (SUMA)  
- Validación básica de datos  
- Gráficos dinámicos (columnas, líneas, circulares)

---

## Archivos del Proyecto

### 🔹 Datos
- [Dataset original](data/ventas_oc.csv)  
- [Dataset limpio](data/ventas_oc_limpia.csv)
- [Excel](data/Compras_Proveedores.xlsx)

### 🔹 Visualizaciones
- `images/costo_proveedor.png`  
- `images/fechas_linea.png`  
- `images/estados_circular.png`
