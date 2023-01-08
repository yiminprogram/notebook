# Shell Script

## Declare Shell

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

```bash
VARIABLE=Hello
VARIABLE1="Hello World"
VARIABLE2='Hello World'
```

## Use Variable

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

## If - Else

```bash
VARIABLE="APPLE"
if [ $VARIABLE = "APPLE" ]
then
	echo "You are APPLE"
else
	echo "You are not APPLE"
fi
```

## If - else if - else

```bash
VARIABLE="APPLE"

if [ $VARIABLE = "APPLE" ]
then
	echo "You are APPLE"
elif [ $VARIABLE = "PEN" ]
then
	echo "You are PEN"
else
	echo "You are not APPLE"
fi
```

## Conditional

- `-eq` equal
- `-ne` not eqaul
- `-gt` greater than
- `-ge` greater than or equal
- `-lt` less than
- `-le` less than or equal

```bash
NUM1=5
NUM2=5

if [ $NUM1 -gt $NUM2 ]
then
	echo "$NUM1 greater than $NUM2"
else
	echo "$NUM1 less than $NUM2"
fi
```

## File Conditional

- `-d` file is directory
- `-e` file is exist

```bash
FILE="abc.txt"
if [ -e $FILE ]
then
	echo "$FILE exist"
else
	echo "$FILE not exist"
fi

FOLDER="folder"
if [ -d $FOLDER ]
then
	echo "$FOLDER is directory"
else
	echo "$FOLDER is not directory"
fi
```

# Case Statement

```bash
read -p "Are you have an apple? Y/N " ANSWER
case $ANSWER in
	[yY] | [yY][eE][sS])
		echo "You have an apple"
		;;
	[nN] | [nN][oO])
		echo "You don't have an apple"
		;;
	*)
		echo "Please enter yes(y) or no(y)"
		;;
esac
```

# For Loop

```bash
NAMES="Apple Pen Pineapple"
for NAME in $NAMES
do
	echo "Hello $NAME"
done
```

# For Loop Rename File

```bash
FILES=$(ls *.txt)
RENAME="new"

for FILE in $FILES
do
	echo "Rename File ... $FILE to new-$FILE"
	mv $FILE $RENAME-$FILE
done
```
