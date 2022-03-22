#Changes

1. Replaced the limit with a required prop instead of accessing it through the parent instance

- less code
- cleaner
- better predictability
- easier to maintain

2. Replaced function "n()" responsible to generate the numbers with a property updated by a watcher placed on the "limit" prop

- cleaner
- vue takes care of updating it (reactivity)

3. Updated the "hov()" and "reset()" methods which now only update the "numbers" property

- less code
- using vue reactivity to update the template
