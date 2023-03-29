# Hackaton-Mestalla

by SQBATA

---
## Introducción:

Para conmemorar los 100 años desde que se construyo el estadio de *Mestalla* en el barrio con el mismo nombre, *Hiberus* ha propuesto a una serie de voluntari@s y esforzad@s miembros del mundo del dato, un reto apasionante:

> Determinar el ratio de permanencia de l@s abonad@s que tiene el Valéncia C.F. para la próxima temporada.

Para ello, nos ha facilitado una serie de Datasets con los datos de asistencia y de abonados existentes desde la temporada 2015/16 hasta la actual.

Los datos que nos ha facilitado es:

- **ABONADOS:**
    - ID
    - SEXO
    - NOMBRE_ZONA
    - NOMBRE_SECTOR
    - FEC_NACIMIENTO
    - FEC_ALTA
    - CP
    - CUOTA_PAGADA


- **ASISTENCIA:**
    - ID
    - FECHA
    - PKIDPARTIDO
    - NOMBRE
    - JORNADA
    - COMPETICION
    - NOMBRE_ZONA
    - NOMBRE_SECTOR
    - HORA_ACCESO
---
## Estructura del procesamiento:

Dado que lo que vamos a determinar es la tasa de renovación de l@s abonad@s, vamos a valorar primeramente qué abonados han permanecido durante este tiempo.

Se entiende que est@s abonad@s se mantendrán fieles y por lo tanto para la estimación del procesamiento de permanencia de los abonados, provocaría un desajuste en los mecanismos del modelado de aprendizaje programado que vamos a utilizar.

Una vez determinados estos, los vamos a separar del resto de registros del dataset completo de los abonados para trabajar con ellos.

### Generación de variables nuevas:

- Vamos a generar *INICIO_TEMPORADA*,
- Vamos a generar *EDAD* a partir de las fechas de nacimiento hasta la fecha actual,
- Hemos utilizado ENCODER para dejar valores numéricos por *NOMBRE_SECTOR*,
- Hemos generando una última columna indicando si ha renovado o no.
    Esta sería nuestra columna target.

- Por otra parte utilizaremos los datasets de *ASISTENCIA* para generar determinar cuántas veces un abonad@ ha asistido a los partidos del Valéncia C.F. 



Con todo ello nuestro dataset para el tratamiento de los datos quedará de esta manera:

- **DATA:**
    - ID
    - INICIO_TEMPORADA
    - EDAD
    - FEC_ALTA
    - % De ASISTENCIA
    - CUOTA_PAGADA
    - NOMBRE_SECTOR
    - Renuevan/No renuevan

