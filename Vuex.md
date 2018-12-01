# An Overview
![vuex overview]
(./images/vuex-overview.png)


### /store/store.js
``` javascript
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

export const store = new Vuex.Store({
	state: {
		name: 0
	},
	getters: {
		doubleValue: state => {
			return state.name * 2;
		}
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
	import { mapGetters } from 'vuex'; // map getters to properties
	
	computed:{
		...mapGetters([ // here u add three dots becuase then u can mix your own computed 
						//properties with the ones from map getters as well
						// having this will cause an unexpected syntax error but it can be easily resolved with
						// npm install --save-dev babel-preset-stage-2
						// after the command runs, go to .babelrc add ["stage-2"] as a new preset.
		'doubleValue',
		//...
		]);
	}

	this.$store.state.name++;
	// or 
	return this.$store.getters.doubleValue;
```

