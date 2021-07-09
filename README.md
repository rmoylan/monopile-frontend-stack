# Frontend App
## [React](https://reactjs.org/)
A Javascript library for creating user interfaces. 
#### Example:
```js
import React from 'react';

function Button({onClick}) {
  return (
    <button className="square" onClick={onClick}>
      Hello World!
    </button>
  );
}
```
## [Nextjs](https://nextjs.org/)
Framework built on top of React that adds support for server rendering, bundling, routing, etc. When using the Typescript version of Nextjs, the bundler will handle the transpiling Typescript to Javascript.


## [Styled components](https://styled-components.com/)
CSS in JS solution.
#### Example:
```js
import styled from 'styled-components';

const Button = styled.button`
  background-color: #f00;
  padding: 1rem;
`;

render() {
  <Button>Hello world!</Button>
}
```


## [Material ui](https://material-ui.com/)
A library of themable React components
#### Example:
```js
import React from 'react';
import { Button } from '@material-ui/core';

function App() {
  return <Button color="primary">Hello World!</Button>;
}
```

## [React-Hook-Form](https://react-hook-form.com/) or [Formik](https://formik.org/)
Library for handling forms in React. 
Formik has been around longer, but React Hook Form seems to have a lot of push behind it(about 22k stars on Github), and is built using hooks so it should be the future. The handling of forms with React Hook Form is also very much like the traditional way of handling forms in HTML(on front end).
#### React Hook Form
```js
import * as React from "react";
import { useForm } from "react-hook-form";

export default function App() {
  const { register, handleSubmit } = useForm();
  const onSubmit = (data) => alert(JSON.stringify(data));

  return (
    <form onSubmit={handleSubmit(onSubmit)}>

      <input {...register("firstName")} placeholder="First name" />
      <input {...register("lastName")} placeholder="Last name" />
      <select {...register("category")}>
        <option value="">Select...</option>
        <option value="A">Category A</option>
        <option value="B">Category B</option>
      </select>

      <input type="submit" />
    </form>
  );
}
```
#### Formik
```js
import React from "react";
import ReactDOM from "react-dom";
import { Formik, Field, Form } from "formik";
import "./styles.css";

function App() {
  return (
    <div className="App">
      <h1>Contact Us</h1>
      <Formik
        initialValues={{ name: "", email: "" }}
        onSubmit={async values => {
          await new Promise(resolve => setTimeout(resolve, 500));
          alert(JSON.stringify(values, null, 2));
        }}
      >
        <Form>
          <Field name="name" type="text" />
          <Field name="email" type="email" />
          <button type="submit">Submit</button>
        </Form>
      </Formik>
    </div>
  );
}
```
## [Babel](https://babeljs.io/docs/en/) vs [Typescript](https://www.typescriptlang.org/)
These two are not directly comparable, but both do transpile code into production ready Javascript. 

Babel transpile new/next gen Javascript features that may not be supported by older (or current browsers) into code that can be used in legacy/current browsers.  

Typescript is a language built on top of javascript that allows for typing. Typescript can handle the transpiling that Babel does


# Code Formatting
Tools for maintaining a uniform styling across all devs/editors.
## [ESLint](https://eslint.org/)
A configurable tool for establishing code linting standards.
## [AirBNB rules](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb)
AirBNB open sourced their linting rules which are great out of the box, but can also be tweaked as needed.
## [Prettier](https://prettier.io/)
Opinionated code formatter that has support for most editors and many different languages. This can be used alongside ESLint, or is configurable on its own.

