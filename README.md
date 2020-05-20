# Tailwind: The future of CSS

In this talk [Amadou Sall](https://twitter.com/ahasall) gives an introduction to [Tailwindcss](https://tailwindcss.com/), a utility-first CSS framework for rapidly building custom designs.

Here's the talk [link](https://egghead.io/lessons/tailwind-egghead-talks-tailwind-the-future-of-css-is-here-amadou-sall) :video_camera:

Table Of Contents

- [Tailwind: The future of CSS](#tailwind-the-future-of-css)
  - [Key Takeaways from this talk](#key-takeaways-from-this-talk)
  - [Approaches when writing CSS](#approaches-when-writing-css)
  - [Why Tailwind is Awesome](#why-tailwind-is-awesome)
    - [Benefits](#benefits)
    - [Great Developer Experience](#great-developer-experience)
  - [Perceived barriers](#perceived-barriers)
  - [Challenges you might face](#challenges-you-might-face)

## Key Takeaways from this talk

- See Tailwind in action
- Benefits of using Tailwind and why it's awesome
- Perceived barriers
- Challenges faced when using Tailwind

## Approaches when writing CSS

When writing CSS, generally there are two ways:

- write your CSS from scratch
- use a CSS framework like [materialize](https://materializecss.com/), [bootstrap](https://getbootstrap.com/), [bulma](https://bulma.io/)

When styling a button using CSS you'll have something like this:

```css

.my-button{
    padding: .5rem 1rem;
    border-width: 1px;
    border-color: transparent;
    border-radius: .375rem;
    color:#fff;
    line-height: 1.25rem;
    font-weight: 500;
    background-color: #1413e9;
    cursor: pointer;
}

```

but you also need to add hover, focus, and active states to this element. So you'll do something like this:

```css
.my-button:hover,
.my-button:active {
    background-color: #3939e3;
}

.my-button: focus{
    outline:none;
    border-color:#3B67Bc;
}

```

With this approach:

- :white_check_mark: you're building custom designs
- :x: Time consuming
- :x: Not scalable
- :x: Unmaintainable
- :x: bad Code quality

The other approach is to use a CSS framework like Bootstrap

```html
<button class="btn btn-primary">My Button</button>
```

You need to add these two classes to every button.

This method is:

- :white_check_mark: productive, you don't spend a lot of time writing CSS
- :white_check_mark: no need to be a CSS expert, just add the classes and it works
- :white_check_mark: Code quality is high since you don't need to worry about naming conventions or repetitive code
- :x: UI monotony. All websites that use this framework will look the same.
- :x: Hard to customize. You must override styles

Tailwind is a utility first framework. It doesn't give you components like bootstrap, but it provides reusable CSS utility classes that you can use to build your UI.

Before seeing what Tailwind looks like, make sure that you keep an open mind because once you see how it's used, it will seem like a terrible idea at first. But once you start getting comfortable using Tailwind, you will only want to use it.

Amadou Sall gives a live coding session at [9:35](https://egghead.io/lessons/tailwind-egghead-talks-tailwind-the-future-of-css-is-here-amadou-sall/#t=570) during his talk.

Here's the link for the [documentation](https://tailwindcss.com/docs/installation) referenced in the talk.

Use NPM or Yarn to install Tailwind

```bash
# using npm
npm install tailwindcss

# using Yarn
yarn add tailwindcss

```

Add Tailwind to your CSS

```postcss

@tailwind base

@tailwind components

@tailwind utilities

```

PostCSS will be used for this file. It is like a compiler for CSS, that it will transform the directives to actual CSS

Here's what a button built using Tailwind looks like

```html
<div class="p-16">
 <button class="bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-pink-500">My Button</button>
</div>

```

Here's an explanation of what each class does:

**Padding**:

`p-16` adds padding to the top, right, bottom, and to the left of an HTML element.

`px-2` adds padding to the left and right

`py-2` adds padding to the top and bottom

**Background color**:

`bg-blue-500` is used to add the background color.
this class is made up of 2 parts:
`bg` to add a background color
`blue-500` the color name + it's shade. ( You can have blue-900 if you want a darker shade)

**color**:

The `text-white` class is used to change the text color. It also follows the same naming convention as the background color (`text-`color)

**border-radius**:

To add a border-radius you simply add the `rounded-lg` class

**Hover state**:

To add a hover state to an element, you simply add the hover `hover:` class.

The `hover:bg-pink-500` class will make the element's background color pink on hover.

Amadou gives another example of building a layout using Tailwind at [12:21](https://egghead.io/lessons/tailwind-egghead-talks-tailwind-the-future-of-css-is-here-amadou-sall/#t=741) in his talk

## Why Tailwind is Awesome

### Benefits

- It's a true design system. It allows you to define everything you need to create your own unique design system
- It's responsive to the core. You don't need to write media queries
- Highly customizable. You can tweak everything to your liking in the config file.
- You can build your own tailwind plugins.
- Smaller bundle size, which means your website will be faster. This is done by removing unused CSS

### Great Developer Experience

- You don't need to leave your HTML and work in a different CSS file.
- You don't worry about naming things.
- Allows you to rapidly prototype.
- Refactoring is easy. You don't need to care about deleting a CSS file.

## Perceived barriers

> But aren't we writing inline styles this way?

Not really, because you can easily customize the styles.

> Won't there be a lot of repetitions?

You can create components using tailwind and re-use them.

> The bundle size must be huge, right?

When used correctly, you don't need to worry about the bundle size.

## Challenges you might face

- You need to know CSS. However, it's a great opportunity to learn CSS through Tailwind.
- Framework integration is not straight forward.
- Internet Explorer isn't targeted by tailwind
- Working with CMS content is challenging. Since you don't have access to the HTML directly, you can't add your utility classes. Thankfully, tailwind provides directives that can be embedded inside CSS files.
