# ESTRUCTURA DE LA PROBLEMATICA

## Contexto

El MINSA clasifica el primer nivel de atencion en dos principales categorias: I-1 e I-2, las cuales reciben el nombre como puesto/posta de salud. Sin embargo el panorama general es categoria I-1, I-2, I-3, I-4. Las categorias I-3 e I-4 reciben el nombre de centros de salud. Para este proyecto mi principal objetivo es centrarme en centros de salud de nivel I-3 (coloquialmente llamadas postas) como mi MVP. Debemos tener en cuenta que como proyecto, estoy tomando la clasificacion de manera literal; aclaro este punto ya que las clasificaciones no son literales, si no son referenciales.

## Por que I-3?

Un centro de salud, es el primer nivel de atencion, quiere decir que debe ser eficaz y rapido. 
Mis criterios de evaluacion para elegir un I-3 son:
1. Procesos manuales que ralentizan el servicio de salud y ademas generan tendencia al error humano. 
2. Alta gestion y control de insumos (Farmacia).
3. El proceso de atencion esta segmentado por areas (un area depende de la otra, si lo requiere).
4. Las areas de un I-3 a pesar de convivir en un espacio, actuan como zonas aisladas, es ahi donde se genera el cuello de botella.
5. Los sistemas modernos de salud obligan a que esten 100% conectados a Internet para funcionar, en zonas de provincia o distritos lejanos si el internet se cae obliga a todo el personal a requerir al papel de emergencia lo que regresa al criterio de seleccion numero 1.
6. Si la informacion no es veridica esto impide a instituciones como la DIRESA la correcta distribucion a tiempo de medicamentos esenciales, causando problemas de abastecimiento.

Es por eso que el proyecto esta orientado a solucionar ese cuello de botella critico el cual impide la operacion continua sin friccion para el personal de salud y la poblacion que adquiere el servicio como consecuencia.

## Por que no una I-1 o I-2?

- Las clasificaciones I-1 e I-2, manejan servicios en conjunto (un solo personal puede rotar las diferentes areas, a pesar de estar segmentadas en papel y por lo general el personal es de SERUM), siendo asi como la perdida de un servicio afecta a un solo usuario (por lo general los pacientes no tendrian que interactuar con el sistema, a menos que sea requerido).
- La gestion de insumos, se presenta de manera reducida.
- Generalmente los pacientes de I-1, I-2, son derivados hacia los centros medicos clasificados como I-3 que actuan como una cabecera.

La decision fue basada teniendo en cuenta riesgo y consecuencias, esto no indica que las problematicas que presenta una posta medica de categoria I-1 o I-2 sea insignificante o ajena a la atencion.

## La mayor limitacion

La implementacion a nivel local se puede considerar uno de nuestros menores problemas, sin embargo, los centros de salud necesitan responder a los requerimientos de su misma area, por ejemplo los reportes a la DIRESA. En este caso nuestra mayor limitacion seria:
- Caso A: El internet es inexistente.
- Caso B: Existe conexion debial hacia internet(3G/4G).
- Caso C: Existe conexion intermitente hacia Internet.
Para aterrizar el caso, lo  que se esta pensado en implementar es un entorno hibrido (offline-first). 
El motivo y razon es porque abarca los 3 casos de una mejor manera.
En el caso A, las personas no requeririan regresar al papel, al contrario, pueden solucionarse de manera fisica, la informacion sigue siendo digital lo unico que necesitarian es movilizarse a una zona con cobertura y realizar la comunicacion con Internet para lo que necesiten.
En el caso B y C, los cuales si tienen un acceso a internet, dependeria mucho mas de la configuracion implementada a nivel local (por ejemplo, metodologias para no saturar el ancho  de banda en el envio de informacion) y decisiones que abarcaremos mas adelante.