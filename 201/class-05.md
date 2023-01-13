# Images, Color, Text

## Class 05

### HTML Media
- What is a real world use case for the altattribute being used in a website?
A real world use case for the `alt` attribute in the `img` tag is for the image to be descriptive and for the screen reader to read out the description to a user if they are visually impaired. Another real world use case is for search engine optimization. 

- How can you improve accessibility of images in an HTML document?
One of the best practices for improving accessibility for images in HTML documents is to use very descriptive `alt` text as an attribute, try not to use the `title` attribute and using `<figures>` and a descriptive `<figcaption>`

- Provide an example of when the figureelement would be useful in an HTML document.
A `<figcaption>` would be useful in an HTML document when you have numerous amounts of images that need semantically linked captions to them, using `<figcaption>`.

- Describe the difference between a gif image and an svg image, pretend you are explaining to an elder in your community.
A gif (Graphics Interchange Format) image is a good choice for simple animations and images, 
<br>
An svg (Scalable Vector Graphics) image is good for user interface elements, icons, diagrams, etc., that must be drawn accurately at different sizes.
<br>
The differences between the two is that gifs are like mini animated clips of a movie or image you can place somewhere on a website that animate depending on how many frames there are and svg images are like drawings you can create with code commands that can scale with its canvas (the website)

- What image type would you use to display a screenshot on your website and why?
I would use PNG because it is a lossless image format that can render images and texts in a screenshot clearly. If I cared about it being compressed then Lossless WebP.

### CSS: Styling HTML Elements 
- Describe the difference between foreground and background colors of an HTML element, pretend you are talking to someone with no technical knowledge.
The difference between the foreground and the background colors is the layer that the color is applied to. If we have a line of texts, the foreground would be the color of the texts, the background would be the color behind the texts.

- Your friend asks you to give his colorless blog website a touch up. How would you use color to give his blog some character?
I would add some background-color, maybe give the title and heading a contrasting color to the background color that makes it stand out, and give certain sections of the website a border to visually seperate areas.

- What should you consider when choosing fonts for an HTML document?
You should consider the compatibility and readability of the font and font-family you are implementing. Make sure that the font has a safe universal font to fall back on if the initial custom font does not load for someone's browser.

- What do font-size, font-weight, and font-style do to HTML text elements?

```css
font-size: 2rem; /*font-size controls how big the font is, usually starting from a default of 16px */

font-weight: 100; /*font-weight controls how thick the font is, the boldness of the font. */

font-style: normal /* font-style is used to turn fonts italic or not. */

```

- Describe two ways you could add spacing around the characters displayed in an h1 element.
Two ways to add spacing vertically between characters are the properties `letter-spacing` and `word-spacing` which takes a numeric size value (`px`,`em`,`rem`,`%`).

>Resources
>
>[Images in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML)
>
>[Common Image Types](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
>
>[Image Formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#choosing_an_image_format)
>
>[Applying Color to HTML Elements Using CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Applying_color)
>[Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

### Things I want to learn more about
- I definitely want to get a better understanding of the CSS box model, and how it works with positioning
- The usage of image formats in real-world situations
