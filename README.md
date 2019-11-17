# Concurrently Nodemon
StackOverflow [answer for question][soq]

## Using [concurrently][concurrently]
Using concurrently to run two instances of nodemon simultaneously

check [package.json](package.json)
```json
{
  "scripts": {
    "serve": "nodemon index.js",
    "logs": "nodemon logs.js",
    "start": "concurrently \"npm:serve\" \"npm:logs\""
  },
  "devDependencies": {
    "concurrently": "^5.0.0",
  }
}
```

## Using VSCode compounds
Example of runnung multiple debug servers using compounds. Check [launch.json](.vscode/launch.json)


## Result

```sh
> concurrently "npm:serve" "npm:logs"

[serve] 
[serve] > so-concurrently@1.0.0 serve so-concurrently
[serve] > nodemon index.js
[serve] 
[logs] 
[logs] > so-concurrently@1.0.0 logs so-concurrently
[logs] > nodemon logs.js
[logs] 
[logs] [nodemon] 1.19.4
[logs] [nodemon] to restart at any time, enter `rs`
[logs] [nodemon] watching dir(s): *.*
[logs] [nodemon] watching extensions: js,mjs,json
[logs] [nodemon] starting `node logs.js`
[serve] [nodemon] 1.19.4
[serve] [nodemon] to restart at any time, enter `rs`
[serve] [nodemon] watching dir(s): *.*
[serve] [nodemon] watching extensions: js,mjs,json
[serve] [nodemon] starting `node index.js`
[logs] Example app listening on port 4000!
[serve] Example app listening on port 3000!
[serve] [nodemon] restarting due to changes...
[logs] [nodemon] restarting due to changes...
[logs] [nodemon] starting `node logs.js`
[serve] [nodemon] starting `node index.js`
[logs] Example app listening on port 4000!
[serve] Example app listening on port 3000!
```

[soq]: https://stackoverflow.com/questions/58898386/how-to-run-multiple-js-servers/58898609
[concurrently]: https://www.npmjs.com/package/concurrently