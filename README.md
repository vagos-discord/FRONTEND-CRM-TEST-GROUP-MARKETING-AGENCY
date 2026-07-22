# 🎨 CRM - Frontend

Repositorio cliente para la interfaz de usuario del sistema **CRM**, desarrollado con **Next.js**, **TypeScript** y **Tailwind CSS**.

---

## 📌 Regla de Oro del Equipo (Gitflow & Seguridad)

> ⛔ **Está estrictamente prohibido hacer `push` directo o trabajar sobre las ramas `main` o `dev`.**  
> * Las ramas `main` y `dev` están **protegidas**.
> * Todo desarrollo se realiza en una rama propia creada a partir de `dev` (ejemplo: `feature/pantalla-login`).
> * La integración de código se hace **ÚNICAMENTE mediante Pull Requests (PR)** apuntando hacia `dev` y requiere la revisión y aprobación del Tech Lead.

---

## 💻 Requisitos Previos del Sistema

Antes de comenzar, asegúrate de tener instalado en tu máquina local:
* **Node.js** (Versión `18.x` o superior)
* **npm** o **pnpm**
* **Git**
* El backend levantado y corriendo (por defecto en `http://localhost:4000`)

---

## 🛠️ Paso a Paso de Instalación y Configuración Inicial

### 1. Clonar el repositorio y posicionarse en `dev`
Abre tu terminal e ingresa los siguientes comandos:

```bash
git clone https://github.com/vagos-discord/FRONTEND-CRM-TEST-GROUP-MARKETING-AGENCY.git
cd FRONTEND-CRM-TEST-GROUP-MARKETING-AGENCY
git checkout dev
git pull origin dev
```

### 2. Instalar dependencias del proyecto

```bash
npm install
```

### 3. Configurar las Variables de Entorno (`.env.local`)
Crea un archivo llamado `.env.local` en la raíz del proyecto frontend:

* **En Linux / macOS / Bash:**
  ```bash
  cp .env.example .env.local
  ```
* **En Windows (PowerShell):**
  ```powershell
  Copy-Item .env.example .env.local
  ```

Abre el archivo `.env.local` generado y define la URL del API Backend:

```env
NEXT_PUBLIC_API_URL=http://localhost:4000/api
```

---

## 🚀 Levantar el Entorno de Desarrollo

Ejecuta el servidor de desarrollo:

```bash
npm run dev
```

Abre tu navegador en [http://localhost:3000](http://localhost:3000) para ver la aplicación corriendo.

---

## 🔄 Flujo de Trabajo con Git (Gitflow)

### Paso 1: Iniciar una nueva tarea
```bash
git checkout dev
git pull origin dev
git checkout -b feature/nombre-de-tu-tarea
```

### Paso 2: Guardar y subir avances
```bash
git add .
git commit -m "feat: implementar componente de tabla de contactos"
git push -u origin feature/nombre-de-tu-tarea
```

### Paso 3: Sincronizar tu rama con `dev` (Rebase)
```bash
git fetch origin dev
git rebase origin/dev
```

### Paso 4: Abrir el Pull Request (PR)
1. Ve al repositorio en **GitHub**.
2. Haz clic en **Compare & pull request**.
3. Revisa los destinos: `base: dev` 👈 `compare: feature/nombre-de-tu-tarea`.
4. Asigna al **Tech Lead** como revisor.

---

## 💡 Convención de Commits

* `feat:` Nueva funcionalidad o pantalla.
* `fix:` Corrección de UI, bugs o componentes.
* `docs:` Cambios en la documentación.
* `style:` Estilos, Tailwind o maquetación sin lógica.
* `refactor:` Optimización de código/componentes.

---

## ⚠️ Resolución de Problemas Frecuentes

* 🔴 **Error:** `ECONNREFUSED 127.0.0.1:4000` o fallos en las peticiones API.
  * **Solución:** Asegúrate de que el servidor Backend esté levantado en el puerto `4000` y revisa la variable `NEXT_PUBLIC_API_URL` en tu `.env.local`.

* 🔴 **Error:** `GH006: Protected branch update failed`
  * **Solución:** No hagas push a `dev` o `main`. Crea tu rama `feature/` y abre un PR.
