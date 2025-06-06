# X Check App / RS Assessment Tool

## Цели задания

- Разработать инструмент, который может использоваться тысячами реальных пользователей.
- Помочь будущим поколениям студентов и менторов школы Rolling Scopes.
- Получить опыт командной работы близкий к условиям реальных проектов.
- Украсить CV ссылкой на качественное приложение.

После оценки работ мы (организаторы и студенты) выберем решение, которое будет интегрировано в RS App.
Решения будут оцениваться по следующим критериям:

- Согласие команды на использование их кода.
- Качество кода и реализации.
- Схожесть дизайна и набора технологий с RS App.
- Готовность команды работать над интеграцией решения в RS App.

## Особенности задания

- Работа ведётся в группах. [Описание процесса командной работы](https://docs.rs.school/#/final-task) <!-- TODO: страница с описанием процесса командной работы в документации отсутствует -->
- Для проверки и оценки решений проводится [кросс-чек](https://rs.school/docs/ru/cross-check-flow).
- Информацию, которую команда хочет донести до проверяющих необходимо поместить в README репозитория.

## Технические требования

### Нужно использовать

- React

### Можно использовать

- Redux.
- Create React App
- TypeScript, Next.js, Ant Design - для более простой интеграции решения в RS App
- Всё остальное

### Можно не использовать

- Хуки. Правда, можно и без них.

### Сервер

В качестве сервера рекомендуется использовать [json-server](https://github.com/typicode/json-server).
Это будет достаточным приближением к реальному Rest API.

Для удобства командной работы можно коммитить исходный файл (db.json).
Но будьте внимательны и не добавляйте в коммиты нежелательные изменения (не делайте `git add .`).

В продакшн сборке не будет локального json-server, поэтому каждая команда должна задеплоить свой json-server
на какой-нибудь хостинг, [например - heroku](https://github.com/jesperorb/json-server-heroku).

Можно использовать не json-server, а любую другой способ реализации Rest API.
Если не используется сервер, а например локальная эмуляция с localStorage, то оценка будет ниже (см. критерии оценки).

## Функциональные требования

Приложению нужна аутентификация, но форму логина можно сделать упрощённой - с обязательным вводом только логина (githubId).
Наличие поля для ввода пароля - на ваше усмотрение, но тогда нужна и упрощённая регистрация.
У пользователя также должна быть одна или несколько ролей. Роли выбираются при логине или регистрации (если она есть).

Задание создаётся пользователем (автором) в виде списка оцениваемых требований.
Каждое требование обязательно содержит название и максимальную оценку.
Для удобства можно сделать отдельное текстовое описание.

Чтобы создать запрос на оценку, студент выбирает задачу и указывает ссылку на решение и на pull request.

Перед тем как запрос становится доступен для проверяющих, студент должен выполнить самопроверку.

При самопроверке студент ставит оценку по каждому пункту от 0 до максимума. Для каждого пункта можно оставить комментарий,
например, пояснить каким образом было реализовано требование.

При проверке чужой работы процедура та же, но проверяющий видит оценки и комментарии из самопроверки.
Для удобства можно заполнять форму оценками из самопроверки, чтобы проверяющий менял только те оценки, с которыми не согласен.

После того как проверяющий опубликовал свою проверку, она становится доступна для просмотра студенту.
Если студент не согласен с оценкой по каким-то пунктам, он может оспорить каждый пункт в отдельности.
Проверяющий может изменить оценку или оставить как есть.

Можно организовывать сессии кросс-чека как в последних наборах RS School.
При этом сохраняется возможность создания запроса на проверку вне сессии.

Кросс-чек сессия проходит несколько стадий:

- Сбор запросов на оценку.
- Проверка работ случайно выбранными участниками сессии.
- Выставление итоговой оценки по результатам проверок.

Если для стадий кросс-чек сессии можно указать дедлайны, то они носят информативный характер
и переключение между стадиями производятся пользователем.

## Сущности и состояния

Ниже следует пример того, как могли бы выглядеть сущности в приложении.
Ваше приложение может использовать как точно такие же структуры, так и совершенно другие.
Скорее всего, список неполный и понадобятся ещё вспомогательные сущности.
Набор полей точно не исчерпывающий, например не описана структура для финальных оценок после кросс-чека.

```
const user = {
  githubId: "torvalds",
  roles: ["author", "student", "supervisor", "course_manager"]
};

const task = {
  id: "simple-task-v1",
  author: "cardamo",
  state: "DRAFT", // enum [DRAFT, PUBLISHED, ARCHIVED]
  categoriesOrder: ["Basic Scope", "Extra Scope", "Fines"],
  items: [
    {
      id: "basic_p1",
      minScore: 0,
      maxScore: 20,
      category: "Basic Scope",
      title: "Basic things",
      description: "You need to make things right, not wrong"
    },
    {
      id: "extra_p1",
      minScore: 0,
      maxScore: 30,
      category: "Extra Scope",
      title: "More awesome things",
      description: "Be creative and make up some more awesome things"
    },
    {
      id: "fines_p1",
      minScore: -10,
      maxScore: 0,
      category: "Fines",
      title: "App crashes",
      description: "App causes BSoD!"
    }
  ]
};

const taskScore = {
  task: "simple-task-v1",
  items: {
    basic_p1: {score: 20, comment: "Well done!"},
    extra_p1: {score: 15, comment: "Some things are done, some are not"},
    fines_p1: {score: 0, comment: "No ticket today"},
  }
};

const crossCheckSession = {
  id: "rss2020Q3react-xcheck",
  state: "DRAFT", // enum [DRAFT, REQUESTS_GATHERING, CROSS_CHECK, COMPLETED]
  taskId: "simple-task-v1",
  coefficient: 0.7,
  startDate: "2020-07-07",
  endDate: "2020-07-14",
  discardMinScore: true,  # ignore the review with minimal score when calculating average
  discardMaxScore: false, # similar to discardMinScore
  minReiewsAmount: 1, // how many peer reviews are required to set a score
  desiredReviewersAmount: 2, // how many peers are assigned to evaluate each solution
  attendees: [ // shuffled randomly when state is cahnged from REQUESTS_GATHERING to CROSS_CHECL
    {githubId: "ButterBrot777", reviewerOf: ["torvalds", "cardamo"]},
    {githubId: "torvalds", reviewerOf: ["cardamo"]},
    {githubId: "cardamo", reviewerOf: ["ButterBrot777"]}
  ]
}

const reviewRequest = {
  id: "rev-req-1",
  crossCheckSessionId: "rss2020Q3react-xcheck", // may be null if this review is not a part of any session
  author: "cardamo",
  task: "simple-task-v1",
  state: "PUBLISHED", // enum [DRAFT, PUBLISHED, COMPLETED]
  selfGrade: { /* embedded `taskScore` object */ }
};

const review = {
  id: "rev-id-1",
  requestId: "rev-req-1",
  author: "ButterBrot777",
  state: "DISPUTED", // enum [DRAFT, PUBLISHED, DISPUTED, ACCEPTED, REJECTED],
  grade: { /* embedded `taskScore` object */ }
};

const dispute = {
  reviewId: "rev-id-1",
  state: "ONGOING", // enum [ONGOING, ACCEPTED, REJECTED]
  idem: "extra_p1",
  comment: "Check out the 'All things' page to see all things that were implemented",
  suggestedScore: 30
};
```

## Демо

Его нет! Вы создаёте уникальное приложение, общеизвестных аналогов которому не существует.
Если подобное приложение вам попадалось - просьба отправить ссылку @cardamo.

## Критерии оценки:

**Максимальный балл за задание: 600 баллов**

- **Базовая функциональность +140**:
  - Упрощённая страница/окно авторизации. +10
  - Страница со списком задач (tasks). +10
  - Форма (на отдельной странице или в окне) создания и редактирования задачи. +20
  - Страница со списком запросов на проверку (review requests). +10
  - Список запросов на проверку можно сортировать и фильтровать по заданию и выполнившему студенту. +10
  - Форма создания запроса на проверку. +10
  - Форма проверки и самопроверки задания. +20
  - Страница со списком оценок работ (reviews). +10
  - Список оценок можно сортировать по всем полям/колонкам, где сортировка применима. +10
  - Список оценок можно фильтровать по заданию, выполнившему студенту и проверяющему . +10
  - Страница или окно с деталями оценки одного проверяющего. +10
  - Главная страница со ссылками на остальные доступные страницы ИЛИ всегда видимое меню для навигации. +10
- **Дополнительные возможности при создании задания +90**:
  - Пометить пункт как штраф ИЛИ возможность указать минимальный балл меньше 0. +10
  - Пометить пункт как проверяемый только ментором (скрывать при кросс-чеке), или более сложная система ролей при проверке. +10
  - Объединение требований в категории (basic scope, advanced, etc). +10
  - Импорт пунктов и категорий в формате [RSS Checklist](https://github.com/rolling-scopes-school/checklist); +10
  - Импорт пунктов и категорий в markdown формате, в котором описано большинство задач RSS. +30
  - Экспорт и импорт задания в собственном JSON формате. Побочный эффект - задание легко скопировать, оставив оригинальное без изменений. +20
- **Дополнительные возможности при проверке задания +40**:
  - Кнопки для быстрой оценки (не выполнено - 0 баллов, выполнено частично - 50%, выполнено полностью - 100%),
    но остаётся возможность указать любое промежуточное значение. +10
  - Дать возможность проверяющему добавить ещё один пункт со штрафными или поощрительными баллами. Способы реализации
    могут быть различными, например можно просто дать возможность указывать не только максимальный балл за требование, но и минимальный меньше ноля. +10
  - Сделать поле комментария обязательным, если оценка не совпадает с самопроверкой. +10
  - Промежуточное состояние проверки (и самопроверки тоже) можно сохранить, не публикуя её. +10
- **Дополнительные возможности после проверки задания +50**:
  - Возможность оставить обратную связь проверяющему - поблагодарить или пожаловаться. +10
  - Возможность оспорить оценку по каждому пункту. +30
  - Принять решение по оспариваемому пункту может не только проверяющий, но и пользователь со специальной ролью. +10
- **Кросс-чек +50**:
  - Страница со списком кросс-чек сессий. Автор заданий (или другая роль на ваше усмотрение) может создавать и редактировать сессии. +20
  - Студенты могут создавать запросы на проверку в рамках конкретной кросс-чек сессии. +10
  - Автор задания может остановить сбор запросов на проверку в рамках кросс-чек сессии и случайным образом распределить проверяющих. +10
  - Автор задания может завершить кросс-чек сессию, после чего студент может посмотреть свою итоговую оценку. +10
- **Дополнительная функциональность +100**:
  - Каждое действие, меняющее данные, доступно только при наличии у пользователя соответствующей роли. Набор ролей можно взять из примера или придумать свои.
    Ограничения должны быть описаны в README.
    Если выбор роли недоступен при логине или регистрации, тогда в исходной базе (db.json) должны быть тестовые пользователи с каждой из ролей, а их логины и пароли должны быть в README. +30
  - Полноценная авторизация через GitHub OAuth. Для удобства проверки выбор ролей лучше оставить при логине. +20
  - В исходной базе (db.json) есть примеры сущностей каждого типа. +10
  - В исходной базе (db.json) воспроизведено задание [xcheck](https://github.com/rolling-scopes-school/tasks/blob/master/tasks/xcheck/xcheck.md) и создан запрос на его оценку. +10 бонусных очков за стиль
  - Дополнительные полезные возможности, не описанные в требованиях к заданию. Для оценки должны обязательно быть описаны в README. до +30
- **Качество кода +130**: (требуется code review)
  - README файл в репозитории с описанием используемых технологий, инструкцией для начала разработки и для деплоя продакшн версии. +20
  - Написаны юнит-тесты, 1 балл за каждый % code coverage (statements), но не более 50 баллов. Способ получения coverage report описан в README. до +50
  - По названиям юнит-тестов понятно, что они тестируют. Тесты не просто вызывают код, но и делают осмысленные ассерты. до +30,
    если code coverage меньше 50%, максимальная оценка снижается пропорционально (при 25% максимум +15 баллов).
  - Использован eslint preset (не обязательно airbnb) и нет предупреждений и ошибок. +20
  - В репозитории есть "следы" активной командной работы - комментарии в пулл реквестах. +10

### Cross-check

- инструкция по проведению cross-check: https://rs.school/docs/ru/cross-check-flow
- форма для проверки задания: https://rolling-scopes-school.github.io/checklist/ (task X CHECK APP)
