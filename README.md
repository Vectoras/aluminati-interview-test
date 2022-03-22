# Changes

1. Replaced the limit with a required prop instead of accessing it through the parent instance

   - less code
   - better predictability
   - easier to maintain

2. Removed the use of the browser's DOM. The active class will be added/removed using the binded `:class` directive

   - much cleaner and intuitive
   - very easy to add / remove the class

3. Restructured the `numbers` property which now is an array of objects holding the number's value and the active/inactive state

   - provides a very clean way to add/remove the `.active` class

4. Replaced function `n()` responsible to generate the numbers with a property updated by a watcher placed on the `limit` prop

   - cleaner
   - vue takes care of updating it (reactivity)

5. Updated the `hov()` and `reset()` methods which now only update the `numbers` property

   - less code
   - using vue reactivity to update the template
