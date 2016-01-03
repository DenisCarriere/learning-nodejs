# Switching from Python to NodeJS

Here are a collection of examples that show you how I currently program in Python with the NodeJS equivalent.

Topics I'll be covering:

- Opening a file
- Reading a JSON
- Reading YAML
- Saving a JSON
- Making a HTTP request

Libraries I'll be exploring

| NodeJS      | Python    |
|:------------|:----------|
| Express     | Flask     |
| Benchmark   |           |
| Turf        | GDAL      |
| Tape        | pytest    |
|             | Requests  |

## Opening a File

### Python
#### Reading entire file
```python
with open('example.txt') as data:
    print data.read()
```

### Reading multiple lines
```
with open('example.txt') as data:
    for line in data.readlines():
        print line.strip()
```

### NodeJS
#### Reading entire file
```nodejs
var fs = require('fs');
var data = fs.readFileSync('example.txt')
console.log(data.toString())
```