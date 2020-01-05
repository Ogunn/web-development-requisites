# Shallow Rendering API

Shallow rendering is useful to constrain yourself to testing a component as a unit, and to ensure that your tests arent indirectly asserting on behavior of child components.

As of Enzyme v3, the `shallow` API does call React lifecycle methods such as `componentDidMount` and `componentDidUpdate`. You can read more about this in the version 3 migration guide.

## `shallow(node[, options]) => ShallowWrapper`

### Arguments

1. `node` (`ReactElement`): The node to render

2. `options` (`Object` [optional]):

   - `options.context`:(`Objetc` [optional]): Context to be passed into the component.

   - `options.disableLifecycleMethods`: (`boolean` [optional]): If set to true, `componentDidMount` is not called on the component, and `componentDidUpdate` is not called after `setProps` and `setContext`. Default to `false`.

   - `options.wrappingComponent`: (`ComponentType` [optional]): A component that will render as a parent of the `node`. It can be used to provide context to the `node`, among other things. See the `getWrappingComponent()` docs for an example.

     Note: `wrappingComponent` <em>must</em> render its children.

# ShallowWrapper API

`.find(selector) => ShallowWrapper`

Find every node in the render tree that matches the provided selector.

`.findWhere(predicate) => ShallowWrapper`

Find every node in the rander tree that returns true for the provided predicate function.

`.filter(selector) => ShallowWrapper`

Remove nodes in the current wrapper that do not matche the provided selector.

`.filterWhere(predicate) => ShallowWrapper`

Remove nodes in the current wrapper that do not return true for the provided predicate function.

`.hostNode() => ShallowWrapper`

Remove nodes that are not host nodes; e.g., this will only return HTML nodes.

`.contains(nodeOfNodes) => Boolean`

Returns whether or not a given node or array of nodes is somewhere in the render tree.
