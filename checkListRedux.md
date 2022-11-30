*Antes de começar*
- [ ] pensar como será o *formato* do seu estado global
- [ ] pensar quais actions serão necessárias na sua aplicação

*Instalação*
- [ ] npx create-react-app my-app-redux;
- [ ] npm install --save redux react-redux;
- [ ] npm install --save @redux-devtools/extension

*Criar dentro do diretório `src`:*
- [ ] diretório `redux`

*Criar dentro do diretório `redux`*
- [ ] diretório `store`
- [ ] diretório `actions`
- [ ] diretório `reducers`

*Criar dentro do diretório `store`:*
- [ ] arquivo `index.js`.

*Criar dentro do diretório `actions`:*
- [ ] arquivo `index.js`.

*Criar dentro do diretório `reducers`:*
- [ ] arquivo `index.js`.

*Criar dentro do arquivo `redux/store/index.js`:*
- [ ] importar o createStore
- [ ] configurar o [Redux DevTools](https://github.com/reduxjs/redux-devtools)
- [ ] importar o rootReducer
- [ ] criar e exportar a store

Exemplo:

```js
import { legacy_createStore as createStore } from 'redux';
import { composeWithDevTools } from '@redux-devtools/extension';
import rootReducer from '../reducers';

const store = createStore(rootReducer, composeWithDevTools());

export default store;
```

*Criar dentro do arquivo `redux/reducers/index.js`:*
- [ ] estado inicial
- [ ] criar função reducer com `switch` retornando apenas a opção `default`
- [ ] criar `rootReducer` usando o `combineReducers`
- [ ] exportar `rootReducer`

Exemplo:

```js
import { combineReducers } from 'redux';

const INITIAL_STATE = {};

const exampleReducer = (state = INITIAL_STATE, action) => {
 switch(action.type) {
   default:
    return state;
 }
}

const rootReducer = combineReducers({ exampleReducer })

export default rootReducer;
```

*No arquivo `App.js`:*
- [ ] importar a `store`
- [ ] importar o `Provider`, para fornecer os estados a todos os componentes encapsulados pelo `<App />`

Exemplo:

```js
// Na importação
import { Provider } from 'react-redux';
import store from './redux/store'
```

```js
// No render
 <Provider store={ store } >
   <App />
 </Provider>
```

*Na pasta `actions/index.js`:*
- [ ] criar e exportar os actionTypes

Exemplo:

```js
// ACTIONS TYPES
export const ADD_EMAIL = 'ADD_EMAIL';
```

- [ ] criar e export os actions creators necessários

Exemplo:

```js
// ACTIONS CREATORS
export const addEmail = (email) => ({
  type: ADD_EMAIL,
  email,
})
```

*Nos reducers:*
- [ ] criar os casos para cada action criada, retornando o devido estado atualizado

*Nos componentes que irão ler o estado:*
- [ ] criar a função `mapStateToProps`
- [ ] exportar usando o `connect`

*O dispatch vem por padrão ao utilizar o connect ele que vai modificar o estado:*
- [ ] const { `connect` } = this.props;

Exemplo:

```js
// No import
import { connect } from 'react-redux';
```

```js
// No export
export default connect(mapStateToProps)(Component)
```
