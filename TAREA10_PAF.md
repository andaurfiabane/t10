FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Tarea 10 - Control de tráfico urbano

Esta es una simple API de consulta de videos on-line y grabaciones.


## Videos [/videos]

### Listar videos [GET]

Permite listar videos grabados.
 
+ Response 200 (application/json)

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
                            "idCamara": "Cam_01"
                                     }
                    }
                          ]
             }
        ] 
 
### Grabar video [POST]

Permite la grabación de video.

+ Request (application/json)

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

            Location: /videos

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
            
### Eliminar video [DELETE]

Permite la eliminación de un video.

+ Response 200 (application/json)

    + Headers
            
            Location: /videos/5
            
    + Body
    
            {
                "Mensaje": "Video eliminado correctamente!"    
            }


## Transmisión de video [/transmision]

### Transmitir video [GET]

Permite la transmisión de video on-line.
 
+ Response 200 (application/json)

    + Headers
            
            Location: /transmision/Cam_02

    + Body
    
            {
                "Transmisión_on-line": 
                    {
                      "Video": {
                        "id": 5,
                        "factorCalidad": "Alta",
                        "brillo": 18,
                        "color": "rgba(0,0,0)",
                        "contraste": 22,
                        "idCamara": "Cam_02",
                        "inicioTransmisión": "11:55:40"
                             }       
                    }
                               
             }

## Reproducción de video [/reproduccion]

### Reproducir video [GET]

Permite la reproducción de grabaciones de video.
 
+ Response 200 (application/json)

    + Headers
            
            Location: /reproduccion/5

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
            
            
            
            
            
            
