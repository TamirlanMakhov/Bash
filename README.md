# Bash
## Оглавление: 

### -[Простые команды](https://github.com/TamirlanMakhov/Bash/edit/main/README.md#Простые-команды) bash: №1-15

### -[Скрипты и условные конструкции](https://github.com/TamirlanMakhov/Bash/edit/main/README.md#Скрипты-и-условные-конструкции): №15-21
----------------------------------------------------------------------------------------------------------------------------------------------

 **Задания:**
 ##### Простые команды

1. Посмотреть где я:

![image](https://user-images.githubusercontent.com/104026290/170882881-d9cd1e82-92c9-4fa6-8a57-c338679fa9d1.png)

2. Создать папку:

![image](https://user-images.githubusercontent.com/104026290/170882910-0a302ac4-9b09-4b6b-9db7-ec706aab4a55.png)

3. Зайти в папку:

![image](https://user-images.githubusercontent.com/104026290/170882933-f93b34ac-2c65-4c06-884e-09b0179ed64e.png)

4. Создать 3 папки. P.S: folder1 был создан еще со 2 задания, поэтому тоже вывелся здесь.

```bash
mkdir -p folder2 folder3 folder4
```
![image](https://user-images.githubusercontent.com/104026290/170882990-72522997-a8ad-4527-898f-eb8cf933a200.png)

5. Зайти в любую папку

![image](https://user-images.githubusercontent.com/104026290/170883028-3101aa80-6c3b-4cab-bb41-d53a558be556.png)

6. Создать 5 файлов (3 txt, 2 json)

![image](https://user-images.githubusercontent.com/104026290/170883043-4e1934e8-fbe9-4adf-907b-fc42906a4a86.png)

7. Создать 3 папки

![image](https://user-images.githubusercontent.com/104026290/170883061-40edb76d-e2ba-4748-8a89-48013d4b1cc8.png)

8. Открыть любой txt файл, написать что-нибудь, сохранить и выйти

![image](https://user-images.githubusercontent.com/104026290/170883141-b6a76eab-2fdf-4fe5-9d2e-948357cb1adf.png)
![image](https://user-images.githubusercontent.com/104026290/170883104-348133f6-5c0d-4253-8c9a-0dbf7d668430.png)


9. Выйти из папки на уровень выше

![image](https://user-images.githubusercontent.com/104026290/170883157-38b5131f-503c-4950-b9ae-bac5b0dc6730.png)

10. Переместить любые файлы

![image](https://user-images.githubusercontent.com/104026290/170883179-47894143-7ca2-4bf8-b60b-2b8892194f1c.png)

11. Скопировать любые 2 файла, которые вы создали, в любую другую папку.

![image](https://user-images.githubusercontent.com/104026290/170883210-fd6e8fbb-2791-42f0-8448-6babea285798.png)

12. Найти файл по имени

![image](https://user-images.githubusercontent.com/104026290/170883226-fdc9cce9-cffd-40e8-a809-ce07db071dd9.png)

13. Посмотреть содержимое в реальном времени

![image](https://user-images.githubusercontent.com/104026290/170883255-bdae57af-c334-4ae8-b659-579f18addf0c.png)

13. Вывести первые несколько строк из файла

![image](https://user-images.githubusercontent.com/104026290/170883269-9600390c-b3d5-4a4b-9664-d12fd126c685.png)

14. Просмотреть содержимое длинного файла

![image](https://user-images.githubusercontent.com/104026290/170883292-df9ef26c-63b4-41cc-b4c1-32895e1fa4af.png)

15. Вывести дату и время

![image](https://user-images.githubusercontent.com/104026290/170883321-a95ecf65-b7c9-481d-b59a-3e9a9a043380.png)

##### Скрипты и условные конструкции

16. Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13
```bash
#!
cd ~/Рабочий\ стол/folder1 #3
mkdir -p ~/Рабочий\ стол/folder2 ~/Рабочий\ стол/folder3 ~/Рабочий\ стол/folder4 #4
cd ~/Рабочий\ стол/folder2 #5
touch ~/Рабочий\ стол/file1.txt ~/Рабочий\ стол/file2.txt ~/Рабочий\ стол/file3.txt ~/Рабочий\ стол/file4.json ~/Рабочий\ стол/file5.jso
mkdir -p ~/Рабочий\ стол/again1 ~/Рабочий\ стол/again2 ~/Рабочий\ стол/again3 #7
ls ~/Рабочий\ стол/again1 #8
mv ~/Рабочий\ стол/file1.txt ~/Рабочий\ стол/file2.txt ~/Рабочий\ стол/file3.txt ~/Рабочий\ стол/file4.json ~/Рабочий\ стол/file5.json ~
```
![image](https://user-images.githubusercontent.com/104026290/170883380-1c5d19cb-12da-45db-be07-7db80141699c.png)

17. Напишите скрипт на bash, который принимает на вход два аргумента и выводит на экран строку следующего вида:
Arguments are: $1=первый_аргумент $2=второй_аргумент
```bash
#!

var1=$1
var2=$2

echo "Arguments are: \$1=$1 \$2=$2"
```

18. Напишите скрипт на bash, который принимает на вход один аргумент (целое число от 0 до бесконечности), который будет обозначать число студентов в аудитории. В зависимости от значения числа нужно вывести разные сообщения. 

Соответствие входа и выхода должно быть таким:
0 -->  No students
1 -->  1 student
2 -->  2 students
3 -->  3 students
4 -->  4 students
5 и больше --> A lot of students

```bash
#!/usr/bin/bash

re='^[0-9]+$'
if ! [[ $1 =~ $re ]] ; then
   exit 1
   
else 
	case $1 in
		0) echo "No students";;
		1) echo "$1 student";;
		2) echo "$1 students";;
		3) echo "$1 students";;
		4) echo "$1 students";;
		*) echo "A lot of students"
	esac
fi
```

19. Напишите скрипт на bash, который будет определять в какую возрастную группу попадают пользователи. При запуске скрипт должен вывести сообщение "enter your name:" и ждать от пользователя ввода имени (используйте read, чтобы прочитать его). Когда имя введено, то скрипт должен написать "enter your age:" и ждать ввода возраста (опять нужен read). Когда возраст введен, скрипт пишет на экран "<Имя>, your group is <группа>", где <группа> определяется на основе возраста по следующим правилам:

младше либо равно 16: "child",
от 17 до 25 (включительно): "youth",
старше 25: "adult".
После этого скрипт опять выводит сообщение "enter your name:" и всё начинается по новой (бесконечный цикл!). Если в какой-то момент работы скрипта будет введено пустое имя или возраст 0, то скрипт должен написать на экран "bye" и закончить свою работу (выход из цикла!).

```bash
#!/usr/bin/bash


flag=True
while [ "$flag"="True" ]
do
	echo "enter your name:"
	read name
	if [[ -z $name ]]
	then
		 echo "bye"
		 flag="false"
		 break
	fi

	echo "enter your age:"
	read age

	if [[ $age -eq 0 ]]
	then 
		echo "bye"
		flag="false"
		break

	elif [[ $age -le 16 ]]
	then
		group="child"
		echo "$name, your group is $group"
		
	elif [[ $age -ge 17 && $age -le 25 ]]
	then 
		group="youth"
		echo "$name, your group is $group"
	
	elif [[ $age -ge 25 ]]
	then 
		group="adult"
		echo "$name, your group is $group"

	fi
done
```

20. Напишите скрипт на bash, который будет искать наибольший общий делитель (НОД, greatest common divisor, GCD) двух чисел. При запуске ваш скрипт не должен ничего писать на экран, а просто ждет ввода двух натуральных чисел через пробел (для этого можно использовать read и указать ему две переменные -- см. пример в видеофрагменте). После ввода чисел скрипт считает их НОД и выводит на экран сообщение "GCD is <посчитанное значение>", например, для чисел 15 и 25 это будет "GCD is 5". После этого скрипт опять входит в режим ожидания двух натуральных чисел. Если в какой-то момент работы пользователь ввел вместо этого пустую строку, то нужно написать на экран "bye" и закончить свою работу. 

Вычисление НОД несложно реализовать с помощью алгоритма Евклида. Вам нужно написать функцию gcd, которая принимает на вход два аргумента (назовем их M и N). Если аргументы равны, то мы нашли НОД -- он равен M (или N), нужно выводить соответствующее сообщение на экран (см. выше). Иначе нужно сравнить аргументы между собой. Если M больше N, то запускаем ту же функцию gcd, но в качестве первого аргумента передаем (M-N), а в качестве второго N. Если же наоборот, M меньше N, то запускаем функцию gcd с первым аргументом M, а вторым (N-M).

```bash
#!/bin/bash
 
while [ true ] 
do
    read n1 n2
if [ -z $n1 ]; then
    echo "bye"
    break
else
    gcd () {
    remainder=1
    if [ $n2 -eq 0 ]
    then
    echo "bye"
    fi
    while [ $remainder -ne 0 ]
    do
    remainder=$((n1%n2))
    n1=$n2
    n2=$remainder
    done
    }
    gcd $1 $2
    echo "GCD is $n1" 
fi
done
```

21. Напишите калькулятор на bash. При запуске ваш скрипт должен ожидать ввода пользователем команды (при этом на экран выводить ничего не нужно). Команды могут быть трех типов: 

Слово "exit". В этом случае скрипт должен вывести на экран слово "bye" и завершить работу. 
Три аргумента через пробел -- первый операнд (целое число), операция (одна из "+", "-", "*", "/", "%", "**") и второй операнд (целое число). В этом случае нужно произвести указанную операцию над заданными числами и вывести результат на экран. После этого переходим в режим ожидания новой команды.
Любая другая команда из одного аргумента или из трех аргументов, но с операцией не из списка. В этом случае нужно вывести на экран слово "error" и завершить работу.

```bash
#!

while [[ True ]]
do
  read birinchi amal ikkinchi
  if [[ $birinchi == "exit" ]]
  then
    echo "bye"
    break
  elif [[ "$birinchi" =~ "^[0-9]+$" && "$ikkinchi" =~ "^[0-9]+$" ]]
  then
    echo "error"
    break
  else
    case $amal in
"+") let "result = birinchi + ikkinchi";;
"-") let "result = birinchi - ikkinchi";;
"/") let "result = birinchi / ikkinchi";;
"*") let "result = birinchi * ikkinchi";;
"%") let "result = birinchi % ikkinchi";;
"**") let "result = birinchi ** ikkinchi";;
*) echo "error" ; break ;;
    esac
    echo "$result"
  fi
done
```
