# RESTAPI ClickImagine
API for Click Imagine

## Collections
1. USER TABLE
2. IMAGECOLLECTION TABLE


## List User records

### EXAMPLE REQUEST
curl "https://api.airtable.com/v0/{{base}}/User?maxRecords=3&view=Grid%20view" \  
  -H "Authorization: Bearer YOUR_API_KEY"

### EXAMPLE RESPONSE
```json
{
    "records": [
        {
            "id": "recjQcdpzC5TcduQx",
            "fields": {
                "FirstName": "Hidayt",
                "LastName": "Rahman",
                "MobileNo": "12345",
                "Address": "Noida"
            },
            "createdTime": "2020-07-14T20:26:23.000Z"
        },
        {
            "id": "recM8xyFP5GrH3A1C",
            "fields": {
                "FirstName": "Rahul",
                "LastName": "Anand",
                "MobileNo": "7387",
                "Address": "Dubai"
            },
            "createdTime": "2020-07-14T20:26:23.000Z"
        },
        {
            "id": "recKolHLfb6G1dijD",
            "fields": {
                "FirstName": "s"
            },
            "createdTime": "2020-07-14T20:26:23.000Z"
        }
    ],
    "offset": "recKolHLfb6G1dijD"
}
```
 
## Retrieve a User record

### EXAMPLE REQUEST
curl https://api.airtable.com/v0/{{base}}/User/recjQcdpzC5TcduQx \  
  -H "Authorization: Bearer YOUR_API_KEY"

### EXAMPLE RESPONSE
```json
{
    "id": "recjQcdpzC5TcduQx",
    "fields": {
        "FirstName": "Hidayt",
        "LastName": "Rahman",
        "MobileNo": "12345",
        "Address": "Noida"
    },
    "createdTime": "2020-07-14T20:26:23.000Z"
}
```

## Create User records

### EXAMPLE REQUEST
curl -v -X POST https://api.airtable.com/v0/{{base}}/User \  
  -H "Authorization: Bearer YOUR_API_KEY" \  
  -H "Content-Type: application/json" \  
  ```json
  --data '{
  "records": [
    {
      "fields": {
        "FirstName": "Hidayt",
        "LastName": "Rahman",
        "MobileNo": "12345",
        "Address": "Noida"
      }
    },
    {
      "fields": {
        "FirstName": "Rahul",
        "LastName": "Anand",
        "MobileNo": "7387",
        "Address": "Dubai"
      }
    }
  ]
}'
```

## Update User records

### EXAMPLE REQUEST
curl -v -X PATCH https://api.airtable.com/v0/{{base}}/User \  
  -H "Authorization: Bearer YOUR_API_KEY" \  
  -H "Content-Type: application/json" \  
```json  
  --data '{
  "records": [
    {
      "id": "recjQcdpzC5TcduQx",
      "fields": {
        "FirstName": "Hidayt",
        "LastName": "Rahman",
        "MobileNo": "12345",
        "Address": "Noida"
      }
    },
    {
      "id": "recM8xyFP5GrH3A1C",
      "fields": {
        "FirstName": "Rahul",
        "LastName": "Anand",
        "MobileNo": "7387",
        "Address": "Dubai"
      }
    }
  ]
}'
```

## Delete User records
### EXAMPLE REQUEST
curl -v -X DELETE https://api.airtable.com/v0/{{base}}/User \  
  -H "Authorization: Bearer YOUR_API_KEY" \  
  -G \  
  --data-urlencode 'records[]=recjQcdpzC5TcduQx' \  
  --data-urlencode 'records[]=recM8xyFP5GrH3A1C'  
### EXAMPLE RESPONSE
```json
{
    "records": [
        {
            "id": "recjQcdpzC5TcduQx",
            "deleted": true
        },
        {
            "id": "recM8xyFP5GrH3A1C",
            "deleted": true
        }
    ]
}
```