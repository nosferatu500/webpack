<template lang="pug">
  #app
    img(src="./assets/logo.png")
    {{#router}}
    router-view
    {{else}}
    hello
    {{/router}}
</template>

<script>
{{#unless router}}
import Hello from './components/Hello'{{#if_eq lintConfig "airbnb"}};{{/if_eq}}

{{/unless}}
export default {
  name: 'app'{{#router}}{{#if_eq lintConfig "airbnb"}},{{/if_eq}}{{else}},
  components: {
    Hello{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
  }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}{{/router}}
}{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
</script>

<style lang="sass">

#app 
  font-family: Hammersmith_One
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #2c3e50
  margin-top: 60px
  // must for mobile build
  width: auto
  
@media screen and (max-width: 400px)
  #app
    margin-top: 30px
    img
      width: 50%
</style>
