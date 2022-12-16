# Stylize everything with CSS

## Class 5 - Design web pages with CSS

CSS stands for Cascading Style Sheets. It's a stylesheet language that is used to describe the look and formatting of a document written in a markup language. CSS is most often used to style web pages written in HTML and XHTML, but it can also be used with any kind of XML document, including SVG and XUL.

CSS allows you to apply styles, such as fonts, colors, and layout, to your web pages. This makes it easy to create consistent, attractive, and user-friendly websites.

Here's an example of some simple CSS syntax:

```css
    body {
    font-family: Arial, sans-serif;
    color: #333;
    }

    h1 {
    font-size: 24px;
    color: #000;
    }

    p {
    font-size: 16px;
    color: #666;
    line-height: 1.5;
    }
```

In this example, the body, h1, and p elements are being styled. 

>Syntax breakdown - **Selector {property: value}**

The body element is being given a font family of Arial and a color of #333 (a dark gray), the h1 element is being given a font size of 24px and a color of black, and the p element is being given a font size of 16px, a color of #666 (a lighter gray), and a line height of 1.5.

### There are Three ways to add CSS to your markup document:

- External CSS - You can `<link>` an external .css file in the `<head>` of an HTML page

- Internal CSS - You can add CSS properties in a `<style>` `</style>` element, located in the head section of an HTML page

- Inline CSS - You can apply the `style` attribute directly to the HTML element

>References
>
>[What is CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/What_is_CSS)
>
>[How to Add CSS](https://www.w3schools.com/css/css_howto.asp)
>
>[CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
>

>>Tools
>>[Reset CSS to reduce browser inconsistencies](https://meyerweb.com/eric/tools/css/reset/)



## Things I want to know more about
- Animations in CSS
- Transitions
- Creating really cool stuff