# HTML Semantic
Essencial for SEO's and assistive technologies
### Credits - [freeCodeCamp](https://www.freecodecamp.org/)

## Applied Accessibility

*  Wrap Content (**div, section, article**)

```
<div> - groups content
<section> - groups related content
<article> - groups independent, self-contained content
```

* Add a Text Alternative to Images for Visually Impaired Accessibility (**alt**)
```
<img src="cat.jpeg" alt="My cat description"> - should provide a correspondent description for image. 
```

* Make Screen Reader Navigation Easier with the header Landmark (**header**)
```
<header> - allows assistive technologies to quickly navigate to that content. Take place in the top of <body>
```

* Make Screen Reader Navigation Easier with the nav Landmark (**nav**)
```
<nav> - this tag is meant to wrap around the main navigation links in your page. Use it instead of div
```

* Make Screen Reader Navigation Easier with the footer Landmark (**footer**)
```
  <footer> - it's primarily used to contain copyright information or links to related documents that usually sit at the bottom of a page.
```

* Improve Accessibility of Audio Content with the audio Element (**audio**)
```
<audio controls> - wraps sound or audio stream content in your markup. Audio content also needs a text alternative to be accessible to people who are deaf or hard of hearing. 
  Example:
    <audio id="myClip" controls>
      <source src="audio/myClip.mp3" type="audio/mpeg" />
    </audio>
```