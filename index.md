## PopcornJS

PopcornJS is a mini JavaScript library that is aimed at tackling lightweight reactive UI components. How will you benefit from PopcornJS? Imagine all the big libraries of frameworks out there running on webpacks, with NodeJS services running on the backend; would you really need those for a simple application? Or, would you really like to rewrite your entire application's frontend just for some added features?

Guess not, hence you stumble upon this library.

### Introduction

Let's get started. How do you use PopcornJS? Simple.

1. Download the zip of this git. Extract it.
2. Get index.js into your project.
3. Get popping.

### Creating a component

#### Firstly, create a simple Popcorn component
```javascript
class ExampleComponent extends Popcorn{
    render(){
        return(
            `
            <p>Hello ${this.state.message}</p>
            `
        )
    }
}
```

#### Next, get it into your `<script>`
```html
<html>
  <body>
    <div class="content"></div>
    
    <script>
      let input = new ExampleComponent('.content');
    </script>
  </body>
</html>
```
Your component is now ready and rendered into your HTML page.

#### That's it. Yeah, yeah I know. This shouldn't be just it. There's more. Keep reading.
