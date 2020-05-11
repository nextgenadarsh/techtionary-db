# Enzyme

- Testing utility for ReactJs
- Make it easier to assert, manipulate, traverse React Component's output
- React TestUtils + JSON + CheerIO
- **NOT** a unit testing framework 
- Excludes Test Runner, Assertion Library
- not opinionated
- can be used within Jest
- Quite useful to write tests using assertions
- Does not allow to change the value of input elements. The `simulate` method is useful to simulate user actions.
- APIs: `shallow`, `mount`, `render`
- Querying Nodes: `find`, `findWhere`, `some`, `someWhere`, `first`, `at`, `html`, `text`
- Interaction: `simulate`, `setProps`, `setState`, `setContext`, `props()`, `props(key)`, `state(key)`, `context(key)`

```js
import { shallow} from 'enzyme'
const component = shallow(<Welcome />);
except(welcome.find('div').text()).toEqual("Hello world");
```

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


