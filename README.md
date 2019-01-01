<h1 align="center"> SASS Startend - Bidirectional CSS</h1>

<p align="center"> Handy mixins for bidirectional css inspired by flex-start &amp; flex-end behavior. </p>

<hr/>

ℹ️ Input
```sass
div
  +padding-start(5px)
  +padding-end(10px)
  +margin-start(5px)
  +margin-end(10px)
```

🅾️ Output: ltr
```css
div {
  padding-left: 5px;
  padding-right: 10px;
  margin-left: 5px;
  margin-right: 10px;
}
```

🅾️ Output: rtl
```css
div {
  padding-right: 5px;
  padding-left: 10px;
  margin-right: 5px;
  margin-left: 10px;
}
```

🅾️ Output: bidi
```css
html[dir='ltr'] div {
  padding-left: 5px;
  padding-right: 10px;
}

html[dir='rtl'] div {
  padding-left: 10px;
  padding-right: 5px;
}

html[dir='ltr'] div {
  margin-left: 5px;
  margin-right: 10px;
}

html[dir='rtl'] div {
  margin-left: 10px;
  margin-right: 5px; 
}
```

<h3> Installation </h3>

```shell
$ yarn add sass-startend
```

<h3> Usage </h3>

To produce a single CSS for both LTR & RTL (You must specifiy direction in your html `<html dir="rtl">`):
```sass
@import "~sass-startend/mixins/bidirectional"

// Your sass here
```

To produce a single CSS for each direction (You must have 2 entry files):

```sass
// RTL

$direction: rtl;
@import "~sass-startend/mixins/monodirectional"

// Your sass here
```

```sass
// LTR

$direction: ltr;
@import "~sass-startend/mixins/monodirectional"

// Your sass here
```

<p>
Still confused? Take a look at bidi.sass, ltr.sass & rtl.sass in this repo.
</p>

<h3>License</h3>

This project is licensed under the MIT License
