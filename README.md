# https://api.lib.social/api/manga

Получение списка тайтлов. Можно отфильстровать по параметрам. На станице mangalib в коде есть параметр __DATA в котором лежат json со всеми жанрами и состояниями

## Параметры
 - site_id[] - Это номер сайта (1 - MangaLib)
 - page - Страница списка
 - q - Поиск по списку
 - format[] - Формат произведения
```json
[
    {
        "id": 1,
        "name": "4-кома (Ёнкома)"
    },
    {
        "id": 2,
        "name": "Сборник"
    },
    {
        "id": 3,
        "name": "Додзинси"
    },
    {
        "id": 4,
        "name": "В цвете"
    },
    {
        "id": 5,
        "name": "Сингл"
    },
    {
        "id": 6,
        "name": "Веб"
    },
    {
        "id": 7,
        "name": "Вебтун"
    }
]
```
 - status[] - Состояние произведения
 ``` JSON
 [
  {
    "id": 1,
    "label": "Продолжается",
    "created_at": "2016-03-05 16:35:36",
    "updated_at": "0000-00-00 00:00:00",
    "type": 1
  },
  {
    "id": 2,
    "label": "Завершен",
    "created_at": "2016-03-05 16:35:36",
    "updated_at": "0000-00-00 00:00:00",
    "type": 1
  },
  {
    "id": 3,
    "label": "Заморожен",
    "created_at": "2018-07-25 05:03:23",
    "updated_at": "0000-00-00 00:00:00",
    "type": 1
  },
  {
    "id": 4,
    "label": "Заброшен",
    "created_at": "2020-07-05 01:02:27",
    "updated_at": "0000-00-00 00:00:00",
    "type": 1
  }
]
 ```
 - types[]
``` json
{
  "1": "Манга",
  "4": "OEL-манга",
  "5": "Манхва",
  "6": "Маньхуа",
  "8": "Руманга",
  "9": "Комикс западный"
}
```
 - chap_count_min
 - chap_count_max
 - year_min
 - year_max
 - rating_min
 - rating_max
 - rate_min
 - rate_max

## Ответ
``` json
{
  "data": [
    {
      "id": 124822,
      "name": "sihanbulaseo pa-eobhaessneunde",
      "rus_name": "Я устроила забастовку, потому что моё время на исходе",
      "eng_name": "I went on strike because it was the deadline",
      "slug": "sihanbulaseo-pa-eobhaessneunde",
      "slug_url": "124822--sihanbulaseo-pa-eobhaessneunde",
      "cover": {
        "filename": "XFag3f3PKp6O",
        "thumbnail": "https://cover.imglib.info/uploads/cover/sihanbulaseo-pa-eobhaessneunde/cover/XFag3f3PKp6O_thumb.jpg",
        "default": "https://cover.imglib.info/uploads/cover/sihanbulaseo-pa-eobhaessneunde/cover/XFag3f3PKp6O_250x350.jpg",
        "md": "https://cover.imglib.info/uploads/cover/sihanbulaseo-pa-eobhaessneunde/cover/XFag3f3PKp6O_250x350.jpg"
      },
      "ageRestriction": {
        "id": 0,
        "label": "Нет"
      },
      "site": 1,
      "type": {
        "id": 5,
        "label": "Манхва"
      },
      "rating": {
        "average": "8.38",
        "averageFormated": "8.4",
        "votes": 1377,
        "votesFormated": "1.4 K",
        "user": 0
      },
      "model": "manga",
      "status": {
        "id": 4,
        "label": "Приостановлен"
      },
      "releaseDateString": ""
    }, 

    ...
    
    }
  ],
  "links": {
    "first": "http://api.lib.social/api/manga?page=1",
    "last": null,
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "path": "http://api.lib.social/api/manga",
    "per_page": 60,
    "to": 40,
    "page": 1,
    "has_next_page": false,
    "seed": "86354424b0ef69d6ef92ee377982162d"
  }
}
```

# https://api.lib.social/api/manga/{slug_url}/relations
Возвращает список связанных с этим тайтлов

# https://api.lib.social/api/manga/{slug_url}/similar

Возвращает список похожих тайтлов

# https://api.lib.social/api/manga/{slug_url}/stats?bookmarks=true&rating=true

Возвращает статистику пользователей (оценки и добавление в любимое, читаю...). Какие еще есть параметры не знаю, держите так

# https://api.lib.social/api/manga/{slug_url}/chapters

Возвращает список глав и их переводы

# https://api.lib.social/api/manga/{slug_url}/chapter?number={Номер_главы}&volume={Номер_тома}

Возвращает список страниц в главе с ссылками на их изображения

# https://api.lib.social/api/manga/{slug_url}?fields[]=background&fields[]=eng_name&fields[]=otherNames&fields[]=summary&fields[]=releaseDate&fields[]=type_id&fields[]=caution&fields[]=views&fields[]=close_view&fields[]=rate_avg&fields[]=rate&fields[]=genres&fields[]=tags&fields[]=teams&fields[]=authors&fields[]=publisher&fields[]=userRating&fields[]=moderated&fields[]=metadata&fields[]=metadata.count&fields[]=metadata.close_comments&fields[]=manga_status_id&fields[]=chap_count&fields[]=status_id&fields[]=artists&fields[]=format

Возвращает полную инфу о тайтле. Насколько это полный список параметров? Я не знаю.