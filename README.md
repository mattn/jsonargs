# jsonargs

xargs for JSON stream

## Usage

### input data

```
{ "name": "foo1", "value": "bar1" }
{ "name": "foo2", "value": "bar2" }
{ "name": "foo3", "value": "bar3" }
{ "name": "foo4", "value": "bar4" }
{ "name": "foo5", "value": "bar5" }
```

### sequencial execute

```
$ cat input.dat | jsonargs echo '{{.name}}' '{{.value}}'
foo1 bar1
foo2 bar2
foo3 bar3
foo4 bar4
foo5 bar5
```

### handle array

If you want to handle input data as array, please specify `-a` flag.

```
[
  { "name": "foo1", "value": "bar1" },
  { "name": "foo2", "value": "bar2" },
  { "name": "foo3", "value": "bar3" },
  { "name": "foo4", "value": "bar4" },
  { "name": "foo5", "value": "bar5" }
]
```

```
$ cat input.dat | jsonargs -a echo '{{.name}}' '{{.value}}'
foo1 bar1
foo2 bar2
foo3 bar3
foo4 bar4
foo5 bar5
```

## Installation

```
go get github.com/mattn/jsonargs
```

## License

MIT

## Author

Yasuhiro Matsumoto (a.k.a. mattn)
