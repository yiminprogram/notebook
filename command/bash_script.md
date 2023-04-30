# bash script

## 基本語法

```sh
# 宣告使用的shell
# 尋找目標shell位置
which shell_name
#! /bin/bash

# 註解:
```

## 列印

```sh
echo Hello World
```

## 變數

```sh
VARIABLE=Hello
VARIABLE1="Hello World"
VARIABLE2='Hello World'
```

### 使用變數

```sh
NAME=APPLE
echo Hello, $NAME
echo Heloo, ${NAME}
```

## 輸入值

```bash
read -p "What's your name : " NAME
echo Hello, $NAME
```

## 條件判斷

### if

```bash
NAME=APPLE
if [ $NAME == "APPLE" ]
then
  echo HEllo $NAME
fi
```

### if - else

```sh
VARIABLE="APPLE"
if [ $VARIABLE = "APPLE" ]
then
	echo "You are APPLE"
else
	echo "You are not APPLE"
fi
```

### if - else if - else

```sh
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

## 條件修飾

- `-eq` equal
- `-ne` not eqaul
- `-gt` greater than
- `-ge` greater than or equal
- `-lt` less than
- `-le` less than or equal

```sh
NUM1=5
NUM2=5

if [ $NUM1 -gt $NUM2 ]
then
	echo "$NUM1 greater than $NUM2"
else
	echo "$NUM1 less than $NUM2"
fi
```

## 檔案狀態

- `-d` file is directory
- `-e` file is exist

```sh
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

## Case 判斷

```sh
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

## 迴圈

```bash
NAMES="Apple Pen Pineapple"
for NAME in $NAMES
do
	echo "Hello $NAME"
done
```

### 迴圈更改檔案名稱

```bash
FILES=$(ls *.txt)
RENAME="new"

for FILE in $FILES
do
	echo "Rename File ... $FILE to new-$FILE"
	mv $FILE $RENAME-$FILE
done
```
