# Scrum & Gestión de Producto — Criterios y Posicionamiento

### Preguntas conceptuales sobre Scrum y Product Management

---

## Contexto

Las siguientes respuestas están escritas desde la perspectiva de un profesional con más de 4 años de experiencia en IT, con perfil de QA Engineer y SDET, experiencia en automatización de pruebas y un período como Scrum Master. Este background técnico-ágil influye directamente en la forma de ver los procesos, los criterios de calidad y la gestión del equipo.

---

## Tabla de Contenidos

1. [Finalidad de los criterios de aceptación](1-cuál-es-la-finalidad-de-los-criterios-de-aceptación)
2. [Otros tipos de solicitudes en un product backlog](2-adems-de-requerimientos-del-cliente-qu-otros-tipos-de-solicitudes-se-pueden-incorporar-en-un-product-backlog)
4. [Criterio para ordenar un product backlog](3-qué-criterio-optaría-para-ordenar-un-product-backlog)
5. [Cantidad de product backlogs por proyecto](4-cuántos-product-backlogs-podemos-tener-por-proyecto)
6. [Participación obligatoria del PO en ceremonias Scrum](5-en-qué-ceremonias-de-scrum-debe-participar-obligatoriamente-el-product-owner)
7. [Error crítico de QA con sprint en curso](6-si-el-equipo-de-qa-encuentra-un-error-crítico-con-el-sprint-en-curso-qué-decisiones-tomarías)
8. [Incidente productivo urgente en mitad de un sprint](7-incidente-productivo-urgente-reportado-por-soporte-en-mitad-de-un-sprint-cómo-lo-abordarías)
9. [Producto atrasado en su desarrollo](8-el-producto-está-atrasado-en-su-desarrollo-qué-pasos-tomarías-para-minimizar-el-impacto)
10. [Cambio urgente del cliente en mitad de un sprint](9-un-cliente-solicita-un-cambio-urgente-en-mitad-de-un-sprint-cómo-lo-abordarías)

---

## 1. ¿Cuál es la finalidad de los criterios de aceptación?

La finalidad principal es eliminar la ambigüedad. Cuando escribís una historia de usuario sin criterios de aceptación, cada persona del equipo puede interpretar "listo" de forma distinta. El desarrollador cree que terminó, QA cree que falta la mitad, y el cliente esperaba algo diferente.

Los criterios de aceptación establecen de antemano qué tiene que pasar exactamente para que todos estén de acuerdo en que la historia está completa. Y son también la base directa de los casos de prueba. Si un criterio está bien escrito en formato Dado/Cuando/Entonces, casi se convierte en un test automatizado por sí solo.

---

## 2. Además de requerimientos del cliente ¿Qué otros tipos de solicitudes se pueden incorporar en un product backlog ?

El backlog no es solo funcionalidades nuevas. También puede contener:
- **Deuda técnica**: Refactors, migraciones, actualizaciones de dependencias que el equipo necesita hacer para no acumular riesgo técnico.
- **Bugs**: Especialmente los que no son críticos en el momento pero hay que resolver antes del próximo release.
- **Spikes**: Tareas de investigación o prueba de concepto cuando hay incertidumbre técnica antes de comprometerse con una solución.
- **Mejoras de performance o seguridad**: Que no las pide explícitamente el cliente pero son necesarias para sostener el producto.
- **Tareas de infraestructura o DevOps**: Configuraciones, pipelines, ambientes.
- **Historias técnicas**: Trabajo que no tiene valor directo para el usuario final pero habilita funcionalidad que sí lo tiene.

---

## 3. ¿Qué criterio optaría para ordenar un product backlog?

No elegiría un solo criterio porque el backlog es dinámico y lo que importa cambia con el tiempo. Pero si tuviera que dar un marco, combinaría tres ejes:
- **Valor para el negocio o el usuario** - ¿cuánto impacto real tiene esto si lo entregamos?
- **Riesgo e incertidumbre** - lo que más riesgo técnico o de negocio tiene, antes. Si algo puede salir mal, mejor saberlo temprano
- **Dependencias** - algunas cosas tienen que estar antes porque otras dependen de ellas

MoSCoW es útil como primera pasada para clasificar, y después dentro de cada categoría se ordena por valor y riesgo. La conversación con los stakeholders es clave — el PM no ordena el backlog solo.

---

## 4. ¿Cuántos product backlogs podemos tener por proyecto?

Uno solo. Es un principio fundamental de Scrum: hay una única fuente de verdad para el trabajo del equipo, y esa es responsabilidad del Product Owner. Tener múltiples backlogs genera desincronización, trabajo duplicado y pérdida de visibilidad.

Dentro de ese único backlog podés tener vistas filtradas, agrupaciones por épica, etiquetas por componente o equipo — pero siempre es el mismo backlog. Si el proyecto es muy grande y tiene múltiples equipos, modelos de escalado como SAFe o LeSS resuelven eso con un Program Backlog compartido que alimenta los backlogs de cada equipo, pero conceptualmente sigue siendo una sola fuente de verdad.

---

## 5. ¿En qué ceremonias de Scrum debe participar obligatoriamente el Product Owner?

Obligatoriamente en tres:
- **Sprint Planning**: Es quien explica qué se va a construir y por qué, clarifica las historias y acepta el compromiso del equipo
- **Sprint Review**: Es quien valida que lo entregado cumple con lo que se esperaba y recibe feedback de los stakeholders
- **Refinement / Backlog Grooming**: Aunque técnicamente no es una ceremonia oficial de Scrum, en la práctica es donde el PO mas trabaja, prioriza, clarifica y descompone historias junto al equipo

La Daily y la Retrospectiva son opcionales para el PO. En la Daily puede observar pero no debería interrumpir el flujo del equipo. En la Retro su presencia depende del equipo — a veces suma, a veces inhibe la conversación honesta.

---

## 6. Si el equipo de QA encuentra un error crítico con el sprint en curso, ¿qué decisiones tomarías?

En mi experiencia, lo primero seria evaluar el impacto real: si afecta alguna funcionalidad ya entregada en producción, si es algo dentro del sprint actual, o si hay workaround posible.

Si es crítico y bloquea aluguna de las historias en curso, lo primero es comunicarlo de inmediato al equipo y no esperar a la daily del día siguiente. En la práctica esto implica levantar el tema directamente con el desarrollador responsable para que lo tome lo antes posible.

Si el bug afecta el compromiso del sprint, hay que hablarlo con el Scrum Master y el PO para evaluar si se ajusta el alcance del sprint, se prioriza el fix sobre otras tareas, o se escala si el impacto supera lo que el equipo puede absorber. Como PM o PO, nunca ignoraría un defecto crítico solo para proteger el sprint, eso siempre acumula deuda y riesgo real.

---

## 7. Incidente productivo urgente reportado por soporte en mitad de un sprint, ¿cómo lo abordarías?

Lo primero es entender el impacto: cuántos usuarios afecta, qué funcionalidad está caída, si hay pérdida de datos involucrada.

Si es verdaderamente urgente, en Scrum existe la posibilidad de interrumpir el sprint. No es lo ideal pero es válido cuando el impacto en producción supera el valor del trabajo en curso. En ese caso coordinaría con el Scrum Master para reasignar capacidad del equipo al incidente.

Si el impacto es acotado, intentaría manejarlo en paralelo: un desarrollador atiende el incidente mientras el resto del equipo no se detiene. El incidente se documenta como un ítem en el backlog para darle trazabilidad, y en la retrospectiva analizamos cómo evitar que se repita.

También me seria interesaría entender si el incidente pasó por testing y cómo. Esa conversación siempre aporta al proceso.

---

## 8. El producto está atrasado en su desarrollo, ¿qué pasos tomarías para minimizar el impacto?

Primero entender por qué está atrasado. No es lo mismo deuda técnica acumulada que "scope creep", o que estimaciones incorrectas. Cada causa tiene una respuesta distinta.

Después evaluaría opciones en este orden:

- **Reducir scope**: Hay funcionalidades del release que son "Could Have" o "Should Have" y pueden moverse al siguiente ciclo sin romper el valor central?.
- **Revisar dependencias**: Hay algo bloqueado externamente que pueda desbloquearse?.
- **Comunicar temprano a los stakeholders**: El peor momento para dar malas noticias es el día de la entrega. Cuanto antes se ajustan expectativas, más opciones hay sobre la mesa.
- **No agregar personas al equipo de golpe**: La Ley de Brooks aplica, agregar gente tarde en un proyecto lo atrasa más.

Lo que no haría es presionar al equipo para trabajar más horas. Eso baja la calidad, sube los bugs y compromete el próximo sprint también.

---

## 9. Un cliente solicita un cambio urgente en mitad de un sprint, ¿cómo lo abordarías?

Lo primero es escuchar y entender qué tan urgente es realmente. "Urgente" para un cliente a veces significa "lo quiero pronto" y no necesariamente "para mañana".

Si después de evaluarlo es genuinamente urgente y prioritario, lo converso con el PO y el Scrum Master para ver si tiene sentido incorporarlo. En Scrum, los sprints tienen el objetivo de proteger al equipo de interrupciones constantes, pero hay excepciones válidas.

Si se incorpora, algo del sprint actual tiene que salir para mantener el compromiso realista. El equipo no puede absorber trabajo nuevo sin soltar algo. Esa conversación con el cliente también es parte del trabajo del PM: ayudarlo a entender que agregar algo significa quitar otra cosa, y que esa decisión la toma él con información clara.

Si no es tan urgente, va al backlog, se prioriza en el próximo planning y se gestiona bien. Esa es la respuesta más común y más sana.

---

*PM Challenge · Julio 2026 · Francisco Roldán — [roldanfrancisco.personal@gmail.com](mailto:roldanfrancisco.personal@gmail.com) · [LinkedIn](https://www.linkedin.com/in/roldanfrancisco) · [GitHub](https://github.com/roldn)*
