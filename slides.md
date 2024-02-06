---
theme: seriph
background: background01.jpeg
class: text-center
highlighter: shikiji
lineNumbers: true
drawings:
  persist: false
transition: slide-left
title: Modern CSS
mdc: true
---

# CSS Moderno

<h2>El fin de Javascript</h2>

<img v-click src="/explosion.gif" class="explosion" />

<style>
.explosion {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-indez: 10;
}
</style>
---
layout: center
class: text-center
---

<h1>El fin...¿Cómo es eso posible?</h1>
<h1 v-click class="noloes">NO LO ES</h1>
<h1 v-click>Pero me gustan los nombres de presentación pretenciosos</h1>

<style>
.noloes {
  color: white;
  font-size: 3rem;
  line-height: 1;
}
</style>

---
layout: default
---

# Table of contents

<Toc maxDepth="1"></Toc>

---

# Scroll animation

Nos permite hacer animationes en CSS donde el timeline está controlado por el largo del scroll o por la posición de ese elemento en el viewport

<br>

```css {all|7}
@keyframes fade {
  to {
    opacity: 1;
  }
}
animation: fade linear forwards;
animation-timeline: scroll();
animation-range: 0vh 100vh;
```

---

<Codepen user="oscar_thc" id="qBvoeEm" />

---

# Scrollbar Gutter

Nos permite definir un área reservada para la barra de scroll esté esta presente en ese momento o no

<br/>

```css
scrollbar-gutter: stable;
```

<br/>

[Demo](https://play.vuejs.org/#eNqFVmFv2zYQ/SsHdUPdJpLsZMsK1cmWBcWwYdiKbt+qIqUlWmYikQRJOfaC/PcdSdGm7cQ1EkO8ezy+e3dH6zG5ljJb9jQpkqmuFJMGNDW9hJbw5rJMjC6Tq5KzTgpl4BEUncMTzJXo4DVue/2+5CWvBNcG5EIYoeHSYqa872ZUff5yNfr85Q2CPKQSPTceMRpbc8nnPa8MExxIXX+0EUZv4LHkMITLlqTtaSZ7vRi53d5g94IP5w0nJ2h5isIp2oklPRJRyNFBlDT1Uaa51wIzx4WhnWyJobgCmNZsCVVLtEZ1iJROHsDPdEFJTdWwsuvJ1W+kbalaT3N83tjjADPDvcDeh95Zb4zAU4PBrCW1QG9Oto44xO0tqhc7f6laVt1bhoOqsTM6DuAErusaPGbLIvfnHSN2hNo+OV+LXcSGYVSoF0mm8MmhvslzmqO6oSD5TkV2dG98YSLprXsbeJnOhUKcaxlgfOidmGBxT9cB8VxdhiNub/cQsaZaEn64oRWkZrzZ6YsBfPWn92VZhj1qDbEY+wbWNVBoVWHwrwtjpC7yXIteVTTrucae1ousEl1eCTzZjU0+mVycX5z/lP/wbrzC//xnVl9+9+hSePpaJpC/IHV4Dk/TPJoaXGqzbinoSkhaoyXDyRmGEjsUEyrgDBvBT58vm3fXzPJcFzBv6cqN612vDZuvU7xRDOWmAMy6oumMmgdKuYOQljU8ZchAF1AhiCpnnwmFgdOZwJ7pCpjIFWjRshpeVVXlEAObLcSTAuiIahg/tC8mnmdAFDB2dkwDILPtH/yHmQA0RBaQ/RiCDTvcNJ/uGPyQhFAhk3DY1pIqbI8esx5nZ1HYSOaxO26bgGtZ0QoM9rBAyQaj4x/zic4m1X2j8NKssQZu46vx+AY/z249YH64++Z6cnH2Lt6NX/iXDROx1wmNYrUD24c0tJmN1nccU1dUUmJG56cwmSt/xe8ilXhAWIflHHrIY2wttnWlrFlgc52NgwWzUPNWPBRAeiOcKX+LPxM4OzOi0gYvIlsRbcispe/f5q4Bdi+BoIIUmtlps1yREVsG1YmWOIdYRPQimXwy2O0gbxTsyCp9YLVZIGI8/n5b4peiAvyXMl7TFaazp3JMcbh2DkmSGU5Jv2kNI1Co0HgtnaNKYaW8aGEZpiWsnxuBg3GO5vXlSY5SChqFbgqj7HsIL0V78+CVk5ziywyeMmdNdqcFxzcel2mZ4BUoGWrwt7T54iVfBA3w97PFkv/hbEb1dJhK3LOg1f0z9ju9srYy+aiopsr+6m18Bm8Iarz7wz9/0RU+b5ydqPsW0Uecn6irA3L0sF9xiJB2hHNsf3fvaljJf/WHFWqqQ1KWqFPG4csE399ujqS+pXuenQdFk6f/AVCFO4Q=)

---

# Logical properties
La idea de las propiedades lógicas es dejar de usar direcciones físicas en las propiedades de CSS y en su lugar usar propiedades que dependan de la dirección de lectura del documento

<br/>
<br/>

<div grid="~ cols-2 gap-2" m="t-2">
<v-clicks>
```css
margin-left: 1rem;
padding-bottom: 1rem;
```

```css
margin-inline-start: 1rem;
padding-block-end: 1rem;
```
</v-clicks>
</div>

---

<Codepen user="oscar_thc" id="QWorWjm" />

---

# has() selector

Es una pseudo-clase de CSS que permite hacer querys contra el contenido de un elemento. Los usos son casi infinitos. Por ejemplo puede funcionar como "parent selector".

```css
figure:has(figcaption) {
  border: 1px solid red;
  img {
    margin-block-end: .5rem;
  }
}
```

---

<Codepen user="oscar_thc" id="rNRJXEJ" />

---

# Container queries y container units

Las container queries nos permiten definir contenedores de CSS y personalizar los estilos y layout de sus descendientes en case al tamaño del contenedor. Es decir, son como las media queries pero en base al tamaño de un elemento en vez de al tamaño del viewport.

```css {none|2|3|5|8}
.element {
  container-type: inline-size;
  container-name: element;
  h1 {
    font-size: max(1rem, .5rem + 3cqi);
  }
}
@container element (min-width: 20rem) {}
```

---

<Codepen user="oscar_thc" id="oNVdVeX" />

---

# Overscroll behavior

<Codepen user="seyedi" id="dyRpwmN" />

---

# Scroll margin

<Codepen user="oscar_thc" id="MWxGREY" />

---

# Text wrap: Balance

<Codepen user="Chursin" id="ExraamB" />

---

# Accent color

<Codepen user="web-dot-dev" id="PomBZdy" />

---
layout: center
---

# Gracias

---
layout: center
---

# Créditos

- Imágenes [unsplash](https://unsplash.com)
- Presentation slides [slidev](https://sli.dev/)
- Fuente de odio [Cruzcampo](https://www.cruzcampo.es/)