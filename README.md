# Fashion MNIST classification (MLOps pipeline)

Задача классификации одежды на наборе данных [Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist)

## Запуск

- Настройка окружения:
```bash
poetry install
```

- Запуск `pre-commit`:
```bash
pre-commit install
pre-commit run --all-files
```

[Google Drive с данными для DVC](https://drive.google.com/drive/u/6/folders/1pseSLm5GJNShatTFvCr5DsU9K61fVr5R)

- Загрузка данных и обученных весов:
```bash
dvc pull
```

- Запуск локального mlflow tracking server:
```bash
mlflow server --host 127.0.0.1 --port 8080
```
Для другого сервера необходимо поменять uri в `conf/config.yaml`

- Обучение:
```bash
cd fashion_mnist
poetry run python train.py
```

- Инференс используя mlflow models:
```bash
poetry run python run_server.py
```
