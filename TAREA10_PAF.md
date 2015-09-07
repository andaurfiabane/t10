FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Tarea 10 - Control de tr�fico urbano

Esta es una simple API de consulta de videos on-line y grabaciones.


## Videos [/videos/{?id}]

### Listar videos [GET /videos/]

Permite listar videos grabados.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Videos": [
                    {
                            "Video": {
                            "id": 1,
                            "inicioTransmisi�n": "12:02:00",
                            "finTransmisi�n": "12:04:30",
                            "fechaGrabaci�n": "2015-08-01",
                            "horaGrabaci�n": "12:04:35",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 20,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/video?1",
                            "idCamara": "Cam_03"
                                     }
                    },
                     {
                            "Video": {
                            "id": 2,
                            "inicioTransmisi�n": "14:52:00",
                            "finTransmisi�n": "14:56:55",
                            "fechaGrabaci�n": "2015-08-24",
                            "horaGrabaci�n": "14:57:02",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 25,
                            "color": "rgba(0,0,0)",
                            "contraste": 25,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/video?2",
                            "idCamara": "Cam_01"
                                     }
                    },
                     {
                            "Video": {
                            "id": 3,
                            "inicioTransmisi�n": "10:00:00",
                            "finTransmisi�n": "10:05:00",
                            "fechaGrabaci�n": "2015-08-29",
                            "horaGrabaci�n": "10:05:06",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 10,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/video?3",
                            "idCamara": "Cam_02"
                                     }
                    },
                     {
                            "Video": {
                            "id": 4,
                            "inicioTransmisi�n": "12:52:00",
                            "finTransmisi�n": "12:59:55",
                            "fechaGrabaci�n": "2015-09-05",
                            "horaGrabaci�n": "13:00:00",
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 15,
                            "color": "rgba(0,0,0)",
                            "contraste": 25,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/video?4",
                            "idCamara": "Cam_01"
                                     }
                    }
                          ]
                 }
             ] 
 
### Grabar video [POST /videos/]

Permite la grabaci�n de video.

+ Request (application/json)
  

    + Body
    
            {
                "Video": {
                            "id": 5,
                            "formatoCompresi�n": "XviD",
                            "formato": "AVI",
                            "inicioTransmisi�n": "11:55:40",
                            "finTransmisi�n": "11:59:40",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 20,
                            "idCamara": "Cam_02"
                         }
            }

+ Response 201 (application/json)

    + Headers

            Location: /videos/

    + Body

            {
                "Mensaje": "Video grabado correctamente!",
                "Video": {
                            "fechaGrabaci�n": "2015-09-05",
                            "horaGrabaci�n": "11:59:50",
                            "duraci�nVideo": 180,
                            "formatoDuraci�n": "Segundos"
                     }
            }
            
### Eliminar video [DELETE /videos/{?id}]

Permite la eliminaci�n de un video.

+ Request (application/json)

+ Parameters
  + id (required, int)


+ Response 200 (application/json)

    + Headers
            
            Location: /videos/
            
    + Body
    
            {
                "Mensaje": "Video eliminado correctamente!"    
            }


## C�maras [/camaras/{?id}]

### Listar c�maras [GET /camaras/]

Permite listar las c�maras disponibles.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Camaras": [
                    {
                            "camara": {
                            "id": "Cam_01",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 20,
                            "ip": "192.168.1.22"
                                     }
                    },
                     {
                            "camara": {
                            "id": "Cam_02",
                            "factorCalidad": "Alta",
                            "brillo": 42,
                            "color": "rgba(0,0,0)",
                            "contraste": 10,
                            "ip": "192.168.1.23"
                                     }
                    }
                          ]
                 }
             ] 
 
### Agregar c�mara [POST /camaras/]

Permite agregar una nueva c�mara.

+ Request (application/json)
  

    + Body
    
            {
                 "camara": {
                            "id": "Cam_03",
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 13,
                            "ip": "192.168.1.23"
                            }
            }

+ Response 201 (application/json)

    + Headers

            Location: /camaras

    + Body

            {
                "Mensaje": "C�mara agregada correctamente!"
            }            

### Eliminar c�mara [DELETE /camaras/{?id}]

Permite quitar una c�mara del sistema.

+ Request (application/json)

+ Parameters
  + id (required, int)


+ Response 200 (application/json)

    + Headers
            
            Location: /camaras/
            
    + Body
    
            {
                "Mensaje": "C�mara quitada correctamente!"    
            }            
            
### Modificar c�mara [PUT /camaras/{?id}]

Permite modificar una c�mara.

+ Request (application/json)
  

    + Body
    
            {
                 "camara": {
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 13,
                            "ip": "192.168.1.23"
                            }
            }

+ Response 201 (application/json)

    + Body

            {
                "Mensaje": "C�mara modificada correctamente!"
            }            


## Transmisi�n de video [/transmision/{?idCamara}]

### Transmitir video [GET /transmision/{?idCamara}]

Permite la transmisi�n de video on-line.

+ Request (application/json)
  
+ Parameters
  + idCamara (required, string)
  
 
+ Response 200 (application/json)

    + Body
    
            {
                "Transmisi�n_on-line": 
                    {
                      "id": 5,
                      "urlTransmision": "http://www.ejemplotransmision.com/transmision/?idCamara=Cam_02",
                      "factorCalidad": "Alta",
                      "brillo": 18,
                      "color": "rgba(0,0,0)",
                      "contraste": 22,
                      "inicioTransmisi�n": "11:55:40"
                    }
                               
             }
             

## Reproducci�n de video [/reproduccion/{?idVideo}]

### Reproducir video [GET /reproduccion/{?idVideo}]

Permite la reproducci�n de grabaciones de video.

+ Request (application/json)
  
+ Parameters
  + idVideo (required, int)

+ Response 200 (application/json)

    + Body

            {
                "Reproducci�n": 
                    {
                      "Video": {
                        "id": 5,
                        "factorCalidad": "Alta",
                        "brillo": 18,
                        "color": "rgba(0,0,0)",
                        "contraste": 22,
                        "idCamara": "Cam_02",
                        "duraci�nVideo": 180,
                        "formatoDuraci�n": "Segundos"
                             }       
                    }
                               
             }
   