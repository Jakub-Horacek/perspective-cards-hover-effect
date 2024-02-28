# ABOUT

This is a project showcasing a perspective cards hover effect. It is hosted [here](https://jakub-horacek.github.io/perspective-cards-hover-effect/).

## Description

The perspective cards hover effect is a visually appealing way to display information on a webpage. It creates a 3D effect when the user hovers over the cards, providing an interactive and engaging experience.

## Usage

If you'd like to use this effect in your own project, feel free to explore the code.
The `index.html` file contains the HTML markup for the cards, and the `style.css` file contains the CSS for the hover effect.

## Usage Demo

![Demo](gifs/demo.gif)

HTML:

```html
<!-- BARNEY CARD -->
<div class="card">
  <div class="wrapper">
    <img src="images/barney-background.jpeg" class="cover-image" />
  </div>
  <h2 class="title">Barney Stinson</h2>
  <img src="images/barney.png" class="character" />
</div>
```

CSS:

```css
:root {
  --card-height: 500px;
  --card-width: calc(var(--card-height) / 1.5);
  --highlight-color: #ffc83d;
}

.card {
  width: var(--card-width);
  height: var(--card-height);
  position: relative;
  display: flex;
  justify-content: center;
  align-items: flex-end;
  padding: 0 36px;
  perspective: 2500px;
  margin: 0 50px;
  cursor: pointer;
  transition: 0.2s;
}

.card:hover .wrapper {
  border: 4px solid var(--highlight-color);
  transform: perspective(900px) translateY(-5%) rotateX(25deg) translateZ(0);
  box-shadow: 2px 35px 32px -8px rgba(0, 0, 0, 0.75);
}

.wrapper::before,
.wrapper::after {
  content: "";
  opacity: 0;
  width: 100%;
  height: 80px;
  transition: all 0.5s;
  position: absolute;
  border-radius: 10px;
  left: 0;
}

.wrapper::before {
  top: 0;
  height: 100%;
  background-image: linear-gradient(
    to top,
    transparent 46%,
    rgba(12, 13, 19, 0.5) 68%,
    rgba(12, 13, 19) 97%
  );
}

.wrapper::after {
  bottom: 0;
  opacity: 1;
  background-image: linear-gradient(
    to bottom,
    transparent 46%,
    rgba(12, 13, 19, 0.5) 68%,
    rgba(12, 13, 19) 97%
  );
}

.card:hover .wrapper::before,
.wrapper::after {
  opacity: 1;
}

.card:hover .wrapper::after {
  height: 120px;
}

.card:hover .cover-image {
  filter: blur(2px);
}
```
