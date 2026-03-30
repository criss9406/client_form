# Registro de Clientes — Versión Básica

Sistema web para registrar clientes a través de un formulario, almacenar sus datos en un archivo Excel y generar reportes en PDF. Diseñado para operar localmente en el equipo del usuario sin necesidad de conexión a internet ni servicios externos.

## Funcionalidades

- Formulario web para capturar nombre, email y servicio del cliente
- Almacenamiento automático en archivo Excel (`clientes.xlsx`)
- Generación de reporte PDF con el listado completo de clientes
- Descarga del archivo Excel como respaldo

## Requisitos

- Python 3.10 o superior

## Instalación

```bash
cd registro-clientes-mvp
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

> En Linux/Mac usar `source venv/bin/activate` en lugar de `venv\Scripts\activate`.

## Ejecución

```bash
uvicorn main:app --reload
```

Abrir `http://localhost:8000` en el navegador.

Para detener el servidor: `Ctrl + C` en la terminal.

## Endpoints

| Método | Ruta | Descripción |
|--------|------|-------------|
| GET | `/` | Muestra el formulario de registro |
| POST | `/guardar-cliente` | Guarda un cliente en el Excel |
| GET | `/descargar-excel` | Descarga el archivo Excel |
| GET | `/generar-reporte` | Genera y descarga el reporte PDF |

## Estructura del proyecto

```
registro-clientes-mvp/
├── templates/
│   └── formulario.html
├── main.py
├── requirements.txt
├── .gitignore
└── README.md
```

Los archivos `clientes.xlsx` y `reporte_clientes.pdf` se generan automáticamente al usar la aplicación.

## Stack técnico

- **FastAPI** — framework web
- **Uvicorn** — servidor ASGI
- **Openpyxl** — lectura y escritura de archivos Excel
- **python-multipart** — procesamiento de formularios HTML
- **ReportLab** — generación de archivos PDF