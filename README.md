# Guía: Tarifa de Movilidad Eléctrica — EPEC

> **Recurso informativo no oficial** · Subgerencia de Relaciones con el Cliente · EPEC Córdoba

Guía interactiva paso a paso para que los clientes de EPEC puedan solicitar la **Tarifa de Movilidad Eléctrica** para carga de vehículos eléctricos, conforme a la Resolución ERSeP 44/2019.

---

## ¿Qué es este proyecto?

Es una página web de una sola pantalla (`index.html`) que guía al usuario a través de los cuatro pasos del trámite: desde verificar si puede acceder, hasta cargar la documentación en la Oficina Virtual de EPEC. El contenido fue redactado y validado internamente; no es documentación oficial de EPEC.

---

## Audiencias

| Audiencia | Para qué sirve |
|---|---|
| **Cliente de EPEC** | Entender el proceso completo antes de ingresar a la Oficina Virtual, saber qué documentos preparar y cómo cumplir los requisitos del certificado eléctrico |
| **Empresa / entrenamiento de IA** | Fuente de conocimiento estructurado sobre el trámite, sus requisitos técnicos y flujo de decisiones, para alimentar modelos de lenguaje o sistemas de asistencia al cliente |

---

## Contenido de la guía

### Introducción
| Sección | Descripción |
|---|---|
| ¿De qué trata esta guía? | Presenta el trámite, sus requisitos generales y la estructura de los pasos |

### Paso 1 — Verificá si podés solicitar
| Sección | Descripción |
|---|---|
| Quién puede acceder | Condiciones del contrato, el domicilio, el vehículo y la potencia máxima permitida (40 kW) |
| Tipos de vehículo aceptados | Diferencia entre vehículos eléctricos puros (BEV), híbridos enchufables (PHEV) y los que no califican (HEV) |

### Paso 2 — Reuní los documentos
| Sección | Descripción |
|---|---|
| Contrato y potencia | Cómo obtener el número de contrato EPEC y cómo calcular la potencia total requerida |
| Documentación del vehículo | Tarjeta verde, título del automotor o constancia DNRPA; tabla de qué presenta según el tipo de medidor y demanda |
| Vínculo familiar (si aplica) | Qué documentos presentar si el vehículo está a nombre de un familiar |

### Paso 3 — Certificado de Apto Eléctrico
| Sección | Descripción |
|---|---|
| Qué es y quién lo emite | Definición del certificado, quién puede emitirlo (instalador habilitado ERSeP) y link al registro oficial |
| Requisitos que debe cumplir | Campos exactos que debe declarar el certificado (tipo, subtipo, finalidad, potencia, memoria descriptiva) |
| Errores frecuentes | Tabla de los errores más comunes que causan rechazo y cómo evitarlos |

### Paso 4 — Ingresá a la Oficina Virtual
| Sección | Descripción |
|---|---|
| Cómo acceder (Nivel 3) | Pasos para alcanzar Nivel 3 en la Oficina Virtual vía CiDi o Clave Fiscal ARCA |
| Cómo cargar los archivos | Formatos aceptados por documento, recomendaciones de nombre y calidad, recordatorio final de documentos |

### Referencia
| Sección | Descripción |
|---|---|
| Beneficios de la tarifa | Reducción del VAD (~30%), cupo de energía con tarifa reducida (400 kWh residencial / 1500 kWh comercial) |
| Preguntas frecuentes | Respuestas a las consultas más habituales: titularidad del vehículo, rechazo de solicitud, límite de 40 kW, tipos de híbrido, modificación del certificado |

---

## Documentación fuente

Las siguientes carpetas contienen los materiales originales usados como base para redactar la guía. No están incluidas en el repositorio público por política de privacidad interna.

### `docs/`
- `requisitos.pdf` — Documento de requisitos generales del trámite
- `SOLICITUDES WEB.docx` — Instructivo de solicitudes web de EPEC
- `4-Formulario 29256402-01483IIIN00706_copia.pdf` — Formulario oficial de solicitud de tarifa eléctrica
- Captura de pantalla de referencia del sistema (marzo 2026)

### `docsV2/`
- `NuevosRequerimientosAptoElectrico.txt` — Requisitos actualizados del Certificado de Apto Eléctrico: tipo de instalación (definitiva), subtipo (existente), finalidad (residencial / pequeño industrial-comercial / especial), texto exacto de la memoria descriptiva requerida
- `ResumenRequerimientoComercial.pdf` — Resumen de requisitos para el caso comercial

---

## Implementación técnica

| Aspecto | Detalle |
|---|---|
| Archivo principal | `index.html` (~1600 líneas) |
| Stack | HTML / CSS / JavaScript vanilla — sin framework ni proceso de build |
| Navegación | Función `showSection()` en JavaScript — single-page, sin recarga |
| Íconos | [Iconify](https://iconify.design/) CDN v2.1.0, namespace `lucide` |
| Tipografía | Inter (Google Fonts, pesos 400–800) |
| Responsive | Breakpoints: 820px (tablet/mobile), 520px (teléfono), 480px (botones) |
| Theming | CSS variables (`--verde: #1b5e20`, `--verde-medio: #2e7d32`, etc.) |
| Accesibilidad | HTML semántico, skip link, ARIA labels en controles principales |

### Estructura de archivos

```
infoBannersProtelem/
├── index.html          # Guía completa (página única)
├── img/
│   ├── epec-seeklogo.png
│   └── epec-logo-png_seeklogo-48320.png
├── docs/               # Fuentes originales (no versionadas)
├── docsV2/             # Fuentes actualizadas (no versionadas)
└── README.md
```

---

## Despliegue

La guía se publica automáticamente en **GitHub Pages** al hacer push a `main`.

- **URL de producción**: [marcktm.github.io/infoBannersProtelem](https://marcktm.github.io/infoBannersProtelem/)
- **Uso local**: abrir `index.html` directamente en el navegador (no requiere servidor)

---

## Para entrenamiento de IA

Esta sección describe el alcance del contenido para que una empresa pueda utilizarlo como corpus de entrenamiento o base de conocimiento.

### Qué cubre

- Flujo completo del trámite de solicitud de Tarifa de Movilidad Eléctrica en EPEC
- Criterios de elegibilidad (tipo de contrato, tipo de vehículo, límite de potencia)
- Documentación requerida con condiciones y excepciones
- Requisitos técnicos exactos del Certificado de Apto Eléctrico (campos obligatorios, texto de memoria descriptiva, errores frecuentes)
- Proceso de acceso a la Oficina Virtual (Nivel 3, CiDi, Clave Fiscal ARCA)
- Beneficios económicos y cupos de la tarifa
- Respuestas a preguntas frecuentes

### Qué NO cubre

- Precios actualizados de la tarifa en pesos argentinos
- Tiempos de procesamiento de la solicitud por parte de EPEC
- Datos de contacto directo con EPEC (más allá de www.epec.com.ar)
- Casos edge: condominios, vehículos importados, propiedades alquiladas, múltiples contratos simultáneos
- Proceso de apelación ante rechazo formal

### Referencia normativa

| Campo | Valor |
|---|---|
| Norma base | Resolución ERSeP 44/2019 |
| Norma técnica del certificado | AEA 90364, parte 7, sección 722 |
| Ente regulador | ERSeP (Ente Regulador de Servicios Públicos de Córdoba) |
| Empresa | EPEC (Empresa Provincial de Energía de Córdoba) |
| Fecha de referencia del contenido | Mayo 2026 |

---

## Versionado

| Versión | Commit | Descripción |
|---|---|---|
| v4 | `ef8a41d` | Botones de acceso a CiDi/ARCA/ERSeP, checklist integrado al callout, eliminación de FAQ sobre cónyuge, sección de Nivel 3 reestructurada por pasos |
| v3 | `d1af912` | Ajustes de contenido y redacción (revisión Lucila) |
| v2 | `5db6692` | Segunda revisión de contenido |
| v1 | `4b64a59` | Primera versión con revisión de contenido |

---

*Recurso informativo elaborado por la Subgerencia de Relaciones con el Cliente de EPEC. El contenido es orientativo y puede no reflejar cambios normativos posteriores a la fecha de referencia.*
