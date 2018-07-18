# DeHacktory - Vuex
DeHacktory Vuejs session topic on 18th July, 2018. The first session will involve a brief introduction and then examples will follow. 

## Introduction

### Prerequisite
- Component communication via props and events
- Computed properties
### By definition, what is Vuex?
- A state management pattern and a library for Vuejs applications.
- A central data store that keeps track of state ensuring single source of truth.

```
    new Vue({
      // state
      data () {
        return {
          count: 0
        }
      },
      // view
      template: `
        <div>{{ count }}</div>
      `,
      // actions
      methods: {
        increment () {
          this.count++
        }
      }
    })
```

  _A simple implementation of state_

![one-way-data-flow](/screenshots/simple_state_management.png)

_Graphical representation of the simple implementation of state_

- But what happens when more than one component share same state

![vuex](/screenshots/vuex.png)

- Enables UI refresh in real time without need of a page refresh.

![grec-1](/screenshots/grec-1.png)

### Concepts

- State
    - AKA store
    - where the data is stored
    
    ```
        const store = new Vuex.Store({
          state: {
            count: 0
          }
        });
    ```
      
- Mutations

     - Used to modify a state
     ```
         const store = new Vuex.Store({
           state: {
             count: 0
           },
           mutations: {
             increment(state) {
               state.count++;
             }
           }
         });
         
         console.log('Count before commit', store.state.count);
         
         // commit the "increment" mutation
         store.commit('increment');
         
         console.log('Count after commit', store.state.count);
     ```
     - To invoke a commit, you need a key (name) and a value which is optional.
   
- Actions
    
    - Commit mutations
    - They are asynchronous
    ```
        const store = new Vuex.Store({
          state: {
            count: 0
          },
          mutations: {
            increment(state) {
              state.count++;
            }
          },
          actions: {
            increment(context) {
              context.commit('increment');
            }
          }
        });
        
        console.log('Count before dispatch', store.state.count);
        
        // dispatch the "increment" action
        store.dispatch('increment');
        
        console.log('Count after dispatch', store.state.count);
    ```

- Getters

    - They are as a result of state computation.
    - Allow data transformation prior to returning to view
    ```
        const store = new Vuex.Store({
          state: {
            todos: [
              { id: 1, text: '...', done: true },
              { id: 2, text: '...', done: false }
            ]
          },
          getters: {
            doneTodos: state => {
              return state.todos.filter(todo => todo.done)
            }
          }
        })
    ```


### Access Helpers

   - mapGetters 
   
     - Maps store getters to local computed properties
   - 
## References
* [Vuex](https://vuex.vuejs.org/)
* [Managing Your Vue.js Application’s State with Vuex — Part 1](https://morningstar.engineering/managing-your-vue-js-applications-state-with-vuex-part-1-355514a7b710)