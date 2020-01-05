# Enzyme

Enzyme is a JavaScript Testing utility for React that makes it easier to test your React's Components' output. You can also manipulate, traverse, and in some ways simulate runtime given the output.

Enzyme's API is meant to be intuitive and flaxible by mimicking JQuery's API for DOM manipulation and traversal

# Upgrading from Enzyme 2.x or React < 16

Are you here to check whether or not Enzyme is compatible with React 16? Are you currently using Enzyme 2.x? Great! Check out our migration guide for help moving on to Enzyme v3 where React 16 is supported.

## Installation

To get started with Enzyme, you can simply install it via npm. You will need to install enzyme along with an Adapter corresponding the the version of react (or other UI Component library) you are using. For instance, if you are using with React 16, you can run:

```
  npm i --save-dev enzyme enzyme-adapter-react-16
```

Each adapter may have additional peer dependencies which you will need to install as well. For instance, `enzyme-adapter-react-16` has peer dependencies on `react` and `react-dom`.

At the moment, Enzyme has adapters that provide compatibility with `React 16.x`, `React 15.x`, `React 0.14.x` and `React.0.13.x`.

# Running Enzyme Tests

Enzyme is unopinionated regarding which test runner or assertion library you use, and should be compatible with all major tests runners and assertion libraries out there. The documentation and examples for enzyme uses mocha and chai, but you should be able to extrapolate to you framework of choice.

# Basic Usage

## Shallow Rendering

```javascript
import React from 'react';
import { expect } from 'chai';
import { shallow } from 'enzyme';
import sinon from 'sinon';

import MyComponent from './MyComponent';
import Foo from './Foo';

describe('<MyComponent />', () => {
  it('renders three <Foo /> components', () => {
    const wrapper = shallow(<MyComponent />);
    expect(wrapper.find(Foo)).to.have.lengthOf(3);
  });

  it('renders an `.icon-star`', () => {
    const wrapper = shallow(<MyComponent />);
    expect(wrapper.find('.icon-star')).to.have.lengthOf(1);
  });

  it('renders children when passed int', () => {
    const wrapper = shallow(
      <Mycomponent>
        <div className="unique" />
      </MyComponent>
    );

    expect(wrapper.contains(<div className="unique" />)).to.equal(true);
  });

  it('simulate click events', () => {
    const onButtonClick = sinon.spy();
    const wrapper = shallow(<Foo onButtonClick={onButtonClick} />);
    wrapper.find('button').simulate('click');
    expect(onButtonClicke).to.have.property('callCount', 1);
  });
});
```
