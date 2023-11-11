# validator-data

create similiar schema (reqCLientType) and use validtor-data as a middeleware

```
const validatedata = require('validator-data');

```

```
example schema definition

const reqCLientType = {
  routes: {
    sourcePath: { type: 'string', required: true },
    destinationUrl: { type: 'string', required: true },
  },
  clients: {
    clientId: { type: 'string', required: true },
    limit: { type: 'number', required: false },
    seconds: { type: 'number', required: false },
  },
};
```

Use as middleware

```
app.post('/configure', validatedata(reqCLientType), async (req, res) => {
  return res.sendStatus(200);
});

```

```

example req.body

{
      "routes": [
        {
          "sourcePath": "/items",
          "destinationUrl": "https://example.com/items"
        }
      ],
      "clients": [
        {
          "clientId": "1234",
          "limit": 1000,
          "seconds": 10
        },{
            "clientId": "1234",
          "limit": 1000,
          "seconds": 10
        }
      ]
    }
```

returns status code 400 if the validation schema not match with the request object
