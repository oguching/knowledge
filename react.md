React is a JavaScript library for building User Interfaces.

### component based

```JSX
  var HelloMessage = React.createClass({
    render: function() {
      return(
        <div> Hello Nurse! </div>
      )
    }
  })
  
  ReactDOM.render( <HelloMessage />, document.getElementById('container'))
```

Here we are creating a `HelloMessage` component using JSX.  
In the render method, you’ll return what you want React to draw on the page.  
ReactDOM accepts two arguments: the UI object, in this case `<HellowMessage>` and the DOM object, in this case `document.getElementById('container')`

### Props and State
Props are passed down from components higher up in the hierarchy.

```JSX
var BUTTONTEXT = 'you want to err click ze button?'

var ButtonForm = React.createClass({
  render: function() {
    return(
      <div>
        <h3>{this.props.text}</h3>
        <input type="submit" />
      </div>
    )
  }
})

var App = React.createClass({
  render: function() {
    return(
      <div>
        <h1>Welcome to my Button App!</h1>
        <ButtonForm text={this.props.text} />
      </div>
    )
  }
})

ReactDOM.render(<App text={BUTTONTEXT} />, document.getElementById('container'))
```

Another way of storing data in React is in the component's state. Unlike props-which are immutable from the compoents perspective - 
the state is mutable. So if you want the data in your app to change - for example based on user interractions - it must be stored
in a component's state somewhere in the app.

State must be initialized. We use `getInitialState()` for this. To initialize we simply pass a `getInitialState()` to the 
component, and return whatever state you want your component to be initialized with. To modify state, simply call `this.setState()`
passing in the new state as the argument.

```JSX
  var App = React.createClass({
    getInitialState: function() {
      return {
        active: true
      }
    },
    
    handleClick: function() {
      this.setState({
        active: !this.state.active
      })
    },
    
    render: function() {
      var buttonSwitch = this.state.active ? "on" : "off"
      
      return (
        <div>
          <p>Click ze button</p>
          <input type="submit" onClick={this.handleClick} />
          <p>{buttonSwitch}</p>
        </div>
      )
    }
  })  
  
  ReactDOM.render(<App />, document.getElementById("content"))
```

### Gotchas
* The component name must be capitalised. I tried `var helloMessage = ... ReactDOM.render(<helloMessage /> ...` and it didn't work.
* With JSX, on `render()`, there must be exactly one outer-most tag inside `return (...)`.

So the following code does not work because there's zero outermost tag:
```JSX
  return( Hello Nurse! )
```

This also doesn't work because there's more than one outermost tag:
```JSX
  return(
    <span> Hello </span>
    <span> Nurse! </span>
  )
```

What we can do is wrap the `span` tags in a `div` and it would be fine
```JSX
  return(
    <div>
      <span> Hello </span>
      <span> Nurse! </span>
    </div>
  )
```

* JSX is basically XML so be sure to close your tags. `<br>` won't do. `<br />` is better.

Sources:  
[Learn React in 7 Minutes](https://medium.com/learning-new-stuff/learn-react-js-in-7-min-92a1ef023003#.w2w6eo9uj)  
[Building your first React App](https://medium.com/learning-new-stuff/building-your-first-react-js-app-d53b0c98dc#.uu77ljaci)
