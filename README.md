1. Replaced the limit with a required prop instead of accessing it through the parent instance

- less code
- cleaner
- better predictability
- easier to maintain

2. replaced function "n()" responsible to generate the numbers with a property updated by a watcher placed on the "limit" prop

- cleaner
- vue takes care of updating it (reactivity)

3.
