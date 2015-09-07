FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Tarea 10 - Control de tráfico urbano

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
                            "inicioTransmisión": "12:02:00",
                            "finTransmisión": "12:04:30",
                            "fechaGrabación": "2015-08-01",
                            "horaGrabación": "12:04:35",
                            "formatoCompresión": "XviD",
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
                            "inicioTransmisión": "14:52:00",
                            "finTransmisión": "14:56:55",
                            "fechaGrabación": "2015-08-24",
                            "horaGrabación": "14:57:02",
                            "formatoCompresión": "XviD",
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
                            "inicioTransmisión": "10:00:00",
                            "finTransmisión": "10:05:00",
                            "fechaGrabación": "2015-08-29",
                            "horaGrabación": "10:05:06",
                            "formatoCompresión": "XviD",
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
                            "inicioTransmisión": "12:52:00",
                            "finTransmisión": "12:59:55",
                            "fechaGrabación": "2015-09-05",
                            "horaGrabación": "13:00:00",
                            "formatoCompresión": "XviD",
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

Permite la grabación de video.

+ Request (application/json)
  

    + Body
    
            {
                "Video": {
                            "id": 5,
                            "formatoCompresión": "XviD",
                            "formato": "AVI",
                            "inicioTransmisión": "11:55:40",
                            "finTransmisión": "11:59:40",
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
                            "fechaGrabación": "2015-09-05",
                            "horaGrabación": "11:59:50",
                            "duraciónVideo": 180,
                            "formatoDuración": "Segundos"
                     }
            }
            
### Eliminar video [DELETE /videos/{?id}]

Permite la eliminación de un video.

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


## Cámaras [/camaras/{?id}]

### Listar cámaras [GET /camaras/]

Permite listar las cámaras disponibles.
 
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
 
### Agregar cámara [POST /camaras/]

Permite agregar una nueva cámara.

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
                "Mensaje": "Cámara agregada correctamente!"
            }            

### Eliminar cámara [DELETE /camaras/{?id}]

Permite quitar una cámara del sistema.

+ Request (application/json)

+ Parameters
  + id (required, int)


+ Response 200 (application/json)

    + Headers
            
            Location: /camaras/
            
    + Body
    
            {
                "Mensaje": "Cámara quitada correctamente!"    
            }            
            
### Modificar cámara [PUT /camaras/{?id}]

Permite modificar una cámara.

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
                "Mensaje": "Cámara modificada correctamente!"
            }            


## Transmisión de video [/transmision/{?idCamara}]

### Transmitir video [GET /transmision/{?idCamara}]

Permite la transmisión de video on-line.

+ Request (application/json)
  
+ Parameters
  + idCamara (required, string)
  
 
+ Response 200 (application/json)

    + Body
    
            {
                "Transmisión_on-line": 
                    {
                      "id": 5,
                      "urlTransmision": "http://www.ejemplotransmision.com/transmision/?idCamara=Cam_02",
                      "factorCalidad": "Alta",
                      "brillo": 18,
                      "color": "rgba(0,0,0)",
                      "contraste": 22,
                      "inicioTransmisión": "11:55:40"
                    }
                               
             }
             

## Reproducción de video [/reproduccion/{?idVideo}]

### Reproducir video [GET /reproduccion/{?idVideo}]

Permite la reproducción de grabaciones de video.

+ Request (application/json)
  
+ Parameters
  + idVideo (required, int)

+ Response 200 (application/json)

    + Body

            {
                "Reproducción": 
                    {
                      "Video": {
                        "id": 5,
                        "factorCalidad": "Alta",
                        "brillo": 18,
                        "color": "rgba(0,0,0)",
                        "contraste": 22,
                        "idCamara": "Cam_02",
                        "duraciónVideo": 180,
                        "formatoDuración": "Segundos"
                             }       
                    }
                               
             }
   