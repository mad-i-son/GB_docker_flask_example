# python-flask-docker
Итоговый проект (пример) курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy
API: flask
Данные: с kaggle - https://www.kaggle.com/c/real-estate-price-prediction-moscow

Задача: предсказать цены на квартиры.

Используемые признаки:

- Id                 int64
- DistrictId         int64
- Rooms            float64
- Square           float64
- LifeSquare       float64
- KitchenSquare    float64
- Floor              int64
- HouseFloor       float64
- HouseYear          int64
- Ecology_1        float64
- Ecology_2         object
- Ecology_3         object
- Social_1           int64
- Social_2           int64
- Social_3           int64
- Healthcare_1     float64
- Helthcare_2        int64
- Shops_1            int64
- Shops_2           object
- Price            float64

Преобразования признаков: Dummies

Модель: RandomForestRegressor

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/mad-i-son-sudo/GB_docker_flask_example.git
$ cd GB_docker_flask_example
$ sudo docker build -t mad-i-son/gb_docker_flask_example .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models mad-i-son/gb_docker_flask_example
```

### Переходим на localhost:8180