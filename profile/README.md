# LUDO3 — FIUBA

**LUDO** es la plataforma digital de la Facultad de Ingeniería de la UBA. Integra la gestión académica, administrativa e institucional en una sola app móvil.

---

## Repositorios

| Repo | Descripción | Stack |
|------|-------------|-------|
| `ludo3-mobile` | App móvil para alumnos, docentes y administrativos | React Native · Expo · TypeScript |
| `ludo3-backend` | API REST y lógica de negocio | Django · DRF · PostgreSQL |
| `ludo3-mobile-teacher` | Vista docente (legacy) | React Native |

---

## Funcionalidades

**Alumnos**
- Inscripción a comisiones y seguimiento de materias cursadas, aprobadas y pendientes
- Calendario académico y estadísticas de avance
- Credencial digital y verificación de identidad por reconocimiento facial
- Plan de carrera interactivo integrado con FIUBA-Map
- Trámites y formularios online
- Grupos de estudio con comparación de horarios
- Mapa de aulas con búsqueda y resaltado de salas por piso
- Avisos institucionales con push notifications

**Docentes**
- Gestión de comisiones, cuatrimestres y evaluaciones
- Toma de asistencia con QR
- Validación de identidad de alumnos
- Publicación de novedades y calificaciones

**Administradores**
- ABM de departamentos, comisiones y usuarios
- Envío de avisos masivos segmentados por grupo (alumnos, docentes, administrativos, todos)
- Panel de gestión desde la misma app móvil

---

## Integraciones

- **SIU Guaraní** — historial académico y finales (requiere VPN FIUBA)
- **FIUBA-Map** — plano interactivo de edificios de la facultad
- **Google Sign-In** — autenticación OAuth
- **Firebase** — push notifications

---

## Desarrollo local

Cada repo tiene sus instrucciones en su propio `README.md`. En líneas generales:

```bash
# Backend
cd ludo3-backend
docker-compose up

# Mobile (web / emulador Android)
cd ludo3-mobile
cp .env.template .env   # completar variables
npm install
npx expo start          # web
npx expo run:android    # emulador Android
```

Los tests E2E (Playwright) viven en `ludo3-mobile/e2e/` y requieren el backend corriendo:

```bash
cd ludo3-mobile/e2e
bash setup-db.sh        # siembra usuario de test
npx playwright test
```

---
