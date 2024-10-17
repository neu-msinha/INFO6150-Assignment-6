# Assignment: Two-Page Website Using CSS Grid, Flexbox, and SCSS Features

## Overview
This assignment is designed to demonstrate the use of **CSS Grid layout**, **Flexbox**, and **SASS/SCSS** in building a two-page website. The site uses a combination of modern CSS techniques and advanced SCSS features to create a responsive, visually rich user interface.

### Features Implemented:
1. **CSS Grid Layout**: Applied in two areas to organize content into a structured, responsive grid.
2. **Flexbox Layout**: Used to arrange flexible, adaptable layouts across various sections for improved alignment and distribution of elements.
3. **SASS/SCSS Features**: The project leverages multiple SCSS features including variables, custom properties, nesting, interpolation, placeholder selectors, mixins, and functions. Additional SCSS features such as loops and conditionals are also implemented to enhance code efficiency.

---

## SCSS Features Implemented

### 1. **Variables**
SCSS variables are defined to store colors, font sizes, and padding values for consistency and easier maintenance.
- **Example**:
    ```scss
    $primary-color: #333;
    $secondary-color: rgba(255, 255, 255, 0.9);
    $font-size-xl: 2rem;
    $padding-lg: 5rem;
    ```

### 2. **Custom Properties (CSS Variables)**
Custom properties are defined in the `:root` to allow theme flexibility and easy adjustments across the site.
- **Example**:
    ```scss
    :root {
        --primary-color: #333;
        --secondary-color: rgba(255, 255, 255, 0.9);
        --slide-duration: 20s;
    }
    ```

### 3. **Nesting**
SCSS nesting is used to group related styles for better code organization and readability.
- **Example**:
    ```scss
    .slideshow-slide {
        position: absolute;
        
        img {
            width: inherit;
            height: inherit;
            object-fit: cover;
        }
    }
    ```

### 4. **Interpolation**
Interpolation is used to dynamically generate class names and insert variables into CSS properties.
- **Example**:
    ```scss
    .slideshow-slide:nth-child(#{nth($item, 1)}) {
        animation-delay: nth($item, 2);
    }
    ```

### 5. **Placeholder Selectors**
Placeholder selectors are used for reusable blocks of styles, which are then extended by other elements.
- **Example**:
    ```scss
    %center-position {
        position: absolute;
        top: 0;
        left: 0;
        width: inherit;
        height: inherit;
    }

    .slideshow-slide {
        @extend %center-position;
    }
    ```

### 6. **Mixins**
Mixins are defined to create reusable, modular blocks of styles, particularly for responsive breakpoints.
- **Example**:
    ```scss
    @mixin response($size) {
        @if $size == xl {
            @media (max-width: 1200px) { @content; }
        }
    }
    ```

### 7. **Functions**
SCSS functions are utilized to retrieve values from maps, making the code more dynamic.
- **Example**:
    ```scss
    @function color($name) {
        @return map-get($colors, $name);
    }
    ```

### 8. **Loops**
Loops are used to iterate over a list of values, dynamically applying styles to multiple elements.
- **Example**:
    ```scss
    $animList: 1 0s, 2 4s, 3 8s, 4 12s, 5 16s;

    @each $item in $animList {
        .slideshow-slide:nth-child(#{nth($item, 1)}) {
            animation-delay: nth($item, 2);
        }
    }
    ```

### 9. **Conditionals**
Conditional statements are used within mixins to apply styles based on breakpoints.
- **Example**:
    ```scss
    @mixin response($size) {
        @if $size == xl {
            @media (max-width: 1200px) { @content; }
        }
    }
    ```

### 10. **Keyframes in SCSS**
Keyframe animations are written directly within SCSS to control the visibility and opacity of the slideshow slides. By utilizing SCSS, animations are modular and reusable.
- **Example**:
    ```scss
    @keyframes slideshow {
        0% {
            visibility: hidden;
            opacity: 0;
        }
        2% {
            visibility: visible;
            opacity: 1;
        }
        18% {
            visibility: visible;
            opacity: 1;
        }
        20% {
            visibility: hidden;
            opacity: 0;
        }
        100% {
            visibility: hidden;
            opacity: 0;
        }
    }
    ```

### 11. **Inheritance with `@extend`**
SCSS inheritance is used with `@extend` to allow multiple elements to share the same style by extending placeholder selectors. This promotes code reusability and efficiency.
- **Example**:
    ```scss
    %fade-animation {
        visibility: hidden;
        opacity: 0;
        transition: visibility 0.3s, opacity 0.3s;
    }

    .slideshow-slide {
        @extend %fade-animation;
    }
    ```

### 12. **Responsive Design Using Media Queries**
SCSS uses media queries inside the `response` mixin to adapt the layout based on screen size, ensuring the website is fully responsive.
- **Example**:
    ```scss
    @mixin response($size) {
        @if $size == xl {
            @media (max-width: 1200px) { @content; }
        } @else if $size == lg {
            @media (max-width: 992px) { @content; }
        }
        @else if $size == md {
            @media (max-width: 768px) { @content; }
        }
    }
    ```


---

## File Structure
The SCSS files are organized into multiple folders for maintainability, based on UI features and common elements:

