# sy-node-mysql
a simple mysql orm

[![npm package](https://nodei.co/npm/sy-node-mysql.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/sy-node-mysql/)


### Getting Started
```shell
$ npm install sy-node-mysql --save
```


### Example

```javascript
const MySql = require('sy-node-mysql');
const config = require('./example/config.json');
const mysql = new MySql(config);

async function getItems() {
    const sql = `select * from db_one.person`;
    const opts = {
        where: ['id = ?'],
        params: [100]
    };
    const res = await mysql.exec(sql, opts, 'db_one');
    return res[0];
}

getItems().then(data => {
    console.log(data);
});
```
