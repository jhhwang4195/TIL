## To set an environment variable once, use the export command in the prompt
```
$ export GITHUB_USERNAME=jhhwang4195
```

## To set an environment variable everytime, use the export command in the .bashrc fil
```
$ vi ~/.bashrc
export GITHUB_USERNAME=jhhwang4195
$ source ~/.bashrc
```

## To see an environment variable
```
$ printenv GITHUB_USERNAME
$ echo $GITHUB_USERNAME
```
