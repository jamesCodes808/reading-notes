# Audio, Video, Images

## Video and Audio Content

- Explain how the ability to use video and audio on the web has evolved since the early 2000s.

Since the 2000's we have evolved from using plug-in based technology such as flash and silverlight to using javascript APIs and HTML solutions with tags such as `<audio>` and `<video>`. Which provide for a more secure and accessible way to audio and video files on the web.

- Describe the use of the src and controls attributes in the `<video>` element.

src is the attribute used to get the URL of the video thats going to be embedded in the `<video>` element. You can also use the `<source>` element inside of a `<video>` element alternatively. 

the controls attribute, if present, will offer controls for the user to use on the videos such as volume, seeking and pause/resume play. 

- Why is it important to have fallback content inside the `<video>` element?

It is important to have fallback content inside of the `<video>` element because not all browsers and computers will be able to support the video playback, or the video format.

- Write a very short story where `<audio>` and `<video>` are characters.

The world was grey and lifeless. People would browse on web pages silently, not feeling any type of emotion during their browse. So then came along two friends, `<audio>` and `<video>`. They both loved to entertain people and had the ability to embed different kinds of entertainment to web pages for people to enjoy. `<video>` liked to be showy with their entertainment while `<audio>` liked to hide behind the screen and only let them listen to their entertainment. Both embedded themselves into these web pages and started to entertain people for decades and sometimes came with attributes to give the people control over their entertainment! The people were happy, they were dancing and so tuned in to the entertainment `<audio>` and `<video>` provided, color filled the world. The world has changed with `<audio>` and `<video>`'s embedding powers. 

## Grid

- How does Grid layout differ from Flex?

Flex or Flexbox is a layout tool that has a one-directional flow of either rows or columns. CSS Grid uses a grid to set the column and row sizes, put the items in that grid and then rearrange them based on the screen size. 

- Grid container, grid item, and grid line are a few important terms to understand when using Grid. Please describe these terms in a few sentences.

The grid container will be the parent container to all the grid items. Having the CSS property, `display: grid`.

Grid Items are ONLY the direct children in the grid container. 

Grid lines are the dividing lines that make up the structure of the grid. They can either be vertical(column grid lines) or horizontal(row grid lines).

## Responsive Images

- Besides making a site visually appealing across different screen sizes, why should developers make images responsive?

Images should be responsive because there are different types of devices with different screen sizes that could affect the size of the image. A 900px image on a 1200px wide screen will look fine but if that 900px image was on a mobile device with a 360px screen, it would be huge and almost impossible to navigate or tell what it is at first site. If the image were responsive, and shrunk as the screen size changed, it would be more user friendly. 

- Define the following `<img>` attributes srcset and sizes. Write an example of how they are used.

the `srcset` attribute usually comes with a set of images and set of sizes and will change to the image based on the size of the screen. When we give the `<img>` tag a `srcset` of images to use and a width to use them at we have to pair it with the `sizes` attribute. The sizes attribute will let the browser know how large of a space the image will be displaying in. In the example, we are saying that when a media conditions matches max-width of 600px, load the 200px wide image, in a 50vw (500px approx) otherwise, load the other images

Example:

```html

<img 
  alt="A picture of a picture frame"
  src="img/frame.jpg"
  srcset="
    frame-s.jpg 300w,
    frame-m.jpg 600w,
    frame-l.jpg 1200w,
    frame-xl.jpg 2000w"

    sizes="(max-width: 600px) 300px, 50vw"
>

```

- How is `srcset` more helpful for responsive images than CSS or JavaScript?

It is more helpful in a way because you are specifying to the `<img>` tag that there are different images to use at different widths which is more helpful for the user and accessibility and a lot easier to code. 

>References
>
>[Video and audio content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
>
>[A Complete Guide to CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

### Things I want to know more about

- After reading about srcset and sizes, I read about vw, vh, vmin, vmax and definitely want to learn more about these metrics of measurement. 
