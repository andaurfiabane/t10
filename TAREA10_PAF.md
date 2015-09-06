FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Tarea 10 - Control de tr�fico urbano

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
                            "idCamara": "Cam_01"
                                     }
                    }
                          ]
             }
        ] 
 
### Grabar video [POST]

Permite la grabaci�n de video.

+ Request (application/json)

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

            Location: /videos

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
            
### Eliminar video [DELETE]

Permite la eliminaci�n de un video.

+ Response 200 (application/json)

    + Headers
            
            Location: /videos/5
            
    + Body
    
            {
                "Mensaje": "Video eliminado correctamente!"    
            }


## Transmisi�n de video [/transmision]

### Transmitir video [GET]

Permite la transmisi�n de video on-line.
 
+ Response 200 (application/json)

    + Headers
            
            Location: /transmision/Cam_02

    + Body
    
            {
                "Transmisi�n_on-line": 
                    {
                      "Video": {
                        "id": 5,
                        "factorCalidad": "Alta",
                        "brillo": 18,
                        "color": "rgba(0,0,0)",
                        "contraste": 22,
                        "idCamara": "Cam_02",
                        "inicioTransmisi�n": "11:55:40"
                             }       
                    }
                               
             }

## Reproducci�n de video [/reproduccion]

### Reproducir video [GET]

Permite la reproducci�n de grabaciones de video.
 
+ Response 200 (application/json)

    + Headers
            
            Location: /reproduccion/5

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
            
            
            
            
            
            
