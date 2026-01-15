# Sistema de Gestión Integral para Industria Maderera (ERP)

![Estado del Proyecto](https://img.shields.io/badge/Estado-En_Desarrollo-yellow)
![Tech Stack](https://img.shields.io/badge/Stack-MEAN%2FMySQL-blue)

## 📖 Descripción
Sistema web integral diseñado para optimizar el flujo operativo de empresas madereras. Abarca desde la adquisición de materia prima hasta la transformación (packing), venta y distribución.

El proyecto resuelve la complejidad de calcular volúmenes de madera (Pies Tablares), gestionar inventarios en tiempo real y controlar la facturación con normativas fiscales (IGV, Detracciones).

## 🏗 Arquitectura y Tecnologías

* **Frontend:** Angular (Gestión de componentes, servicios y vistas reactivas).
* **Backend:** Node.js (API RESTful).
* **Base de Datos:** MySQL 8.0.
* **Diseño:** Arquitectura Relacional con lógica de negocio en base de datos.

## 🗂 Modelo de Datos
El núcleo del sistema es una base de datos relacional robusta que maneja la integridad de los datos financieros y logísticos.

![Diagrama Entidad Relación](database/diagrama_er.png)
*(Asegúrate de guardar tu imagen como 'diagrama_er.png' en la carpeta database)*

### Características destacadas de la BD:
* **Cálculos Automáticos:** Uso de `GENERATED ALWAYS` para calcular totales de compra y saldos pendientes a nivel de fila.
* **Vistas Materializadas (Virtuales):**
    * `v_stock_real`: Kárdex en tiempo real que calcula `Entradas - Salidas` automáticamente.
    * `v_facturas_totales`: Motor financiero que desglosa Subtotal, IGV (18%), Detracción (4%) y Netos.
* **Auditoría:** Sistema de rastreo de cambios mediante campos JSON (`diff_json`) para seguridad de la información.
* **Lógica de Negocio:** Transformación de dimensiones físicas (espesor, ancho, largo) a volumen comercial (PT).

## 🚀 Módulos Principales

1.  **Compras:** Gestión de proveedores y recepción de materia prima.
2.  **Packing (Producción):** Transformación de madera bruta en listas de empaque detalladas.
3.  **Facturación:** Emisión de comprobantes vinculados a las guías de remisión y packing lists.
4.  **Logística (Fletes):** Control de transporte, adelantos y liquidación de fletes.
5.  **Cobranzas:** Gestión de cuentas por cobrar y amortizaciones.

## 🔧 Instalación y Despliegue

1.  Clonar el repositorio:
    ```bash
    git clone [https://github.com/tu-usuario/ERP-Maderera.git](https://github.com/tu-usuario/ERP-Maderera.git)
    ```
2.  Restaurar la base de datos:
    * Importar el archivo `/database/script_db_completo.sql` en MySQL WorkBench o phpMyAdmin.

3.  Backend:
    ```bash
    cd server
    npm install
    npm start
    ```
4.  Frontend:
    ```bash
    cd client
    npm install
    ng serve
    ```

---
**Autor:** [Tu Nombre]
**Licencia:** MIT
