# INFORME STELLAR / DRIPS



## Proyecto



**Plataforma comunitaria para la preservación y transmisión de la lengua y memoria cultural de Santa María Cuquila**



**Asignatura:** Gestión de Proyectos de Software

**Unidad:** 2

**Actividad:** Informe Stellar/Drips

**Fecha:** Septiembre de 2026



---



# 1. Introducción



El presente informe analiza Stellar y Drips desde una perspectiva de ingeniería de software, calidad, seguridad y financiamiento de proyectos de código abierto.



El análisis se relaciona con el proyecto de una plataforma comunitaria para la preservación y transmisión de la lengua y memoria cultural de Santa María Cuquila.



El propósito es determinar qué características técnicas de Stellar y Drips podrían aportar valor al proyecto, qué requisitos deberían cumplirse y qué riesgos deben considerarse antes de utilizar tecnologías blockchain.



El análisis también toma en cuenta las condiciones de la región Mixteca, especialmente la conectividad limitada, el uso de dispositivos móviles, la accesibilidad y la necesidad de proteger el contenido cultural.



---



# 2. Problemática del proyecto



La problemática seleccionada es:



**Preservación y transmisión de la lengua y memoria cultural de Santa María Cuquila.**



La propuesta contempla una plataforma con funcionalidades para:



- consultar palabras y expresiones;

- escuchar pronunciaciones;

- aportar conocimiento;

- consultar memoria cultural;

- validar contenido.



El objetivo tecnológico no es utilizar blockchain por sí misma, sino analizar si alguna de sus características puede resolver una necesidad concreta del proyecto.



---



# 3. Objetivo del informe



Analizar técnicamente Stellar y Drips, identificar sus requisitos de calidad y desarrollo, evaluar sus riesgos y determinar de qué manera podrían relacionarse con el proyecto y su estrategia de sostenibilidad.



---



# 4. Objetivos específicos



- Investigar las características técnicas de Stellar y Soroban.

- Analizar los mecanismos de financiamiento de Drips.

- Identificar requisitos de calidad y seguridad.

- Adaptar métricas al contexto de la región Mixteca.

- Analizar riesgos técnicos y éticos.

- Relacionar calidad de software y financiamiento Web3.

- Determinar qué partes del proyecto podrían beneficiarse realmente de estas tecnologías.

---



# 5. Análisis técnico de Stellar y Soroban



## 5.1 Stellar y Soroban



Stellar es una red blockchain orientada a transferencias de valor y aplicaciones financieras. Soroban es la plataforma de contratos inteligentes integrada en la red Stellar.



Para nuestro análisis es importante distinguir ambas capas:



- **Stellar:** red blockchain donde se registran las operaciones.

- **Soroban:** plataforma que permite ejecutar contratos inteligentes sobre Stellar.



Los contratos de Soroban se desarrollan actualmente con Rust y se compilan a WebAssembly (Wasm). La documentación oficial también señala que el entorno de ejecución tiene restricciones de recursos y seguridad, por lo que no todo el ecosistema estándar de Rust puede utilizarse directamente dentro de los contratos. 



---



## 5.2 Herramientas de desarrollo



El desarrollo de contratos Soroban utiliza el **Soroban Rust SDK** y el **Stellar CLI**.



Estas herramientas permiten realizar actividades como:



- compilación;

- pruebas;

- inspección;

- versionado;

- despliegue;

- interacción con contratos.



Además, el entorno local permite ejecutar y probar contratos en la computadora del desarrollador antes de utilizarlos en una red pública. 



---



## 5.3 Requisitos técnicos



Una integración de nuestro proyecto con Soroban tendría que considerar como mínimo:



1\. Rust y Cargo.

2\. Stellar CLI.

3\. Target `wasm32v1-none`.

4\. Soroban SDK.

5\. pruebas unitarias.

6\. pruebas de integración.

7\. ambiente local de pruebas.

8\. Testnet antes de Mainnet.



La documentación oficial actual requiere Rust 1.84.0 o superior para utilizar el target `wasm32v1-none` y recomienda emplear `stellar contract build` para construir contratos. 



---



## 5.4 Calidad del código



En una aplicación tradicional, un error normalmente puede corregirse actualizando el servidor o la base de datos.



En un contrato inteligente existe un riesgo adicional: una lógica incorrecta puede afectar directamente las operaciones realizadas sobre la red.



Por ello, la calidad debe considerarse desde la etapa de diseño.



Para nuestro proyecto se propone revisar:



- claridad del código;

- validación de entradas;

- control de autorización;

- manejo de errores;

- consumo de recursos;

- dependencias;

- pruebas automatizadas;

- documentación;

- control de versiones.



---



## 5.5 Pruebas locales



Antes de realizar cualquier despliegue se deben realizar pruebas locales.



El SDK de Soroban proporciona herramientas para realizar pruebas unitarias y permite utilizar un entorno local equivalente al host de contratos.



Esto permite detectar errores antes de utilizar una red pública. 



### Aplicación al proyecto



Antes de utilizar blockchain se podrían probar:



- escritura y lectura de información;

- validación de permisos;

- operaciones financieras;

- datos inválidos;

- errores esperados;

- límites del contrato.



---



## 5.6 Pruebas de integración



Las pruebas de integración permiten comprobar la interacción entre diferentes componentes.



La documentación de Stellar contempla utilidades para probar contratos contra otros contratos y utilizar contratos reales desplegados en redes como Testnet. 



Para nuestro proyecto se podrían evaluar:



```text

Aplicación

   ↓

API

   ↓

Módulo Web3

   ↓

Contrato Soroban

   ↓

Red Stellar
---

# 6. Análisis técnico de Drips Protocol

## 6.1 ¿Qué es Drips?

Drips es un protocolo orientado al financiamiento de proyectos de código abierto mediante infraestructura blockchain compatible con Ethereum y redes EVM.

Su objetivo es facilitar que los proyectos puedan recibir apoyo económico y, al mismo tiempo, distribuir fondos hacia otras personas, proyectos o dependencias.

Drips contempla diferentes mecanismos de distribución:

- streaming;
- giving;
- splitting.

Fuente oficial:

https://docs.drips.network/the-protocol/overview/

---

## 6.2 Streaming de fondos

El streaming permite distribuir fondos progresivamente durante un periodo de tiempo.

En lugar de realizar una única transferencia, se establece una tasa de distribución y el receptor puede obtener los fondos que correspondan conforme transcurre el tiempo definido.

Esto puede ser útil para financiar:

- mantenimiento;
- desarrollo;
- documentación;
- infraestructura;
- colaboradores.

### Aplicación al proyecto

En una etapa futura podría utilizarse un stream para financiar el mantenimiento de la plataforma de preservación lingüística.

Por ejemplo, un patrocinador podría establecer un flujo periódico para contribuir al mantenimiento del proyecto.

---

## 6.3 Giving

El mecanismo de giving permite realizar una aportación directa.

Su utilidad sería similar a una donación puntual.

### Aplicación

Una organización o persona interesada en apoyar el proyecto podría realizar una aportación sin establecer un flujo permanente.

Esto podría ser útil para:

- compra de infraestructura;
- almacenamiento;
- actividades de mantenimiento;
- desarrollo de nuevas funciones.

---

## 6.4 Splitting

El mecanismo de splitting permite distribuir los fondos recibidos entre diferentes receptores.

Por ejemplo, un proyecto podría repartir parte de sus fondos entre:

- mantenedores;
- colaboradores;
- dependencias;
- otros proyectos de código abierto.

Esto introduce una relación económica entre diferentes proyectos y componentes del ecosistema.

---

## 6.5 Reclamación de un repositorio

Drips permite reclamar un repositorio de código abierto para asociarlo con una identidad o dirección compatible.

La documentación indica que el proceso puede utilizar un archivo:

`FUNDING.json`

Este archivo permite indicar la dirección que controlará el proyecto en Drips.

La documentación de reclamación debe consultarse antes de realizar la configuración porque un error en la dirección podría provocar problemas de control.

Fuente:

https://docs.drips.network/get-support/claim-your-repository/

---

## 6.6 Requisitos para recibir fondos

Para una implementación futura se deberían considerar:

1. Repositorio de código abierto.
2. Proceso de reclamación del proyecto.
3. Dirección compatible con Ethereum.
4. Archivo `FUNDING.json`.
5. Wallet para administrar fondos.
6. ETH disponible para operaciones que requieran gas.
7. Configuración de destinatarios y distribuciones.

El proyecto deberá verificar cuidadosamente la dirección utilizada antes de reclamarlo.

---

## 6.7 Gestión del código abierto

Drips está orientado específicamente al financiamiento de proyectos de código abierto.

Esto implica que la calidad del repositorio adquiere importancia.

Un proyecto que pretenda recibir apoyo debe mantener:

- documentación;
- estructura clara;
- historial de cambios;
- información de financiamiento;
- control de versiones;
- responsables identificables.

Para nuestro proyecto, GitHub se mantendrá como el principal repositorio de documentación y código.

---

## 6.8 Seguridad de Drips

El manejo de fondos introduce riesgos que no aparecen de la misma manera en una aplicación web convencional.

### Riesgo: dirección incorrecta

Si el proyecto se configura con una dirección equivocada, los fondos podrían quedar asociados con un receptor incorrecto.

**Mitigación:**

- revisar la dirección dos veces;
- utilizar una checklist;
- validar la configuración antes de operar con fondos reales.

### Riesgo: compromiso de wallet

Si una wallet es comprometida, el atacante podría obtener control sobre los fondos.

**Mitigación:**

- almacenamiento seguro;
- control de acceso;
- separación de responsabilidades;
- multisig cuando sea apropiado.

### Riesgo: error de distribución

Una configuración incorrecta de porcentajes puede hacer que los fondos se distribuyan de manera diferente a la prevista.

**Mitigación:**

- revisión por pares;
- pruebas con cantidades pequeñas;
- comprobación de las reglas antes de ejecutarlas.

---

## 6.9 Evidencia de auditoría del protocolo

La seguridad no debe asumirse únicamente porque un protocolo sea de código abierto.

Drips cuenta con revisiones de seguridad públicas. Una revisión reciente del protocolo examinó contratos desplegados en Ethereum y registró hallazgos de distinta naturaleza, incluyendo problemas de bajo nivel, optimizaciones de gas e información adicional. Esto demuestra que incluso un sistema público y auditado requiere revisión continua. 

También existe una revisión anterior donde se analiza específicamente el proceso de actualización de propietarios a partir del archivo `FUNDING.json`, mostrando que la interacción entre GitHub y blockchain puede introducir riesgos que deben ser considerados. 

### Conclusión de seguridad

El código abierto facilita la inspección, pero no elimina los riesgos.

Por lo tanto, se recomienda:

- revisar el código;
- consultar auditorías;
- mantener dependencias actualizadas;
- utilizar wallets seguras;
- verificar configuraciones;
- realizar pruebas antes de utilizar fondos reales.

---

## 6.10 Límites del modelo de Drips

Drips también posee condiciones técnicas.

Las Drip Lists permiten organizar múltiples receptores.

De acuerdo con la documentación del protocolo, una lista puede trabajar con hasta **200 receptores**.

Este límite debe considerarse si el proyecto en el futuro intenta distribuir fondos entre numerosos colaboradores o dependencias.

---

## 6.11 Calidad del software y Drips

La incorporación de Drips no elimina la necesidad de un Plan de Calidad.

Al contrario, introduce nuevos puntos de revisión:

- calidad del repositorio;
- seguridad;
- integridad de las configuraciones;
- administración de wallets;
- pruebas;
- trazabilidad;
- documentación.

Por esta razón, antes de utilizar Drips se deberán agregar nuevos criterios de aceptación relacionados con las operaciones financieras.

---

## 6.12 Posibles métricas para Drips

| Métrica | Fórmula | Meta |
|---|---|---:|
| Transacciones exitosas | exitosas / totales × 100 | ≥ 95 % |
| Configuraciones correctas | correctas / configuraciones × 100 | 100 % |
| Errores críticos | cantidad | 0 |
| Operaciones revisadas | revisadas / operaciones × 100 | 100 % |
| Incidentes de seguridad | cantidad | 0 críticos |
| Dependencias actualizadas | actualizadas / dependencias × 100 | ≥ 95 % |

---

## 6.13 Aplicación al proyecto

Drips podría utilizarse únicamente en una etapa posterior.

La primera versión del proyecto debe funcionar sin requerir:

- wallet;
- criptomonedas;
- transacciones;
- interacción directa con blockchain.

Esto permitirá que la tecnología Web3 no se convierta en una barrera para usuarios de la comunidad.

---

## 6.14 Propuesta de uso

La posible estrategia futura sería:

```text
Proyecto de software
        ↓
Repositorio abierto
        ↓
MVP funcional
        ↓
Validación comunitaria
        ↓
Evaluación de sostenibilidad
        ↓
Configuración de Drips
        ↓
Financiamiento
        ↓
Mantenimiento del proyecto
---

# 7. Pensamiento crítico sobre seguridad, calidad y ética

## 7.1 Blockchain no significa seguridad automática

Una de las principales consideraciones del proyecto es que utilizar blockchain
no garantiza por sí mismo que un sistema sea seguro.

Una aplicación blockchain puede presentar vulnerabilidades en:

- contratos inteligentes;
- lógica de negocio;
- administración de claves;
- configuración;
- dependencias;
- interfaces;
- integración con servicios externos.

Por esta razón, la calidad debe evaluarse antes, durante y después de una
integración con Stellar o Drips.

---

## 7.2 Riesgo de errores en contratos inteligentes

Un contrato inteligente ejecuta reglas programadas que pueden afectar
operaciones reales.

Un error lógico puede ocasionar:

- operaciones incorrectas;
- pérdida de fondos;
- bloqueo de recursos;
- comportamiento diferente al esperado.

### Medidas de mitigación

Se propone:

1. definir los requisitos antes del desarrollo;
2. realizar pruebas unitarias;
3. realizar pruebas de integración;
4. probar datos inválidos;
5. probar límites;
6. realizar revisión de código;
7. utilizar Testnet;
8. realizar auditoría antes de Mainnet.

---

## 7.3 Riesgo de administración de claves

Las wallets y claves privadas representan uno de los elementos más críticos
de una solución Web3.

Una clave comprometida puede permitir operaciones no autorizadas.

### Mitigación

El proyecto deberá considerar:

- almacenamiento seguro de claves;
- separación de responsabilidades;
- control de acceso;
- autenticación;
- wallets de hardware cuando corresponda;
- multisig para fondos que requieran control colectivo.

---

## 7.4 Riesgo de configuración

Una dirección, porcentaje o parámetro incorrectamente configurado puede
provocar una operación diferente a la prevista.

Esto es especialmente importante en Drips debido a sus mecanismos de
distribución.

### Mitigación

Antes de cualquier operación:

- revisar la dirección;
- revisar los receptores;
- verificar porcentajes;
- revisar permisos;
- realizar pruebas con cantidades pequeñas;
- registrar quién autorizó el cambio.

---

# 8. Pensamiento crítico sobre código abierto

El código abierto permite que otras personas puedan revisar y reutilizar
el software.

Sin embargo, publicar el código no garantiza:

- ausencia de vulnerabilidades;
- calidad del desarrollo;
- mantenimiento constante;
- seguridad de las dependencias.

Por lo tanto, un proyecto abierto necesita procesos adicionales.

## Prácticas recomendadas

- revisión por pares;
- control de versiones;
- pruebas automatizadas;
- documentación;
- actualización de dependencias;
- seguimiento de vulnerabilidades;
- registro de cambios.

---

# 9. Transparencia y riesgos

Blockchain puede aumentar la transparencia porque determinadas operaciones
pueden ser verificables públicamente.

Sin embargo, la transparencia también puede generar riesgos.

Una transacción puede revelar información sobre:

- movimientos de fondos;
- direcciones;
- relaciones entre proyectos;
- patrones de actividad.

Por esta razón, la transparencia debe analizarse junto con la privacidad.

---

# 10. Aspectos éticos del proyecto

Nuestro proyecto trabaja con información relacionada con la lengua y memoria
cultural de Santa María Cuquila.

Esto implica responsabilidades adicionales.

## 10.1 Privacidad

No se deben registrar innecesariamente datos personales o información
sensible en una blockchain pública.

## 10.2 Consentimiento

Los contenidos aportados por miembros de la comunidad deben contar con una
autorización adecuada para su publicación.

## 10.3 Control comunitario

La comunidad debe conservar capacidad de decidir qué información puede
publicarse y bajo qué condiciones.

## 10.4 Inmutabilidad

Una característica de blockchain es que ciertas operaciones pueden ser
difíciles de modificar o eliminar posteriormente.

Por ello, información cultural que requiera modificaciones futuras no debería
almacenarse directamente en blockchain sin analizar previamente las
consecuencias.

## 10.5 Inclusión tecnológica

No debe ser obligatorio tener:

- criptomonedas;
- wallet;
- conocimiento de blockchain;

para utilizar las funciones principales de la plataforma.

---

# 11. Blockchain y datos culturales

Una decisión importante del proyecto será separar:

### Datos culturales

Palabras, expresiones, audios y memoria cultural.

### Información de trazabilidad o financiamiento

Datos que realmente puedan beneficiarse de una infraestructura blockchain.

La propuesta es mantener los contenidos culturales principalmente fuera de
la blockchain y utilizar Web3 solamente cuando exista una necesidad
justificada.

Esto reduce:

- costos;
- complejidad;
- dependencia tecnológica;
- riesgos de privacidad.

---

# 12. Riesgos técnicos y éticos combinados

| Riesgo | Técnico | Ético | Mitigación |
|---|---|---|---|
| Error de contrato | Alto | Alto | Pruebas y auditoría |
| Clave comprometida | Crítico | Alto | Seguridad y multisig |
| Dirección incorrecta | Alto | Alto | Revisión por pares |
| Información pública innecesaria | Medio | Crítico | Minimización de datos |
| Exclusión por uso de wallet | Medio | Alto | Web3 opcional |
| Contenido cultural incorrecto | Alto | Crítico | Validación comunitaria |
| Dependencia de terceros | Medio | Medio | Revisión de dependencias |
| Mala conectividad | Alto | Alto | Diseño ligero |

---

# 13. Toma de decisiones crítica

Antes de incorporar Stellar o Drips se deberán responder las siguientes
preguntas:

1. ¿Qué problema concreto resuelve blockchain?
2. ¿Puede resolverse de forma más sencilla sin blockchain?
3. ¿El beneficio supera la complejidad adicional?
4. ¿Qué datos deben permanecer fuera de blockchain?
5. ¿Quién administrará las wallets?
6. ¿Qué ocurre si se pierde una clave?
7. ¿Qué sucede si la red no está disponible?
8. ¿Cuál será el costo de las operaciones?
9. ¿Cómo se comprobará la seguridad?
10. ¿Cómo se protegerán los usuarios y la comunidad?

La integración solamente debería aprobarse cuando las respuestas sean
favorables y estén documentadas.

---

# 14. Criterio de decisión tecnológica

Se utilizará la siguiente regla:

**Necesidad → comparación → análisis de riesgos → prueba → validación → decisión**

No se utilizará blockchain únicamente porque sea una tecnología moderna.

La decisión deberá estar respaldada por:

- necesidad funcional;
- beneficio;
- costo;
- seguridad;
- privacidad;
- accesibilidad;
- sostenibilidad.

---

# 15. Conclusión del pensamiento crítico

El análisis muestra que las tecnologías blockchain pueden aportar
transparencia y nuevos mecanismos de financiamiento, pero también aumentan
la complejidad y los riesgos del software.

En el proyecto de Santa María Cuquila, la privacidad y el control comunitario
son factores especialmente importantes.

Por eso, la propuesta prioriza mantener el contenido cultural fuera de la
blockchain y evaluar una integración Web3 únicamente para funciones que
realmente requieran descentralización o mecanismos financieros.

La calidad debe mantenerse mediante pruebas, revisiones, auditorías,
control de cambios y medidas de seguridad.
---

# 16. Integración interdisciplinaria

El análisis de Stellar y Drips no se limita al estudio de tecnologías
blockchain. Para determinar su posible utilidad en el proyecto se integran
conocimientos de ingeniería de software, aseguramiento de calidad, economía
Web3 y contexto social y cultural.

La integración interdisciplinaria permite evaluar no solamente si una
tecnología puede implementarse, sino también si es conveniente para el
proyecto, cuánto puede costar, qué riesgos introduce y qué impacto puede
tener para los usuarios.

---

## 16.1 Ingeniería de software

Desde la ingeniería de software se consideran:

- requisitos;
- historias de usuario;
- arquitectura;
- desarrollo;
- pruebas;
- seguridad;
- mantenimiento;
- control de versiones.

Estos elementos permiten determinar si una integración con Stellar o Drips
puede incorporarse sin afectar negativamente las funcionalidades principales.

---

## 16.2 Calidad de software

La calidad se relaciona con la integración Web3 mediante:

- pruebas;
- métricas;
- revisiones;
- seguridad;
- disponibilidad;
- rendimiento;
- mantenibilidad;
- trazabilidad.

La incorporación de blockchain aumenta la necesidad de pruebas debido a que
una operación incorrecta puede tener consecuencias financieras.

Por eso, antes de utilizar fondos reales se debe realizar una etapa de
pruebas y validación.

---

## 16.3 Economía Web3

Desde la perspectiva económica se analizan:

- financiamiento;
- donaciones;
- streaming de fondos;
- distribución;
- costos de operación;
- sostenibilidad.

Drips puede utilizarse como mecanismo para recibir apoyo continuo para un
proyecto de código abierto.

Stellar puede utilizarse cuando una función financiera o descentralizada del
proyecto justifique técnicamente su incorporación.

---

## 16.4 Contexto social y cultural

El proyecto tiene como propósito preservar y transmitir la lengua y memoria
cultural de Santa María Cuquila.

Esto implica considerar:

- participación comunitaria;
- autorización para publicar contenidos;
- privacidad;
- accesibilidad;
- inclusión tecnológica;
- conectividad.

La tecnología debe adaptarse a las necesidades de la comunidad y no al
contrario.

---

# 17. Relación entre calidad y financiamiento

La calidad del software influye directamente en la posibilidad de utilizar
mecanismos de financiamiento de forma responsable.

Un proyecto con:

- documentación deficiente;
- código difícil de mantener;
- errores frecuentes;
- problemas de seguridad;
- poca trazabilidad;

presenta mayor riesgo para cualquier persona u organización que lo apoye.

Por eso se propone una relación:

**Calidad → confianza → sostenibilidad → financiamiento**

La calidad no garantiza que el proyecto reciba financiamiento, pero reduce
riesgos y facilita demostrar que existe una base técnica para continuar su
desarrollo.

---

# 18. Relación entre financiamiento y calidad

El financiamiento también puede impactar positivamente la calidad.

Los recursos podrían utilizarse para:

- infraestructura;
- almacenamiento;
- pruebas;
- auditorías;
- mantenimiento;
- seguridad;
- documentación;
- desarrollo de nuevas funciones.

Por lo tanto, el financiamiento no debe considerarse únicamente como dinero
para programar, sino como un recurso que puede fortalecer las actividades
de calidad.

---

# 19. Modelo integrado propuesto

La relación entre las diferentes áreas puede representarse de la siguiente
manera:

```text
Necesidad comunitaria
        ↓
Historias de usuario
        ↓
Ingeniería de software
        ↓
Plan de calidad
        ↓
Pruebas y métricas
        ↓
Evaluación Web3
   ↙             ↘
Stellar          Drips
   ↓               ↓
Integración      Financiamiento
        ↘       ↙
      Sostenibilidad
           ↓
   Mejora del proyecto




