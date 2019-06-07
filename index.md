# PopcornJS

PopcornJS is a mini JavaScript library that is aimed at tackling lightweight reactive UI components. How will you benefit from PopcornJS? Imagine all the big libraries of frameworks out there running on webpacks, with NodeJS services running on the backend; would you really need those for a simple application? Or, would you really like to rewrite your entire application's frontend just for some added features?

Guess not, hence you stumble upon this library.

### Introduction

Let's get started. How do you use PopcornJS? Simple.

1. Download the zip of this git. Extract it.
2. Get index.js into your project.
3. Get popping.

## Creating a component

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

## Functions? Events? How??

If you want to get event-triggered functions, it will be slightly different from the usual convention. You would need to use kernels. A popcorn's prior state is a kernel... get it? So first off, get your kernel ready, before you can start popping.

#### Loading Kernels
```javascript
class Input extends Popcorn{
    loadKernel(){
        return {
            inputFn: (text) => {
                console.log(text);
            },
        }
    }
    
    render(){
        return `<input oninput="kernel.inputFn(this.value)">`
    }
}
```
Load up the `loadKernel` method, and return a object-based functions with it. Take note how the oninput is written to include the kernels. Now it's ready. Give it a try yourself.

## What? We have states?
Yes! Else how would it be reactive?

#### Initialise a component's state(s)
You can choose to, or not to. Entirely up to you, really. Do so if you need initial states for some magic.
```javascript
let exampleComponent = new ExampleComponent('.content',{
    message: 'Hello World',
    data: ['This', 'Is', 'PopcornJS']
});
```

#### Accessing states
Really simple. Everything is in `this.state`.
```javascript
class ExampleComponent extends Popcorn{
    render(){
        let dataStr;
        for(var i=0; i<this.state.data.length; i++){
            dataStr += `${this.state.data[i]} `
        }
        return(
            `
            <p>Hello ${this.state.message}</p>
            <p>Hello ${dataStr}</p>
            `
        )
    }
}
```

#### Setting states
```javascript
exampleComponent.setState({
    message: "Bye World",
    data: ['I', 'Shall', 'Sleep']
})
```
