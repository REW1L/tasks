## Plants#3

Добавление функционала при помощи JavaScript

| Start task | Deadline task        | Start cross-check | Deadline cross-check |
| ---------- | -------------------- | ----------------- | -------------------- |
| 23.01.2022 | 06.02.2022 00:00 UTC | 06.02.2022        | 09.02.2022 00:00 UTC |

- [Описание и требования задания](plants.md)

В этой части задания необходимо добавить в свёрстанную на предыдущих этапах веб-страницу следующий функционал:

- При нажатии на кнопки:`Gardens`,`Lawn`,`Planting` происходит смена фокуса на услугах в разделе `service`.
- Accordion в секции `prices` который будет включать в себя 3 выпадающих списка об услугах и ценах.
- В разделе `contacts` реализовать select с выбором городов. В зависимости от выбора пользователя появляется блок с адресом и телефоном офиса в определенном городе.

Материалы:

- [Макет в figma](https://www.figma.com/file/ntVt8IwlwzfVFMBuVVAze8/Plants?node-id=0%3A1)

## Порядок работы

1. Задание выполняется в приватном репозитории школы.
2. От ветки `plants` создайте ветку `plants-part3` в ней уже будет находиться папка `plants` с файлами проекта
3. Продолжите выполнение задания.
4. Проверьте соответствие вашей работы [Требованиям к функционалу](#требования-к-функционалу)
5. Cамостоятельно оцените свою работу согласно предложенным [Критериям оценки](#критерии-оценки)
6. Самооценку своей работы выведите в консоль браузера.
7. Создайте и замержите Pull Request из ветки `plants-part3` в ветку `plants`.  
   Название Pull Request произвольное. Описывать данный Pull Request нет необходимости.
8. После окончания кросс-чека предыдущей части задания создайте и замержите Pull Request из ветки `plants` в ветку `gh-pages`.  
   Название Pull Request произвольное. Описывать данный Pull Request нет необходимости.  
   Через 10-15 минут после мержа, иногда больше, деплой вашей работы будет доступен по ссылке  
   `https://rolling-scopes-school.github.io/GITHUB-USERNAME-JSFEPRESCHOOL2022Q4/plants/`  
   в которой вместо GITHUB-USERNAME укажите свой никнейм на сайте GitHub
9. После завершения работы отредактируйте Pull Request из ветки `plants` в ветку `main`, дополнив его функционалом третьей части задания.  
   Мержить данный Pull Request не нужно.
10. Ссылку на деплой засабмитьте в [rs app](https://app.rs.school/) раздел "Cross-Check Submit"
11. После дедлайна таска стартует кросс-чек. Продолжительность кросс-чека три дня. Для получения балла за таск необходимо проверить все присланные на проверку работы и засабмитить в [rs app](https://app.rs.school/) результат проверки.

## Требования к функционалу

1. При нажатии на кнопки:`Gardens`,`Lawn`,`Planting` происходит смена фокуса на услугах в разделе `service` +50
   - При выборе одной услуги (нажатии одной кнопки), остальные карточки услуг принимают эффект blur, выбранная услуга остается неизменной + 20
   - Пользователь может нажать одновременно две кнопки услуги, тогда эта кнопка тоже принимает стиль активной и карточки с именем услуги выходят из эффекта blur. При этом пользователь не может нажать одновременно все три кнопки услуг. При повторном нажатии на активную кнопку она деактивируется (становится неактивной) а привязанные к ней позиции возвращаются в исходное состояние (входит в состяние blur если есть еще активная кнопка или же перестають быть в блюре если это была единственная нажатая кнопка). +20
   - Анимации плавного перемещения кнопок в активное состояние и карточек услуг в эффект blur +10
2. Accordion в секции `prices` реализация 3-х выпадающих списков об услугах и ценах + 50

- При нажатии на dropdown кнопку появляется описание тарифов цен в соответствии с макетом. Внутри реализована кнопка `order`, которая ведет на секцию `contacts`, при нажатии на нее Accordion все еще остается открытым. +25
- Пользователь может самостоятельно закрыть содержимое нажав на кнопку dropup, но не может одновременно открыть все тарифы услуг, при открытии нового тарифа предыдущее автоматически закрывается. +25

3. В разделе `contacts` реализован select с выбором городов +25
   - В зависимости от выбора пользователя появляется блок с адресом и телефоном офиса в определенном городе +15
   - При нажатии на кнопку `Call us` реализован вызов по номеру, который соответствует выбранному городу +10

## Критерии оценки

**Максимальная оценка за задание 100 баллов**

Баллы за пункты требований указаны в разделе [Требования к функционалу](#требования-к-функционалу)

Для удобства проверки выведите в консоль браузера самооценку своего проекта по пунктам с указанием баллов за каждый выполненный вами пункт.

Разница между максимальной оценкой за задание (100 баллов) и максимально возможным количеством баллов за выполнение всех пунктов требований (125 баллов) позволит сгладить возможные ошибки проверяющих в ходе кросс-чека, неточности в описании задания, разное понимание требований задания проверяющим и проверяемым.

## Как сабмитить задание

- Задание `Plants#3` проверяется в ходе кросс-чека.
- После выдачи задания, но до наступления дедлайна зайдите в rs app https://app.rs.school/, выберите **Cross-Check: Submit**, в выпадающем списке выберите название задания, в поле **Solution URL** добавьте ссылку на задеплоенную страницу с вёрсткой, нажмите кнопку **Submit**.

## Рекомендации по сабмиту

- Засабмитить задание рекомендуется как можно раньше, как только в rs app появится такая возможность. После сабмита задание можно продолжать выполнять до самого дедлайна
- Так как проект выполняется в приватном репозитории, сабмитить ссылку на репозиторий или pull request нет смысла - проверяющий его не увидит. Приватный репозиторий школы видите только вы сами, админы курса, и увидят ваши менторы, когда они появятся
- Убедитесь, что задеплоенная вами ссылка открывается в режиме инкогнито браузера
- Сделайте скриншот засабмиченной ссылки и сохраняйте его у себя до старта кросс-чека. Если вам не придут работы на проверку, скриншот послужит доказательством, что вы вовремя засабмитили ссылку на работу. В таком случае вашу работу проверят в ходе апелляции

## Проверка задания Plants#3

- форма для кросс-чека (Plants#3): https://rolling-scopes-school.github.io/checklist/
- инструкция по проведению cross-check: https://rs.school/docs/ru/cross-check-flow
