## Создание простого приложение с использованием фреймворка [FastAPI](https://fastapi.tiangolo.com/)

### Требования

- python 3.7+

### Установка компонентов

- Установите фреймворк [FastAPI](https://fastapi.tiangolo.com/):

    ```sh
    pip install fastapi
    ```

- Установите ASGI сервер [uvicorn](https://www.uvicorn.org/):

    ```sh
    pip install "uvicorn[standard]"
    ```

### Создание приложения

- Создайте файл `main.py` со следующим содержимым:

    ```python
    from fastapi import FastAPI

    app = FastAPI()


    @app.get("/")
    def read_root():
        return {"Hello": "World"}
    ```

    Для изменения ответа на запрос в данном случае достаточно модифицировать возвращаемый методом `read_root()` объект. Например, можно возвращать заданный вручную `id` виртуальной машины, на которой запущено приложение:

    ```python
    id = 1

    @app.get("/")
    def read_root():
        return {"id": id}
    ```

    Для лучшего понимания работы приложения можете обратиться к [документации](https://fastapi.tiangolo.com/tutorial/first-steps/).

### Запуск приложения

- Запустите приложение через ASGI сервер:

    ```sh
    uvicorn main:app --host 0.0.0.0 --port 8000
    ```

    Опцией `--host` сокет привязывается к указанному хосту. По умолчанию: `127.0.0.1`

    Опцией `--port` сокет привязывается к указанному порту. По умолчанию: `8000`

    Для лучшего понимания работы `uvicorn` можете обратиться к [документации](https://www.uvicorn.org/).

    Справка по использованию:

    ```sh
    uvicorn --help
    ```

### Готово

- Вы восхитительны!
