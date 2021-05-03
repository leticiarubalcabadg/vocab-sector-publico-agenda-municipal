

<img src="https://ciudadesabiertas.es/assets/img/cabiertas/logo.svg" alt="LogoCiudadesAbiertas" width="200"/> 

# DESARROLLO API REST DE DATOS REUTILIZABLE. MODELO DE TABLAS: AGENDA MUNICIPAL

&nbsp;

## **ÍNDICE**   
1. [AUTORES](#id1)
2. [LINKS](#id2)
3. [DIAGRAMA CONCEPTUAL](#id3)
4. [TABLAS](#id4)  
    - [EVENTO](#id5)  
    - [DOCUMENTACIÓN](#id6)  
    - [ROLINTEGRANTEEVENTO](#id7)  
5. [TAXONOMIAS SKOS](#id8) 
    - [TIPO DE ACCESO](#id9) 
    - [TIPO DE CARGO](#id10)  
    - [TIPO DE SESIÓN](#id11) 
    - [ROL DE INTEGRANTE DE REUNIÓN](#id12)  
    - [CANAL DE EVENTO](#id13) 
    - [TIPO DE EVENTO](#id14) 





&nbsp;

## AUTORES <a name="id1"></a>
- Edna Ruckhaus
- Hugo Lafuente Matesanz
- Leticia Rubalcaba
- Oscar Corcho
- Paola Espinoza Arias

&nbsp;

## LINKS <a name="id2"></a>


Este documento contiene la información detallada del modelo de datos asociado al vocabulario de los convenios. A continuación, se detallan los enlaces de interés asociados a este vocabulario:

- *[Documentación](http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal/index-es.html)*
- *[Repositorio](https://github.com/CiudadesAbiertas/vocab-sector-publico-agenda-municipal)*
- *[Webinar](https://youtu.be/S9TlBIuy3Lc)*
- *[Requisitos](https://github.com/CiudadesAbiertas/vocab-sector-publico-agenda-municipal/blob/master/requirements/Requisitos%20-%20Agenda%20Municipal.xlsx)*
- *[Issues](https://github.com/CiudadesAbiertas/vocab-sector-publico-agenda-municipal/issues)*

&nbsp;

## DIAGRAMA CONCEPTUAL <a name="id3"></a>
&nbsp;
La figura muestra las clases y propiedades del vocabulario de los eventos de la agenda municipal y sus participantes.   

&nbsp;
![Diagrama conceptual](http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal/resources/images/modeloConceptual.png)
&nbsp;



## TABLAS <a name="id4"></a>
En principio se considera esta estructura de datos bastante estable y no se estima que sufrirá cambios. Pero puesto que la actuación D2, que es donde se enmarca la definición de estas tablas, aún está en desarrollo, no se puede asegurar al 100% que será la definitiva.     

[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### EVENTO <a name="id5"></a>
&nbsp;
|     Campo                 |     Tipo            |     Ejemplo                                                                                                                                                                                                                                                                                                   |     Descripción                                                                                                                                                                                                                                                                                                                                      |     URL                                                                                                      |
|---------------------------|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|     ikey                  |     VARCHAR(50)     |     1                                                                                                                                                                                                                                                                                                         |     Identificador   de la Tabla (PK).                                                                                                                                                                                                                                                                                                                |                                                                                                              |
|     id                    |     VARCHAR(50)     |     AME0001                                                                                                                                                                                                                                                                                                   |     Identificador   del evento.                                                                                                                                                                                                                                                                                                                      |                                                                                                              |
|     title                 |     VARCHAR(400)    |     Preside el   homenaje a los campeones del mundo y a las campeonas de Europa de baloncesto                                                                                                                                                                                                                 |     Nombre del   evento.                                                                                                                                                                                                                                                                                                                             |     http://purl.org/dc/elements/1.1/title                                                                    |
|     description           |     VARCHAR(400)    |     28014                                                                                                                                                                                                                                                                                                     |     Descripción   del evento.                                                                                                                                                                                                                                                                                                                        |     http://schema.org/description                                                                            |
|     url                   |     VARCHAR(400)    |     https://www.madrid.es/portales/munimadrid/es/Inicio/El-Ayuntamiento/Agenda-de-hoy/Preside-el-homenaje-a-los-campeones-del-mundo-y-a-las-campeonas-de-Europa-de-baloncesto/?vgnextfmt=default&vgnextoid=5bcd15044bf6e610VgnVCM1000001d4a900aRCRD&vgnextchannel=8071317d3d2a7010VgnVCM100000dc0ca8c0RCRD    |     URL del   evento.                                                                                                                                                                                                                                                                                                                                |     http://schema.org/url                                                                                    |
|     start_date            |     DATETIME        |     2019-11-18T11:00:00.0                                                                                                                                                                                                                                                                                     |     La fecha y   hora del inicio del evento.     Formato de   fecha ISO 8601:     http://en.wikipedia.org/wiki/ISO_8601"                                                                                                                                                                                                                             |     http://schema.org/startDate                                                                              |
|     end_date              |     DATETIME        |     2019-11-18T12:59:59.0                                                                                                                                                                                                                                                                                     |     La fecha y   hora de la finalización del evento.     Formato de   fecha ISO 8601:     http://en.wikipedia.org/wiki/ISO_8601"                                                                                                                                                                                                                     |     http://schema.org/endDate                                                                                |
|     location_title        |     VARCHAR(400)    |     Palacio de Cibeles                                                                                                                                                                                                                                                                                        |     Nombre de la localización                                                                                                                                                                                                                                                                                                                        |     https://schema.org/location                                                                              |
|     street_address        |     VARCHAR(200)    |     Plaza Cibeles, 1                                                                                                                                                                                                                                                                                          |     Dirección completa.                                                                                                                                                                                                                                                                                                                              |     https://schema.org/address                                                                               |
|     postal_code           |     VARCHAR(10)     |     28007                                                                                                                                                                                                                                                                                                     |     Código postal.                                                                                                                                                                                                                                                                                                                                   |     http://schema.org/postalCode                                                                             |
|     callejero_id          |     VARCHAR(10)     |     Integración con callejero, id   (asociado a callejero_portal). PORTAL00008                                                                                                                                                                                                                                |     Identificador del callejero                                                                                                                                                                                                                                                                                                                      |                                                                                                              |
|     municipio_id          |     VARCHAR(50)     |     28076                                                                                                                                                                                                                                                                                                     |     El identificador de un Municipio.                                                                                                                                                                                                                                                                                                                |     http://vocab.linkeddata.es/datosabiertos/def/sector-publico/territorio#Municipio                         |
|     municipio_title       |     VARCHAR(400)    |     Madrid                                                                                                                                                                                                                                                                                                    |     Nombre de un   Municipio.                                                                                                                                                                                                                                                                                                                        |     http://vocab.linkeddata.es/datosabiertos/def/sector-publico/territorio#Municipio                         |
|     distrito_id           |     VARCHAR(50)     |     2807601                                                                                                                                                                                                                                                                                                   |     Es el identificador de un distrito.   Un distrito es cada una de las demarcaciones en que se subdivide un   territorio o una población para distribuir y ordenar el ejercicio de los   derechos civiles y políticos, o de las funciones públicas, o de los servicios   administrativos [fuente: Diccionario de la Real Academia (DRAE) 2011].    |     http://vocab.linkeddata.es/datosabiertos/def/sector-publico/territorio#Distrito                          |
|     distrito_title        |     VARCHAR(400)    |     Centro                                                                                                                                                                                                                                                                                                    |     Nombre o   título de un distrito, se especifica con la propiedad dct:title,   geonames:name, y rdf:label es el proporcionado por el Registro de Entidades   Locales del Ministerio de Política Territorial, en   http://www.ine.es/nomen2/index.do                                                                                               |     http://vocab.linkeddata.es/datosabiertos/def/sector-publico/territorio#Distrito                          |
|     barrio_id             |     VARCHAR(50)     |     28076011                                                                                                                                                                                                                                                                                                  |     Identificador de un barrio.                                                                                                                                                                                                                                                                                                                      |     http://vocab.linkeddata.es/datosabiertos/def/sector-publico/territorio#Barrio                            |
|     barrio_title          |     VARCHAR(400)    |     Hortaleza                                                                                                                                                                                                                                                                                                 |     Nombre del   barrio.                                                                                                                                                                                                                                                                                                                             |     http://vocab.linkeddata.es/datosabiertos/def/sector-publico/territorio#Barrio                            |
|     equipamiento_id       |     VARCHAR(50)     |     Integración con equipamiento, id   (asociado a equipamiento). PORTAL00008                                                                                                                                                                                                                                 |     Identificador del equipamiento.                                                                                                                                                                                                                                                                                                                  |     http://vocab.linkeddata.es/datosabiertos/def/urbanismo-infraestructuras/equipamiento-municipal#id        |
|     equipamiento_title    |     VARCHAR(200)    |     EQ0001                                                                                                                                                                                                                                                                                                    |     Título o   nombre del equipamiento.                                                                                                                                                                                                                                                                                                              |     http://vocab.linkeddata.es/datosabiertos/def/urbanismo-infraestructuras/equipamiento-municipal#nombre    |
|     super_event_id        |     VARCHAR(50)     |     Invocación al id padre de Agenda   Municipal Evento                                                                                                                                                                                                                                                       |     Un evento del que este evento es   parte. Por ejemplo, una colección de actuaciones musicales individuales   puede tener cada una un festival de música como su superEvent.     FK a la tabla EVENTO                                                                                                                                             |     http://schema.org/superEvent                                                                             |
|     reunion_lobby         |     NUMBER(1,0)     |     0                                                                                                                                                                                                                                                                                                         |     Reuniones   con carácter de lobby en donde una persona física, jurídica y entidades sin   personalidad que pretenda influir en la normativa y en las políticas   municipales y en las decisiones de impacto general, lo hacen a través de   encuentros con concejales, directivos y personal eventual municipal.                                 |     http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal#reunionLobby                        |
|     tipo_acceso           |     VARCHAR(200)    |     público                                                                                                                                                                                                                                                                                                   |     Tipo de asistencia al evento: público,   privado o restringido.     URL SKOS:     http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/tipo-acceso                                                                                                                                                                       |     http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal#tipoAcceso                          |
|     tipo_sesion           |     VARCHAR(200)    |                                                                                                                                                                                                                                                                                                               |     Para los eventos de órganos colegiados,   tipo de sesión puede ser ordinaria, extraordinaria o extraordinaria urgente.     URL SKOS:     http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/tipo-sesion                                                                                                                |     http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal#tipoSesion                          |
|     tipo_evento           |     VARCHAR(200)    |     Premio o   Reconocimiento                                                                                                                                                                                                                                                                                 |     Tipología que   define a qué categoría pertenece el evento. Los tipos de evento se   representan mediante una lista de conceptos.     URL SKOS:     http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/tipo-evento                                                                                                     |     http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal#tipoEvento                          |
|     canal                 |     VARCHAR(200)    |     presencial                                                                                                                                                                                                                                                                                                |     Medio de realización del evento:   presencial o en línea.     URL SKOS:     http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/canal                                                                                                                                                                                   |     http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal#canal                               |



[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### DOCUMENTACIÓN <a name="id6"></a>
&nbsp;
|     Campo             |     Tipo              |     Ejemplo                                                                  |     Descripción                                                                                                                                                                                                                                                                                                                                |     URL                                 |
|-----------------------|-----------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|
|     ikey              |     VARCHAR(50)       |     1                                                                        |     Identificador   de la Tabla (PK).                                                                                                                                                                                                                                                                                                          |                                         |
|     id                |     VARCHAR(50)       |     AMD0001                                                                  |     Identificador   de la documentación.                                                                                                                                                                                                                                                                                                       |                                         |
|     encodingFormat    |     VARCHAR  (400)    |     text/plain                                                               |     El tipo de   medio normalmente se expresa con un formato MIME (consulte el sitio de IANA y   la referencia de MDN).     En los casos   en que un CreativeWork tiene varias representaciones de tipos de medios, la   codificación se puede utilizar para indicar cada MediaObject junto con   información de encodingFormat particular.    |     http://schema.org/encodingFormat    |
|     name              |     varchar(400)      |     Inscripción Evento                                                       |     Nombre de   documentación.                                                                                                                                                                                                                                                                                                                 |     http://schema.org/name              |
|     url               |     varchar(400)      |     https://datos.madrid.es/FwFront/portal_egob/new/img/portal_logo_h.png    |     URL                                                                                                                                                                                                                                                                                                                                        |     http://schema.org/url               |
|     evento_id         |     VARCHAR(50)       |     AME0001                                                                  |     Identificador   del evento.     FK a la   tabla EVENTO                                                                                                                                                                                                                                                                                     |                                         |




[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### ROLINTEGRANTEEVENTO <a name="id7"></a>
&nbsp;
|     Campo                 |     Tipo            |     Ejemplo                   |     Descripción                                                                               |     URL                                                                                                                                                                                                                                                  |
|---------------------------|---------------------|-------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     ikey                  |     VARCHAR(50)     |     1                         |     Identificador   de la Tabla (PK).                                                         |                                                                                                                                                                                                                                                          |
|     id                    |     VARCHAR(50)     |     AMR0001                   |     Identificador   del rol integrante del evento.                                            |                                                                                                                                                                                                                                                          |
|     agent_name            |     VARCHAR(400)    |     Eduardo   López García    |     Nombre del   agente.                                                                      |     http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal#nombre     http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal#apellido1     http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal#apellido2    |
|     organization_title    |     VARCHAR(400)    |     AREA DE   ALCALDIA        |     Nombre de la   organización a la que pertenece el agente en calidad de miembro.           |     http://xmlns.com/foaf/spec/#name                                                                                                                                                                                                                     |
|     organization_id       |     VARCHAR(50)     |     2                         |     Identificador   de la organización a la que pertenece el agente en calidad de miembro.    |     http://www.w3.org/ns/org#identifier                                                                                                                                                                                                                  |
|     role                  |     VARCHAR(400)    |     Alcalde                   |     Actividad   que el agente desempeña en una relación de pertenencia a una organización.    |     http://www.w3.org/ns/org#role                                                                                                                                                                                                                        |
|     rol                   |     VARCHAR(400)    |     convocante                |     El rol que puede tener un integrante de   un evento.                                      |     http://vocab.ciudadesabiertas.es/def/sector-publico/agenda-municipal#rol                                                                                                                                                                             |
|     evento_id             |     VARCHAR(50)     |     AME0001                   |     Identificador   del evento                                                                |                                                                                                                                                                                                                                                          |





[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
## TAXONOMIAS SKOS <a name="id8"></a>
&nbsp;




[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TIPO DE ACCESO <a name="id9"></a>
&nbsp;
http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/tipo-acceso    

Tesauro que recoge los tipos de acceso de los asistentes a un evento.    
|     Tipo           |     Label           |     Definition                                             |
|--------------------|---------------------|------------------------------------------------------------|
|     privado        |     Privado         |     Solo pueden asistir los participantes en el evento.    |
|     publico        |     Público         |     Cualquier persona puede asistir.                       |
|     restringido    |     Restringido     |     Solo se puede asistir por invitación.                  |





[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 

&nbsp;
### TIPO DE CARGO <a name="id10"></a>
&nbsp;
http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/tipo-cargo    

Tesauro que recoge los tipos de cargos generales que se pueden tener en un Ayuntamiento.    
|     Tipo                 |     Label                 |     Definition                                                                                                                                                                                                                                           |
|--------------------------|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     alcalde-sa           |     alcalde/sa            |     Cargo público que se encuentra al frente de la administración   política de una ciudad.                                                                                                                                                              |
|     concejal-a           |     concejal/a            |     Miembro seleccionado para la administración política de los municipios.                                                                                                                                                                              |
|     directivo-a          |                           |                                                                                                                                                                                                                                                          |
|     personal-eventual    |     Personal eventual     |     Cargo en el que una persona mediante un nombramiento libre   ocupa puestos de trabajo no reservados a funcionarios de carrera,   desempeñando con carácter temporal funciones exclusivamente calificadas de   confianza o asesoramiento especial.    |



[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 

&nbsp;
### TIPO DE SESIÓN <a name="id11"></a>
&nbsp;
http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/tipo-sesion    

Tesauro que recoge los tipos de sesión de un evento como Ordinaria, Extraordinaria y Extraordinaria Urgente.    
|     Tipo                      |     Label                     |     Definition                                                                                                                                                                                                           |
|-------------------------------|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     extraordinaria            |     Extraordinaria            |     Sesión que se realiza a solicitud del interesado de acuerdo a   la disposición legal del gobierno municipal.                                                                                                         |
|     extraordinaria-urgente    |     Extraordinaria urgente    |     Sesión que se realiza a solicitud del interesado cuando la   urgencia del asunto o asuntos a tratar no permita convocar la sesión   extraordinaria con la antelación mínima establecida por la disposición legal.    |
|     ordinaria                 |     Ordinaria                 |     Sesiones que se realizan periódicamente.                                                                                                                                                                             |





[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 

&nbsp;
### ROL DE INTEGRANTE DE REUNIÓN <a name="id12"></a>
&nbsp;
http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/rol-integrante    

Tesauro que recoge los roles de los integrantes de un evento.     
|     Tipo          |     Label          |     Definition                               |
|-------------------|--------------------|----------------------------------------------|
|     asistente     |     Asistente      |     Persona invitada a asistir al evento.    |
|     convocante    |     Convocante     |     Persona que convoca el evento.           |
|     titular       |     Titular        |     Persona que organiza el evento.          |



&nbsp;
### CANAL DE EVENTO <a name="id13"></a>
&nbsp;
http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/canal    

Tesauro que recoge los tipos de canal del evento.    
|     Tipo          |     Label          |     Definition                                                    |
|-------------------|--------------------|-------------------------------------------------------------------|
|     presencial    |     Presencial     |     Evento que se realiza de forma presencial.                    |
|     virtual       |     Virtual        |     Evento que se realiza a través de una herramienta digital.    |







&nbsp;
### TIPO DE EVENTO <a name="id14"></a>
&nbsp;
http://vocab.linkeddata.es/datosabiertos/kos/sector-publico/agenda-municipal/tipo-evento    

Tesauro que recoge los tipos de evento de la agenda municipal.     
|     Tipo                                |     Subtipo                                           |     Label                                             |
|-----------------------------------------|-------------------------------------------------------|-------------------------------------------------------|
|     acto                                |                                                       |     Acto                                              |
|                                         |     acto-conmemorativo                                |     Acto Conmemorativo                                |
|                                         |     clausura                                          |     Clausura                                          |
|                                         |     comida                                            |     Comida                                            |
|                                         |     dia-de                                            |     Dia de                                            |
|                                         |     firma                                             |     Firma                                             |
|                                         |     gala                                              |     Gala                                              |
|                                         |     homenaje                                          |     Homenaje                                          |
|                                         |     inauguracion                                      |     Inauguración                                      |
|                                         |     jornada-o-congreso                                |     Jornada o Congreso                                |
|                                         |     matrimonio-civil                                  |     Matrimonio Civil                                  |
|                                         |     premio-o-reconocimiento                           |     Premio o Reconocimiento                           |
|                                         |     presentacion                                      |     Presentación                                      |
|                                         |     visita                                            |     Visita                                            |
|     evento-con-medio-de-comunicacion    |                                                       |     Evento con Medio de Comunicación                  |
|                                         |     entrevista                                        |     Entrevista                                        |
|                                         |     rueda-de-prensa                                   |     Rueda de Prensa                                   |
|     otras-reuniones                     |                                                       |     Otras Reuniones                                   |
|                                         |     reunion-con-asociaciones                          |     Reunión con Asociaciones                          |
|                                         |     reunion-con-ciudadania                            |     Reunión con Ciudadanía                            |
|                                         |     reunion-con-empresa                               |     Reunión con Empresa                               |
|                                         |     reunion-con-organizacion-sindical                 |     Reunión con Organización Sindical                 |
|                                         |     reunion-con-otras-administraciones                |     Reunión con otras Administraciones                |
|                                         |     reunion-de-grupo-politico                         |     Reunión de Grupo Político                         |
|                                         |     reunion-interna                                   |     Reunión Interna                                   |
|     sesion-organos-colegiados           |                                                       |     Sesión Órganos Colegiados                         |
|                                         |     comision-no-permanente                            |     Comisión No Permanente                            |
|                                         |     comision-permanente                               |     Comisión Permanente                               |
|                                         |     consejo-de-administracion-empresas-municipales    |     Consejo de Administración Empresas Municipales    |
|                                         |     consejo-de-ciudad                                 |     Consejo de Ciudad                                 |
|                                         |     consejo-sectorial                                 |     Consejo Sectorial                                 |
|                                         |     junta-de-distrito                                 |     Junta de Distrito                                 |
|                                         |     junta-de-gobierno                                 |     Junta de Gobierno                                 |
|                                         |     junta-de-portavoces                               |     Junta de Portavoces                               |
|                                         |     otro-consejo                                      |     Otro Consejo                                      |
|                                         |     pleno                                             |     Pleno                                             |






&nbsp;








<p float="right" align="center">
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/gobEspana-logo.svg" alt="Logo Gobierno España" width="200"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/red-logo.svg" alt="Logo red.es" width="150"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ciudadesInteligentes-logo.svg" alt="Logo CiudadesInteligentes" width="150"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/unionEuropea-logo.svg" alt="Logo UnionEuropea" width="200"/>
</p>


<p float="right" align="center">
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ayuntAcoruna-logo.svg" alt="Logo AyuntACoruña" width="200"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ayuntMadrid-logo.svg" alt="Logo Madrid" width="100"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ayuntSantiagoCompostela-logo.svg" alt="Logo Concello Santiago" width="200"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ayuntZaragoza-logo.svg" alt="Logo Ayun.Zaragoza" width="200"/>
</p>



