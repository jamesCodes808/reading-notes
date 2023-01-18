# CSS Layout

## Class 7

### CSS: Flexbox
- Flexbox is designed for one-dimensional content. Explain what this means.

One-dimensional content means that the content has an x-axis and a y-axis. It is designed to provide a layout for this type of content. It does not provide solutions for the z-axis that I know of.

- Explain the difference between the main axis and cross axis.

The main axis is set by `flex-direction`. It can either be along the `row` or the `column`. 

The cross-axis would be the opposite of the main axis `flex-direction`. 

If main axis' `flex-direction`'s property was set to `row`, then cross axis' `flex-direction` will be set to `column`.

- How can using certain properties of flexbox negatively impact accessibility?

Some properties of `flex-direction` such as `row-reverse` or `column-reverse` only reorders content visually not logically for screen readers, making users with accessibility issues have to navigate backwards.

### CSS: Layout-Flexbox

- What are some advantages of using flexbox over float?

Compared to `flexbox`, `float` is limiting when it comes to layout designing, centering blocks of content inside of a parent container, getting equal width and heights on children content and making all columns in a multiple-column layout adopt the same height.

- How does this topic connect with your long term goals?

Some of my long term goals are to be in a full stack dev role. I want to create beautiful, accessible and easy to follow web applications and UI, so learning about `flexbox` and using that in my future code over floats and positioning, will help me achieve that.

>References
>
>[Learn CSS - Flexbox](https://web.dev/learn/css/flexbox/)
>
>[Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

### Things I want to know more about
- I want to know how to implement flexbox to my layout styling
- Can you use flexbox AND floats/positions?