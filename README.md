<p align="center">
  <img src="https://img.shields.io/badge/Home%20Assistant-41BDF5?style=for-the-badge&logo=homeassistant&logoColor=white" alt="Home Assistant">
  <img src="https://img.shields.io/badge/Google%20Nest%20Hub-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Google Nest Hub">
  <img src="https://img.shields.io/badge/100%25%20Local-06d6a0?style=for-the-badge" alt="100% Local">
  <img src="https://img.shields.io/badge/Sin%20Nabu%20Casa-ff6b35?style=for-the-badge" alt="Sin Nabu Casa">
</p>

<h1 align="center">📺 Home Assistant → Google Nest Hub<br>Guía de Cast Local</h1>

<p align="center">
  <strong>Castea tu dashboard de Home Assistant a tu Google Nest Hub 2 de forma automática, 100% local, por HTTP, y sin necesidad de Nabu Casa.</strong>
</p>

<p align="center">
  <a href="https://TU_USUARIO.github.io/NOMBRE_REPO/](https://serverheaven.github.io/Cast-home-assistant-to-google-nest/">🌐 Ver la guía online</a> ·
  <a href="https://github.com/TU_USUARIO/NOMBRE_REPO/issues">🐛 Reportar error</a> ·
  <a href="https://github.com/TU_USUARIO/NOMBRE_REPO/issues">💡 Sugerir mejora</a>
</p>

---

## 📖 ¿Qué es esto?

Una guía web interactiva y paso a paso que explica **3 métodos** para mostrar dashboards de Home Assistant en pantallas Google Nest Hub usando únicamente tu red local.

**Problema:** El cast oficial de Home Assistant requiere HTTPS con certificados válidos o una suscripción a Nabu Casa. Si tu instancia solo funciona por HTTP en local, no puedes usar el cast nativo.

**Solución:** Esta guía documenta las alternativas de la comunidad que funcionan con HTTP local, sin exponer nada a internet.

## 🎯 Métodos incluidos

| # | Método | Dificultad | Auto-recuperación | Descripción |
|---|--------|:----------:|:-----------------:|-------------|
| 1 | **Continuously Casting Dashboards** | 🟢 Fácil | ✅ Sí | Integración HACS con config por UI, horarios y re-cast automático |
| 2 | **DashCast** | 🟡 Media | ❌ Manual | Componente custom ligero, requiere automatizaciones YAML |
| 3 | **CATT** | 🔴 Alta | ❌ Manual | Herramienta CLI en Python, máximo control, requiere host adicional |

## ✅ Requisitos previos

- **Home Assistant** funcionando en tu red local (HTTP, ej: `http://192.168.1.100:8123`)
- **Google Nest Hub 2** configurado y en la misma red Wi-Fi
- **HACS** instalado en Home Assistant (para métodos 1 y 2)
- **IP fija** asignada al Nest Hub desde tu router

## 🚀 Inicio rápido

1. Clona este repositorio o descarga el archivo HTML:

```bash
git clone https://github.com/TU_USUARIO/NOMBRE_REPO.git
```

2. Abre `index.html` en tu navegador, o visita la [versión online](https://TU_USUARIO.github.io/NOMBRE_REPO/).

3. Sigue el método que prefieras paso a paso.

## 🔧 Configuración común a todos los métodos

Independientemente del método elegido, necesitarás configurar **Trusted Networks** en tu `configuration.yaml` para que el Nest Hub pueda iniciar sesión sin contraseña:

```yaml
homeassistant:
  auth_providers:
    - type: trusted_networks
      trusted_networks:
        - 192.168.1.XX/32  # IP fija de tu Nest Hub
      trusted_users:
        192.168.1.XX:
          - "TU_USER_ID"
      allow_bypass_login: true
    - type: homeassistant
```

> ⚠️ **Importante:** Reinicia Home Assistant después de modificar este archivo.

## 📁 Estructura del repositorio

```
.
├── index.html          # Guía web completa (archivo único, sin dependencias)
├── README.md           # Este archivo
└── LICENSE             # Licencia del proyecto
```

## 💡 Tips incluidos en la guía

- Instalar **kiosk-mode** para ocultar barras de navegación
- Diseñar dashboards optimizados para pantallas de 7"
- Reducir el sonido del "bip" de cast
- Usar temas oscuros para horario nocturno
- Solución de problemas comunes (pantalla en blanco, desconexiones, login loop)

## 🔗 Proyectos y recursos relacionados

- [Continuously Casting Dashboards](https://github.com/b0mbays/continuously_casting_dashboards) — Integración HACS principal
- [DashCast](https://github.com/AlexxIT/DashCast) — Componente custom de AlexxIT
- [CATT](https://github.com/skorokithakis/catt) — Cast All The Things (CLI)
- [ha-catt-fix](https://github.com/swiergot/ha-catt-fix) — Fix para el timeout de 10 minutos
- [kiosk-mode](https://github.com/NemesisRE/kiosk-mode) — Ocultar UI elements en dashboards

## 🤝 Contribuir

Las contribuciones son bienvenidas. Si encuentras un error, algo desactualizado o quieres añadir otro método:

1. Haz fork del repositorio
2. Crea una rama (`git checkout -b fix/mi-mejora`)
3. Haz commit de tus cambios (`git commit -m 'Corrige X'`)
4. Push a la rama (`git push origin fix/mi-mejora`)
5. Abre un Pull Request

## 📜 Licencia

Distribuido bajo la licencia MIT. Consulta el archivo `LICENSE` para más información.

---

<p align="center">
  Hecho con ❤️ para la comunidad de Home Assistant en español
  <br>
  <sub>Si te ha sido útil, dale una ⭐ al repo</sub>
</p>
