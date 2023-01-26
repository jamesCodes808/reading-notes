# CSS Transitions and Animations

## CSS Transforms

- What does a CSS transform allow the developer to do to an element?

A CSS transform allows the developer to size, position, distort, rotate, scale and even make a 2D element appear as if it were 3D. 

- Provide an example of a transform and how you could see that being used on a website.

I could see transform being used to center an element in its parent, or transform its size based on the parent. It can also be used to create a text bubble like on smart phone messages. Or rotate images and have text appear behind them, kind of like a flash card. Here is an example of a text bubble.

```html 
<!-- html -->
<div class="box">
  <div class="box-content">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam
  </div>
</div>

```

```css
/* css */
html {
  font-size: 20px;
}

.box {
  width: 10rem;
  background-color: #e0e0e0;
  padding: 1rem;
  margin: 1rem;
  border-radius: 1rem;
  position: relative;
}

.box::before {
  content: '';
  width: 1rem;
  height: 1rem;
  background-color: #e0e0e0;
  overflow: hidden;
  position: absolute;
  right: -0.5rem;
  top: 50%;
  margin-top: -0.5rem;
  transform: rotate(45deg);
}

.box-content {
  position: relative;
  z-index: 2;
}

```


## CSS Transitions & Animations

- What does a CSS transition allow the developer to do to an element?

Transitions can work with transforms or any type of change in the element, and allow it to transition to that changing property with a different state such as `:hover`.

- How does a CSS animation differ from a CSS transition?

CSS transitions are good for single state changes, like a `:hover` or `:focus`, changing properties of an element and CSS animations are better for transitioning CSS properties in multiple state changes, such as moving an element at 50% of its animation-duration, then again at 75%, then again at 100%.

## CSS Transitions to wow users

- What are some benefits to using CSS transitions on websites?

Some benefits of using CSS transitions and animations on websites is the effect it has on the users. When seeing that a website is more than just static, and more animated, users will engage with that web site or application more and it will draw more traffic.

- How this topic fit in with your long-term goals?

I am definitely going to use more transitions and animations in my web applications just to increase its interactivity and engagement. I personally would prefer a website that has subtle smooth animations over one that is completely static and bland. 

>References
>
>[Transforms](https://learn.shayhowe.com/advanced-html-css/css-transforms/)
>
>[CSS Transitions & Animations](https://learn.shayhowe.com/advanced-html-css/transitions-animations/)
>
>[8 simple CSS3 transitions that will wow your users](http://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users)

## Things I want to know more about

- After looking at some of the examples of CSS transitions and animations, I definitely want to learn more about it and how to implement them.

- I want to learn about more CSS properties 