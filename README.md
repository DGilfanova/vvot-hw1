# Задание 1. Обработка фотографий с лицами людей

## Видеодоказательство работоспособности

[Youtube](https://youtu.be/hWlwETKL0R8)

## Инструкция по запуску

1. Клонировать репозиторий и перейти в нужную директорию

```bash
git clone git@github.com:DGilfanova/vvot-hw1.git
cd vvot-hw1
```

2. Создать сервисный аккаунт

```bash
yc iam service-account create --name {sa-name}
```

Пример ответа:  
id: {sa-id}  
folder_id: {folder-id}  
created_at: "2023-11-30T11:49:44.352068508Z"  
name: {sa-name}

3. Наделить аккаунт правами админа 

```bash
yc resource-manager folder add-access-binding {folder-id} --role=admin --service-account-id={sa-id}
```

4. Создать авторизованный ключ для сервисного аккаунта и сохранить его в файл key.json

```bash
yc iam key create --service-account-id {sa-id} --folder-id {folder-id} --output key.json
```

5. Определить переменные среды в terraform.tfvars  
```bash
cloud_id - your cloud id  
folder_id - {folder-id}  
sa_id - {sa-id}  
tg_key - telegram bot access token 
``` 

Необязательно: можно также переопредилить названия всех функций, триггеров и т.д. Описаны в variables.tf

6. Выполнить команды:

```bash
terraform init   
terraform validate  
terraform plan  
terraform apply
```

Бывает такое, что вылезают странные ошибки, в таком случае нужно повторно запустить команду "terraform apply"

