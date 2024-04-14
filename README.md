# api-ecommerce

Api encargada de listar facturas asociadas a un cliente:



## Uso básico
```http
GET /findCustomerInvoice/{id}/{date}    : Obtiene información de cliente y la factura filtrada por id y fecha
GET /findCustomer/{id}                  : Obtiene información del cliente en base a su id
GET /findInvoiceItem/{id}               : Obtiene información de la factura en base a su id
```


### Consulta informacion de  factura y cliente

GET /findCustomerInvoice/{id}/{date}

Respuesta:

```json
{
  "customer": {
    "id": "mgonzalez",
    "name": "Juan",
    "lastName": "González",
    "age": 42,
    "phone": "56225831245",
    "address": "Calle Principal",
    "rol": [
      {
        "id": 1,
        "value": "COMERCIAL"
      }
    ]
  },
  "invoiceitem": {
    "id": 4,
    "date": "2024-03-24",
    "products": [
      {
        "id": 1,
        "description": "Producto 5",
        "unitPrice": 10.000,
        "quantity": 5
      },
      {
        "id": 2,
        "description": "Producto 6",
        "unitPrice": 5.000,
        "quantity": 5
      }
    ]
  },
  "total": 75.000,
  "discount": 0.03,
  "totalWithDiscount": 72.75000
}
```


### Consulta informacion de cliente

GET /findCustomer/{id}

Respuesta:

```json
{
    "id": "frojas",
    "name": "Francica",
    "lastName": "Rojas",
    "age": 28,
    "phone": "+56225830430",
    "address": "Calle 123",
    "rol": [
        {
            "id": 1,
            "value": "ADMIN"
        },
        {
            "id": 2,
            "value": "USERR"
        }
    ]
}

### Consulta informacion de factura

GET /findInvoiceItem/{id}

Respuesta:

```json
{
    "id": 1,
    "date": "2024-03-23 14:25",
    "products": [
        {
            "id": 1,
            "description": "Producto 1",
            "unitPrice": 10.000,
            "quantity": 5
        },
        {
            "id": 2,
            "description": "Producto 2",
            "unitPrice": 10.000,
            "quantity": 5
        }
    ]
}