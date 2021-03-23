ABCD API v1.0
-------------


----------


**Contenido:**

- Instalacion

- Endpoints

  - Enrollement
  - SPEI
  - Destination Account

- Catalogos


----------


## información importante:

**Para poder hacer uso del API es necesario contar un perfil Mexicano.**

    - Nombre
    - Apellidos
    - CURP
    - Entidad federal del país

## Instalar colección en Postman:

1. Crea un Entorno Sandbox de ABCD Sandbox
2. Descarga ABCD_colection_postman.json 
5. Importar la Collecion [ABCD_colection_postman.json](https://github.com/abc-capital-digital/documentation/blob/b4dab24ab4fc97b0ea171ac4a056654ae24d2e92/ABCD.postman_collection.json) en postman
6. Posicionar el Entorno Sandbox de ABCD Sandbox
7. Revisar que en Create Account Endpoint Headers el campo x-api-key incluya la API Key de Sandbox

### Host:

Sandbox: POST [https://nkcmhwm54b.execute-api.us-east-1.amazonaws.com/sandbox](https://nkcmhwm54b.execute-api.us-east-1.amazonaws.com/sandbox)

### API Key:

    Sandbox: HNWlpPY3Xt36w9DZoGoPX8afFcxCrdp4sfsAMb8f

### Headers

    x-api-key: [API KEY]
    x-mock-match-request-body:[true: Mock | false: Sandbox, Production]
    Content-Type:application/json


----------


## Enrollement

**Description:**

Creacion de una cuenta Nivel 2 ABC Capital, Galileo y envio de Documentacion para KYC.
    
### Create Account

#### Service:

    /account/create
    
#### Request
``
    {
        "client": {
            "paternalName": "[Paternal Name]",
            "maternalName": "[Maternal Name]",
            "firstName": "[Name]",
            "birthDate": 19701103,
            "birthPlace": "24",
            "gender": "M",
            "curp": "[CURP]",
            "telephone": 5585774007,
            "email": "test@hotmail.com",
            "streetAddress": "salaverry",
            "premise": "1123",
            "subPremise": "1A",
            "postalCode": "07310",
            "neighborhood": "Bosques de Morelos",
            "numberId": "2898403",
            "dateExpeditionNumberId": 20130120,
            "dateExpirationNumberId": 20210405,
            "channel": 6,
            "rfc": null
        },
        "documents": {
            "idFront": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABMwAAAJHCAIAAADjcV0VAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAAEnQAABJ0Ad5mH3gAAAznSURBVHhe7dcxAQAADMOg+TfdmcgJLrgBAABARDIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAENkefSjf/8iEQNQAAAAASUVORK5CYII=",
            "idReverse": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABMwAAAJHCAIAAADjcV0VAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAAEnQAABJ0Ad5mH3gAAAznSURBVHhe7dcxAQAADMOg+TfdmcgJLrgBAABARDIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAENkefSjf/8iEQNQAAAAASUVORK5CYII=",
            "proofAddress": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABMwAAAJHCAIAAADjcV0VAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAAEnQAABJ0Ad5mH3gAAAznSURBVHhe7dcxAQAADMOg+TfdmcgJLrgBAABARDIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAENkefSjf/8iEQNQAAAAASUVORK5CYII=",
            "selfie": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABMwAAAJHCAIAAADjcV0VAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAAEnQAABJ0Ad5mH3gAAAznSURBVHhe7dcxAQAADMOg+TfdmcgJLrgBAABARDIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAkJFMAAAAMpIJAABARjIBAADISCYAAAAZyQQAACAjmQAAAGQkEwAAgIxkAgAAENkefSjf/8iEQNQAAAAASUVORK5CYII="
        }
    }
``
#### Example Response Json

    {
        "statusCode": 200,
        "message": "Registro de Usuario",
        "idClient": 1000100581,
        "idAccount": "00000564671",
        "CLABE": "138580000005646712",
        "prn": "999900448690"
    }

**Success HTTP list** 

|CODE|MESSAGE|
|-----------|-----------|
|200|Registro en proceso|


**Success EVENT list** 

|CODE|MESSAGE|
|-----------|-----------|
|200|Registro de Usuario|


### Exceptions and Errors

#### Response

    {
        "status":"exception",
        "code":01,
        "message":"firma incorrecta",
    }

**Exceptions Code Http**
    
|CODE|MESSAGE|
|-----------|-----------|
|400|Data no encontrada|
|404|Registro no satisfactorio|

**Exceptions Code EVENT**
    
|CODE|MESSAGE|
|-----------|-----------|
|400|Data no encontrada|
|404|Registro no satisfactorio|

**Status Code**
    
|CODE|MESSAGE|
|-----------|-----------|
|01|ERROR EN JASON DE ENTRADA, ID de Documento no registrado, Error al acceder a la Base de Datos, Relación Cliente y Linea de Negocio inexistente, El Número de Cliente ya existe, Código único de cliente inexistente|
|02|CANAL INVÁLIDO, Error al acceder a la Base de Datos, Canal no registrado en Core Bancario, Longitud de Número de Cliente o CUC inválida, El Número de Cliente o CUC tiene una longitud diferente 10 posiciones, Parámetros Incorrectos|
|03|REFERENCIA ABC-RENAPO INVÁLIDA, Error al cargar el archivo en contenedor, Cadena de Matadato Inválida, No existe el Número de Cliente o CUC, Línea de Negocio Inválida, Ocurrió un error al realizar la consulta en la BD|
|04|CURP’s NO COINCIDEN, Se presentó un error al cargar el archivo, Metadato no existente, Línea de Negocio Inválida, Ocurrió un error al realizar la consulta en la Base de Datos|
|05|NO COINCIDE ALGUNO DE LOS NOMBRES (Nombres, Apellido Paterno, Apellido Materno), ID de Documento inválido (0), Tipo de Documento sin información|
|06|LA FECHA DE NACIMIENTO NO FUE PROPORCIONADA, ID de Documento no registrado, Tipo de Documento inexistente|
|07|PROBLEMAS EN LA CONVERSION DE LA FECHA|
|08|FECHAS DE NACIMIENTO NO COINCIDEN|
|09|NO SE PROPORCIONO LA CURP|
|10|ERROR AL REALIZAR CONSULTA RENAPO|
|11|CONSULTA RENAPO NO EXITOSA|
|12|LA CURP NO SE ENCUENTRA EN LA BASE DE DATOS|
|13|ERROR EN JSON DE ENTRADA|
|14|OCURRIO UN PROBLEMA AL ACCEDER AL CORE|
|15|NO SE REALIZO EL ALTA|

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|
|-----------|-----------|-----------|-----------|-----------|-----------|
|idClient|15|alphanumeric|optional|-|Identificador de Cliente|
|paternalName|35|alphanumeric|mandatory|-|Apellido Paterno|
|maternalName|35|alphanumeric|mandatory|-|Apellido Materno|
|firstName|35|alphanumeric|mandatory|-|Nombres|
|birthDate|8|numeric|mandatory|AAAAMMDD|Fecha de Nacimiento|
|birthPlace|2|alphanumeric|mandatory|-|Lugar de Nacimiento|
|gender|1|alphanumeric|mandatory|F, M|Genero|
|curp|18|alphanumeric|mandatory|-|CURP|
|telephone|10|numeric|mandatory|-|Número de Celular|
|email|50|alphanumeric|mandatory|-|Correo electrónico|
|streetAddress|35|alphanumeric|mandatory|-|Calle|
|premise|35|alphanumeric|mandatory|-|No. Exterior|
|subPremise|35|alphanumeric|mandatory|-|No. Interior|
|postalCode|5|alphanumeric|mandatory|-|Código Postal|
|neighborhood|15|alphanumeric|mandatory|-|Colonia|
|numberId|20|alphanumeric|mandatory|-|Número de Identificación|
|dateExpeditionNumberId|8|numeric|mandatory|AAAAMMDD|Fecha de Expedición de la Identificación|
|dateExpirationNumberId|8|numeric|mandatory|AAAAMMDD|Fecha de Vencimiento de la Identificación|
|channel|2|numeric|mandatory|00|Número Asignado por ABC|
|rfc|13|alphanumeric|mandatory|-|RFC|
|identification|-|alphanumeric|mandatory|-|Credencial del INE|
|proofAddress|-|alphanumeric|mandatory|-|Comprobante de Domicilio|
|selfie|-|alphanumeric|mandatory|-|Prueba de Vida|

## Transactions
----------

### SPEI

**Description:**

Lanzar transacciones via SPEI (Sistema de Pagos Electrónicos Interbancarios).

### SPEI EXPRESS

**NOTA:** Esta modalidad de SPEI, contiene mas datos, que deben ser llenados de forma obligatoria cada que se envie una solicitud.

    destination
    beneficiaryName
    idBank
    typeAccount

**Caracteristicas**

    Monto maximo por cada transaccion: $8,000.00 M.N.
    Cualquier Horario.

#### Request

    {
       "origin":"1323123312312",
       "destination":"789789789789",
       "amount":"MXN300.00",
       "idBank":"000",
       "typeAccount":"debit",
       "beneficiaryName":"Juanito Perez Perez",
       "concept":"Concepto de Pago",
       "reference":"1234567",
       "channel":"001",
       "geolocation":"44.244167,7.769444",
       "signing":"Important! - See the documentation Encryption signature."
    }
    
### SPEI SIMPLE

**IMPORTANTE:** Esta modalidad de SPEI, solo puede ser enviada SI previamente se hizo un LINK DESTINATION ACCOUNT, y los mismos parametros que se enviaron deben de ser enviados, para consultar estos datos, REVISAR el Listado de DESTINATION ACCOUNTS.

    destination

**Caracteristicas**

        Monto maximo por cada transaccion: $200,000.00 M.N.
        Solo aplica el monto maxino antes de las 6:00PM Hora de Mexico.
    
#### Request

    {
       "origin":"1323123312312",
       "destination":"789789789789",
       "amount":"MXN300.00",
       "concept":"Concepto de Pago",
       "reference":"1234567",
       "channel":"001",
       "geolocation":"44.244167,7.769444",
       "signing":"Important! - See the documentation Encryption signature."
    }
 
#### Service:

    /transaction/spei

#### Response Success

    {
       "status":"success",
       "message":"successful shipment",
       "idTransaction":"12345678",
    }

**Success Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|200|Ok!|
|201|Transaccion en envio|



### Exceptions and Errors

#### Response

    {
        "status":"exception",
        "message":"firma incorrecta",
    }


**Exceptions Code Http**
    
|CODE|CONTEXT|
|-----------|-----------|
|400|Problemas con la Data Enviada|
|409|No es posible hacer la transaccion|


### Definicion de parametros

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|
|-----------|-----------|-----------|-----------|-----------|-----------|
|origin|11|numeric|mandatory|-|Identificador unico ABC lo designa automaticamente |
|destination|18|numeric|mandatory|-|Cuenta beneficiaria, de acuerdo a la Longitud del catálogo|
|amount|100|alphanumeric|mandatory|MXN00.00|Monto de retiro|
|idBank|3|numeric|optional|000|Id de la institución beneficiaria|
|beneficiaryName|40|alphanumeric|optional|-|Nombre del Beneficiario|
|typeAccount|10|numeric|optional|3, 10, 40|Tipo de Cuenta de Beneficiario.|
|concept|40|alphanumeric|mandatory|-|Concepto de pago|
|reference|7|numeric|optional|-|Referencia de Pago|
|channel|3|numeric|mandatory|000|Número Asignado por ABC|
|geolocation|40|alphanumeric|mandatory|44.244167,7.769444|Datos del dispositivo al momento de instruir la transacción|
|signing|300|alphanumeric|mandatory|!!!|Important! - See the documentation Encryption signature.|

## Destination Account
----------

**Description:**

Enlace a cuentas destino para transaccionar recurrentes.

### Link Destination Account

#### Service:

    /client/destination
    
#### Request

    {
       "prn":"foo",
       "account":"12345678",
       "beneficiary":"Juan Perez Perez",
       "rfc":"ABCDE123456",
       "email":"test@abc.com.mx",
       "channel":"001"
    }

#### Response Success

    {
        "status":"success",
        "message":"linked account",
        "idBeneficiary":"12345678"
    }

**Success Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|200|Registro de Beneficiario|


---


### Modify Destination Account

#### Service:

    /client/destination/121412431
    
#### Request

    {
       "prn":"foo",
       "account":"12345678",
       "beneficiary":"Juan Perez Perez",
       "rfc":"ABCDE123456",
       "email":"test@abc.com.mx",
       "channel":"001"
    }

#### Response Success

    {
        "status":"success",
        "message":"modified account",
    }

**Success Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|200|Ok!|


---


### Unlink Destination Account

#### Service:

    /client/destination/1000100581.002180700600012331
    
#### Request

    {
       "channel":"001",
    }

#### Response Success

        {
            "status":"success",
            "message":"unlinked account"
        }

**Success Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|200|Ok!|


### Exceptions and Errors

#### Response

    {
        "status":"error",
        "code":1,
        "message":"firma incorrecta",
    }

**Exceptions Code Http**
    
|CODE|CONTEXT|
|-----------|-----------|
|400|Problemas con la informacion de Formulario|

**Status Code**
    
|CODE|MESSAGE|
|-----------|-----------|
|0|PRN no existe|
|1|Longitud de cuenta inválida|
|2|Falta información obligatoria|
|3|Error en email|
|4|Error en canal|
|5|Cliente inexistente|
|6|Error en RFC|
|7|Error en email|
|8|Error en la cuenta beneficiaria|

### Definition of parameters

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|
|-----------|-----------|-----------|-----------|-----------|-----------|
|function|1|character|mandatory|I = new, M = Modify, D = Delete|Digito para identificar la operacion|
|prn|11|alphanumeric|mandatory|-|Identificador de Galileo|
|account|18|alphanumeric|mandatory|CLABE 18, PHONE ID BANK  + 10, DEBIT 16|Cuenta del beneficiario|
|beneficiary|40|alphanumeric|mandatory|-|Nombre del Beneficiario|
|rfc|13|alphanumeric|optional|-|RFC con homoclave del beneficiario|
|email|70|alphanumeric|optional|-|Email de beneficiario|
|channel|3|numeric|mandatory|000|Número Asignado por ABC|

## Encryption signature
---

### Description

Transactions must include the SIGNATURE field to ensure point-to-point security. 

### Requirements:

    - Original string
    - Digital certificate and its corresponding private key (provided by ABC Capital)
    - Public key cryptography algorithms for advanced electronic signature
    - Conversion specifications of the advanced electronic signature to Base64.

### Definition fields:

|  Definition | Parameters |
|-|-|
| Cuenta de Cargo | DEBIT.ACCT.NO |
|MXN+Monto de cargo|DEBIT.AMOUNT|
|Concepto|EXTEND.INFO|
|Cuenta beneficiaria|CTA.EXT.TRANSF|
|Canal|CANAL.ENTIDAD|

### Rules:

the original string MUST NOT contain the character | ("Pipe"), because it is a character to control the separation of the fields individuals.

**correct:**
|00302020345|

**incorrect:**
|Charge account 00302020345|
|00302|0203|45|
|Charge account|

Los espacios en blanco que se presenten dentro de la cadena original serán tratados de la siguiente manera:

 - Se deberán remplazar todos los tabuladores, retornos de carro y
   saltos de línea por espacios en blanco.
 - Acto seguido se elimina cualquier carácter en blanco al principio y
   al final de cada separador | (“pipe” sencillo).
 - Finalmente, toda secuencia de caracteres en blanco intermedias se
   sustituye por un único carácter en blanco.

Toda la cadena original se expresará en el formato de codificación UTF-8

    Cuenta de Cargo|MXNMonto|Concepto|Cuenta beneficiaria|Canal

Los algoritmos utilizados en la generación de la firma digital son los siguientes: 

Algoritmos de digestión: es una función de digestión (o resumen) de un solo sentido tal que para cualquier entrada produce una salida de longitud fija denominada “digestión”. 

Los algoritmos que soporta el sistema son:

 - SHA-256, produce una cadena de 32 bytes (256 bits)
 - (default) SHA-512, produce una cadena de 64 bytes (512 bits)


Cabe señalar que los aplicativos de los participantes deberán tener la funcionalidad necesaria que les permita configurar rápidamente el uso de diferentes algoritmos de digestión. 

 - Algoritmo de firma:  RSA, con el relleno “PKCS1padding”

Para generar la firma digital de una cadena original se deberá emplear el procedimiento de esquema de firma descrito en la sección 8.2 RSASSA-PKCS1-v1_5 del documento RFC 3447 Public-Key Cryptography Standards (PKCS) 1: RSA Cryptography Specifications Version 2.1. 

Al resultado de este procedimiento se le debe aplicar un filtrado en base 64, como se describe en el documento RFC 4648 The Base16, Base32, and Base64 Data Encodings.

La funcionalidad descrita en los estándares antes mencionados se encuentra implementada en los motores criptográficos OpenSSL y Bouncy Castle.

El alfabeto empleado en la codificación base 64 a utilizar se expresa en el siguiente catálogo:

![enter image description here][1]


  [1]: https://shareimagess.s3-us-west-2.amazonaws.com/Picture1.png
  

## Catalogs
----------

**Description:**

Todo lo relacionado a catalogos e informacion establecida por el ABC.

#### Service:

    /catalog/bank

    
#### Request

    {
       "id":"002",
       "bank":"bbva",
    }

#### Response Success
    {
        {
            "id":"002",
            "name":"bbva",
            "type":"foo",
        },
        {
            "id":"003",
            "name":"banorte",
            "type":"foo",
        },
    }

### Definition of parameters

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|
|-----------|-----------|-----------|-----------|-----------|-----------|
|id|3|alphanumeric|optional|001|Id de la institución|
|bank|10|alphanumeric|optional|banco...nombre|Nombre Corto de la Institución|
    
#### Service:

    /catalog/neighborhood

    
#### Request

    {
       "postalCode":"54760"
    }

#### Response Success
    {
        {
            "id":"42344",
            "name":"Bosques de Morelos",
            "city":"Cuautitlan Izcalli",
            "state":"Edomex",
        },
        {
            "id":"034603",
            "name":"3 de Mayo",
            "city":"Cuautitlan Izcalli",
            "state":"Edomex",
        },
    }

### Definition of parameters

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|
|-----------|-----------|-----------|-----------|-----------|-----------|
|postalCode|5|alphanumeric|mandatory|54760|Código Postale|

**Success Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|200|OK!|

**Exception Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|400|Problemas para obtener el catalogo|

## Catalogos fijos:

### Entidades Federativas

| ID | ESTADO                          |
|----|---------------------------------|
| 1  | AGUASCALIENTES                  |
| 2  | BAJA CALIFORNIA                 |
| 3  | BAJA CALIFORNIA SUR             |
| 4  | CAMPECHE                        |
| 5  | COAHUILA DE ZARAGOZA            |
| 6  | COLIMA                          |
| 7  | CHIAPAS                         |
| 8  | CHIHUAHUA                       |
| 9  | CIUDAD DE MEXICO                |
| 10 | DURANGO                         |
| 11 | GUANAJUATO                      |
| 12 | GUERRERO                        |
| 13 | HIDALGO                         |
| 14 | JALISCO                         |
| 15 | MEXICO                          |
| 16 | MICHOACAN DE OCAMPO             |
| 17 | MORELOS                         |
| 18 | NAYARIT                         |
| 19 | NUEVO LEON                      |
| 20 | OAXACA                          |
| 21 | PUEBLA                          |
| 22 | QUERETARO                       |
| 23 | QUINTANA ROO                    |
| 24 | SAN LUIS POTOSI                 |
| 25 | SINALOA                         |
| 26 | SONORA                          |
| 27 | TABASCO                         |
| 28 | TAMAULIPAS                      |
| 29 | TLAXCALA                        |
| 30 | VERACRUZ DE IGNACIO DE LA LLAVE |
| 31 | YUCATAN                         |
| 32 | ZACATECAS                       |

### Tipos de Cuenta

| ID | ESTADO                          | LONGITUD |
|----|---------------------------------|---|
| 0  | CUENTA                  |11|
| 3  | TARJETA DEBITO             |16|
| 10  | CELULAR             |10|
| 40  | CLABE             |18|
