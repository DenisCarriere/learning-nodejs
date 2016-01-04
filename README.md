# Switching from Python to NodeJS

Here are a collection of examples that show you how I currently program in Python with the NodeJS equivalent.

Topics I'll be covering:

- Read & Write files
- Read JSON
- Read YAML
- Save to JSON
- Making a HTTP request

Documentation:
- https://github.com/lukehoban/es6features

Libraries I'll be exploring

| NodeJS      | Python    |
|:------------|:----------|
| Express     | Flask     |
| Benchmark   |           |
| Turf        | GDAL      |
| Tape        | pytest    |
|             | Requests  |

## Read & Write files

### Python
#### Read File
```python
with open('example.txt') as f:
    print f.read()
```

#### Read Lines
```python
with open('example.txt') as f:
    for line in f.readlines():
        print line.strip()
```

#### Write File
```python
with open('output.txt', 'w') as f:
    f.write('Foo Bar')
```


### NodeJS
#### NPM Modules
```nodejs
var fs = require('fs'),
    readline = require('readline');
```
#### Read File
```nodejs
var data = fs.readFileSync('example.txt', 'utf-8').toString()
console.log(data)
```

#### Read Lines
```nodejs
var rl = readline.createInterface({
    input: fs.createReadStream('example.txt'),
    output: process.stdout
});

rl.on('line', function(line) {
    console.log(line);
});
```

#### Write File
```nodejs
fs.writeFile("output.txt", "Foo Bar")
```

## Loops
### Python
#### For loop
```python
for i in xrange(10):
    print "Hello: ", i
```
#### While Loop
```python
i = 0
while (i < 10):
    print 'Hello: ', i
    i += 1
```

### NodeJS
#### NPM Modules
```
var xrange = require('xrange')
```
#### For loop
```nodejs
for (var i = 0; i < 10; i++) {
    console.log("Hello: ", i);
}
```
#### For Loop - Using xrange

```nodejs
xrange(10).forEach(function(i) {
    console.log('Hello:', i)
});
```
#### While Loop
```nodejs
var i = 0
while (i < 10) {
    console.log("Hello: ", i);
    i++;
}
```