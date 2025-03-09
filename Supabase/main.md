# Supabase

## Que es Supabase?

Supabase es una plataforma de backend como servicio (BaaS) que proporciona una alternativa de código abierto a *Firebase*. Se basa en **PostgreSQL** y ofrece herramientas para autenticación, almacenamiento, **APIs** en tiempo real y más.

![This is an alt text.](./images/supabase-logo-vector.png "Logo de Supabase.")

## Diferencias a Firebase?

| **Característica**             | **Supabase**                                 | **Firebase**                                   |
|---------------------------------|----------------------------------------------|------------------------------------------------|
| **Base de Datos**               | PostgreSQL (relacional, SQL)                 | Firestore (NoSQL) / Realtime Database          |
| **Modelo de Datos**             | Relacional (SQL) con relaciones entre tablas | NoSQL, orientado a documentos                  |
| **API Automática**              | Genera automáticamente una API REST           | No genera automáticamente una API REST         |
| **Autenticación**               | Email, OAuth, Magic Links                    | Email, Google, Facebook, otros métodos         |
| **Seguridad y Roles**           | Basado en roles de base de datos (PostgreSQL) | Reglas de seguridad específicas de Firebase    |
| **Tiempo Real**                 | WebSockets, sincronización en tiempo real    | Firestore y Realtime Database, sincronización  |
| **Almacenamiento de Archivos**  | Soporta almacenamiento con control de acceso | Firebase Storage                               |
| **Código Abierto**              | Sí, es open-source                           | No, es un servicio cerrado                     |
| **Precios**                     | Plan gratuito, precios bajos                 | Plan gratuito, pero costos según uso           |
| **Escalabilidad**               | Escalable, con PostgreSQL                    | Muy escalable, sin necesidad de gestionar infraestructura |
| **Desarrolladores y Herramientas**| Ideal para quienes prefieren SQL y control  | Ideal para integración con aplicaciones móviles, SDKs específicos |
| **Infraestructura y Control**   | Puedes autohospedarlo y tener control total  | Completamente gestionado por Google            |

