# Enzyme

- JavaScript testing utility framework
- Designed for testing React components

## Features

- Shallow rendering
- Help access business logic of react component
- Full DOM rendering
- Support `react-hooks` in shallow rendering, with some limitations

## shallow vs mount vs render

### shallow

- Lets you render a component `one level deep`
- Assert facts about what its render method returns, without worrying about the child component behavior
- Child components are not instantiated or rendered

### mount

- Use `mount` if `componentDidMount` or `componentDidUpdate`  need to be tested

### render

- Use `render` if you need to test children rendering with less overhead than `mount`
- Use `render` if you are not interested in lifecycle methods

## References

- [AirNb Shallow Rendering API](https://enzymejs.github.io/enzyme/docs/api/shallow.html)