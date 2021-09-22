# devops-netology
# Домашнее задание к занятию "2.2. Основы Git"
<details>
Строка в ветке fix
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