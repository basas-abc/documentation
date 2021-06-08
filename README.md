ABCD API v1.0
-------------

----------

**Contenido:**

- Instalación

- Endpoints

  - Account
  - SPEI
  - Destination Account
  - Servicios Bacarios

- Catalogos

----------

## información importante:

**Para poder hacer uso del API es necesario contar un perfil Mexicano.**

    - Nombre
    - Apellidos
    - CURP
    - Entidad federal del país

## Instalar colección en Postman:

1. Crea un Entorno Sandbox de ABCD Sandbox.
2. Descarga ABCD_colection_postman.json.
5. Importar la Collecion [ABCD_colection_postman.json](https://github.com/abc-capital-digital/documentation/blob/b4dab24ab4fc97b0ea171ac4a056654ae24d2e92/ABCD.postman_collection.json) en postman.
6. Posicionar el Entorno Sandbox de ABCD Sandbox.
7. Revisar que en Create Account Endpoint Headers el campo x-api-key incluya la API Key de Sandbox.

### Host:

    Sandbox: POST [https://sandbox.abc4digital.com/[fintech]/api](https://sandbox.abc4digital.com)
    Production: POST [https://production.abc4digital.com/[fintech]/api](https://sandbox.abc4digital.com)

### API Key:

    Sandbox | Production : ABC Capital proporcionara para ambientes Sandbox y Production.

### Headers

    x-api-key: [API KEY]
    Content-Type:application/json

----------

## Account

**Description:**

Apertura de una cuenta Nivel 2 en ABC Capital, Galileo y envío de Documentación para KYC.

![enter image description here][2]

  [2]: https://images-shared-team.s3.amazonaws.com/Service+single+SignUp-last.jpeg

### Register Simple

#### Service:

    /account/register

#### Request:

    {
        "paternalName": "[Paternal Name]",
        "maternalName": "[Maternal Name]",
        "firstName": "[Name]",
        "birthDate": 19631231,
        "birthPlace": "14",
        "gender": "M",
        "curp": "[CURP]",
        "telephone": 3325418120,
        "email": "test@hotmail.com",
        "streetAddress": "salaverry",
        "premise": "1123",
        "subPremise": "1A",
        "postalCode": "07310",
        "neighborhood": "15121547603120",
        "numberId": "2898403",
        "dateExpeditionNumberId": 20130120,
        "dateExpirationNumberId": 20211230,
        "channel": 00,
        "rfc": null,
        "idSign": "20210510160506"
    }

#### Response:

    {
       "status": "success",
       "idClient": "1000087634",
       "code": "00"
    }

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|SOURCE FORM|SOURCE OCR|SOURCE DEVICE|
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
|paternalName|35|alphanumeric|mandatory|-|Apellido Paterno|✔️|-|-|
|maternalName|35|alphanumeric|mandatory|-|Apellido Materno|✔️|-|-|
|firstName|35|alphanumeric|mandatory|-|Nombres|✔️|-|-|
|birthDate|8|numeric|mandatory|AAAAMMDD|Fecha de Nacimiento|✔️|-|-|
|birthPlace|2|alphanumeric|mandatory|-|Lugar de Nacimiento|✔️|-|-|
|gender|1|alphanumeric|mandatory|F, M|Genero|✔️|-|-|
|curp|18|alphanumeric|mandatory|-|CURP|✔️|-|-|
|telephone|10|numeric|mandatory|-|Número de Celular|✔️|-|-|
|email|50|alphanumeric|mandatory|-|Correo electrónico|✔️|-|-|
|streetAddress|35|alphanumeric|mandatory|-|Calle|✔️|-|-|
|premise|35|alphanumeric|mandatory|-|No. Exterior|✔️|-|-|
|subPremise|35|alphanumeric|optional|-|No. Interior|✔️|-|-|
|postalCode|5|alphanumeric|mandatory|-|Código Postal|✔️|-|-|
|neighborhood|15|alphanumeric|mandatory|15121547603120|Id de la Colonia, Se obtiene del Servicio de /catalog/neighborhood|✔️|-|-|
|numberId|20|alphanumeric|mandatory|-|Número de Identificación|-|✔️|-|
|dateExpeditionNumberId|8|numeric|mandatory|AAAAMMDD|Fecha de Expedición de la Identificación|-|✔️|-|
|dateExpirationNumberId|8|numeric|mandatory|AAAAMMDD|Fecha de Vencimiento de la Identificación|-|✔️|-|
|channel|2|numeric|mandatory|00|Número Asignado por ABC|Hide|-|-|
|rfc|13|alphanumeric|optional|-|RFC|-|✔️|-|
|idSign|14|numeric|mandatory|-|Codigo para confirmacion de firma|Hide|-|-|

### KYC

#### Service:

    /account/kyc

#### Request:

    {
        "idClient": 1000000000,
        "paternalName": "[Paternal Name]",
        "maternalName": "[Maternal Name]",
        "firstName": "[Name]",
        "curp": "[CURP]",
        "idFront": "[base64]",
        "idReverse": "[base64]",
        "proofAddress": "[base64]",
        "selfie": "[base64]"
    }

#### Response:

    {
       "status": "success"
    }

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|SOURCE FORM|SOURCE OCR|SOURCE DEVICE|
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
|idClient|15|alphanumeric|optional|-|Identificador de Cliente|Hide|-|-|
|paternalName|35|alphanumeric|mandatory|-|Apellido Paterno|✔️|-|-|
|maternalName|35|alphanumeric|mandatory|-|Apellido Materno|✔️|-|-|
|firstName|35|alphanumeric|mandatory|-|Nombres|✔️|-|-|
|curp|18|alphanumeric|mandatory|-|CURP|✔️|-|-|
|identification|-|alphanumeric|mandatory|-|Credencial del INE|-|✔️|-|
|proofAddress|-|alphanumeric|mandatory|-|Comprobante de Domicilio|-|✔️|-|
|selfie|-|alphanumeric|mandatory|-|Prueba de Vida|-|✔️|-|

### Create Account

#### Service:

    /account/create
    
#### Request:

    {
        "idClient": 1000000000,
        "paternalName": "",
        "maternalName": "",
        "firstName": "",
        "telephone": 3325418120,
        "geolocation": "10°','-60",
        "channel": 00,
        "idSign": "20210415150355"
    }

#### Response:

    {
        "status": "success",
        "idClient": 1000000000,
        "idAccount": 00204593126,
        "clabe": 002010077777777779,
        "prn": 14027000005,
        "code": "00"
    }

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|SOURCE FORM|SOURCE OCR|SOURCE DEVICE|
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
|idClient|15|alphanumeric|optional|-|Identificador de Cliente|Hide|-|-|
|paternalName|35|alphanumeric|mandatory|-|Apellido Paterno|✔️|-|-|
|maternalName|35|alphanumeric|mandatory|-|Apellido Materno|✔️|-|-|
|firstName|35|alphanumeric|mandatory|-|Nombres|✔️|-|-|
|telephone|10|numeric|mandatory|-|Número de Celular|✔️|-|-|
|geolocation|40|alphanumeric|mandatory|44.244167,7.769444|Datos del dispositivo al momento de instruir la transacción|-|-|✔️|
|channel|2|numeric|mandatory|00|Número Asignado por ABC|Hide|-|-|
|idSign|14|numeric|mandatory|-|Codigo para confirmacion de firma|Hide|-|-|

### Sign Terms & Condition and Geolocation

#### Service:

    /account/sign/privacy
    
#### Request:

    {
        "idDevice": "D5C5F59A-6183-4F22-B9F1-D26C0A46276E",
        "sendTo": "3325418120",
        "idCompany": "4AD8A2A7-57A4-4731-B0ED-37EE5B17D1EF"
    }

#### Response:

    {
        "idSign": "20210527121455",
        "keygen": "Su codigo de verificacion temporal es : 78460827"
    }

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|SOURCE FORM|SOURCE OCR|SOURCE DEVICE|
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
|idDevice|-|alphanumeric|mandatory|-|-|Hide|-|-|
|sendTo|10|numeric|mandatory|3325418120|Numero telefónico del cuentahabiente|✔️|-|-|
|idCompany|-|alphanumeric|mandatory|-|-|Hide|-|-|

### Sign Contract

#### Service:

    /account/sign/contract
    
#### Request:

    {
        "idDevice": "D5C5F59A-6183-4F22-B9F1-D26C0A46276E",
        "sendTo": "3325418120",
        "idCompany": "4AD8A2A7-57A4-4731-B0ED-37EE5B17D1EF"
    }

#### Response:

    {
        "idSign": "20210527121455",
        "keygen": "Su codigo de verificacion temporal es : 78460827"
    }

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|SOURCE FORM|SOURCE OCR|SOURCE DEVICE|
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
|idDevice|-|alphanumeric|mandatory|-|-|Hide|-|-|
|sendTo|10|numeric|mandatory|3325418120|Numero telefónico del cuentahabiente|✔️|-|-|
|idCompany|-|alphanumeric|mandatory|-|-|Hide|-|-|

### Confirm Signature

#### Service:

    /account/sign/confirm
    
#### Request:

    { 
        "idSign": "20210527121620",
        "idDevice": "D5C5F59A-6183-4F22-B9F1-D26C0A46276E", 
        "sendTo": "3325418120",
        "keygen": "14443499"
    }

#### Response:

    {
        "signed": "success"
    }

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|SOURCE FORM|SOURCE OCR|SOURCE DEVICE|
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
|idSign|14|numeric|mandatory|20210527121620|Codigo para confirmacion de firma|Hide|-|-|
|idDevice|-|alphanumeric|mandatory|-|-|Hide|-|-
|sendTo|10|numeric|mandatory|3325418120|Numero telefónico del cuentahabiente|✔️|-|-|
|keygen|8|numeric|mandatory|14443499|Código de confirmación de 8 dígitos que llega en un SMS|Hide|-|-|

### Account Detail

#### Service:

    /account/detail
    
#### Request:

    {
        "idAccount": "00302020344",
        "channel": 00
    }

#### Response:

    {
        "idAccount": 00302020344,
        "description": "ABC Cuenta de Ahorro",
        "balance": "200246.9",
        "blockedBalance": "84000",
        "accountBalance": "284246.9",
        "clabe": "138580003020203441"
    }

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|SOURCE FORM|SOURCE OCR|SOURCE DEVICE|
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
|idAccount|11|alphanumeric|mandatory|00302020344|Número Asignado por ABC|Hide|-|-|
|channel|2|numeric|mandatory|00|Número Asignado por ABC|Hide|-|-|

### Exceptions and Errors

#### Response

    {
        "status": "exception",
        "code": 01,
        "message": "firma incorrecta",
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


## Movements
----------

**Description:**

Todo lo relacionado a la informacion de la Consulta de movimientos en la Cuenta.

### Movements Pending

#### Service:

    /account/movements/pending
    
#### Request:

    {
        "idAccount": "00302020344",
        "channel": 00
    }

#### Response:

    {
        "originAccount": "00302020344",
        "reference": "ACLK2113300001",
        "dateBlocked": "13/05/2021",
        "amountBlocked": "84000.00"
    }

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|SOURCE FORM|SOURCE OCR|SOURCE DEVICE|
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
|idAccount|11|alphanumeric|mandatory|00302020344|Número Asignado por ABC|Hide|-|-|
|channel|2|numeric|mandatory|00|Número Asignado por ABC|Hide|-|-|

### Movements List

#### Service:

    /account/movements/list
    
#### Request:

    {
        "idAccount": "00302020344",
        "channel": 00,
        "startDate": "2021/03/01",
        "endDate": "2021/03/30"
    }

#### Response:

    [
        {
            "idTransaction": "20210301",
            "shortDescription": "TRANSFERENCIA SPEI RECIBIDO SANTANDER RASTREO: 2021030140014BMOV0000466445930 CONCEPTO: AHORRO REFERENCIA: 210301",
            "reference": "FT16092001367217",
            "post": "20210301",
            "fullDescription": "TRASFERENCIA SPEI RECIBIDO |CUENTA ORIGEN: 014180605669601973| BANCO: SANTANDER| ORDENANTE: SANDRA FIGUEROA ESQUIVEL| CLAVE DE RASTREO: 2021030140014BMOV0000466445930| REFERENCIA: 210301| CONCEPTO: AHORRO|",
            "narrative": "2103011257",
            "pamDebitCard": "0.00",
            "pamCreditCard": "5000.00",
            "runningBalance": "74253.88"
        }
    ]

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|SOURCE FORM|SOURCE OCR|SOURCE DEVICE|
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
|idAccount|11|alphanumeric|mandatory|00302020344|Número Asignado por ABC|Hide|-|-|
|channel|2|numeric|mandatory|00|Número Asignado por ABC|Hide|-|-|
|startDate|10|alphanumeric|mandatory|2021/03/30|Fecha de inicio|Hide|-|-|
|endDate|10|alphanumeric|mandatory|2021/03/30|Fecha final|Hide|-|-|

### Exceptions and Errors

#### Response

    {
        "status": "exception",
        "code":01,
        "message": "firma incorrecta",
    }

**Exceptions Code Http**
    
|CODE|MESSAGE|
|-----------|-----------|
|400|Data no encontrada|
|404|Registro no satisfactorio|

## Transfers
----------

### Reglas de Transferencia

    Aplica:
    Trasferencias ABC a ABC o ABC a Otro

    Casos de Uso:
    - Transferencias Express solo aplican si son menores a $8,000.00 sin importar el Horario.
    - Transferencias Mayores a $8,000.00 hasta $200,000.00 solo pueden hacerse si previamente se registró una cuenta Destino y teniendo en cuenta la restricciones Horarias.
    - El Tiempo de alta de una cuenta destino es de 30 min.
    - Después de las 6:01 PM Horario México solo se pueden hacer trasferencias de $8,000.00, sin o con Cuenta Registrara Hasta las 6:00AM del día Siguiente.

### SPEI

**Description:**

Lanzar transacciones via SPEI (Sistema de Pagos Electrónicos Interbancarios).

### Service:

    /transfers/spei

#### SPEI EXPRESS Request:

    {
        "origin": "1323123312312",
        "destination": "789789789789",
        "amount": "MXN300.00",
        "idBank": "000",
        "typeAccount": "debit",
        "beneficiaryName": "Juanito Perez Perez",
        "concept": "Concepto de Pago",
        "reference": "1234567",
        "channel": 00,
        "geolocation": "44.244167,7.769444",
        "signing": "Important! - See the documentation Encryption signature."
    }
    
#### SPEI SIMPLE Request:

    {
       "origin": "1323123312312",
       "destination": "789789789789",
       "amount": "MXN300.00",
       "concept": "Concepto de Pago",
       "reference": "1234567",
       "channel": 00,
       "geolocation": "44.244167,7.769444",
       "signing": "Important! - See the documentation Encryption signature."
    }

#### SPEI Response

    {
       "status": "success",
       "message": "successful shipment",
       "idTransaction": "12345678",
    }

### F2F

**Description:**

Lanzar transferencias entre cuentas Fintech a Fintech.

### Service:

    /transfers/abc

#### F2F EXPRESS Request:

    {
       "origin": "1323123312312",
       "destination": "789789789789",
       "amount": "MXN300.00",
       "idBank": "000",
       "typeAccount": "debit",
       "beneficiaryName": "Juanito Perez Perez",
       "concept": "Concepto de Pago",
       "reference": "1234567",
       "channel": 00,
       "geolocation": "44.244167,7.769444",
       "signing": "Important! - See the documentation Encryption signature."
    }
    
#### F2F SIMPLE Request:

    {
       "origin": "1323123312312",
       "destination": "789789789789",
       "amount": "MXN300.00",
       "concept": "Concepto de Pago",
       "reference": "1234567",
       "channel": 00,
       "geolocation": "44.244167,7.769444",
       "signing": "Important! - See the documentation Encryption signature."
    }

#### F2F Response

    {
       "status": "success",
       "message": "successful shipment",
       "idTransaction": "12345678",
    }

**Success Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|200|Ok!|
|201|Transaccion en envio|

### Exceptions and Errors

#### Response

    {
        "status": "exception",
        "message": "firma incorrecta",
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
|channel|2|numeric|mandatory|00|Número Asignado por ABC|
|geolocation|40|alphanumeric|mandatory|44.244167,7.769444|Datos del dispositivo al momento de instruir la transacción|
|signing|300|alphanumeric|mandatory|!!!|Important! - See the documentation Encryption signature.|

## Destination Account
----------

**Description:**

Enlace a cuentas destino para transferencias recurrentes entre cuentas.

### Reglas de alta para Cuentas Destino.

    Aplica:
    Trasferencias ABC a ABC o ABC a Otro

    Casos de Uso:
    - El tiempo promedio para el alta de una cuenta destino es no mayor a 30min.

### Link Destination Account

#### Service:

    /account/destination
    
#### Request

    {
       "prn": "foo",
       "account": "12345678",
       "beneficiary": "Juan Perez Perez",
       "rfc": "ABCDE123456",
       "email": "test@abc.com.mx",
       "channel": 00
    }

#### Response

    {
        "status": "success",
        "message": "linked account",
        "idBeneficiary": "12345678"
    }

**Success Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|200|Registro de Beneficiario|

---

### Modify Destination Account

#### Service:

    /account/destination/121412431
    
#### Request

    {
       "prn": "foo",
       "account": "12345678",
       "beneficiary": "Juan Perez Perez",
       "rfc": "ABCDE123456",
       "email": "test@abc.com.mx",
       "channel": 00
    }

#### Response

    {
        "status": "success",
        "message": "modified account",
    }

**Success Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|200|Ok!|

---

### Unlink Destination Account

#### Service:

    /account/destination/1000100581.002180700600012331
    
#### Request

    {
       "channel": 00
    }

#### Response Success

    {
        "status": "success",
        "message": "unlinked account"
    }

**Success Code Http** 

|CODE|CONTEXT|
|-----------|-----------|
|200|Ok!|


### Exceptions and Errors

#### Response

    {
        "status": "error",
        "code":1,
        "message": "firma incorrecta",
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

### Definicion de campos

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|
|-----------|-----------|-----------|-----------|-----------|-----------|
|function|1|character|mandatory|I = new, M = Modify, D = Delete|Digito para identificar la operacion|
|prn|11|alphanumeric|mandatory|-|Identificador de Galileo|
|account*|18|alphanumeric|mandatory|CLABE (18), PHONE (ID BANK  + 10), DEBIT CARD (16)|Cuenta del beneficiario|
|beneficiary|40|alphanumeric|mandatory|-|Nombre del Beneficiario|
|rfc|13|alphanumeric|optional|-|RFC con homoclave del beneficiario|
|email|70|alphanumeric|optional|-|Email de beneficiario|
|channel|2|numeric|mandatory|00|Número Asignado por ABC|

(*) La CLABE bancaria deberá de tener máximo 18 dígitos, el teléfono debe de concatenar el id del banco a dos dígitos más el numero telefónico a diez dígitos, por numero de tarjeta esta tiene que ser máximo 16 dígitos.


## Banking Services
----------

**Description:**

Todos los Servicios bancarios disponibles como Tiempo Aire, Pagos Referenciados, etc.

### TopUps

#### Service:

    /services/topups

#### Response:

    [
        {
            "type": "biller",
            "id": 13690,
            "name": "MovistarPaquetesInternet",
            "biller_type": "MXCell",
            "bill_type": "phone_number",
            "country": "MX",
            "currency": "MXN",
            "requires_name_on_account": false,
            "hours_to_fulfill": 0,
            "account_number_digits": "10",
            "mask": "",
            "can_check_balance": false,
            "supports_partial_payments": false,
            "has_xdata": false,
            "available_topup_amounts": [
                "10.00",
                "30.00",
                "60.00",
                "80.00",
                "120.00",
                "200.00",
                "300.00"
            ],
            "topup_commission": 0
        }
    ]

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
       "id": "002",
       "bank": "bbva",
    }

#### Response

    [
        {
            "id": "002",
            "name": "bbva",
            "type": "foo",
        },
        {
            "id": "003",
            "name": "banorte",
            "type": "foo",
        },
    ]

### Definition of parameters

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|
|-----------|-----------|-----------|-----------|-----------|-----------|
|id|3|alphanumeric|optional|001|Id de la institución|
|bank|10|alphanumeric|optional|banco...nombre|Nombre Corto de la Institución|
    
#### Service:

    /catalog/neighborhood

    
#### Request

    {
        "postalCode": 54760
    }

#### Response Success

    [
        {
            "id": "15121547603120",
            "name": "BOSQUES DE MORELOS"
        },
        {
            "id": "15121547603126",
            "name": "LAGO DE GUADALUPE"
        },
        {
            "id": "15121547603129",
            "name": "PLAN DE GUADALUPE"
        },
        {
            "id": "15121547603134",
            "name": "TRES DE MAYO"
        },
        {
            "id": "15121547607949",
            "name": "HALCON ORIENTE"
        },
        {
            "id": "15121547608484",
            "name": "RINCON DEL BOSQUE"
        }
    ]

### Definition of parameters

|FIELD|SIZE|TYPE|REQUIRED|VALUES|DEFINITION|
|-----------|-----------|-----------|-----------|-----------|-----------|
|postalCode|5|numeric|mandatory|54760|Código Postale|

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
