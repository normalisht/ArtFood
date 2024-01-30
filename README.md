# ArtFood

## О проекте
ArtFood - это онлайн-сервис, предоставляющий пользователям возможность 
публикации рецептов, подписки на публикации других пользователей, 
а также добавления понравившихся рецептов в список "Избранное". 
Основная цель ArtFood - облегчить процесс приготовления пищи 
и сделать его более удобным.

На сайте пользователи могут делиться своими любимыми рецептами, 
включая подробные инструкции по приготовлению и список необходимых продуктов. 
Они также могут следить за активностью других пользователей, 
подписываясь на их публикации.

Одна функций ArtFood - это возможность создания списка продуктов. 
Пользователи могут выбрать одно или несколько блюд, 
которые они планируют приготовить, 
и загрузить список необходимых продуктов перед походом в магазин. 
Это упрощает планирование покупок и помогает избежать забывчивости.

## Документация проекта

Документация API находится по пути ```docs/openapi-schema.yml```

## Как развернуть проект

* [Установить docker](https://docs.docker.com/compose/install/)


* Клонировать репозиторий
```bash
git clone git@github.com:normalisht/ArtFood.git
```

* Создать и активировать виртуальную среду, установить зависимости

```bash
python -m venv venv
if [ -e "venv/bin/activate" ]; then
    source venv/bin/activate
else
    source venv/Scripts/activate
fi
pip install docker
```

* На основе файла `.env.example` создать `.env` файл

* Перейти в папку "infra"
```bash
cd infra
```

* Запустить скрипт "start-docker.py".
Скрипт выполнит следующие действия:
1) Запустит docker-compose
2) Выполнит миграции БД.
3) Загрузит в БД ингредиенты и теги.
4) Создаст статику бекенда и скопирует её в том static.
5) Создаст суперпользователя с логином и паролем
"admin" и почтой "admin@example.com". first_name и last_name
нужно будет установить через админ. панель.
```bash
python start-docker.py
```
