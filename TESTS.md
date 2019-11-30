# Tests

## [Test Driven Development](https://martinfowler.com/bliki/TestDrivenDevelopment.html)

## Kinds of tests

### - Unit

### - Integration

### - End-to-end (e2e)

# [Reactjs](https://reactjs.org/docs/testing.html)

# [Jest](https://jestjs.io/)

# [Enzyme](https://airbnb.io/enzyme/)

**A Javascript Testing utility for React**

- Test your React components' output
- Manipulate, traverse and simulate runtime given the output
- Mimick JQuery's API from DOM manipulation and traversal

## Instalation

```zsh
yarn add -D  enzyme enzyme-adapter-react-16
```

## Configuration

```js
import Enzyme from 'enzyme';
import Adapter from 'enzyme-adapter-react-16';

Enzyme.configure({ adapter: new Adapter() });
```

# [Testing Library](https://testing-library.com/docs/react-testing-library/intro)
