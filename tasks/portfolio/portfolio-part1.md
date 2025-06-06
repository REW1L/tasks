## portfolio#1 - Фиксированная вёрстка

| Start task | Deadline task        | Start cross-check | Deadline cross-check |
| ---------- | -------------------- | ----------------- | -------------------- |
| 04.01.2022 | 17.01.2022 23:59 UTC | 18.01.2022        | 20.01.2022 23:59 UTC |

- [Описание и требования задания](portfolio.md)
- [Советы по выполнению задания](portfolio-part1-hints.md)

Вам необходимо сверстать страницу согласно [макету](https://www.figma.com/file/1A1SJ7FYyMUiBqhU3WUiBI/Portfolio) - только **Desktop**  
Ширина контента 1440рх не должна изменяться при изменении размера окна браузера.

## Порядок работы

1. Задание выполняется в приватном репозитории школы.  
   [Как работать с приватным репозиторием школы](https://rs.school/docs/ru/private-repository)
2. От ветки `main` создайте ветку `portfolio` в ней создайте папку `portfolio`, в ней разместите файлы проекта
3. Выполните задание.
4. Проверьте соответствие вашей работы [Требованиям к вёрстке](#требования-к-вёрстке)
5. Cамостоятельно оцените свою работу согласно предложенным [Критериям оценки](#критерии-оценки), с учётом [Особенностей проверки вёрстки на соответствие макету](#особенности-проверки-вёрстки-на-соответствие-макету)
6. Самооценку своей работы выведите в консоль браузера. Для этого подключите к файлу `index.html` файл `index.js`, в нём напишите функцию console.log(), в скобках в кавычках напишите самооценку по пунктам. Для переноса строк используйте символ `\n`
7. Создайте и замержите Pull Request из ветки `portfolio` в ветку `gh-pages`. Название Pull Request произвольное. Описывать данный Pull Request нет необходимости.  
   Через 10-15 минут после мержа, иногда больше, деплой вашей работы будет доступен по ссылке  
   `https://rolling-scopes-school.github.io/GITHUB-USERNAME-JSFEPRESCHOOL/portfolio/`  
   в которой вместо GITHUB-USERNAME укажите свой никнейм на сайте GitHub
8. После завершения работы откройте Pull Request из ветки `portfolio` в ветку `main`. Название Pull Request дайте по названию задания. [Описание Pull Request дайте по схеме](https://rs.school/docs/ru/pull-request-review-process#требования-к-pull-request-pr) Мержить данный Pull Request не нужно.
9. Ссылку на деплой вашей работы засабмитьте в [rs app](https://app.rs.school/) раздел "Cross-Check Submit"
10. После дедлайна таска стартует кросс-чек. Продолжительность кросс-чека три дня. Для получения балла за таск необходимо проверить все присланные на проверку работы и засабмитить в [rs app](https://app.rs.school/) результат проверки.

## Требования к вёрстке

1. Вёрстка валидная +10
   - для проверки валидности вёрстки используйте сервис https://validator.w3.org/
   - валидной вёрстке соответствует надпись "Document checking completed. No errors or warnings to show." В таком случае баллы за пункт требований выставляем полностью.
   - если есть предупреждения - `warnings`, но нет ошибок - `errors`, выставляем половину баллов за пункт требований
2. Вёрстка семантическая +20  
   В коде странице присутствуют следующие элементы (указано минимальное количество, может быть больше):
   - `<header>`, `<main>`, `<footer>` +2
   - шесть элементов `<section>` (по количеству секций) +2
   - только один заголовок `<h1>` +2
   - пять заголовков `<h2>` (количество секций минус одна, у которой заголовок `<h1>`) +2
   - один элемент `<nav>` (панель навигации) +2
   - два списка `ul > li > a` (панель навигации, ссылки на соцсети) +2
   - десять кнопок `<button>` +2
   - два инпута: `<input type="email">` и `<input type="tel">` +2
   - один элемент `<textarea>` +2
   - три атрибута `placeholder` +2
3. Вёрстка соответствует макету +48
   - блок `<header>` +6
   - секция `hero` +6
   - секция `skills` +6
   - секция `portfolio` +6
   - секция `video` +6
   - секция `price` +6
   - секция `contacts` +6
   - блок `<footer>` +6
4. Требования к css + 12
   - для построения сетки используются флексы или гриды +2
   - при уменьшении масштаба страницы браузера вёрстка размещается по центру, а не сдвигается в сторону +2
   - фоновый цвет тянется на всю ширину страницы +2
   - иконки добавлены в формате `.svg`. SVG может быть добавлен любым способом. Обращаем внимание на формат, а не на способ добавления +2
   - изображения добавлены в формате `.jpg` +2
   - есть `favicon` +2
5. Интерактивность, реализуемая через css +20
   - плавная прокрутка по якорям +5
   - ссылки в футере ведут на гитхаб автора проекта и на страницу курса https://rs.school/courses/javascript-preschool-ru +5
   - интерактивность включает в себя не только изменение внешнего вида курсора, например, при помощи свойства `cursor: pointer`, но и другие визуальные эффекты, например, изменение цвета фона или цвета шрифта. Если в макете указаны стили при наведении и клике, для элемента указываем эти стили. Если в макете стили не указаны, реализуете их по своему усмотрению, руководствуясь общим стилем макета +5
   - обязательное требование к интерактивности: плавное изменение внешнего вида элемента при наведении и клике не влияющее на соседние элементы +5

## Критерии оценки

**Максимальная оценка за задание 100 баллов**

Баллы за пункты требований указаны в разделе [Требования к вёрстке](#требования-к-вёрстке)

Для удобства проверки выведите в консоль браузера самооценку своего проекта по пунктам с указанием баллов за каждый выполненный вами пункт.

Разница между максимальной оценкой за задание (100 баллов) и максимально возможным количеством баллов за выполнение всех пунктов требований (110 баллов) позволит сгладить возможные ошибки проверяющих в ходе кросс-чека, неточности в описании задания, разное понимание требований задания проверяющим и проверяемым.

## Особенности проверки вёрстки на соответствие макету

- допускается отклонение вёрстки от макета до 10px по горизонтали и вертикали, если соблюдается визуальное сходство вёрстки и макета
- разрешены и даже приветствуются правки размеров и расположения криво нарисованных блоков
- в качестве инструмента для проверки соответствия вёрстки макету используйте расширение [PerfectPixel](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=ru)
- при проверке вёрстки при помощи расширения PerfectPixel в первую очередь убедетесь, что в расширении выставлен масштаб 1, в браузере и операционной системе - масштаб 100%
- если разрешение экрана 1440рх и больше, для проверки вёрстки на соответствие макету достаточно вручную выставить макет по верхнему левому углу направляющих
- если разрешение экрана меньше 1440рх, для проверки используем device toolbar браузера Google Chrome в режиме responsive
- каждый блок и секция рассматриваются по раздельности, т.е. недочеты предыдущего блока не переносятся на следующий, а при переходе проверки на следующий блок, мы его выравниваем с наложенным изображением
- относительно текста проверяем его выравнивание по левому краю, отступы до границы блока. Размеры текста проверяются только по высоте. Отличие в ширине слов и отступах между буквами при сопоставлении макета и вёрстки не считается ошибкой, если используется правильный шрифт с правильно указанными свойствами

## Как сабмитить задание

- Задание `Portfolio#1` проверяется в ходе кросс-чека.
- После выдачи задания, но до наступления дедлайна зайдите в rs app https://app.rs.school/, выберите **Cross-Check: Submit**, в выпадающем списке выберите название задания, в поле **Solution URL** добавьте ссылку на задеплоенную страницу с вёрсткой, нажмите кнопку **Submit**.

## Рекомендации по сабмиту

- Засабмитить задание рекомендуется как можно раньше, как только в rs app появится такая возможность. После сабмита задание можно продолжать выполнять до самого дедлайна
- Так как проект выполняется в приватном репозитории, сабмитить ссылку на репозиторий или pull request нет смысла - проверяющий его не увидит. Приватный репозиторий школы видите только вы сами, админы курса, и увидят ваши менторы, когда они появятся
- Убедитесь, что задеплоенная вами ссылка открывается в режиме инкогнито браузера
- Сделайте скриншот засабмиченной ссылки и сохраняйте его у себя до старта кросс-чека. Если вам не придут работы на проверку, скриншот послужит доказательством, что вы вовремя засабмитили ссылку на работу. В таком случае вашу работу проверят в ходе апелляции

## Проверка задания Portfolio#1

- инструкция по проведению cross-check: https://rs.school/docs/ru/cross-check-flow
- форма для кросс-чека https://portfolio-part1-check-list.netlify.app/
