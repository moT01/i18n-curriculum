---
id: 64a674c27a7d00f97013ed14
videoId: rIO5326FgPE
title: Блокова модель. Урок №13
challengeType: 15
dashedName: the-box-model-lesson-m
--- 
# --description--

Оскільки поняття блокової моделі є основним, розглянемо його детальніше <a href="https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model#what_is_the_css_box_model" target="_blank">у цьому уроці від MDN</a> (англійською мовою). Він охоплює той самий матеріал, що й відео вище та ознайомить вас з вбудованими блоками, які ми розглянемо в наступному уроці. Зверніть увагу на приклади та приділіть деякий час, щоб поекспериментувати з редактором у браузері!

# --questions--

## --text--

Як налаштувати альтернативну блокову модель для всіх елементів?

## --answers--

```css
html {
    box-sizing: inherit;
}
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

---

```css
* {
    box-sizing: border-box;
}
```

---

```css
html {
  box-sizing: border-box;
}
* {
  box-sizing: inherit;
}
```

---

```css
html {
    box-sizing: border-box;
}
*,
*::before,
*::after {
    box-sizing: inherit;
}
```



## --video-solution--

4
