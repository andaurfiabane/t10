FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Tarea 10 - Control de tráfico urbano

Esta es una simple API de consulta de videos on-line y grabaciones.


## Videos [/videos]

### Listado de videos [GET /videos]

Permite obtener una lista de los videos grabados.
 
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
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=1",
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
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=2",
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
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=3",
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
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=4",
                            "idCamara": "Cam_01"
                                     }
                    }
                          ]
                 }
             ] 

### Búsqueda de videos [GET /videos/busqueda?fechaGrabacion=fechaGrabacion&sort=-id]

Permite la búsqueda de videos grabados.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Videos": [
                    {
                            "Video": {
                            "id": 8,
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
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=1",
                            "idCamara": "Cam_03"
                                     }
                    },
                     {
                            "Video": {
                            "id": 7,
                            "inicioTransmisión": "14:52:00",
                            "finTransmisión": "14:56:55",
                            "fechaGrabación": "2015-08-01",
                            "horaGrabación": "14:57:02",
                            "formatoCompresión": "XviD",
                            "formato": "AVI",
                            "factorCalidad": "Alta",
                            "brillo": 25,
                            "color": "rgba(0,0,0)",
                            "contraste": 25,
                            "urlDescarga": "http://www.ejemplovideo.com/videos/?video=2",
                            "idCamara": "Cam_01"
                                     }
                    }
                          ]
                 }
             ] 


### Reproducción de video [GET /videos/{id}/reproduccion/]

Permite la reproducción de grabaciones de video.

+ Request (application/json)
  
+ Parameters
  + id (required, int)

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

### Captura de imágenes de video [GET /videos/{id}/?capturas=1]

Permite obtener una determinada cantidad de imágenes de un video grabado.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Imagenes": [
                    {
                            "Imagen": {
                            "id": 12,
                            "formato": "PNG",
                            "Resolución": "1024x768"
                                     }
                    }
                            ]
                }
             ] 


## Cámaras [/camaras]

 
### Listado de cámaras [GET /camaras]

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
                            "ip": "192.168.1.22",
                            "ubicacion": "Agustinas 288922"
                                     }
                    },
                     {
                            "camara": {
                            "id": "Cam_02",
                            "factorCalidad": "Alta",
                            "brillo": 42,
                            "color": "rgba(0,0,0)",
                            "contraste": 10,
                            "ip": "192.168.1.23",
                            "ubicacion": "Ahumada 224466"
                                     }
                    }
                          ]
                 }
             ] 

### Cambiar calidad de transmisión [PUT /camaras/{?id}]

Permite modificar la calidad de transmisión de una cámara.

+ Request (application/json)
  

    + Body
    
            {
                 "Transmisión_on-line": {
                            "factorCalidad": "Alta",
                            "brillo": 10,
                            "color": "rgba(0,0,0)",
                            "contraste": 13
                            }
            }

+ Response 201 (application/json)

    + Body

            {
                "Mensaje": "Calidad de transmisión modificada correctamente!"
            }            

### Búsqueda de cámaras cercanas [GET /camaras/busqueda/{?ubicacion}]

Permite listar las cámaras cercanas a una ubicación.
 
+ Request (application/json)
  
+ Parameters
  + ubicacion (required, string)

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
                            "ip": "192.168.1.22",
                            "ubicacion": "Ahumada 224466"
                                     }
                    }
                          ]
                 }
             ] 


## Transmisiones [/transmisiones]     

### Listado de transmisiones de video [GET /transmisiones]

Listado de transmisiones de video en línea.

+ Response 200 (application/json)

     + Body
    
              {
                 "Transmisiones": [
                          {
                              "Transmisión_on-line": {
                              "id": 8,
                              "urlTransmision": "http://www.ejemplotransmision.com/transmision/?idCamara=Cam_01&idTransmision=8",
                              "factorCalidad": "Alta",
                              "brillo": 18,
                              "color": "rgba(0,0,0)",
                              "contraste": 22,
                              "inicioTransmisión": "11:55:40",
                              "idCamara": "Cam_01"
                                                     }
                           },
                           {
                              "Transmisión_on-line": {
                              "id": 9,
                              "urlTransmision": "http://www.ejemplotransmision.com/transmision/?idCamara=Cam_02&idTransmision=9",
                              "factorCalidad": "Alta",
                              "brillo": 15,
                              "color": "rgba(0,0,0)",
                              "contraste": 30,
                              "inicioTransmisión": "16:55:40",
                              "idCamara": "Cam_02"
                                                     }
                           }
                                   ]
                }

### Transmisión de video [GET /transmisiones/{?id}]

Permite la transmisión de video on-line.

+ Request (application/json)
  
+ Parameters
  + id (required, int)
  
 
+ Response 200 (application/json)

    + Body
    
            {
                "Transmisión_on-line": 
                    {
                      "id": 5,
                      "urlTransmision": "http://www.ejemplotransmision.com/transmision/?idCamara=Cam_02&idTransmision=8",
                      "factorCalidad": "Alta",
                      "brillo": 18,
                      "color": "rgba(0,0,0)",
                      "contraste": 22,
                      "inicioTransmisión": "11:55:40",
                      "idCamara": "Cam_02"
                    }
                               
             }
  
  
### Captura de imágenes de transmisiones en línea [GET /transmisiones/{id}/?capturas=2]

Permite obtener una determinada cantidad de imágenes de una transmisión en línea.
 
+ Response 200 (application/json)

    + Body

             [
                {
                "Imagenes": [
                    {
                            "Imagen": {
                            "id": 1,
                            "formato": "PNG",
                            "Resolución": "1024x768"
                                     }
                    },
                     {
                            "Imagen": {
                            "id": 2,
                            "formato": "PNG",
                            "Resolución": "1024x768"
                                     }
                    }
                          ]
                 }
             ] 
  
             


   