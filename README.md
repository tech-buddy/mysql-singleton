Connecting MySQL database.

example
```ruby
npm install mysql-singleton --save
const mysql_singleton = require('mysql-singleton');
const config = {
  host: 'localhost',
  user: 'root',
  password: '',
  database: 'database'
}
// adding config
mysql_singleton.config(config)

// getting connection using good old callback 
 mysql_singleton.getConnection(function(err,connection){
        // handle err or connection 
});

// using async await 
const connection = await mysql_singleton.getConnectionPromise();

// writing queries 
 connection.query("select * from table",(err,result)=>{
    // handle result or err             
})

// don't for get to realase the connection after it's use
connection.release(); 

```
