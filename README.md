**MSI-Contigo Documentación**
----
  _A continuacion se muestra de forma general cada uno de los servicios creados para la aplicacion movil MSI-Contigo, se incluye toda la información necesaria para hacer las peticiones correspondientes._
  
| Titulo      | Crear Usuario  | 
| :------------ |:---------------    | 
| URL         | `/services/createUser`   |
| Metodo      | **POST**             |
| Headers         | `---`   |
| Params(Body)  | `filial_id[int]*`    |
|             | `email[string]*`     | 
|             | `codigo[string]*`     |
| Success Response | `{"status":true,"data":{"msg":"Cuenta creada exitosamente!!!","token":"--"}}`  |
| Error Response | `{"status":false,"data":{"msg":"Faltan Parametros Obligatorios"}}`  |
|                | `{"status":false,"data":{"msg":"Ya existe una cuenta con esos datos"}}`  |
|                | `{"status":false,"data":{"msg":"Ha ocurrido un error al crear la cuenta"}}`  |

_*Parametro obligatorio_

| Titulo      | Eliminar usuario  | 
| :------------ |:---------------    | 
| URL         | `/services/deleteUser`   |
| Metodo      | **POST**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"status":true,"data":{"msg":"Usuario eliminado con exito"}}`  |
| Error Response | `{"status":false,"data":{"msg":"Faltan Parametros Obligatorios"}}`  |
|                | `{"status":false,"data":{"msg":"Ha ocurrido un error"}}`  |

_*Parametro obligatorio_

| Titulo      | Inicio de Sesión  | 
| :------------ |:---------------    | 
| URL         | `/services/login`   |
| Metodo      | **POST**             |
| Headers         | `---`   |
| Params(Body)  | `email[string]*`    |
|             | `codigo[string]*`     |
| Success Response | `{"status":true,"data":{"msg":"Inicio de Sesión exitoso!!!","token":"-----------"}}`  |
| Error Response | `{"status":false,"data":{"msg":"Faltan Parametros Obligatorios"}}`  |
|                | `{"status":false,"data":{"msg":"No se ha podido Iniciar Sesión, asegurate que los campos sean correctos"}}`  |
|                | `{"status":false,"data":{"msg":"Ha ocurrido un error al iniciar sesión"}}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Filiales  | 
| :------------ |:---------------    | 
| URL         | `/services/getFiliales`   |
| Metodo      | **GET**             |
| Headers         | `---`   |
| Params(Body)  | `---`    |
| Success Response | `{"status":true,"data":{"filiales":[{"id":-,"nombre":"---"},{"id":-,"nombre":"--"},{"id":-,"nombre":"--"}]}}`  |
| Error Response | `{"status":false,"data":{"msg":"Ha ocurrido un error"}}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Informacion del Empleado  | 
| :------------ |:---------------    | 
| URL         | `/services/getEmpleadoInfo`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"informacion":{"nombre":"---","email":"----","filial_id":-}},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Areas  | 
| :------------ |:---------------    | 
| URL         | `/services/getAreas/{filial_id[int]*}`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"areas":[{"id":-,"nombre":"--"},{"id":-,"nombre":"--"}]},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener FAQ  | 
| :------------ |:---------------    | 
| URL         | `/services/getFAQ`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"preguntas":[{"pregunta":"---","respuesta":"-----"}]},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Noticias  | 
| :------------ |:---------------    | 
| URL         | `/services/getNoticias`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"noticias":[{"id":-,"titulo":"---","categoria":"---","fecha":"----","imagen":"-----"}]},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"No hay noticias"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Detalle de Noticia | 
| :------------ |:---------------    | 
| URL         | `/services/noticiaDetail/{noticia_id[int]*}`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"noticia":{"titulo":"----","contenido":"---","autor":"--","categoria":"---","fecha":"--","filial":"---","imagen":"---"}},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"El parametro noticia_id es obligatorio"},"status":true}`  |
|                | `{"data":{"msg":"No existe noticia"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Mural | 
| :------------ |:---------------    | 
| URL         | `/services/getMurales`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"{"data":{"murales":[{"id":-,"titulo":"--","subtitulo":"---","filial":"--","imagen":"---"},{"id":-,"titulo":"--","subtitulo":"---","filial":"--","imagen":"---"}]},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"El parametro filial_id es obligatorio"},"status":true}`  |
|                | `{"data":{"msg":"No existe el mural"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Detalle Mural | 
| :------------ |:---------------    | 
| URL         | `/services/muralDetail/{mural_id[int]*}`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"mural":{"titulo":"--","subtitulo":"--","contenido":"--","fecha":"--","filial":"--","imagen":"--"}},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"El parametro mural_id es obligatorio"},"status":true}`  |
|                | `{"data":{"msg":"No existe el mural"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Actualizar OneSignal | 
| :------------ |:---------------    | 
| URL         | `/services/updateOneSignal`   |
| Metodo      | **POST**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `onesignal[string]*`    |
| Success Response | `{"data":{"msg":"Actualizacion exitosa!!!"},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Cuadro de Honor | 
| :------------ |:---------------    | 
| URL         | `/services/getC_Honor/{filial_id[int]*`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"filial":"--","personas":[{"id":-,"nombre":"---","fecha":"-- --","imagen":"--"}]},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"El parametro filial_id es obligatorio"},"status":true}`  |
|                | `{"data":{"msg":"No existen personas en el cuadro de honor"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Detalle de persona en el Cuadro de Honor | 
| :------------ |:---------------    | 
| URL         | `/services/getC_HonorDetail/{c_honor_id[int]*}`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"persona":{"filial_id":--,"nombre":"--","descripcion":"--","anio":"--","mes":"--","imagen":"--","fecha_unix":--}},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"El parametro c_honor_id es obligatorio"},"status":true}`  |
|                | `{"data":{"msg":"No existe registro de esa persona en el cuadro de honor"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Detalle de persona del mes anterior | 
| :------------ |:---------------    | 
| URL         | `/services/getC_HonorDetailPreviusMonth/{filial_id[int]*}/{fecha_unix[int]*}`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"persona":{"filial_id":--,"nombre":"--","descripcion":"--","anio":"--","mes":"--","imagen":"--","fecha_unix":--}},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"Faltan Parametros Obligatorios"},"status":false}`  |
|                | `{"data":{"msg":"No existe registro para el mes: -----"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Avisos | 
| :------------ |:---------------    | 
| URL         | `/services/getAvisos`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"avisos":[{"emisor":"--","titulo":"--","mensaje":"--","fecha":"--"},{"emisor":"--","titulo":"--","mensaje":"--","fecha":"--"}]},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"No hay avisos"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Areas CERI  | 
| :------------ |:---------------    | 
| URL         | `/services/getAreasCERI`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"areas":[{"id":-,"nombre":"--"},{"id":-,"nombre":"--"}]},"status":true}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Enviar mensaje a un Area | 
| :------------ |:---------------    | 
| URL         | `/services/newMensaje`   |
| Metodo      | **POST**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)    | `area_id[int]*`    |
|                 | `mensaje[string]*`    |
|                 | `filial_id[int]*`    |
|                 | `ceri_area[int]`    |
|                 | `ceri[boolean]*`    |
| Success Response | `{"data":{"msg":"Mensaje enviado con exito!!!"},"status":true}`  |
| Error Response | `{"data":{"msg":"No se ha podido enviar tu mensaje,intentalo mas tarde"},"status":false}`  |
|                | `{"data":{"msg":"Faltan Parametros Obligatorios"},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Agenda | 
| :------------ |:---------------    | 
| URL         | `/services/getAgenda/{filial_id[int]*}`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"agenda":[{"id": -,"titulo": "---","fecha": "--/--/----","imagen": "/images/agenda/-.jpg"},{"id": -,"titulo": "----",              "fecha": "--/--/----","imagen": "/images/agenda/-.jpg"}]},"status": true}`|
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"No existe información disponible :("},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Agenda detalle | 
| :------------ |:---------------    | 
| URL         | `/services/agendaDetail/{agenda_id[int]*}`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"id": -,"titulo": "---","fecha": "--/--/----","imagen": "/images/agenda/-.jpg"},"status": true}`|
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"No existe información disponible :("},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Beneficios | 
| :------------ |:---------------    | 
| URL         | `/services/getBeneficios`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"beneficios":[{"id": -,"titulo": "---","fecha": "--/--/----","imagen": "/images/beneficios/-.jpg"},{"id": -,"titulo": "----",              "fecha": "--/--/----","imagen": "/images/beneficios/-.jpg"}]},"status": true}`|
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"No existe información disponible :("},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Beneficio detalle | 
| :------------ |:---------------    | 
| URL         | `/services/beneficioDetail/{beneficio_id[int]*}`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"data":{"id": -,"titulo": "---","fecha": "--/--/----","imagen": "/images/beneficios/-.jpg"},"status": true}`|
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"No existe información disponible :("},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Videos | 
| :------------ |:---------------    | 
| URL         | `/services/getVideos`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"status":true,"data":{"videos":[{"id":-,"titulo":"--","link":"---","imagen":"---"}]}}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"No existen videos disponibles"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener Otros | 
| :------------ |:---------------    | 
| URL         | `/services/getOtros`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"status":true,"data":{"otros":[{"id":-,"titulo":"--","descripcion":"","link":"---","imagen":"---"}]}}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"No existen elementos disponibles"},"status":true}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Otros detalle | 
| :------------ |:---------------    | 
| URL         | `/services/otroDetail/{otro_id[int]*}`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"status": true,"data":{"otro"{"titulo":"","link":"","descripcion":"","fecha": "","imagen":"/images/otros/-.jpg"}}}`|
| Error Response | `{"status":false,"data":{"msg":"Ha ocurrido un error"}}`  |
|                | `{"status":false,"data":{"msg":"No existe el elemento"}}`  |
|                | `{"status":false,"data":{"msg":"Token Incorrecto!!!"}}`  |

_*Parametro obligatorio_

| Titulo      | Obtener boletin | 
| :------------ |:---------------    | 
| URL         | `/services/getBoletin`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"status":true,"data":{"boletin":"----.pdf"}}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Obtener información | 
| :------------ |:---------------    | 
| URL         | `/services/getInformacion`   |
| Metodo      | **GET**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)  | `---`    |
| Success Response | `{"status":true,"data":{"nombre":"----","filial_id":-}}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_

| Titulo      | Guardar información | 
| :------------ |:---------------    | 
| URL         | `/services/setInformacion`   |
| Metodo      | **POST**             |
| Headers         | `Authorization: token[string]`   |
| Params(Body)    | `filial_id[int]*`    |
|                 | `nombre[string]*`    |
| Success Response | `{"status":true,"data":{"msg":"Actualizacion completada"}}`  |
| Error Response | `{"data":{"msg":"Ha ocurrido un error"},"status":false}`  |
|                | `{"data":{"msg":"Token Incorrecto!!!"},"status":false}`  |

_*Parametro obligatorio_
