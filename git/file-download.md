How to download a file from github.

Using the wget and curl commands, type "? raw = true" after the URL.

## Using wget
```
$ wget -O log.md https://github.com/jhhwang4195/TIL/blob/master/git/log.md?raw=true
```

## Using curl
```
$ curl -LJ -o log.md https://github.com/jhhwang4195/TIL/blob/master/git/log.md?raw=true
```
