# Enzyme Selectors

Many methods in Enzyme's API accept a <em>selector</em> as an argument. You can select several diferent ways:

## 1. A Valid CSS Selector

Enzyme supports a subset of valid CSS selectors to find nodes inside a render tree. Suport is as follows:

- class syntax (`.foo`, ``.foo-bar`, etc.)
- element tag name syntax (`input`, `div`, `span`, etc.)
- id syntax (`#foo`, `#foo-bar`, etc.)
- attribute syntax (`[href="foo"]`, `[type="text"]`, and the other attibute selectors listed [here](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Attribute_selectors))
- universal syntax (`*`)
- React component name and props (`Button`, `Button[type="submit"]`, etc.) - however, please note that it is strongly encouraged to find by component constructor/function and not by display name.
