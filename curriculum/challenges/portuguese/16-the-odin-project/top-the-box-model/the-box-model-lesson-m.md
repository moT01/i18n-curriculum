---
id: 64a674c27a7d00f97013ed14
videoId: rIO5326FgPE
title: Lição M sobre o modelo de caixas
challengeType: 15
dashedName: the-box-model-lesson-m
--- 
# --description--

Como o conceito do modelo de caixas é incrivelmente fundamental, vamos aprofundar um pouco com <a href="https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model#what_is_the_css_box_model" target="_blank">esta lição da MDN</a>. Ela trata do mesmo material que o vídeo acima e apresentará as caixas em linha, das quais trataremos na próxima lição. Preste muita atenção aos exemplos e reserve um tempo para experimentar com o editor no navegador!

# --questions--

## --text--

Como você define o modelo de caixas alternativo para todos os elementos?

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
