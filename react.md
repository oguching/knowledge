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
ReactDOM accepts two arguments: the UI object, in this case `<HellowMessage>` and the DOM object, in this case `document.getElementById('container')`


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
