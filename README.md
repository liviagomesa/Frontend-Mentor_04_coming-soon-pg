# Frontend Mentor - Base Apparel coming soon page solution

This is a solution to the [Base Apparel coming soon page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/base-apparel-coming-soon-page-5d46b47f8db8a7063f9331a0). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page
- Receive an error message when the `form` is submitted if:
  - The `input` field is empty
  - The email address is not formatted correctly

### Screenshot

![](./screenshot.png)

### Links

- [Solution URL](https://github.com/liviagomesa/coming-soon-page)
- [Live Site URL](https://liviagomesa.github.io/coming-soon-page/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- JavaScript

### What I learned

1. I've learned how to validate forms through JavaScript:

```html
<!--- Code inserted within the page head --->
<script>
  function validateForm() {
    // Selecting user's input
    let input_email = document.forms["myForm"]["email"].value;
    // Creating a regular expression to validate an email (note that there's no quotation marks) - see detailed explanation in Useful resources below
    let regular_expression =
      /^[A-Za-z0-9_!#$%&'*+\/=?`{|}~^.-]+@[A-Za-z0-9.-]+$/gm;
    // Using test method with the regular expression and passing the value to validate as parameter
    let is_valid = regular_expression.test(input_email);
    if (!is_valid) {
      document.getElementById("validation-text").innerHTML =
        "Please provide a valid email";
      document.getElementById("validation-icon").style = "visibility: visible;";
      document.getElementById("form").style =
        "border: 3px solid hsl(0, 93%, 68%);";
    }
    return is_valid;
  }
</script>
<!--- form creation --->
<!--- before submitting, the code will verify validateForm() return value. If it's true, the form is submitted; else, it's not. --->
<!--- It's important to use "novalidate", otherwise the page will use html automatic validation --->
<form
  action="post"
  name="myForm"
  onsubmit="return validateForm()"
  novalidate
  id="form"
></form>
```

2. I've commented my css file identifying the parts of the code, from top to bottom. It was important because I've get a more organized code.

### Useful resources

- [Email Validation: Regex & JavaScript](https://www.abstractapi.com/guides/email-validation-regex-javascript) - Through this article, I've learned about regular expressions to validate my email inputs.

## Author

- Frontend Mentor - [@liviagomesa](https://www.frontendmentor.io/profile/liviagomesa)
- LinkedIn - [@liviagomesa](https://www.linkedin.com/in/liviagomesa/)
