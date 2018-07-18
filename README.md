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

## References
* [Vuex](https://vuex.vuejs.org/)
* [Managing Your Vue.js Application’s State with Vuex — Part 1](https://morningstar.engineering/managing-your-vue-js-applications-state-with-vuex-part-1-355514a7b710)