# Hola, soy JEFFERSON ANTONIO ARRIOLA REYES 👋
### 🚀 Ingenierio de Sistemas | 🎵 UNIVERSIDAD NACIONAL DE UCAYALI (VIII Ciclo) |

[![Angular](https://img.shields.io/badge/Frontend-Angular-dd0031?style=flat&logo=angular&logoColor=white)](https://angular.io/)
[![Node.js](https://img.shields.io/badge/Backend-Node.js-339933?style=flat&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![MySQL](https://img.shields.io/badge/Database-MySQL_8.0-4479a1?style=flat&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Engineering](https://img.shields.io/badge/Focus-Methods_Engineering-orange?style=flat&logo=google-scholar&logoColor=white)]()


## Sobre mi
Soy una desarrolladora de software y estudiante avanzado con un perfil multidisciplinario. Combino la rigurosidad de la **Ingeniería de Sistemas** y la **Innovación** con la disciplina y sensibilidad de mi formación profesional en **Ingenieria de Sistemas**. Mi enfoque se centra en crear sistemas robustos, interfaces intuitivas y soluciones que optimicen procesos complejos.

---
PAGINA WEB: https://antoniotabo.github.io/mi-portafolio/ 

## 🛠 Habilidades y Stack Tecnológico

### 💻 Desarrollo de Software
* **Frontend:** Especialista en **Angular** (Componentes, Servicios, RxJS). Mi interés en la innovación y la mejora visual continua me permite tener un ojo crítico para la UI/UX y la teoría del color.
* **Backend:** Desarrollo de APIs escalables con **Node.js** y Express.
* **Base de Datos Avanzada:** Diseño de esquemas complejos en **MySQL Workbench 8.0**. Manejo de Vistas Materializadas, Triggers, Columnas Generadas y datos JSON.
* **Sistemas:** Conocimientos en Sistemas Distribuidos, Migración de Máquinas Virtuales y Arquitectura de Servidores.

### ⚙️ Ingeniería y Procesos
* **Ingeniería de Métodos:** Aplicación de metodologías **5S**, **Balance de Líneas** y Estudios de Tiempos para la optimización de recursos.


---

## 🏆 Proyecto Destacado: ERP Integral Maderero

Diseñé y desarrollé la arquitectura de base de datos y la lógica de negocio para un sistema de gestión industrial. Este proyecto resuelve la complejidad de transformar materia prima (dimensiones físicas) en productos comerciales (Pies Tablares), integrando facturación y logística.

### 🧠 Ingeniería de Datos y Soluciones Implementadas

Basado en el análisis de mi código fuente, estas son las soluciones de ingeniería implementadas:

#### 1. Kárdex e Inventario en Tiempo Real
[cite_start]Implementé una arquitectura de Vistas SQL (`v_stock_real`) que consolida dinámicamente el inventario[cite: 89, 154].
* **Desafío:** Evitar la desincronización entre el almacén físico y el sistema.
* **Solución:** El stock se calcula al vuelo restando las salidas de producción (`packing`) a las entradas (`compras`), sin necesidad de procesos batch nocturnos .

#### 2. Lógica Financiera Inmutable
[cite_start]Para garantizar la integridad contable, trasladé la lógica de negocio a la capa de persistencia usando **Columnas Generadas (Generated Columns)**[cite: 20].
* [cite_start]**Cálculos Automáticos:** El sistema calcula automáticamente subtotales, IGV (18%) y Detracciones (4%) en la vista `v_facturas_totales`[cite: 110].
* [cite_start]**Estados Logísticos:** La tabla `fletes` determina automáticamente si un transporte está `CANCELADO` o `PENDIENTE` basándose en la diferencia matemática entre el valor del flete y los pagos realizados[cite: 35].

#### 3. Auditoría y Trazabilidad (Compliance)
Implementé un sistema de seguridad que registra cada cambio crítico en la base de datos.
* [cite_start]**Tecnología:** Uso de campos tipo **JSON** en la tabla `auditoria` para almacenar el diferencial exacto (`diff_json`) de los datos antes y después de una modificación[cite: 6].

#### 4. Transformación de Unidades (Business Logic)
El sistema maneja la conversión específica de la industria maderera.
* [cite_start]La tabla `packing_items` procesa dimensiones milimétricas (Espesor `e`, Ancho `a`, Largo `l`) para calcular el volumen comercial (`volumen_pt`) necesario para la facturación y exportación[cite: 46].

---
### 5. Experiencia General 
EXPERIENCIA LABORAL: Fuente Planillas Electrónicas
Ruc 20610173285
Razón Social ADECCO SALES & MARKETING S.A. ADECCO S & MS.A.
Desde 08/01/2024
Hasta 22/01/2024

Ruc 20393864886
Razón Social HIPERMERCADOS TOTTUS ORIENTE S.A.C.
Desde 19/11/2018
Hasta 31/07/2023

Ruc 20103845328
Razón Social CAJA MUNICIPAL DE AHORRO Y CREDITO DE MAYNAS
Desde 04/04/2018
Hasta 30/06/2018

Ruc 20429683581
Razón Social CINEPLEX S.A
Desde 03/04/2017
Hasta 18/09/2017

adjunto Certificado Unico Laboral, emitido por el Ministro de Trabajo
[CUL.pdf](https://github.com/user-attachments/files/24986529/CUL.pdf)


## 📂 Estructura del Proyecto (Preview)

El núcleo del sistema se basa en una interconexión sólida entre los módulos de **Compras**, **Producción (Packing)** y **Ventas**:

```sql
-- Ejemplo de lógica de negocio real extraída del proyecto:
-- Vista que calcula el saldo neto a cobrar restando anticipos y aplicando detracciones
CREATE VIEW v_facturas_totales AS 
SELECT 
    f.id,
    (SUM(fi.total_item) * (1 + f.igv_pct)) AS total_con_igv,
    -- Cálculo automático de deuda restante:
    ((SUM(fi.total_item) * (1 + f.igv_pct)) - COALESCE(SUM(c.anticipo),0)) AS saldo
FROM facturas f 
JOIN factura_items fi ON fi.factura_id = f.id
GROUP BY f.id;

## Contacto 
WhatsApp: +51 915366877
email: antonio.tabo@gmail.com    

