# IS 2.d.02 (a) - Auditoría de Superficie de Exposición Post-Incidente (OSINT pasivo)
<!-- AYUDA (BORRAR): Plantilla del informe. Rellenad los campos entre corchetes y eliminad todos los bloques "AYUDA (BORRAR)" antes de entregar. -->

- Entidad objetivo: Clínica de San Rafael de Cádiz
- Equipo/Grupo: Grupo 1
- Integrantes: Nerea Candón Ramos(NCR), Inca Vico Prieto(IVP), Asier Gónzalez(AG), Adrián Sánchez(AS).
- Fecha(s) de investigación: 29/01/2026 a 01/02/2026
- Versión: 1.0
- Límite de entrega (a): máximo 6 folios (12 caras) en PDF (si aplica)


## 1. Resumen ejecutivo
En esta actividad se ha realizado una investigación OSINT pasiva sobre el Hospital San Rafael de Cádiz, 
utilizando únicamente información que ya estaba disponible públicamente en Internet, sin interactuar con sus sistemas.

El objetivo fue identificar qué datos visibles para cualquiera podían haber ayudado a un atacante a prepararse antes de 
un incidente de ciberseguridad. Para ello se analizaron la página web del hospital y otras fuentes abiertas, buscando información 
sobre la organización, el personal, los servicios, los datos de contacto y la estructura interna del centro.

La investigación permitió comprobar que existe una gran cantidad de información accesible, como nombres y cargos de responsables, 
ubicación exacta, teléfonos, distribución del hospital y descripción detallada de servicios y áreas internas. Aunque esta información
es legal y pública, unida puede facilitar engaños, suplantaciones de identidad o correos fraudulentos dirigidos al personal.

Como conclusión, se recomienda revisar el nivel de detalle de la información publicada, limitar la exposición innecesaria y reforzar
la concienciación del personal sobre los riesgos de la información pública en Internet.

**Objetivo.** Determinar qué información pública existía (antes del incidente supuesto) que podría haber facilitado la fase de reconocimiento de un atacante: identidades digitales, contactos, dominios/subdominios, huella documental (metadatos), menciones públicas y exposiciones derivadas.

**Hallazgos clave (3-7 bullets).**
<!-- AYUDA (BORRAR): Elegid solo lo más relevante (lo que facilita ingeniería social/reconocimiento). -->
- A-01, 02: Información del personal expuesta en la web oficial del Hospital. Se facilita la búsqueda en redes sociales y otras plataformas para su posterior ingeniería social. 
- A-03: Datos de contacto proporcionados por el Hospital en la web en un pdf. Conoces todos los trabajadores.
- A-03

**Riesgo global (una frase).**
<!-- AYUDA (BORRAR): Un diagnóstico breve: nivel + causa principal. -->
- [Bajo/Medio/Alto] por [motivo principal].

**Recomendaciones prioritarias (3-5 bullets).**
<!-- AYUDA (BORRAR): Acciones concretas, medibles y alineadas con los hallazgos. -->
- [Acción 1]
- [Acción 2]
- [Acción 3]

## 2. Alcance, supuestos y reglas de compromiso
<!-- AYUDA (BORRAR): Dejad claro QUÉ se ha hecho y QUÉ no (para demostrar OSINT pasivo). Indicad supuestos y límites. -->

**Alcance.** Solo OSINT pasivo sobre la entidad Hospital San Rafael de Cádiz (y su huella pública asociada). No se incluye investigación individual (apartado b).

**Fuentes permitidas (ejemplos).** Motores de búsqueda, hemeroteca, registros públicos, perfiles públicos en RRSS, repositorios públicos, documentos públicos, Wayback/archivos, bases de datos de brechas (consulta pasiva).
<!-- AYUDA (BORRAR): Listad las fuentes reales que usasteis (5-10), no un listado infinito. -->

**Regla crítica.** Prohibida cualquier acción activa: escaneos, enumeración directa de servicios, pruebas de login, interacción con formularios, generación de tráfico hacia los sistemas objetivo.
<!-- AYUDA (BORRAR): Si una herramienta pudiera considerarse “activa”, explicad cómo la usasteis de forma pasiva (solo consultas a datos ya recopilados por terceros). -->

**Minimización y privacidad.**
<!-- AYUDA (BORRAR): Explicad cómo reducís datos personales (enmascarado parcial, iniciales, no incluir PII innecesaria). -->
- Evitar incluir datos personales innecesarios.
- Si aparecen datos personales de terceros (p. ej., correos de empleados), aplicar reducción: mostrar solo lo imprescindible o enmascarar parcialmente cuando no aporte valor al riesgo.

## 3. Metodología (ciclo OSINT)

Esta sección describe el proceso seguido según el ciclo OSINT: planificación, fuentes, adquisición, procesamiento, análisis y difusión.

### 3.1 Planificación y dirección

- Preguntas guía (ejemplos):
  - ¿Tiene página web y que puedo sacar de ella?
  - ¿Qué dominios usa la entidad?
  - ¿Existen patrones de email/usuarios visibles públicamente?
  - ¿Existen documentos públicos con metadatos reveladores?
  - ¿Hay menciones de sedes, organigrama o personal?

- Criterios de priorización:
  - Impacto potencial en ingeniería social.
  - Exposición de infraestructura por huella documental/histórica.
  - Exposición de datos personales

- Ventana temporal:
  - Consulta realizada en: [2026-01-29]
  - Evidencias archivadas en: `evidencias/`.

### 3.2 Identificación de fuentes

Tabla de fuentes:

| Categoría  | Fuente/Herramienta                       | Qué se busca                | Notas (pasivo)              |
| ---------- | ---------------------------------------- | --------------------------- | --------------------------- |
| Buscadores | Google / Yandex / DuckDuckGo             | menciones, PDFs, indexación | dorks sin acceder a paneles |
| Dominios   | WHOIS, viewdns                           | datos de registro           | solo consulta pública       |
| DNS pasivo | dnsdumpster, viewdns                     | subdominios/histórico       | sin enumeración activa      |
| RRSS       | LinkedIn/X/Facebook/Instagram/TopDoctors | perfiles, roles, nicks      | solo contenido público      |
| Metadatos  | exiftool                                 | autores, rutas, software    | sobre ficheros públicos     |

### 3.3 Adquisición (recopilación)

- Consultas realizadas (resumen):
  - Clínica de San Rafael de Cádiz
  - site:hospitalespascual.com filetype:pdf
  - "@hospitalespascual" -site:hospitalespascual.com

- Evidencias: TODO
  - Guardar capturas o PDFs en `evidencias/` con nombres: `YYYY-MM-DD_fuente_tema.ext`
  - Registrar URL (y, cuando sea útil, captura) y fecha de acceso en cada hallazgo.
  - Toda evidencia mencionada en el informe debe estar enlazada (URL y/o ruta relativa a `evidencias/`).
<!-- AYUDA (BORRAR): Si una URL cambia o desaparece, la captura/PDF en `evidencias/` es la prueba de trazabilidad. -->

### 3.4 Procesamiento y organización
<!-- AYUDA (BORRAR): Cómo ordenasteis datos: deduplicación, clasificación por categorías y relevancia, y control de calidad. -->

- Normalización:
  - Deduplicación de correos/teléfonos/dominios.
  - Agrupación por categoría (contacto, identidad, infra, documentos).

- Criterios de calidad:
  - Fiabilidad de la fuente (primaria vs. terciaria).
  - Fecha y vigencia (actual vs. histórico).
  - Corroboración cruzada (>= 2 fuentes cuando sea posible).
  - Continuidad de los patrones previamente vistos (nombres de correos, prefijo de telefono, etc ...)
<!-- AYUDA (BORRAR): Indicad qué hallazgos NO pudisteis corroborar y por qué. -->

### 3.5 Análisis e interpretación
<!-- AYUDA (BORRAR): Transformad datos en “inteligencia”: vectores habilitados, probabilidad/impacto, y mitigación recomendada. -->

- Correlaciones (ejemplos):
  - Patrones de email + nombres de empleados + roles (posible spear phishing).
  - Documentos públicos -> metadatos -> nombres de usuario/software.
  - Dominios/subdominios históricos -> superficies olvidadas.
<!-- AYUDA (BORRAR): Añadid 2-5 correlaciones reales. Mejor pocas y buenas. -->

- Valoración de riesgo: usar una escala simple.
  - Alto: facilita acceso/engaño de alta probabilidad o alto impacto.
  - Medio: aporta información útil, pero requiere pasos adicionales.
  - Bajo: información marginal o muy genérica.
<!-- AYUDA (BORRAR): Justificad el riesgo con una frase (“Alto porque permite suplantación del canal X”, etc.). -->

### 3.6 Difusión
<!-- AYUDA (BORRAR): Explicad a quién va dirigido el informe y cómo se usará (priorizar mitigaciones y concienciación). -->

- Este informe resume hallazgos, evidencia y recomendaciones accionables.
- Presentación clara para audiencias técnicas y no técnicas.

## 4. Herramientas utilizadas
<!-- AYUDA (BORRAR): Incluid solo herramientas realmente usadas y una evidencia por cada una (URL o fichero en `evidencias/`). -->

| Herramienta   | Tipo                          | Uso concreto | Salida/evidencia               |
| ------------- | ----------------------------- | ------------ | ------------------------------ |
| [Herramienta] | [Buscador/DNS/Metadatos/etc.] | [Para qué]   | [archivo en evidencias/ o URL] |

## 5. Resultados (hallazgos)
<!-- AYUDA (BORRAR): Parte principal. Cada hallazgo debe ser verificable y tener evidencia enlazada (URL y/o `evidencias/...`). -->

Formato recomendado por hallazgo:
<!-- AYUDA (BORRAR): Copiad esta tabla por cada hallazgo importante (o adaptadla si preferís una tabla global). -->

| Campo           | Contenido                                                                  |
| --------------- | -------------------------------------------------------------------------- |
| ID              | A-01                                                                       |
| Categoría       | Contacto / Identidad / Dominio-DNS / Documentos-Metadatos / RRSS / Brechas |
| Descripción     | [Qué se encontró, claro y verificable]                                     |
| Evidencia       | [URL] + `evidencias/...`                                                   |
| Fecha evidencia | [YYYY-MM-DD]                                                               |
| Impacto         | [Qué permite a un atacante]                                                |
| Riesgo          | Alto / Medio / Bajo                                                        |
| Recomendación   | [Mitigación concreta]                                                      |

### 5.1 Identidades digitales (nicks, perfiles, cuentas)
<!-- AYUDA (BORRAR): Perfiles corporativos, posibles empleados/roles (solo info pública), y “pivots” para ingeniería social. -->

- A-01

| Campo           | Contenido                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID              | A-01                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Categoría       | Identidad                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Descripción     | Busqueda en Google de la web de la "Clínica de San Rafael de Cádiz", y vamos a la sección de "Equipo humano". Comenienza la busqueda por la primera personal que aparece, el Director médico de cirugía general Ignacio Ortiz Acero [Equipo humano](/evidencias/identidades digitales/2026-01-29_web.png). Buscando su nombre en Google nos aparece que también trabaja en la calle García Carrera 41, marcado como consultorio privado [Consulta privada](/evidencias/identidades digitales/2026-01-29_doctoralia.png).  En la búsqueda se encuentra una cuenta de Facebook abierta [Facebook](/evidencias/identidades digitales/2026-01-29_facebook.png), en la que se confirma que se trata de la misma persona y gracias a la cual obtenemos información familiar, tanto relaciones personasles y académicas de sus hijos, como información de su esposa [Familia](/evidencias/identidades digitales/2026-01-29_facebook_familia.jpeg). |
| Evidencia       | [https://www.doctoralia.es/ignacio-ortiz-acero/cirujano-general/cadiz] Consultorio Privado; Facebook [https://www.facebook.com/ignacio.ortizacero/] ;Evidencias [01-IOA](/evidencias/identidades digitales)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Fecha evidencia | 2026-01-29                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Impacto         | La web del Hospital proporciona un catálogo con el nombre, apellidos y fotos de los trabajadores, facilitando la búsqueda. El Facebook abierto permite conocer su vida personal y académica, lo que podría ser utilizado para crear ataques de ingeniería social más creíbles, gracias a los datos concretos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Riesgo          | Alto                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Recomendación   | Limitar la información de los trabajadores y configurar la privacidad de las cuentas de redes sociales.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |


- A-02




| Campo           | Contenido |
|-----------------|-----------|
| ID              | A-02 |
| Categoría       | Identidad |
| Descripción     | Se recopiló información detallada sobre el Dr. Pascual Espinosa a partir de fuentes públicas. En una página web informativa se describe su perfil profesional como médico especialista en Traumatología y Medicina Familiar y Comunitaria, su actividad como traumatólogo y cirujano ortopédico en distintos centros hospitalarios de Cádiz, así como sus áreas de especialización quirúrgica. Durante la investigación OSINT también se localizaron su perfil de LinkedIn, vídeos en redes sociales, artículos publicados en otras páginas web y su registro como profesional sanitario en diversas aseguradoras médicas. |
| Evidencia       |https://www.topdoctors.es/doctor/jose-manuel-pascual-espinosa/ + https://www.linkedin.com/in/jose-manuel-pascual-espinosa-aaa5711b/ + [evidencia – captura perfil profesional](../evidencias/identidades-digitales/A-02/2026-01-29-aseguradora.PNG) + [evidencia – captura instagram](../evidencias/identidades-digitales/A-02/2026-01-29-instagram.PNG) +[evidencia – captura linkedin](../evidencias/identidades-digitales/A-02/2026-01-29-linkedin.PNG) + [evidencia – captura TOPDOCTORS](../evidencias/identidades-digitales/A-02/2026-01-29-TOPDOCTORS.PNG) |
| Fecha evidencia | 2026-01-29 |
| Impacto         | La agregación de información procedente de múltiples fuentes permite a un atacante construir un perfil exhaustivo del médico, facilitando ataques de ingeniería social altamente dirigidos, suplantación de identidad profesional y campañas de phishing personalizadas. |
| Riesgo          | Medio |
| Recomendación   | Centralizar y controlar la información profesional publicada, reducir la exposición innecesaria en redes sociales, revisar la visibilidad de perfiles profesionales y reforzar la formación del personal sanitario frente a ataques de ingeniería social. |


### 5.2 Datos de contacto (emails, teléfonos, estructuras)
<!-- AYUDA (BORRAR): Patrones de correo (si se infieren), teléfonos publicados, extensiones, formularios de contacto y riesgos asociados. -->

- A-03

| Campo           | Contenido                                                                                                                                                                               |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID              | A-03                                                                                                                                                                                    |
| Categoría       | Contacto                                                                                                                                                                                |
| Descripción     | En la guia de usuario se pueden ver varios datos de contacto                                                                                                                            |
| Evidencia       | [https://www.hospitalespascual.com/wp-content/uploads/2024/03/guia-del-usuario_San-Rafael_Com.pdf]+ evidencias\contacto\2026-01-29_guia1.png + evidencias\contacto\2026-01-29_guia2.png |
| Fecha evidencia | [2026-01-29]                                                                                                                                                                            |
| Impacto         | Saber todos los empleados que trabajan en el hospital                                                                                                                                   |
| Riesgo          | Alto                                                                                                                                                                                    |
| Recomendación   | Remover la seccion de Equipo humano                                                                                                                                                     |

- A-04

| Campo           | Contenido                                                                                            |
| --------------- | ---------------------------------------------------------------------------------------------------- |
| ID              | A-04                                                                                                 |
| Categoría       | Contacto                                                                                             |
| Descripción     | En la guia para el paciente se pueden ver varios telefonos                                           |
| Evidencia       | [https://www.hospitalespascual.com/guia-para-el-paciente/]+ evidencias\contacto\2026-01-29_guia3.png |
| Fecha evidencia | [2026-01-29]                                                                                         |
| Impacto         | Saber vectores de ataque para ingenieria social                                                      |
| Riesgo          | Medio                                                                                                |
| Recomendación   | Hacer saber a los empleados que estos datos son públicos                                             |

### 5.3 Dominios, subdominios y huella DNS (pasivo)
<!-- AYUDA (BORRAR): Dominios oficiales/variantes y subdominios observados en fuentes pasivas/históricas. Evitad enumeración activa. -->

| Campo           | Contenido                                                                                                                      |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| ID              | A-01                                                                                                                           |
| Categoría       | Dominio-DNS                                                                                                                    |
| Descripción     | Subdominios observados en fuentes pasivas/históricas.                                                                          |
| Evidencia       | https://viewdns.info/ + [Subdominios](/evidencias/dominios-subd-huella-dns/subdominios.png)                                    |
| Fecha evidencia | [29-01-2026]                                                                                                                   |
| Impacto         | Permite descubrir servicios expuestos, detectar entornos olvidados, identificar tecnologías, localizar APIs entre otras cosas. |
| Riesgo          | Medio                                                                                                                          |
| Recomendación   | Reducir lo que "se puede enumerar"; cerrar subdominios innecesarios, aislar entornos, evitar registros DNS de más entre otras. |

### 5.4 Huella documental y metadatos (documentos públicos)
<!-- AYUDA (BORRAR): Documentos públicos y metadatos relevantes (autor, software, rutas, fechas). Adjuntad evidencia. -->

- A-07

| Campo | Contenido |
| --- | --- |
| ID | A-07 |
| Categoría | Documentos-Metadatos |
| Descripción | Usando la busqueda site:https://www.hospitalespascual.com/ filetype:pdf, se puede obtener un documento pdf con varios metadatos como Autor y herramienta usada |
| Evidencia | [https://www.hospitalespascual.com/wp-content/uploads/2024/09/POLITICA-DE-MEDIOAMBIENTE44.pdf] + evidencias\huella\2026-01-29_politica.png |
| Fecha evidencia | [2026-01-29] |
| Impacto | Saber herramientas usadas por la empresa |
| Riesgo | Bajo |
| Recomendación | Asegurarse de que no se guarden metadatos de información sensible |

- A-08

### 5.5 Brechas y filtraciones (consulta pasiva)
<!-- AYUDA (BORRAR): Aparición del dominio/correos en brechas conocidas. No incluyáis contraseñas. Priorizad mitigaciones (2FA, rotación, etc.). -->
- A-01B

| Campo           | Contenido                                                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID              | A-0X                                                                                                                                                      |
| Categoría       | Brechas                                                                                                                                                   |
| Descripción     | Si navegamos por la web de la clínica con la consola de las devtools abierta, podemos observar notificaciones de tecnologías específicas y sus versiones. |
| Evidencia       | https://www.hospitalespascual.com + [01-Wordpress.png](/evidencias/brechas-y-filtraciones/01-Wordpress.png)                                               |
| Fecha evidencia | 2026-01-29                                                                                                                                                |
| Impacto         | Permite a un atacante identificar brechas de seguridad en la web de la clínica.                                                                           |
| Riesgo          | Medio                                                                                                                                                     |
| Recomendación   | Evitar la exposición de tecnologías en la medida de lo posible.                                                                                           |

- A-02B

| Campo           | Contenido                                                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID              | A-02B                                                                                                                                                     |
| Categoría       | Brechas                                                                                                                                                   |
| Descripción     | Si navegamos por la web de la clínica con la consola de las devtools abierta, podemos observar notificaciones de tecnologías específicas y sus versiones. |
| Evidencia       | https://www.hospitalespascual.com + [02-Jquery.png](/evidencias/brechas-y-filtraciones/02-Jquery.png)                                                     |
| Fecha evidencia | 2026-01-29                                                                                                                                                |
| Impacto         | Permite a un atacante identificar brechas de seguridad en la web de la clínica.                                                                           |
| Riesgo          | Medio                                                                                                                                                     |
| Recomendación   | Evitar la exposición de tecnologías en la medida de lo posible.                                                                                           |

- A-01A

| Campo           | Contenido                                                                                                                                                    |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ID              | A-01A                                                                                                                                                        |
| Categoría       | Brechas                                                                                                                                                      |
| Descripción     | Busqueda en Google de la web de la "Clínica de San Rafael de Cádiz", y vamos a la sección de "Equipo humano” se puede ver una lista con todos los empleados. |
| Evidencia       | [https://www.hospitalespascual.com/hospital-san-rafael/] + evidencias\identidades digitales\A-01\2026-01-29_web.png                                          |
| Fecha evidencia | [2026-01-29]                                                                                                                                                 |
| Impacto         | Saber todos los empleados que trabajan en el hospital                                                                                                        |
| Riesgo          | Alto                                                                                                                                                         |
| Recomendación   | Remover la seccion de Equipo humano                                                                                                                          |

- A-09




## 6. Resumen de riesgos
<!-- AYUDA (BORRAR): Tabla para priorizar: qué arreglar primero (P1), después (P2) y al final (P3). -->

| ID   | Hallazgo (resumen)                                                                      | Riesgo | Prioridad | Acción recomendada                                                                                      |
| ---- | --------------------------------------------------------------------------------------- | ------ | --------- | ------------------------------------------------------------------------------------------------------- |
| A-01 | Información personal de trabajadores expuesta, facilitando ataques de ingeniería social | Alto   | P1        | Limitar la información de los trabajadores y configurar la privacidad de las cuentas de redes sociales. |
| A-02 | [..]                                                                                    | Medio  | P2        | [..]                                                                                                    |
| A-03 | [..]                                                                                    | Bajo   | P3        | [..]                                                                                                    |

## 7. Conclusiones
<!-- AYUDA (BORRAR): 3-6 bullets: qué superficie pública existía y qué vector pudo facilitar. Sin repetir texto, aportad síntesis. -->

- [Conclusión 1: qué explica la exposición encontrada y por qué importa]
- [Conclusión 2]
- [Conclusión 3]

## 8. Recomendaciones
<!-- AYUDA (BORRAR): Convertid hallazgos en acciones concretas. Si podéis, asignad responsable sugerido (IT/Seguridad/RRHH/Comunicacion). -->

**Quick wins (0-30 días)**
<!-- AYUDA (BORRAR): Cambios rápidos: retirar/editar documentos, sanear metadatos, ajustar contenidos públicos, concienciación inmediata. -->
- [..]
- [..]

**Medio plazo (1-3 meses)**
<!-- AYUDA (BORRAR): Cambios estructurales: políticas de publicación, revisión periódica, procesos, formación, controles de identidad. -->
- [..]

**Mejora continua**
<!-- AYUDA (BORRAR): Medidas recurrentes: monitorización de menciones, revisiones trimestrales de exposición, playbook OSINT. -->
- [..]

## 9. Anexos
<!-- AYUDA (BORRAR): Trazabilidad. Esta sección facilita la corrección: fuentes, consultas y evidencias enlazadas. -->

### 9.1 Registro de fuentes
<!-- AYUDA (BORRAR): Fuentes base consultadas (URL + fecha). No hace falta duplicar cada evidencia si ya está en hallazgos, pero sí lo principal. -->

| Fuente                             | URL                                                                    | Fecha acceso | Nota                    |
| ---------------------------------- | ---------------------------------------------------------------------- | ------------ | ----------------------- |
| Web Hospitales Pascual, San Rafael | [(https://www.hospitalespascual.com/hospital-san-rafael/)]             | 2026/01/29   | Equipo Humano           |
| Doctoralia                         | [https://www.doctoralia.es/ignacio-ortiz-acero/cirujano-general/cadiz] | 2026/01/29   | Consultorio Privado IOA |
| Facebook                           | [https://www.facebook.com/ignacio.ortizacero/]                         | 2026/01/29   | Red Social              |

### 9.2 Consultas (dorks) empleadas
<!-- AYUDA (BORRAR): Dejad 5-15 consultas representativas. Deben ser pasivas y reproducibles. -->

(Registrar aquí las consultas utilizadas. Evitar incluir acciones activas o instrucciones de acceso.)

- `site:[dominio] filetype:pdf [palabra clave]`
- `site:[dominio] "@[dominio]"`
- `"Clínica San Rafael" "Cádiz" [palabra clave]`

### 9.3 Evidencias (índice)
<!-- AYUDA (BORRAR): Índice con enlaces relativos a ficheros dentro de `evidencias/`. Debe permitir abrir cada evidencia sin buscar. -->

<!-- AYUDA (BORRAR): Ejemplo de enlace: `[2026-01-27 - Google - PDF organigrama](../evidencias/2026-01-27_google_organigrama.pdf)` -->

- `evidencias/`:
  - `YYYY-MM-DD_fuente_tema.ext` - [descripción]
