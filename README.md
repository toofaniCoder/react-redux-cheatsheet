# React Redux Cheatsheet

## store.js
```
import { createStore, applyMiddleware } from 'redux';
import { composeWithDevTools } from 'redux-devtools-extension';
import thunk from 'redux-thunk';
import rootReducer from './reducers';

const initialState = {};

const middleware = [thunk];

const store = createStore(
  rootReducer,
  initialState,
  composeWithDevTools(applyMiddleware(...middleware))
);

export default store;
```

## types.js
```
const GET_TODOS = "GET_TODOS";
const GET_TODO = "GET_TODO";
const CREATE_TODOS = "CREATE_TODOS";
const UPDATE_TODOS = "UPDATE_TODOS";
const DELETE_TODOS = "DELETE_TODOS";
```

