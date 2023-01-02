# Shell Script

## Declare shell

find shell `which bash`

```bash
#! /bin/bash
```

## Comment

```bash
# I am comment
```

## Print

```bash
echo Hello World
```

## Variable

name convention

1. uppercase
2. letters, numbers, underscores

if string has space, need to use "" or ''
before or after `=` and do not add space

```bash
VARIABLE=Hello
VARIABLE1="Hello World"
VARIABLE2='Hello World'
```

## Use variable

```bash
NAME=APPLE
echo Hello, $NAME
echo Heloo, ${NAME}
```

## User input

```bash
read -p "What's your name : " NAME
echo Hello, $NAME
```

## If

```bash
NAME=APPLE
if [ $NAME == "APPLE" ]
then
  echo HEllo $NAME
fi
```
