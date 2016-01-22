# vue

This is just the vue app. You will need to create a phoenix app with --no-brunch alongside this app. For simplicity call the phoenix app nobvue.
the browserify task will place app.js inside the  ../nobvue/priv/static/js/app.js folder.
it will recreate the app.js file every time you change your code
For more information see the [docs for vueify](https://github.com/vuejs/vueify).
and the vue-cli tool from where i created this app
http://vuejs.org/2015/12/28/vue-cli/



Just do 
npm install
inside the vue2phoenix app
and then
npm run dev

then
inside nobvue folder run your phoenix app
then inside your layout.html.ex add the vue component < app > < / app >



adapt it to your needs...


