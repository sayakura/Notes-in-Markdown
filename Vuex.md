### /store/store.js
``` javascript
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

export const store = new Vuex.store({
	state: {
		name: "value"
	}		
});

```

### main.js
``` javascript
import { store } from './store/store'


new Vue({
	el: '#app',
	store,		
})

```

### component.vue
``` javascript
	this.$store.state.name++;
```
