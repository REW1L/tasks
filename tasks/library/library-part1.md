## Library#1 - Фиксированная вёрстка

| Start task | Deadline task        | Start cross-check | Deadline cross-check |
| ---------- | -------------------- | ----------------- | -------------------- |
| 10.07.2023 | 31.07.2023 00:00 UTC | 31.07.2023        | 04.08.2023 03:59 UTC |

- [Описание и требования задания](library.md)

Вам необходимо сверстать страницу согласно [макету](https://www.figma.com/file/SGY7eOpXC1xBddFNsb72o7/%D0%91%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B0-stage0) - только **Desktop**  
Ширина контента 1440рх не должна изменяться при изменении размера окна браузера.

## Порядок работы

1. Задание выполняется в приватном репозитории школы.  
   [Как работать с приватным репозиторием школы](https://rs.school/docs/ru/private-repository)
2. От ветки `main` создайте ветку `library` в ней создайте папку `library`, в ней разместите файлы проекта
3. Выполните задание.
4. Проверьте соответствие вашей работы [Требованиям к вёрстке](#требования-к-вёрстке)
5. Cамостоятельно оцените свою работу согласно предложенным [Критериям оценки](#критерии-оценки), с учётом [Особенностей проверки вёрстки на соответствие макету](#особенности-проверки-вёрстки-на-соответствие-макету)
6. Самооценку своей работы выведите в консоль браузера. Для этого подключите к файлу `index.html` файл `index.js`, в нём напишите функцию console.log(), в скобках в кавычках напишите самооценку по пунктам. Для переноса строк используйте символ `\n`
7. Создайте и замержите Pull Request из ветки `library` в ветку `gh-pages`. Название Pull Request произвольное. Описывать данный Pull Request нет необходимости.  
   Через 10-15 минут после мержа, иногда больше, деплой вашей работы будет доступен по ссылке  
   `https://rolling-scopes-school.github.io/GITHUB-USERNAME-JSFEPRESCHOOL2023Q2/library/`  
   в которой вместо GITHUB-USERNAME укажите свой никнейм на сайте GitHub
8. После завершения работы откройте Pull Request из ветки `library` в ветку `main`. Название Pull Request дайте по названию задания. [Описание Pull Request дайте по схеме](https://rs.school/docs/ru/pull-request-review-process#требования-к-pull-request-pr) Мержить данный Pull Request не нужно.
9. Ссылку на деплой вашей работы засабмитьте в [rs app](https://app.rs.school/) раздел "Cross-Check Submit"
10. После дедлайна таска стартует кросс-чек. Продолжительность кросс-чека три дня. Для получения балла за таск необходимо проверить все присланные на проверку работы и засабмитить в [rs app](https://app.rs.school/) результат проверки.

## Требования к вёрстке

При разработке важно помнить о способе проверки вёрстки указанном в [Особенностях проверки вёрстки](#особенности-проверки-вёрстки)

1. Вёрстка валидная **+10**
   - для проверки валидности вёрстки используйте сервис https://validator.w3.org/
   - валидной вёрстке соответствует надпись "Document checking completed. No errors or warnings to show." В таком случае баллы за пункт требований выставляем полностью.
   - если есть предупреждения - `warnings`, но нет ошибок - `errors`, выставляем половину баллов за пункт требований.
2. Вёрстка семантическая **+16**  
   В коде страницы присутствуют следующие элементы (указано минимальное количество, может быть больше):
   - `<header>`, `<main>`, `<footer>` +2.
   - шесть элементов `<section>` (по количеству секций) +2.
   - только один заголовок `<h1>` +2. Если элементов `<h1>` на странице больше одного, считаем это ошибкой.
   - пять заголовков `<h2>` (легко отличимы на верхних границах секций, имеют единый стиль) +2.
   - один элемент `<nav>` (панель навигации в хедере) +2.
   - два списка `ul > li > a` (панель навигации, ссылки на соцсети в футере) +2.
   - семь кнопок `<button>` +2.
   - два инпута `<input>` в секции `LibraryCard` и четыре `<input type="radio">` в секции `Favorites` +2.
3. Вёрстка соответствует макету **+54**  
   Под оценкой за блок или секцию вы найдете более подробное описание задания, если возникнут вопросы по совпадению с макетом. За нарушения в пунктах, которые можно проверить, снимаем по 2 балла помимо других явных ошибок, но не больше общего количества баллов за блок:
   - блок `<header>` +8:
     - Стараемся, чтобы текст совпадал с макетом. Если есть небольшие отклонения, то главное для нас, чтобы расстояние между элементами меню было одинаковое, 30px.
     - Элементы меню работают как якоря. При нажатии на один из них нас перебросит наверх соответствующего раздела.
     - Сами элементы меню при наведении (эффект hover) должны быть интерактивными (решайте сами, должны ли они стновиться жирными или подчеркнутыми. Но обязательно курсор должен поменяться на cursor: pointer)
     - Расстояние от самого меню до иконки пользователя - 40px. Иконка является отдльным элементом, и не входит в `<nav>`.
     - Текст "Brooklyn Public Library" находится в `<h1>`.
   - секция `Welcome` +4.
   - секция `About` +6:
     - Добавьте все картинки, которые будут использованы в папку с картинками. Даже если отображается всего 3, в папке должны быть все 5.
     - Расстояния между кнопками пагинации 10px.
     - Обратите внимание, что кнопки хоть и имеют вид круга, но интерактивная область (область нажатия, выделяемая cursor:pointer) должна быть размером +5px в каждую сторону (круглая, квадратная или со скошенными углами - на ваш выбор). Т.е. это будут прозрачные элементы размерами 26x26, внутри которых будут располагаться непосредственно кнопки 16x16.
   - секция `Favorites` +8:
     - Интерактивные кнопки дожны иметь структуру `input type="radio" + label`.
     - Добавьте небольшую область вокруг кнопки и надписи (например, 5px как в примере секции `about`) для того, чтобы была возможность легче наводить мышку.
     - Картинок и описаний - много, для 4х секций. Их стоит добавить в проект. А лучше сразу на страницу, и скрыть с помощью CSS свойств, например `display: none;`.
     - Кнопки "buy" должны быть интерактивными, плавно менять свой цвет при наведении на них, как указано в макете `styleguides`.
     - Кнопка "own" не должна быть интерактивной, не должна нажиматься. И на ней должен присутствовать атрибут `disabled`.
   - секция `CoffeShop` +6.
   - секция `Contacts` +6:
     - Карту можно вставить просто картинкой. Добавлять ее отдельным сервисом не обязательно.
     - Везде, где в тексте встречаются цифры в виде телефонного номера, это должны быть ссылки с типом "tel" и номером.
     - Там, где в тексте встречается текст с именем контактного лица, это должна быть ссылка с типом "mailto" и адресом почты (например, AmandaHirst@gmail.com).
   - секция `LibraryCard` +8:
     - "Find your Library card" - это должа быть форма с полями `input`.
     - Желательно сделать ограничения в полях `input` на использование только букв и цифр, а также дефиса. Но это правило проверять не нужно.
     - Все 3 кнопки должны быть интерактивными, плавно менять свой цвет при наведении на них, как указано в макете `styleguides`.
     - Хоть иконки из модального окна (Visits, Bonuses, Books) сейчас не нужны будут, можно их добавить в соответствующую папку проекта.
   - блок `<footer>` +8:
     - Адрес библиотеки должен быть ссылкой (место на карте, например).
     - Иконки соцсетей также должны быть ссылками (можете вставить свои соцсети или любые другие аккаунты этих сервисов).
     - Вместо `Username` должно быть ваше имя, как оно пишется на английском языке и ссылка на GitHub.
4. Общие требования к верстке **+20**
   - для построения сетки используются флексы или гриды `(display: flex... или display: grid...)` +2.
   - при уменьшении масштаба страницы браузера вся вёрстка (контент и фоны) размещается по центру, а не сдвигается в сторону +2. Для этого должна быть обертка вокруг всей страницы, которая выравнивается по центру. Фон за рамками страницы может быть черным, белым или любого оттенка серого.
   - иконки добавлены в формате `.svg`. SVG может быть добавлен любым способом. Обращаем внимание на формат, а не на способ добавления +2.
   - изображения добавлены в формате `.jpg (.jpeg)` или `.png` +2.
   - есть `favicon` +2. В макете иконки нет, поэтому можно сгенерировать самому с помощью сервиса [favicon-generator](https://favicon.io/favicon-generator/). Иконка должна содержать 3 буквы "BPL" (Brooklyn Public Library)
   - плавная прокрутка по якорям +2.
   - в футере название ссылки `Username` заменено и ведет на GitHub студента +2.
   - в футере ссылка `The Rolling Scopes School` ведет на страницу курса https://rs.school/courses/javascript-preschool-ru +2.
   - интерактивность элементов согласно макету. Интерактивность включает в себя не только изменение внешнего вида курсора, например, при помощи свойства `cursor: pointer`, но и другие визуальные эффекты, например, изменение цвета фона или цвета шрифта. Если в макете указаны стили при наведении и клике, для элемента указываем эти стили. Если в макете стили не указаны, реализуете их по своему усмотрению, руководствуясь общим стилем макета +2.
   - обязательное требование к интерактивности: плавное изменение внешнего вида элемента при наведении и клике не влияет на соседние элементы +2.

## Критерии оценки

**Максимальная оценка за задание 100 баллов**

Баллы за пункты требований указаны в разделе [Требования к вёрстке](#требования-к-вёрстке)

Для удобства проверки выведите в консоль браузера самооценку своего проекта по пунктам с указанием баллов за каждый выполненный вами пункт.

## Особенности проверки вёрстки

1. Открываем инструменты разработчика:
   - для этого нажимаем клавишу `F12` или кликаем правой кнопки мыши и выбираем в появившемся меню пункт `Посмотреть код`,
   - в левом верхнем углу панели инструментов разработчика кликаем на иконку `Toggle device toolbar`,
   - на верхней панели выбираем `Responsive`.
2. Убедитесь, что в режиме `Responsive` нет вертикальной полосы прокрутки (она отсутствует по умолчанию). Если полоса прокрутки есть, её нужно убрать. Для этого:
   - в верхней панели device toolbar переключите тип устройства с `Desktop` на `Mobile`,
   - если тип устройства не отображается, в верхней панели device toolbar нажмите на три точки справа и выберите `Add device type`.
3. Выставляем ширину области просмотра сайта на требуемую по ТЗ - 1440px. Если видим, что страница проверяемого сайта не перестроилась, или справа осталась белая полоса, возможно придётся обновить страницу несколько раз.

## Особенности проверки вёрстки на соответствие макету

- допускается отклонение вёрстки от макета до 10px по горизонтали и вертикали, если соблюдается визуальное сходство вёрстки и макета. В случае если пиксель перфект превысил данное расхождение то баллы за 3 пункт проверки (верстка соответствует макету) обрезаются на половину за каждый не соответствующий блок (все блоки превысили - 27 баллов максимум, только header выпал - 50 баллов максимум)
- разрешены и даже приветствуются правки размеров и расположения криво нарисованных блоков
- в качестве инструмента для проверки соответствия вёрстки макету используйте расширение [PerfectPixel](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=ru)
- при проверке вёрстки при помощи расширения PerfectPixel в первую очередь убедетесь, что в расширении выставлен масштаб 1, а в операционной системе - масштаб 100%. Масштаб области просмотра сайта может быть меньше 100%, при разрешении монитора недостаточном для отображения сайта в маштабе 100% (если разрешение монитора по ширине меньше чем ширина макета сайта).
- каждый блок и секция рассматриваются по раздельности, т.е. недочеты предыдущего блока не переносятся на следующий, а при переходе проверки на следующий блок, мы его выравниваем с наложенным изображением
- относительно текста проверяем его выравнивание по левому краю, отступы до границы блока. Размеры текста проверяются только по высоте. Отличие в ширине слов и отступах между буквами при сопоставлении макета и вёрстки не считается ошибкой, если используется правильный шрифт с правильно указанными свойствами

## Как сабмитить задание

- Задание `Library#1` проверяется в ходе кросс-чека.
- После выдачи задания, но до наступления дедлайна зайдите в rs app https://app.rs.school/, выберите **Cross-Check: Submit**, в выпадающем списке выберите название задания, в поле **Solution URL** добавьте ссылку на задеплоенную страницу с вёрсткой, нажмите кнопку **Submit**.

## Рекомендации по сабмиту

- Засабмитить задание рекомендуется как можно раньше, как только в rs app появится такая возможность. После сабмита задание можно продолжать выполнять до самого дедлайна
- Так как проект выполняется в приватном репозитории, сабмитить ссылку на репозиторий или pull request нет смысла - проверяющий его не увидит. Приватный репозиторий школы видите только вы сами, админы курса, и увидят ваши менторы, когда они появятся
- Убедитесь, что задеплоенная вами ссылка открывается в режиме инкогнито браузера
- Сделайте скриншот засабмиченной ссылки и сохраняйте его у себя до старта кросс-чека. Если вам не придут работы на проверку, скриншот послужит доказательством, что вы вовремя засабмитили ссылку на работу. В таком случае вашу работу проверят в ходе апелляции

## Проверка задания Library#1

- форма для кросс-чека (Library#1): https://rolling-scopes-school.github.io/checklist/
- инструкция по проведению cross-check: https://rs.school/docs/ru/cross-check-flow
