# React Redux

- [React Redux](#react-redux)
  - [Getting Started](#getting-started)
    - [Installation](#installation)
    - [Create Reducers](#create-reducers)
    - [Create Store](#create-store)
    - [Makes store available to rest of application](#makes-store-available-to-rest-of-application)
    - [Create Actions](#create-actions)
    - [Connect Component to Store](#connect-component-to-store)
      - [Dispatching Actions](#dispatching-actions)
        - [dispatch as a Prop](#dispatch-as-a-prop)
        - [mapDispatchToProps](#mapdispatchtoprops)
        - [bindActionCreators](#bindactioncreators)
      - [Extracting data from State](#extracting-data-from-state)
  - [Advanced](#advanced)
    - [batch](#batch)
    - [Hooks](#hooks)
      - [useSelector()](#useselector)
      - [useDispatch()](#usedispatch)
      - [userStore()](#userstore)
  - [References](#references)

## Getting Started

### Installation

`npm install redux react-redux`

### Create Reducers

```js
import { combineReducers } from "redux";

const userProfile = (state = initialState, action) => {
    switch(action.type) {
        case 'GET_USER_PROFILE':
            ...
        default:
            return state;
    }
}

export const rootReducer = combineReducers({ userProfile, uiData });
```

### Create Store

```js
import { createStore } from "redux";

export const store = createStore(rootReducer);
```

### Makes store available to rest of application

```js
import { Provider } from 'react-redux'

<Provider store={store}>
    <App />
</Provider>
```

### Create Actions

```js
const getUserProfile = userId => ({type: 'GET_USER_PROFILE', userId})
```

### Connect Component to Store

#### Dispatching Actions

##### dispatch as a Prop

- If you don't specify second argument to `connect` then `dispatch` is passed to props

```js
connect(mapStateToProps /** no second argument */)(MyComponent)
```

##### mapDispatchToProps

```js
<button onClick={() => this.props.getUserProfile(this.props.userId)} />

const mapDispatchToProps = dispatch => {
  return {
    getUserProfile: (userId) => dispatch({ type: 'GET_USER_PROFILE',  userId})
  }
}

// OR

<button onClick={() => this.props.getUserProfile()} />

const mapDispatchToProps = (dispatch, ownProps) => {
  return {
    getUserProfile: (userId) => dispatch({ type: 'GET_USER_PROFILE',  ownProps.userId})
  }
}

// OR

const mapDispatchToProps = { getUserProfileAction };

```

##### bindActionCreators

```js
import { bindActionCreators } from 'redux'

const getUserProfile = () => ({ type: 'GET_USER_PROFILE' })

// binding an action creator
const boundGetUserProfile = bindActionCreators(getUserProfile, dispatch)
// returns (...args) => dispatch(getUserProfile(...args))

// OR
const boundActionCreators = bindActionCreators(
  { getUserProfile },
  dispatch
)
// returns
// {
//   getUserProfile: (...args) => dispatch(getUserProfile(...args)),
// }

function mapDispatchToProps(dispatch) {
  return bindActionCreators({ getUserProfile }, dispatch)
}
```

#### Extracting data from State

```js
import { connect } from 'react-redux';

const MyComponent = ({currentValue}) => (<div>Current Value: {currentValue}</div>);

const mapStateToProps = (state /*, ownProps*/) => {
  return {
    currentValue: state.value
  }
}

export default connect(
  mapStateToProps,
  mapDispatchToProps
)(MyComponent)
```

## Advanced

### batch

```js
import { batch } from 'react-redux'

function myThunk() {
  return (dispatch, getState) => {
    // should only result in one combined re-render, not two
    batch(() => {
      dispatch(getUserProfile())
      dispatch(getUserDetails())
    })
  }
}
```

### Hooks

#### useSelector()

- Unlike `connect()`, `useSelector()` does not prevent the component from re-rendering due to its parent re-rendering, even if the component's props did not change.

```js
import { shallowEqual, useSelector } from 'react-redux'

// selector is conceptually equivalent to mapStateToProps
const selectedData: any = useSelector(selector: Function, equalityFn?: Function)

// Inside component to retrieve part of state
const { userProfile, userDetails } = useSelector(state => ({state.userProfile, state.userDetails}), shallowEqual)
```

#### useDispatch()

```js
import React, { useCallback } from 'react'
import { useDispatch } from 'react-redux'

// Inside component
{

    const dispatch = useDispatch()
    const getUserProfile = useCallback(
        (userId) => dispatch({ type: 'GET_USER_PROFILE', userId }),
        [dispatch]
    )
    <GetUserProfileButton onGetUserProfile={getUserProfile}>Get Profile</button>
}

export const GetUserProfileButton = React.memo(({ onGetUserProfile }) => (
  <button onClick={onGetUserProfile}></button>
))
```

#### userStore()

- Returns a reference to the same Redux store that was passed in to the <Provider> component
- Prefer `useSelector()` as your primary choice

```js
import { useStore } from 'react-redux'

export const UserProfileComponent = ({ value }) => {
  const store = useStore()

  // EXAMPLE ONLY! Do not do this in a real app.
  // The component will not automatically update if the store state changes
  return <div>{store.getState()}</div>
}
```



## References

[Quick Start](https://react-redux.js.org/introduction/quick-start)