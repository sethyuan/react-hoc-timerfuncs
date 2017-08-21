# react-hoc-timerfuncs

This HOC (Higher Order Component) provides the following timer like functions
via props that will automatically be cleared when component gets unmounted.
Can be used with both React and React Native.

- setTimeout
- setInterval
- setImmediate
- requestAnimationFrame
- clearTimeout
- clearInterval
- clearImmediate
- cancelAnimationFrame

## Installation

```bash
yarn add react-hoc-timerfuncs
```

## Example

```js
// ...
import timer from "react-hoc-timerfuncs"

@timer
class Counter extends React.Component {
  state = {
    counter: 0
  }

  render() {
    return (
      <div>{this.state.counter}</div>
    )
  }

  componentDidMount() {
    // Instead of standard functions you will use the functions
    // provided by props.
    this.props.setInterval(() => {
      this.setState(state => ({ counter: counter + 1 }))
    }, 10)
  }
}
```

## Dev setup

1. `yarn`

### npm run tasks

- **yarn build**: Transpile source code
