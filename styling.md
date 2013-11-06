Overview
========
Styling are done with [SASS](http://sass-lang.com/) using the SCSS syntax.

## Selector rules
- Don't use IDs, like: `#header`
- No overqualifing, like: `div.foo`
- No universal selectors, like: `*`. The only exception is for styles that should apply to **all** elements, such as `* { box-sizing: border-box }`. See [Googles 'Use Efficient CSS selectors'](https://developers.google.com/speed/docs/best-practices/rendering?hl=de-DE&csw=1#UseEfficientCSSSelectors)

## Coding Style
- Use tabs for indent
- Put spaces after `:` in property declarations
- Use hex color codes `#fff` unless using rgba
- One selector per line, one rule per line
- No unit on zero values.

Lets look at an example:
```css
// This is a great example.
.first-component,
.second-component {
    margin: 0;
    color: #fff;
    background: rgba(0,0,0,0.5);
}
```

## SCSS Style
- Do not nest your styles deeper than 3 levels. If you need deeper nesting, then you are probably doing something wrong and should consider refactoring your code.
- Partial files begins with an underscore to prevent compilation to css.

## Components
Components are reusable parts of your page. Components should be movable within your page without breaking. Component rules should not contain id or element selectors, sticking to only class names. This is to prevent problems with child elements etc. when project complexity grows. Component names with multiple words should be split by a dash `.my-btn`

### Component elements
Component elements are sub elements belonging to a component. A component panel may have sub elements like header and body. Component elements receive their own class composed of the component name and the sub component name, separated by double underscore, like: `.panel__header` and `.panel__body`.

### Component variants
Components often has variants that differ from the base component, e.g., different color or size. 

Use the multi-class pattern to style variant. A component should have a base class and one or more variant classes to be used together with the base class. Example: A button component (`.button`) with a bordered variant (`.button--bordered`) is styled by applying both classes: `<a class="button button--bordered">`. 

## States
States are applied to elements to put them in a state. They usally implies coupling to script code that can change the state. State rules are prefixed with is-. Examples are `.is-active` for tabs when selected, or `.is-hidden` for collapsed elements.

## Naming convensions
Using different naming convensions for components, component elements and component variants makes it easy to distinguish them in the HTML. Use names that are easily understood, do not worry about class name length and file size, HTTP Compression (gzip) have you covered.

Summing up the naming convensions:
- Component names with multiple words are split by a single dash, like: `.my-btn`
- Component elements are separated from the component by double underscores, like: `.my-btn__icon`
- Component variants are separated from the component by double dashes, like: `.my-btn--huge`
- State rules should begin with is-, like: `.is-active`

## File Structure
```
stylesheets
|-- base                      // your basics
|     |-- _base.scss          // this is your base styling. Ex: a { cursor: pointer }
|     |-- _vars.scss          // global variables for your site
|-- mixins                    // global mixins
|     |-- _clearfix.scss 
|     |-- _border-radius.scss
|-- components                // reusable components
|     |-- _panel.scss
|     |-- _color-indicator.scss
|-- style.scss                // this is the main style file, which includes partials.
|-- style-admin.scss          // another style file for a different part of the site.
```

## Comments
TODO

## Links
Great tools:
- [AutoPrefixer](https://github.com/ai/autoprefixer) forget those prefix 
- [grunt-autoprefixer](https://github.com/nDmitry/grunt-autoprefixer) autoprefixer for grunt

## Inspiration
These pages has provided me great inspiration:
- [CSS-Tricks - Sass Style Guide](http://css-tricks.com/sass-style-guide/)
- [CSS-Tricks - CSS Style Guide](http://css-tricks.com/css-style-guides/)
- [GitHub - CSS Style Guide](https://github.com/styleguide/css)
- [Scalable and Modular Architecture for CSS](http://smacss.com/)
- [A style-guide for modular SASS development using SMACSS and BEM](https://medium.com/objects-in-space/f6f404727)



