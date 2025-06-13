# ⚡ ShipFree (by JaimeTR)

¡Hola! 👋

**ShipFree** es una alternativa gratuita a plataformas como ShipFast, diseñada para simplificar y optimizar tu proceso de envíos. Está construida con tecnologías web modernas como **Next.js**, **Supabase**, **Stripe**, **LemonSqueezy**, **Drizzle ORM** y **Mailgun**.

---

## ✨ Características

* Optimización SEO
* Autenticación de usuarios con Supabase
* Integración con Stripe y LemonSqueezy
* Notificaciones por correo vía Mailgun
* Interfaz moderna construida con Next.js y TailwindCSS

---

## 🐳 Configuración con Docker

**ShipFree** ofrece configuraciones Docker tanto para entornos de **desarrollo** como de **producción**. A continuación, te mostramos cómo están organizados los archivos y cómo iniciar tu entorno.

### 📁 Estructura de archivos Docker

```
docker
├── dev
│   ├── Dockerfile                  # Dockerfile para desarrollo
│   ├── docker-compose.yml          # Configuración base para desarrollo
│   ├── docker-compose.mongodb.yml  # Desarrollo con MongoDB
│   └── docker-compose.postgres.yml # Desarrollo con PostgreSQL
└── prod
    ├── Dockerfile                  # Dockerfile para producción
    ├── docker-compose.yml          # Configuración base para producción
    ├── docker-compose.mongodb.yml  # Producción con MongoDB
    └── docker-compose.postgres.yml # Producción con PostgreSQL
```

---

## 🔧 Entorno de Desarrollo

En desarrollo, el proyecto se ejecuta en **modo observación (watch mode)**, lo que significa que detecta automáticamente los cambios y reconstruye la aplicación. Ideal para desarrollo local, **no debe usarse en producción**.

### 🛠️ Comandos para desarrollo

1. **Configuración base** (sin base de datos):

   ```bash
   docker-compose -f docker/dev/docker-compose.yml up --build
   ```

2. **Con PostgreSQL**:

   ```bash
   docker-compose -f docker/dev/docker-compose.yml -f docker/dev/docker-compose.postgres.yml up --build
   ```

3. **Con MongoDB**:

   ```bash
   docker-compose -f docker/dev/docker-compose.yml -f docker/dev/docker-compose.mongodb.yml up --build
   ```

### 🤔 ¿Por qué usar modo observación?

* Refleja cambios en tiempo real sin reiniciar el servidor manualmente.
* Ideal para desarrollo, pero **no recomendable para producción** por temas de rendimiento y seguridad.

---

## 🚀 Entorno de Producción

El entorno de producción está optimizado para **rendimiento** y **seguridad**. Utiliza una compilación multi-etapa que reduce el tamaño de la imagen y solo incluye las dependencias necesarias.

### 🛠️ Comandos para producción

1. **Configuración base** (sin base de datos):

   ```bash
   docker-compose -f docker/prod/docker-compose.yml up --build -d
   ```

2. **Con PostgreSQL**:

   ```bash
   docker-compose -f docker/prod/docker-compose.yml -f docker/prod/docker-compose.postgres.yml up --build -d
   ```

3. **Con MongoDB**:

   ```bash
   docker-compose -f docker/prod/docker-compose.yml -f docker/prod/docker-compose.mongodb.yml up --build -d
   ```

### 🔍 Diferencias clave en producción

* **Sin modo observación**: La aplicación está precompilada y requiere recompilación ante cualquier cambio.
* **Imágenes optimizadas**: Tamaño reducido y arranque más rápido.
* **Variables de entorno**: Asegúrate de definir todas (por ejemplo: `DATABASE_URL`, `API_KEY`, etc.)

---

## 💻 Integración con Portainer

**Portainer** está incluido en los entornos de desarrollo y producción para facilitar la gestión de contenedores Docker desde una interfaz web.

* **Acceso a Portainer**: `http://localhost:9000`
* **Credenciales iniciales**: Se configuran en el primer inicio.

---

## ⚠️ Aviso

* **Modo Desarrollo**: Usa modo observación. No recomendado para producción.
* **Modo Producción**: Optimizado para rendimiento y seguridad. Requiere recompilar para reflejar cambios.

---

## 📂 Documentación

Consulta la documentación completa en:
👉 [Docs ShipFree - JaimeTR](https://shipfree.idee8.agency/docs)

---

## 📜 Código de Conducta

Por favor, revisa nuestro [Código de Conducta](CODE_OF_CONDUCT.md) antes de contribuir.

---

## 🤝 Cómo contribuir

Si deseas colaborar con el proyecto, por favor consulta el archivo [CONTRIBUTING.md](CONTRIBUTING.md).

