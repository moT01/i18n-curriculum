---
id: 6571c34568e4b3b17d3957f8
title: Вступ до гнучкого контейнера. Урок №7
challengeType: 15
dashedName: introduction-flexbox-lesson-g
---

# --description--

Властивість `flex-shrink` схожа до `flex-grow`, але встановлює «коефіцієнт стиснення» гнучкого предмета. `flex-shrink` застосовується лише в тому випадку, коли розмір всіх гнучких предметів більший за їхній батьківський контейнер. Наприклад, якби три елементи div мали оголошення ширини `width: 100px`, а значення `.flex-container` було меншим за `300px`, то елементам div потрібно було б стиснутись, щоб поміститись.

Коефіцієнтом стиснення за замовчуванням є `flex-shrink: 1`, тобто всі предмети стискаються рівномірно. Якщо ви не хочете, щоб предмет стискався, вкажіть `flex-shrink: 0;`. Ви можете вказати більше значення, щоб змусити певні предмети стискатися більше, ніж за звичайних значень.

Ось приклад. Якщо зменшити вікно браузера, ви помітите, що `.two` ніколи не буде меншим за задану ширину `250px`, навіть якщо правило `flex-grow` вказує, що елементи мають бути однакового розміру.

<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_2" scrolling="no" src="https://codepen.io/TheOdinProjectExamples/embed/JjJXZVz?height=300&amp;default-tab=html%2Cresult&amp;slug-hash=JjJXZVz&amp;editable=true&amp;user=TheOdinProjectExamples&amp;name=cp_embed_2" style="width: 100%; overflow:hidden; display:block;" title="Вставка CodePen" loading="lazy" id="cp_embed_JjJXZVz"></iframe>

Важливо звернути увагу: якщо ви вказали `flex-grow` або `flex-shrink`, то не факт, що гнучкі предмети дотримаються заданих значень `width`. У прикладі вище всі 3 елементи div мають `width` зі значенням `250px`, але якщо їхній батьківський контейнер достатньо великий, вони збільшуються, щоб заповнити його. А якщо батьківський контейнер замалий, вони за замовчуванням зменшуються, щоб поміститись. Це не помилка, але може збити з пантелику, якщо ви цього не знаєте.

# --questions--

## --text--

Яка поведінка властивості `flex-shrink` за замовчуванням, якщо застосувати її до гнучких предметів?

## --answers--

Вона заважає будь-якому предмету стискатися.

---

Вона стискає предмети відносно решти.

---

Вона робить так, що стискаються лише певні предмети.

---

Вона однаково збільшує розміри предметів.


## --video-solution--

2
