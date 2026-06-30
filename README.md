# Trabajo Práctico Integrador
## Arquitectura de Sistemas Operativos

### Universidad Tecnológica Nacional (UTN)

---

## Descripción

Este repositorio contiene el desarrollo completo del Trabajo Práctico Integrador correspondiente a la asignatura **Arquitectura de Sistemas Operativos** de la carrera **Tecnicatura Universitaria en Programación** (modalidad a distancia) de la Universidad Tecnológica Nacional.

El proyecto consiste en el diseño, implementación y validación de un laboratorio de seguridad informática orientado a la detección y respuesta automática frente a ataques de fuerza bruta sobre un servidor Linux utilizando herramientas ampliamente empleadas en entornos profesionales.

---

## Objetivos

Los principales objetivos del proyecto fueron:

- Diseñar una arquitectura de laboratorio reproducible.
- Implementar un servidor Ubuntu con el servicio OpenSSH.
- Configurar el mecanismo de protección mediante Fail2Ban.
- Simular un ataque de fuerza bruta utilizando Hydra desde Kali Linux.
- Analizar los registros generados por el sistema operativo.
- Validar el funcionamiento automático del mecanismo de detección y respuesta.

---

## Arquitectura del Laboratorio

El laboratorio fue implementado utilizando VMware Workstation y está compuesto por dos máquinas virtuales.

| Equipo | Sistema Operativo | Función |
|---------|-------------------|----------|
| Servidor | Ubuntu Desktop | Servicio SSH y sistema protegido |
| Atacante | Kali Linux | Simulación del ataque mediante Hydra |

El flujo general del laboratorio puede resumirse de la siguiente manera:

```
Hydra
      │
      ▼
OpenSSH
      │
      ▼
PAM
      │
      ▼
systemd-journald
      │
      ▼
Fail2Ban
      │
      ▼
Firewall
      │
      ▼
Bloqueo automático de la IP atacante
```

---

## Tecnologías utilizadas

- Ubuntu Desktop
- Kali Linux
- VMware Workstation
- OpenSSH Server
- Fail2Ban
- Hydra
- systemd
- journalctl
- Git
- GitHub

---

## Estructura del repositorio

```
TPI-Arquitectura-de-Sistemas-Operativos
│
├── Informe/
├── Configuracion/
├── Evidencias/
├── Recursos/
├── Scripts/
├── README.md
├── LICENSE
└── .gitignore
```

---

## Evidencias

Durante el desarrollo del laboratorio se documentaron todas las etapas mediante capturas de pantalla y registros del sistema.

Entre las principales evidencias se incluyen:

- Preparación del laboratorio.
- Configuración de OpenSSH.
- Configuración de Fail2Ban.
- Reconocimiento mediante Nmap.
- Ataque de fuerza bruta con Hydra.
- Registros de autenticación.
- Bloqueo automático de la dirección IP atacante.

---

## Resultados obtenidos

Las pruebas realizadas permitieron verificar el correcto funcionamiento del sistema implementado.

El servidor registró los intentos de autenticación fallida, Fail2Ban identificó el patrón de ataque y aplicó automáticamente el bloqueo de la dirección IP atacante, impidiendo la continuidad del intento de acceso.

Los resultados obtenidos validan la arquitectura propuesta y demuestran la eficacia de la automatización de respuestas ante eventos de seguridad.

---

## Contenido del repositorio

| Carpeta | Contenido |
|----------|-----------|
| Informe | Documento final del Trabajo Práctico Integrador |
| Configuracion | Archivos de configuración utilizados durante el laboratorio |
| Evidencias | Capturas de pantalla y registros obtenidos |
| Recursos | Diagramas y material gráfico del proyecto |
| Scripts | Scripts auxiliares desarrollados para el laboratorio |

---

## Autor

**Mateo**

Tecnicatura Universitaria en Programación

Universidad Tecnológica Nacional

---

## Licencia

Este proyecto se distribuye bajo la Licencia MIT.