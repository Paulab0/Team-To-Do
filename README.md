# 🎯 Team To-Do: Gestor de Tareas Colaborativo

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![JSON Server](https://img.shields.io/badge/JSON_Server-A6A6A6?style=for-the-badge&logo=json&logoColor=white)

Un dashboard intuitivo y moderno para la gestión de tareas en equipo, construido con tecnologías web modernas. Ofrece una experiencia de usuario fluida con funcionalidades clave como autenticación, creación, búsqueda y actualización de estado de tareas, todo en tiempo real.

---

## ✨ Características Principales
- **Diseño Responsivo:** Adaptable a diferentes tamaños de pantalla para una experiencia consistente en dispositivos móviles y de escritorio.
- **Login Sencillo:** Sistema de autenticación de usuario (acepta cualquier valor para demostración).
- **Dashboard Interactivo:** Una interfaz limpia y con estética pastel para gestionar tareas.
- **Creación de Tareas:** Añade nuevas tareas con descripciones claras.
- **Búsqueda Inteligente:** Filtra tareas por contenido o por autor con un indicador de carga para una mejor UX.
- **Gestión de Estado:** Marca tareas como `completadas` o `pendientes` con un solo clic.
- **Notificaciones Dinámicas:** Feedback visual instantáneo (éxito, error, información) a través de notificaciones "toast".
- **Backend Simulado:** Utiliza **JSON Server** para una rápida simulación de una API RESTful y persistencia de datos en un archivo `database.json`.

---
## 🚀 Demo en Vivo

## 🛠️ Stack Tecnológico

Este proyecto está dividido en dos partes principales: un frontend moderno y un backend ligero para simular una base de datos.

### Frontend
- **React:** Biblioteca para construir la interfaz de usuario.
- **Vite:** Herramienta de desarrollo frontend ultrarrápida.
- **TailwindCSS:** Framework de CSS para un diseño rápido y personalizable.
- **Context API:** Para un manejo de estado global sencillo (ej. autenticación).
- **React Router DOM:** Para la gestión de rutas en la aplicación.
- **Axios:** Cliente HTTP basado en promesas para realizar solicitudes a la API.
- **React Hot Toast:** Biblioteca para mostrar notificaciones "toast" de forma sencilla y personalizable.

### Backend
- **Node.js:** Entorno de ejecución para el servidor.
- **json-server:** Para crear una API REST falsa con cero codificación en segundos.

---

## 📂 Estructura del Proyecto

El proyecto está organizado en dos directorios principales: `frontend` y `backend`, reflejando la separación de responsabilidades entre la interfaz de usuario y la simulación de la API.

```
team-to-do/
├── backend/
│ ├── database.json          # Archivo de datos para json-server
│ ├── package.json           # Dependencias del backend
│ └── server.js              # Script para iniciar json-server (opcional, si se usa un script personalizado)
├── public/                  # Archivos estáticos del frontend
│ └── ...
├── src/                     # Código fuente del frontend
│ ├── assets/                # Imágenes, iconos, etc.
│ ├── components/            # Componentes reutilizables de React
│ │ ├── AuthForm/
│ │ ├── Dashboard/
│ │ ├── Header/
│ │ ├── Notification/
│ │ └── ...
│ ├── context/               # Contextos de React para manejo de estado global (ej. AuthContext)
│ │ └── AuthContext.jsx
│ ├── hooks/                 # Custom Hooks de React
│ │ └── useAuth.js
│ ├── pages/                 # Páginas principales de la aplicación (Login, Dashboard)
│ │ ├── LoginPage.jsx
│ │ └── DashboardPage.jsx
│ ├── services/              # Funciones para interactuar con la API
│ │ └── api.js
│ ├── App.jsx                # Componente principal de la aplicación
│ ├── main.jsx               # Punto de entrada de la aplicación React
│ └── index.css              # Estilos globales de TailwindCSS
├── .env.example             # Ejemplo de variables de entorno
├── package.json             # Dependencias del frontend y scripts generales
├── tailwind.config.js       # Configuración de TailwindCSS
└── vite.config.js           # Configuración de Vite
```

---

## 🚀 Puesta en Marcha

Sigue estos pasos para configurar y ejecutar el proyecto en tu entorno local.

### 1. Pre-requisitos

Asegúrate de tener instalado [Node.js](https://nodejs.org/) (versión 14 o superior) y npm.

### 2. Instalación

1.  **Clona el repositorio:**
    ```bash
    git clone https://github.com/Melo-develop/team-to-do.git
    cd team-to-do
    ```

2.  **Instala las dependencias del Frontend (en la raíz del proyecto):**
    ```bash
    npm install
    ```

3.  **Navega al directorio `backend` e instala sus dependencias:**
    ```bash
    cd backend
    npm install
    cd ..
    ```

### 3. Configuración de Variables de Entorno (Opcional pero Recomendado)

Aunque este proyecto utiliza `json-server` para simular un backend local, en un entorno de desarrollo real o para futuras expansiones, es una buena práctica gestionar las URLs de la API a través de variables de entorno.

1.  **Crea un archivo `.env` en la raíz del proyecto:**
    Copia el contenido de `.env.example` a un nuevo archivo llamado `.env`.

    ```bash
    cp .env.example .env
    ```

2.  **Configura la URL de la API:**
    Abre el archivo `.env` y asegúrate de que la variable `VITE_API_BASE_URL` apunte a la dirección donde se ejecutará tu `json-server`.

    ```
    # .env
    VITE_API_BASE_URL=http://localhost:3001
    ```
    *Nota:* Vite expone las variables de entorno que comienzan con `VITE_` al código del cliente.

### 4. Configuración de la Base de Datos Simulada

El backend utiliza un archivo `database.json` para simular la base de datos. Este archivo debe existir en la carpeta `backend`. Si por alguna razón no lo tienes, créalo con el siguiente contenido inicial:

```json
{
  "tasks": []
}
```

### 4. Ejecución del Proyecto

Necesitarás dos terminales para ejecutar el frontend y el backend de forma simultánea.

1.  **En la primera terminal, inicia el backend (API):**
    *Desde la raíz del proyecto*, ejecuta:
    ```bash
    npm run server
    ```
    Esto iniciará `json-server` en el puerto `3001` y "observará" los cambios en `backend/database.json`.

2.  **En la segunda terminal, inicia el frontend:**
    *Desde la raíz del proyecto*, ejecuta:
    ```bash
    npm run dev
    ```
    La aplicación estará disponible en [http://localhost:5173](http://localhost:5173) (o el puerto que indique Vite).

---

## 🕹️ Uso

1.  Abre la aplicación en tu navegador.
2.  Ingresa cualquier combinación de usuario y contraseña en el formulario de login.
3.  Una vez dentro, podrás ver el dashboard y empezar a gestionar tareas.
4.  Utiliza el botón **"Cerrar Sesión"** en la esquina superior derecha para volver a la pantalla de login.

---

## 👩‍💻 Autora

Desarrollado con ❤️ por **Paula Buitrago**.
