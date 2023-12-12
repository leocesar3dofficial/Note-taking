# React Code-Splitting

## Bundling

Most React apps will have their files “bundled” using tools like Webpack, Rollup, or Browserify. Automatic Webpack setup can be achieved by using tools like Create React App, Next.js, Gatsby, or similar tools.

## Dynamic `import()`

When Webpack comes across this syntax, it automatically starts code-splitting your app.

### Example

```javascript
import("./math").then(math => {
  console.log(math.add(16, 26));
});
```

## `React.lazy` and Error Boundaries

```javascript
import React, { Suspense } from 'react';
import MyErrorBoundary from './MyErrorBoundary';

// Only supports default exports
const OtherComponent = React.lazy(() => import('./OtherComponent'));
const AnotherComponent = React.lazy(() => import('./AnotherComponent'));

const MyComponent = () => (
  <div>
    <MyErrorBoundary>
      <Suspense fallback={<div>Loading...</div>}>
        <section>
          <OtherComponent />
          <AnotherComponent />
        </section>
      </Suspense>
    </MyErrorBoundary>
  </div>
);
```

## Route-based Code Splitting

```javascript
import React, { Suspense, lazy } from 'react';
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';

const Home = lazy(() => import('./routes/Home'));
const About = lazy(() => import('./routes/About'));

const App = () => (
  <Router>
    <Suspense fallback={<div>Loading...</div>}>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </Suspense>
  </Router>
);
```

## Named Exports

### `ManyComponents.js`

```javascript
export const MyComponent = /* ... */;
export const MyUnusedComponent = /* ... */;
```

### `MyComponent.js`

```javascript
export { MyComponent as default } from "./ManyComponents.js";
```

### `MyApp.js`

```javascript
import React, { lazy } from 'react';
const MyComponent = lazy(() => import("./MyComponent.js"));
```