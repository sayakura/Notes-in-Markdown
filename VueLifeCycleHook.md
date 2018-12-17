## beforeCreate:
the instance is initialized, *this* keyword is pointed to the instance, but u
don't have access to the data, computed, watch, methods.

You can initialize variables that are not reactive here.

## created:
the instance is completely created, can access data, watch, and method's function
and data but since not mounted to the dom, have no access to any DOM elements and $el, $ref.

do simple ajax request or initialization of the page.

## beforeMount
This will be triggered before the template is mounted to the page.

## mounted
the instance is mounted to the DOM, u can do DOM API to get info about the DOM, u have access to the $ref var.

## before update
this will be triggered before the reactive variable is changed, it happened before virtual DOM is updated.

You can remove some listeners before the dom is updated. since after this, the old DOM will be changed.

## updated
happened after the virtual DOM is updated after changes have been made.

avoid changing the reactive variables here, might cause an infinite loop, since the instance will detect changes to the reactive variables and go through the life cycle again.

## beforeDestroy
This will be triggered before the instance is destroyed, in this stage, the instance is still usable, this keyword is still pointing to the instance.

You can destroy some timer or global event here.

## destroyed
the instance is destroyed.

1. don't do too much ajax call in the created hook, since the template is no rendered in the view, the page remains white during the ajax call.

2. mounted does not promise all its child components are also mounted if you want to wait till all the components are mounted, you can do *vm.$nextTick*. normally parent components mounted after child components mounted.

3. data between child components and parent components are monitored separately, but any change to the props are detected by both.
