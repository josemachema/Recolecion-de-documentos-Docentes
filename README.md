# 📚 Sistema de Monitoreo de Planeaciones y Entregas

Este proyecto automatiza el **seguimiento de entregas de planeaciones, evidencias y reportes de docentes** usando **Google Sheets + Google Apps Script**.

---

## 🚀 Características
- **Carpetas personales por maestro** (solo accesibles para cada docente y la coordinación).
- **Subcarpetas mensuales automáticas** para organizar las entregas.
- **Registro automático de entregas** (fecha, tipo, tamaño, si fue a tiempo o no).
- **Dashboard en Google Sheets** con estado de cumplimiento por mes.
- **Opcional:** sincronización diaria automática a las 18:00.

---

## 📂 Estructura del Proyecto

- **Google Sheet** con 3 hojas:
  1. **Docentes**: Lista de maestros, correos y carpeta asignada.
  2. **Entregas**: Registro automático de documentos subidos.
  3. **Config**: Parámetros de configuración (carpeta raíz, año, día límite, tipos de documento).

- **Apps Script**:
  - Menú "Monitoreo" con opciones:
    - Crear carpetas por maestro.
    - Crear subcarpetas mensuales.
    - Sincronizar entregas.
    - Instalar disparador diario.

---

## 🛠 Requisitos Previos

- Cuenta de Google con acceso a **Google Drive** y **Google Sheets**.
- Carpeta principal en Google Drive creada (por ejemplo: `PLANEACIONES_2025`).
- Permisos de edición para el coordinador que instalará el script.

---

## 📝 Pasos de Instalación

### 1. Crear el Google Sheet
1. Crea un nuevo Google Sheet llamado **Monitoreo de Entregas**.
2. Agrega **3 hojas** con los nombres: `Docentes`, `Entregas`, `Config`.

#### Ejemplo de cada hoja:

**Docentes:**
| Maestro | Email | CarpetaID | Activo |
|--------|-------|-----------|--------|
| Maestro 1 | maestro1@ejemplo.com |  | TRUE |
| Maestro 2 | maestro2@ejemplo.com |  | TRUE |

**Entregas:** (vacía al inicio)
| Fecha | Mes | SemanaISO | Maestro | Archivo | Tipo | URL | CarpetaID | FileID | SubidoPor | TamañoMB | Modificado | ATiempo |

**Config:**
| Clave | Valor |
|------|-------|
| ROOT_FOLDER_ID | PON_AQUI_EL_ID_DE_LA_CARPETA_PRINCIPAL |
| AÑO_ACTUAL | 2025 |
| DIA_LIMITE | 7 |
| TIPOS_DOC | planeacion,evidencia,reporte |

---

### 2. Configurar Apps Script
1. En el Google Sheet: **Extensiones → Apps Script**.
2. Borra el código que trae por defecto.
3. Pega el código de este repositorio (`Code.gs`).
4. Guarda el proyecto.
5. Regresa al Sheet y recarga la página (F5). Aparecerá el menú **Monitoreo**.

---

### 3. Crear Carpetas y Subcarpetas
1. En la hoja **Config**, pega el ID de la carpeta raíz en `ROOT_FOLDER_ID`.
2. Llena la hoja **Docentes** con los nombres y correos de los maestros.
3. Menú **Monitoreo → 1) Crear/Actualizar carpetas por maestro**.
4. Menú **Monitoreo → 2) Crear subcarpetas mensuales**.

---

### 4. Sincronizar Entregas
- Menú **Monitoreo → 3) Sincronizar entregas ahora** para registrar lo que ya se ha subido.

---

### 5. (Opcional) Instalar Disparador Diario
- Menú **Monitoreo → 4) Instalar disparador diario (18:00)**.
- El sistema se actualizará cada tarde automáticamente.

---

## 🧑‍🏫 Instrucciones para los Maestros
- Usa el **link de tu carpeta personal** para subir archivos.
- Entrega en la subcarpeta del mes correspondiente.
- Nombra los archivos de forma clara, ejemplo: `Planeacion_Semana1_Septiembre.pdf`.
- Fecha límite de entrega: **día 7 de cada mes**.

---

## 🔒 Privacidad
- Cada carpeta de maestro es privada y compartida solo con el docente y coordinación.
- El repositorio **no debe contener** datos reales (correos ni IDs de carpetas). Usa ejemplos genéricos.

---

## 🔧 Desarrollo y Versionado
Se recomienda usar [clasp](https://developers.google.com/apps-script/guides/clasp) para:
- **Descargar** el código desde Apps Script (`clasp pull`).
- **Subir** cambios después de editarlos (`clasp push`).
- Llevar control de versiones en Git.

---

## 🟢 Roadmap / Mejoras Futuras
- Dashboard visual con semáforo de cumplimiento.
- Reporte en PDF semanal para dirección.
- Notificaciones automáticas por correo o chat a maestros que no entregaron.

---

## 📜 Licencia
Este proyecto es de uso interno. Puede ser adaptado para otros ciclos escolares o instituciones.

---

## ✨ Autor
Coordinación Académica – Sistema de Monitoreo de Entregas  
Diseñado para facilitar el seguimiento de planeaciones y evidencias en instituciones educativas.
