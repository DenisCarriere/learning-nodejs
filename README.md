# Switching from Python to NodeJS

Here are a collection of examples that show you how I currently program in Python with the NodeJS equivalent.

Topics I'll be covering:

- Read & Write files
- Read JSON
- Read YAML
- Save to JSON
- Making a HTTP request

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
#### Core Modules
```nodejs
var fs = require('fs'),
    rl = require('readline');
```
#### Read File
```nodejs
var data = fs.readFileSync('example.txt', 'utf-8')
console.log(data.toString())
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