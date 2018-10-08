# HTML Semantic
Essencial for SEO's and assistive technologies


## Applied Accessibility

###  div, section, article 
Wrap Content 

```<div>``` - groups content
```<section>``` - groups related content
```<article>``` - groups independent, self-contained content


### alt 
Add a Text Alternative to Images for Visually Impaired Accessibility 

```<img src="cat.jpeg" alt="My cat description">``` - should provide a correspondent description for image. 

### header 
Make Screen Reader Navigation Easier with the header Landmark 

```<header>``` - allows assistive technologies to quickly navigate to that content. Take place in the top of <body>


### nav 
Make Screen Reader Navigation Easier with the nav Landmark 

```<nav>``` - this tag is meant to wrap around the main navigation links in your page. Use it instead of div


### footer 
Make Screen Reader Navigation Easier with the footer Landmark 

```<footer>``` - it's primarily used to contain copyright information or links to related documents that usually sit at the bottom of a page.


### audio 
Improve Accessibility of Audio Content with the audio Element 

```<audio controls>``` - wraps sound or audio stream content in your markup. Audio content also needs a text alternative to be accessible to people who are deaf or hard of hearing. 
  Example:
  ```
    <audio id="myClip" controls>
      <source src="audio/myClip.mp3" type="audio/mpeg" />
    </audio>
```

### figure / figcaption 
Improve Chart Accessibility with the figure Element 

```<figure> <figcaption>``` - used together, these items wrap a visual representation (like an image, diagram, or chart) along with its caption. 
Example:
```
<figure>
  <img src="roundhouseDestruction.jpeg" alt="Photo of Camper Cat executing a roundhouse kick">
  <br>
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```

### fieldset / legend 
Wrap Radio Buttons in a fieldset Element for Better Accessibility 

```<fieldset> <legend>``` - fieldset tag surrounds the entire grouping of radio buttons to achieve this. It often uses a legend tag to provide a description for the grouping
Example:
```
<form>
  <fieldset>
    <legend>Choose one of these three items:</legend>
    <input id="one" type="radio" name="items" value="one">
    <label for="one">Choice One</label><br>
    <input id="two" type="radio" name="items" value="two">
    <label for="two">Choice Two</label><br>
    <input id="three" type="radio" name="items" value="three">
    <label for="three">Choice Three</label>
  </fieldset>
</form>
```
### time / datetime
Standardize Times with the HTML5 datetime Attribute

<time datetime=""> - attributes to standardize times. This is an inline element that can wrap a date or time on a page.

Example:
```<time datetime="20160-09-15">Thursday, September 15<sup>th</sup></time>```

### access-key
Make Links Navigatable with HTML Access Keys

accesskey - attribute to specify a shortcut key to activate or bring focus to an element. This can make navigation more efficient for keyboard-only users.

Example:
```<button accesskey="b">Important Button</button>```

Note: The way of accessing the shortcut key is varying in different browsers, but usually it is ```Alt```
#### Credits - [freeCodeCamp](https://www.freecodecamp.org/)