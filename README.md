# react-docgen-annotation-resolver

Parse `@component` annotated export as a react component.

Built with [`styleguidist`][sg] [`styled-components`][sc] in mind.

## *BETA*
While this does add exported paths with the `@component` annotation to
react-docgen, react-docgen is not able to grab properties off those components.
This does not actually work for styled-components yet.

## Usage with `styled-components` and `styleguidist`

`yarn add react-docgen-annotation-resolver`

Add the resolver to the styleguidist configuration

```
// styleguide.config.js
const resolver = require('react-docgen-annotation-resolver').default;

module.exports = {
  resolver,
  // Rest of config
}
```

Only exports marked with the `@component` or `@components` annotation will be
exported.

```
// MyComponent.js
import styled from 'styled-components';

const MyComponent = styled.div`
`;

// @component
export default MyComponent;
```

Again, this isn't actually working yet due to how `react-docgen` parses these
component definitions.


[sg]: https://react-styleguidist.js.org/
[sc]: https://styled-components.com
