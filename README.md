# validator-data

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

create similiar objects(reqCLientType) and use validtor-data as a middeleware

```const validatedata = require('validator-data');

```

```
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

````app.post('/configure', validatedata(reqCLientType), async (req, res) => {
  return res.sendStatus(200);
});```
````

returns status code 400 if the validation schema not match with the request object
