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
const CREATE_TODO = "CREATE_TODO";
const UPDATE_TODO = "UPDATE_TODO";
const DELETE_TODO = "DELETE_TODO";
```

## todoReducer.js

```
import {GET_TODOS, GET_TODO, CREATE_TODO, UPDATE_TODO, DELETE_TODO} from "types";

const initialState = {}
// or
const initialState = []

export default (state = initialState, { type, payload }) => {
    switch (type) {
    case GET_TODOS: // code
    case GET_TODO: // code
    case CREATE_TODO: // code
    case UPDATE_TODO: //code
    case DELETE_TODO: //code
    default:
        return state
    }
}

```

## todoAction.js

```
import {GET_TODOS, GET_TODO, CREATE_TODO, UPDATE_TODO, DELETE_TODO} from "types";
import axios from "axios";

// get all todos
export const getAllTodos = () => async dispatch => {
    dispatch({
        type: "GET_TODOS",
        payload: data
    })
}

// get a todo
export const getTodo = (id) => async dispatch => {
    dispatch({
        type: "GET_TODO",
        payload: data
    })
}

// create a todo
export const createTodo = (todo) => async dispatch => {
    dispatch({
        type: "CREATE_TODO",
        payload: data
    })
}

// update a todo
export const createTodo = (id) => async dispatch => {
    dispatch({
        type: "CREATE_TODO",
        payload: data
    })
}

// delete a todo
export const deleteTodo = (id) => async dispatch => {
    
    dispatch({
        type: "DELETE_TODO",
        payload: id
    })
}

```
