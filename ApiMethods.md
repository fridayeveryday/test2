# API

## ARTICLE

### Section
---
#### __GET__ : /hello

___response:___ Hello world

__OK:__

- 200 - Все прошло гладко
```

```

---
#### __POST__ : /createManyQuestions
___response:___

__CREATED:__

- 201 - Созданы вопросы

```
[
    {
       
        "name": "теория автоматов",
        "question": "Какие виды автоматов вы знаете",
        "rightAnswers": [
            "Мили",
		"Мура"
        ]
    },
    {
        "name": "основы автоматики",
        "question": "Что такое САУ?",
        "rightAnswers": [
            "система автоматизированного управления"
        ]
    },
    {
        
        "name": "основы автоматики",
        "question": "Что такое Автоматика?",
        "rightAnswers": [
            "отрасль науки и техники, которая охватывает теорию и принципы построения систем управления техническими процессами, действующих без непосредственного участия человека"
        ]
    }
]
```



#### __POST__: /createOneQuestion

___response:___

__CREATED:__

- 201 - Создан один вопрос

```
    {
       
        "name": "теория автоматов",
        "question": "Какие виды автоматов вы знаете",
        "rightAnswers": [
            "Мили",
	    "Мура"
        ]
    }

```


---
####  __GET__ : /article/article/{id}

___response:___

__OK:__

- 200 - Все прошло гладко

```
{
  "id": Integer,
  "title": String,
  "text": String,
  "description": String,
}
```

__Error:__

- 404 - нет такой статьи

---
####  __POST__ : /article/article

___request:___

___header:__ Token - access token 

```
{
  "id": Integer, 	/* ID черновика */
  "text": String,
  "title": String,
  "description": String,
  "idTheme": Integer
}
```

___response:___

__OK:__

- 200 - Все прошло гладко

__Error:__

- 400 - плохой запрос
- 401 - неавторизован
- 426 - access токен  протух

---

####  __PUT__ : /article/article

___request:___

__header:__ Token - access token

```
{
	"id": Integer,
	"text": String,
	"title": String,
	"description": String,
	"idTheme": Integer
}
```
___response:___

__OK:__

- 200 - Все прошло гладко

__Error:__

- 400 - плохой запрос
- 401 - неавторизован
- 426 - access токен  протух

---

####  __DELETE__ : /article/article

___request:___

___header:___  Token - access token

```
{
	"id": Integer
}
```
___response:___

__OK:__

- 200 - Все прошло гладко

__Error:__

- 400 - плохой запрос
- 401 - неавторизован
- 426 - access токен  протух

---
### Edit
---

####  __GET__ : /article/edit/{id}

___request:___

___header:___  Token - access token

___response:___

__OK:__

- 200 - Все прошло гладко

```
{
  "id": Integer,
  "text": String,
  "title": String,
  "date": String,
  "description": String,
  "idTheme": Integer
}
```

__Error:__

- 400 - плохой запрос
- 401 - неавторизован
- 426 - access токен  протух

---

### Draft
---

####  __POST__ : /article/draft

___request:___

___header:___  Token - access token

```
{
  "title": String,
  "description": String
}
```

___response:___

__OK:__

- 200 - Все прошло гладко

__Error:__

- 400 - плохой запрос
- 401 - неавторизован
- 426 - access токен  протух

---
### Profile
---

####  __GET__ : /article/profile

___request:___

___header:___  Token - access token

___response:___

__OK:__

- 200 - Все прошло гладко

```
{
  "profile": {
    "name": String,
    "surname": String,
    "description": String,
    "position": String,
    "drafts": [
      {
        "title": String,
        "description": String,
        "date": String
      },
      ...
    ],
    "articles": [
      {
        "title": String,
        "description": String,
        "date": String
      },
      ...
    ]
  }
}
```

__Error:__

- 400 - плохой запрос
- 401 - неавторизован
- 426 - access токен  протух

---

####  __PUT__ : /article/profile

___request:___

___header:___  Token - access token

```
{
  "name": String,
  "surname": String,
  "description": String,
  "position": String
}
```

___response:___

__OK:__

- 200 - Все прошло гладко

__Error:__

- 400 - плохой запрос
- 401 - неавторизован
- 426 - access токен  протух
 
