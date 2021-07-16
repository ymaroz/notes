# Front End Testing Tools

We use `jest` for running tests and currently are using a combination of `enzyme` and `react-test-renderer` (in the future we may introduce a combination of `@testing-library/jest-dom/extend-expect` and `@testing-library/react` as well) to configure our assertions. We also occasionally use the `waait` package to simulate delays. We are using a few different techniques to test our components.

## General Testing Strategy

All React tests should at a minimum have snapshot tests that cover the possible "states" (not to be confused with React's state) in which the component can be rendered. For example if a component can be loading, loaded or in-error, there should be snapshot for each; if a component can be rendered as open or closed, there should be snapshots of each. This alone will often "fully cover" a component. However, sometimes there can be 100% coverage on a file, but certain edge cases have not been identified. In that case, it's on the developer to use other strategies to test that case, some of these strategies are mentioned below, but if you have aditional strategies, please contribute them.

## Rendering Techniques

We use three main techniques for rendering our React components for our test runner to consume.

### Shallow Rendering

Shallow rendering will only ever render the top level component. It will never render any children components (so wrapping it with Providers won't get you anywhere). In our repositories you will see shallow rendering accomplished by either using `enzyme`'s `shallow` module or a test-util called `shallowRender` which is based on `react-test-renderer`'s `shallow` module. There are some difference's in assetions that can be made based on which `shallow` is used, but the underlying behavior (rendering the top level component) remains consistent.

### Partial Rendering

### Full Rendering
