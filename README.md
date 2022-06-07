
## cubejs trino driver

> fork from cube.js official and change for support  trino

## Usage

* .env

```code
CUBEJS_DB_HOST=localhost
CUBEJS_DB_USER=admin
CUBEJS_DB_CATALOG=elasticsearch
CUBEJS_DB_SCHEMA=myes
CUBEJS_WEB_SOCKETS=true
CUBEJS_DEV_MODE=true
```


* cube.js

```code
const {PrestoDriver,PrestodbQuery} = require("trino-cubejs-driver")
module.exports = {
    dialectFactory: (dataSource) => {
        // need config  datasource  for multitenant env
        return PrestodbQuery
    },
    dbType: ({ dataSource } = {}) => {
        return "trino"
    },
    driverFactory: ({ dataSource } = {}) => {
        return new PrestoDriver({})
    }
};
```