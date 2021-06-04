<template>
             
              <div id="country" @click="getDetailsOfCountry(country.name)" class="country"
                  v-for="(country,index) in countries" :key="index">
                  <div class="flag" v-bind:style="{ backgroundImage: 'url(' + country.flag + ')' }">
                  </div>
                  <p class="name">{{ country.name }}</p>
                  <p class="infos">Population : <span>{{ country.population }}</span></p>
                  <p class="infos">Region : <span>{{ country.region }}</span></p>
                  <p class="infos">Capital : <span>{{ country.capital }}</span></p>
              </div>
             
</template>

<script>

import axios from 'axios';

export default {
  name: 'ContryList',
  props: {
  },
  data(){
      return {
          countries : "",
      }
  },
  methods:{
        //function to show the countries by name
        name: function (event) {
            this.showCountries("https://restcountries.eu/rest/v2/name/", event.target.value)
        },
        //function to show the countries by region
        region: function (event) {
            this.showCountries("https://restcountries.eu/rest/v2/", event.target.value)
        },
        //function to show all the countries
        all: function () {
            let countries = this.countries;
            console.log(countries)
            //this.showCountries("https://restcountries.eu/rest/v2/all", "")
             axios.get("https://restcountries.eu/rest/v2/all")
                .then(response => {
                  // JSON responses are automatically parsed.
                  this.countries = response.data
                })
        },
        //function to switch between themes
        switchTheme: function() {
            
            if (this.theme == "dark") {
                    this.theme = "light"
            } else {
                    this.theme = "dark"
            }
        },
        //function to get details
        getDetailsOfCountry: function (name) {
            fetch("https://restcountries.eu/rest/v2/name/"+name)
            .then(response => response.json())
            .then(
                function (country) {
                    this.countries = ""
                    this.country = country
                    this.isShow = false
                })
        },
        showCountries: function (url, eventValue) {
        fetch(url + eventValue)
            .then(response => response.json())
            .then(
                function (countries) {
                    this.countries = countries
                    this.country = ""
                    this.isShow = true
                })
}
    },
    mounted(){
        // Load all countries when the page load the first time
        this.all()
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
