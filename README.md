# devops-netology
# Домашнее задание к занятию "3.1 Работа в терминале"
<details>

### 6. Как добавить ресурсов процессора или оперативной памяти виртуальной машине
Через Vagrantfile:
```
config.vm.provider "virtualbox" do |v|
  v.memory = 2048
  v.cpus = 2
end
```

### 8. Ознакомиться с разделами man bash
* Длина журнала задаётся переменной окружения `HISTSIZE`,со строки `№982` и ниже.
* Директива `ignoreboth` содержит сразу две - `ignorespace` и `ignoredups`. Если она задана, в истории не будут сохраняться команды, начинающиеся с пробела, и не будут сохраняться команды идущие подряд. Т.е вместо двух строк в историю запишется одна

### 9. В каких сценариях использования применимы скобки `{}`

1. Строка мануала **№1187**, при работе с массивами.\
   Например `echo ${array[@]}` выведет все элементы массива `array` через пробел, а `echo ${#array[@]}` - количество элементов в массиве `array`.
1. Строка мануала **№1256**, чтобы "перебрать" варианты.\
   Например, команда `ls -l /etc/{sudoers,resolv.conf}` выведет параметры файлов `/etc/sudoers` и `/etc/resolv.conf`, а команда `echo test{1,2,3}test` выведет строку `test1test test2test test3test`
1. Строка мануала **№1334**, чтобы модифицировать строки/переменные и использовать в скриптах. 
   Например `test="12345"; echo ${test:1:3}` выведет три "234", а конструкция `SetSomeVar=${1:-1000}` задаст переменной `SetSomeVar` значение "1000", если скрипту не передали параметров.
1. Строка мануала **№3365**, при написании функций. Тело функции описывается в фигурных скобках.

### 10. ...как создать однократным вызовом touch 100000 файлов?..
* 100000 - да:
`touch file{1..100000}`
* 300000 - нет:
  
        $ touch file{1..300000}
        -bash: /usr/bin/touch: Argument list too long

### 11. Что делает конструкция `[[ -d /tmp ]]`

Проверяет, что `/tmp` существует и это директория 

### 12. type -a bash

```
$ ln -s /usr/bin /tmp/new_path_directory
$ PATH=/tmp/new_path_directory:${PATH}

```

### 13. Чем отличается планирование команд с помощью `batch` и `at`?

* `at` одноразовые команды строго по расписанию 
* `batch` выполнится, когда позволит нагрузка на систему (load average упадёт ниже 1.5 или значения, заданного командой atd)

</details>

# Домашнее задание к занятию "2.2. Основы Git"
<details> 
Добавлена строка в ветке fix

## Упрощаем себе жизнь
```
Коммит через IDE
```

</details>


# Домашнее задание к занятию "2.1. Системы контроля версий"
<details>
test
test

### Уточнение по .gitignore

```
## Local .terraform directories
**/.terraform/*
```
Исключает из индекса все папки с названием `.terraform` во всех вложенных папках и файлы в них.
`./terraform/projects/.terraform` и `./terraform/projects/main/.terraform` не проиндексируются а `./terraform/.terraform` индексируется.

```
# .tfstate files
*.tfstate
*.tfstate.*
```
Исключит в этой папке все файлы с расширением `tfstate`, или в названии которых есть `.tfstate.`, например `test.tfstate.swp`

```
# Crash log files
crash.log
```
Исключит файл `crash.log` в этой папке

```
# Exclude all .tfvars files, which are likely to contain sentitive data, such as
# password, private keys, and other secrets. These should not be part of version
# control as they are data points which are potentially sensitive and subject
# to change depending on the environment.
#
*.tfvars
```
Исключит все файлы с расширением `.tfvars`


```
# Ignore override files as they are usually used to override resources locally and so
# are not checked in
override.tf
override.tf.json
*_override.tf
*_override.tf.json
```
Исключит  файлы `override.tf` и `override.tf.json`, и прочие, которые заканчиваются на `_override.tf` и `_override.tf.json

```
# Ignore CLI configuration files
.terraformrc
terraform.rc
```
Исключит два файла: `.terraformrc` и `terraform.rc`

</details>