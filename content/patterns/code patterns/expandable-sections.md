+++
title = "Expandable sections"
weight = 1
toc = true
+++

# Accordion Menus
Accordion menus are everywhere we look on the web. With such ubiquity, you'd expect that there would be a pretty well defined standard for constructing these components. Well, there's not. So when it comes to making accordion menus accessible, things can get tricky. While the functionality and HTML markup for accordions is pretty straightforward, some implementations are overly complex. Let's take a look at the intended functionality of an accordion menu before we look under the hood.

## Use Case: Why an accordion?

Accordion menus and collapsible regions are great ways to conserve screen space on your website. It is a design element that expands in place to reveal hidden information. They allow the user to get a quick overview of the content on the page. This is especially helpful on mobile devices, where screen size is limited. Accordion menus can become unwieldy very fast, as they can push other content out of view as they expand.

### Accordions are great for:
 - Navigation Menus
 - Forms with multiple sections
 - Polka


## Code patterns

There are a number of ways to construct an accordion menu. Below, we provide some common accordion menu patterns with accessibility friendly features.

## HTML Details Element

What's that? An HTML accordion you say? Yup! It's called the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details">HTML Details Element.</a>
{{<demo>}}
<details>
  <summary>OOOH, WHAT'S IN THERE?</summary>
  <p>IT'S A PUPPY!</p>
  <img src="{{site.baseurl}}/assets/images/this is fine.gif" alt="dog sits in burning house drinking coffee saying, this is fine"/>
</details>
{{</demo>}}

```html
<details>
  <summary>OOOH, WHAT'S IN THERE?</summary>
  <p>IT'S A PUPPY!</p>
  <img src="{{site.baseurl}}/assets/images/this is fine.gif" alt="dog sits in burning house drinking coffee saying, this is fine"/>
</details>
```
{{% note %}}
As of July 2020, it's accessible out of the box -- although I did notice in my testing that the "expanded" and "collapsed" states are not toggled when there is no SUMMARY element nested in the DETIALS element.
{{% /note %}}

{{% snippet file="details.md" %}}

{{% snippet file="visually-hidden.md" %}}

The DETAILS element supports the TOGGLE event, so adding more functionality to it is pretty straightforward.
```JS
details.addEventListener("toggle", event => {
  if (details.open) {
    /* the element was toggled open */
    //do awesome thing!
    } else {
      /* the element was toggled closed */
      // undo awesome thing
    }
  });
```


