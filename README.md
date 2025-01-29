# API-dummyapi.io

 1. [Описание проекта](#Описание-проекта)
    1.  [Post](#POST)
        1. [GET /post (Get List)](#GET-/post-(Get-List))
        2. [GET /user/:id/post (Get List By User)](#GET-/user/:id/post-(Get-List-By-User))
   
   

## Описание проекта
https://dummyapi.io/ - Это сервис для тестирования API. Для выполнения запросов необходим app-id, который генерируется автоматически после регистрации на сайте. В качестве тестиования был взят объект **POST**

### POST
____
### GET /post (Get List)
Получение списка постов, отсортированных по дате создания.
- Доступны параметры запроса пагинации.
- Доступны параметры запроса «Создано».

**Response body:**

**list**
```js
{
 data: Array(Model)
 total: number(total items in DB)
 page: number(current page)
 limit: number(number of items on page)
}
```
**Post Preview**
```js
{
 text: string(length: 6-50, preview only)
 image: string(url)
 likes: number(init value: 0)
 tags: array(string)
 owner: string(User id)
}
```
____
### GET /user/:id/post (Get List By User)
Получает список постов для конкретного пользователя, отсортированных по дате создания.
- Доступны параметры запроса пагинации.
- Доступны параметры запроса «Создано».
  
**Response body:**
  
**list**
```js
{
 data: Array(Model)
 total: number(total items in DB)
 page: number(current page)
 limit: number(number of items on page)
}
```

**Post Preview**
```js
{
 text: string(length: 6-50, preview only)
 image: string(url)
 likes: number(init value: 0)
 tags: array(string)
 owner: string(User id)
}
```
____
### GET /tag/:id/post (Get List By Tag)
Получает список постов для определенного тега, отсортированных по дате создания.
- Доступны параметры запроса пагинации.
- Доступны параметры запроса «Создано».

**Response body:**

**list**
```js
{
 data: Array(Model)
 total: number(total items in DB)
 page: number(current page)
 limit: number(number of items on page)
}
```
**Post Preview**
```js
{
 text: string(length: 6-50, preview only)
 image: string(url)
 likes: number(init value: 0)
 tags: array(string)
 owner: string(User id)
}
```
  
____
### GET /post/:id (Get Post by id)
Получение полных данных поста по идентификатору поста

**Response body:**

**post**
```js
{
 id: string(autogenerated)
 text: string(length: 6-1000)
 image: string(url)
 likes: number(init value: 0)
 link: string(url, length: 6-200)
 tags: array(string)
 publishDate: string(autogenerated)
 owner: object(User Preview)
}
```
____
### POST /post/create (Create Post)
Создать новый пост, вернуть данные о созданном посте.
Body: post create (поля owner и post обязательны для заполнения)

**Request body:**

**post create**
```js
{
 text: string(length: 6-50, preview only)
 image: string(url)
 likes: number(init value: 0)
 tags: array(string)
 owner: string(User id)
}
```

**Response body:**

**post**
```js
{
 id: string(autogenerated)
 text: string(length: 6-1000)
 image: string(url)
 likes: number(init value: 0)
 link: string(url, length: 6-200)
 tags: array(string)
 publishDate: string(autogenerated)
 owner: object(User Preview)
}
```
____
### PUT /post/:id (Update Post)
Обновление поста по id, возврат обновленных данных поста
Body: Post data, (поле owner запрещено для обновления)

**Request body:**

**post data**
```js
{
 text: string(length: 6-1000)
 image: string(url)
 likes: number(init value: 0)
 link: string(url, length: 6-200)
 tags: array(string)
 owner: string(User id)
}
```

**Response body:**

**post**
```js
{
 id: string(autogenerated)
 text: string(length: 6-1000)
 image: string(url)
 likes: number(init value: 0)
 link: string(url, length: 6-200)
 tags: array(string)
 publishDate: string(autogenerated)
 owner: object(User Preview)
}
```

____
### DELETE /post/:id (Delete Post)
Удалить сообщение по id, вернуть id удаленного сообщения

**Response body:**
```js
{
 id: string
}
```

## Майнд-карта
Данная майнд карта содержит в себе набор тестов для тестирования объекта **POST**. Подробная проверка для **Get List**, **Get List By User**, **Get List By Tag**, **Get Post by id**, **Create Post**, **Update Post**, **Delete Post**

## Коллекции POSTMAN
Коллекция запросов для объектов для **Get List**, **Get List By User**, **Get List By Tag**, **Get Post by id**, **Create Post**, **Update Post**, **Delete Post**

[Скачать](https://github.com/Reyman556/API-dummyapi.io/blob/main/POST%20dummyapi.io.postman_collection.json)





