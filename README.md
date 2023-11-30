# Задание 1. Обработка фотографий с лицами людей

## Инструкция по запуску

1. Необходимо создать сервисный аккаунт

```bash
yc iam service-account create --name <sa-name>
```

Пример ответа:
id: <your-sa-id>
folder_id: <your-folder-id>
created_at: "2023-11-30T11:49:44.352068508Z"
name: <sa-name>

2. Наделить аккаунт правами админа 

```bash
yc resource-manager folder add-access-binding <your-folder-id> --role=admin --service-account-id=<your-sa-id>
```

3. Создать авторизованный ключ для сервисного аккаунта и сохранить его в файл key.json

```bash
yc iam key create --service-account-id <your-sa-id> --folder-id <your-folder-id> --output key.json
```

## Usage

```python
import foobar

# returns 'words'
foobar.pluralize('word')

# returns 'geese'
foobar.pluralize('goose')

# returns 'phenomenon'
foobar.singularize('phenomena')
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)