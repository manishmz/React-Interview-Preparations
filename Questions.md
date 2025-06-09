# Questions
[youtube playlist](https://www.youtube.com/playlist?list=PL7pEw9n3GkoUZX3e9lBbmQqdCpgAWYooz)
### How to create react app from scratch
index.html
```
<html>
    <head>
    </head>
    <body>
        <div id="root"></div>
    </body>
</html>
```

index.js
```
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';
import reportWebVitals from './reportWebVitals';
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
````

### Lifecycle Methods (v 16.4+)
##### Mount Phase
- `constructor`: runs only once
- `static getDerievedStateFromProps`: Update state from props. This is static method as developer should not use 'this' in method.
- `render`: returns body of component (jsx)
- `componentDidMount`: do something after compoenent mount in this lifecycle

##### Update Phase
- `static getDerievedStateFromProps`
- `shouldComponentUpdate`: Make decision here that the component should rerender or not
- `render`
- `getSnpashotBeforeUpdate`: Before updating if we want some old state values we can get here
- `componentDidUpdate`: do something after component update

##### Unmount
- `componentWillUnMount`


### How to do typecheck 
We can use `prop-types` library or `typescript`
##### PropTypes
#
```
import Reat from 'react';
import PropTypes from 'prop-types';

const Test = (props) => {
    return <Fragment>
        <h1>{props.str}</h1>
        <span>{props.bool ? 'YES' : 'NO'}</span>
        <span>{props.strOrNum}</span>
        <ul>
        {props.arry.map((val)=> {
            return <li key={val}> {val} </li>;
        });
        }
        </ul>
    </Fragment>
}

Test.propTypes = {
    str: PropTypes.string,
    bool: PropTypes.bool,
    strOrNum: PropTypes.oneOfType(PropTypes.string, PropTypes.number),
    arry: PropTypes.arrayOf(PropTypes.number)
}
```
### What is Higher Order Component
```
import React from 'react';
import commonStyles from '../styles/commonStyles';

const translateProps = (props) => {
    let _style = {...commonStyles.default};
    if(prop.disable){
        _style = {..._style, ...commonStyles.disable};
    }
    const newProps = {...props, styles: _style};
    return newProps;
}

export default (WrappedComponent) => {
    return function wrappedRender(args) {
        return WrappedComponent(translateProps(args));
    }
}
```
##### Use
#
```
import Reat from 'react';
import stylesWrapper from '../HOC/stylesWrapper';

const ButtonOne = (props) => {
    return (
        <button style={props.style}>Click Me</button>
    )
}
export default stylesWrapper(ButtonOne);
```
### What is Redux
Redux is a library which used to manage state in application, i.e sharing data over all components very easily.
##### Without using hooks
`reducer.js`
```
const intialState = {
    age: 23
}

const reducer = (state = intialState, action) => {
    const newState = {...state};
    if(action.type == "AGE_UP" ){
        newState.age += action.val;
    }
     if(action.type == "AGE_DOWN" ){
        newState.age -= action.val;
    }
    return newState;
}

export default reducer;
```
`index.js`
```
import Provider from 'react-redux';
import {createStore} from 'redux';
import reducer from './store/reducer';
 
const store = createStore(reducer);

ReactDOM.render(
    <Provider store={store}>
        <App/>
    </Provider>, 
    document.getElementById('root'));
```
`App.js`
```
import  {connect} from 'react-redux';

class App extends Component {
    render() {
        return (<div>
            <span>{this.props.age}</span>
            <button onclick={this.props.onAgeUp}>Age Up</button>
            <button onclick={this.props.onAgeDown}>Age Down</button>
        </div>);
    }
}

const mapStateToProps = (state) => {
    return {
        age: state.age
    }
}
const mapDispatchToProps = (dispatch) => {
    return {
        onAgeUp : dispatch({type: 'AGE_UP', val: 2}),
        onAgeDown : dispatch({type: 'AGE_DOWN', val: 1}),
    }
}

export default connect(mapStateToProps, mapDispatchToProps)(App);
```
##### Using Hooks
`index.js` and `reducer.js` will be same as above, changes will be in `App.js`

`App.js`
```
import { useDispatch, useSelector } from "react-redux";
const App = (props) => {
    const age = useSelector(state=> state.age);
    const dispatch = useDispatch();
    const onAgeUp = () => {
        return dispatch({type: 'AGE_UP', val: 2});
    }
    const onAgeDown = () => {
        return dispatch({type: 'AGE_DOWN', val: 1});
    }
    return (<div>
            <span>{age}</span>
            <button onclick={onAgeUp}>Age Up</button>
            <button onclick={onAgeDown}>Age Down</button>
        </div>);
}
export default App;
```

### How to use multiple reducer
Use combineReducers from 'redux' to combine multiple reducers
```
import {createStore, comibneReducers} from 'redux';
import reducerA from './store/reducerA';
import reducerB from './store/reducerB';

const combReducer = comibneReducers(reducerA, reducerB);
const store = createStore(combReducer);
...
```
### Redux middleware
Redux middleware mainly it helps to update database data before updating the store. They are two mostly use middleware library `redux-thunk` and `redux-saga`

##### redux-thunk
#
```
import React from 'react';
import Provider from 'react-redux';
import {createStore, applyMiddleware} from 'redux';
import reducer from './store/reducer';
import thunk from {redux-thunk};

const store = createStore(reducer, applyMiddleware(thunk));
ReactDOM.render(<Provider store={store}>
        <App/>
    </Provider
    , document.getElementById('root'));
```

##### redux-saga 
`index.js`
```
import React from 'react';
import Provider from 'react-redux';
import {createStore, applyMiddleware} from 'redux';
import reducer from './store/reducer';
import createSagaMiddleware from {redux-saga};
import {watchAgeUp} from './saga';

const sagaMiddleware = createSagaMiddleware();
const store = createStore(reducer, applyMiddleware(sagaMiddleware));
sagaMiddleware.run(watchAgeUp);

ReactDOM.render(<Provider store={store}>
        <App/>
    </Provider
    , document.getElementById('root'));
```
`saga.js`
```
import {takeEvery, put} from 'redux-saga/effects';
import {delay} from 'redux-saga';

function* ageUpAsync() {
    yield delay(4000);
    yield put({type: 'AGE_UP_ASYNC', val: 1});
}
export function* watchAgeUp() {
    yield takeEvery('AGE_UP', ageUpAsync);
}
```
### Whait is react Memo
It's an alternate option for Pure component and shouldComponentUpdate.
It's for an fucntional component as above alternatives for class component.
```
import React from 'react';

export default React.Memo((props) => {
    return (<div>{props.val}</div>);
});
```
### React Lazy Loading
Lazy Loaded component not loaded at start and will Load when it is asked for first time
```
import React, {lazy} from 'react';
// import AboutUs from './components/AboutUs';
const AboutUs = lazy(() => import('./components/AboutUs'));
import Loading from './components/Loading';

const App = () => {
    return (<div> 
        <h3>Dashboard</h3>
        <Suspense fallback={<Loading/>}>
            <AboutUs></AboutUs>
        </Suspense>
    <div>);
}

export default App;
```

### Explain Error Boundaries
A custom component used to catch errors, similar like a try catch block
```
import SomeCustomErrorBoundComp from './component/SomeCustomErrorBoundComp';
const App = () => {
    return <div>
        <SomeCustomErrorBoundComp>
            <SomeComp/>
        </SomeCustomErrorBoundComp>
    </div>
}
export default App;
```
It has two lifecycle method
- `static getDerivedStateFromError`
- `componentDidCatch`

`SomeCustomErrorBoundComp.js`
```
class SomeCustomErrorBoundComp extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    // Update state so the next render will show the fallback UI.
    return { hasError: true };
  }

  componentDidCatch(error, errorInfo) {
    // You can also log the error to an error reporting service
    logErrorToMyService(error, errorInfo);
  }

  render() {
    if (this.state.hasError) {
      // You can render any custom fallback UI
      return <h1>Something went wrong.</h1>;
    }

    return this.props.children; 
  }
}
export default SomeCustomErrorCoundComp;
```

### What is context-api
context api used to allow to access props to descendents childs. Solution for prop drilling
`Context.js`
```
import React, { createContext, useState } from "react";

export const AppContext = createContext();

const { Provider } = AppContext;

export const AppProvider = (props) => {
  const [count, setCount] = useState(0);
  return <Provider value={[count, setCount]}>{props.children}</Provider>;
};
```

`Parent.js`
```
import React, { useState } from "react";
import Button from "./Child1";
import Label from "./Label";
import { AppProvider } from "./Context";

const Parent = (props) => {
  const [b1Count, setB1Count] = useState(0);
  const onB1Click = () => {
    setB1Count(b1Count + 1);
  };

  return (
    <AppProvider>
      <h3>Parent</h3>
      <Button onclick={onB1Click}>B1</Button> <br />
      <Label value={b1Count}></Label>
    </AppProvider>
  );
};

export default Parent;
```
`Button.js`
```
import React, { Fragment, useContext } from "react";
import { AppContext } from "./Context";

const Button = (props) => {
  const [count, setCount] = useContext(AppContext);
  const onButtonClick = () => {
    setCount(count + 1);
  };

  return (
    <Fragment>
      <button className="" onClick={onButtonClick}>
        {props.children}
      </button>
    </Fragment>
  );
};

export default Button;

```

`Label.js`
```
import React, { Fragment, useContext } from "react";
import { AppContext } from "./Context";

const Label = (props) => {
  const [count, setCount] = useContext(AppContext);

  return (
    <Fragment>
      <label>Count: {count}</label>
    </Fragment>
  );
};

export default Label;
```
### What id render prop
passsing component as function

##### What is Fragment
React return single element when render. So Wrapping multiple elements we use Fragments. We can use <div> but at last it can also have some css attach.

##### How to do code splitting in react
When the react bundles, its a huge bundle. so while loading website to gets slow because of bundle size.
The solution is to split the bundles and load bundles when user asked for, using lazy loading which is called code splitting
lazy load components which user hardly visits
