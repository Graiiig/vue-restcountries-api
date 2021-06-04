<template>
         <header :class="theme">
            <div :class="theme">
                <span>Where in the world ?</span>
                <div class="themeSwitcher"><em class="far fa-moon"></em><span class="themeButton" @click="switchTheme">Dark Mode</span></div>
            </div>
        </header>
        
</template>

<script>
export default {
  name: 'Header',
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
