<template>
<body>
  

  <Header/>
  <Filters/>
  <transition-group tag="div" name="fade" class="countries" id="countries">


  <CountryList/>
  <CountryDetails/>
  </transition-group>
</body>
</template>

<script>
import Header from '../src/components/Header.vue'
import Filters from '../src/components/Filters.vue'
import CountryList from '../src/components/CountryList.vue'
import CountryDetails from '../src/components/CountryDetails.vue'

export default {
  name: 'App',
  components: {
    Header,
    Filters,
    CountryList,
    CountryDetails
  }
}

// Function to show the countries depends on the filter choosen


</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@300;600;800&display=swap');


html,
body {
    font-family: 'Nunito Sans', sans-serif;
    margin: 0;
    box-sizing: content-box;
}

#vueContainer{
    min-height: 100vh;
}

header>div {
    margin-left: auto;
    margin-right: auto;
    height: 9vh;
    width: 85vw;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    
    font-weight: 600;
}

header{
    width: 100vw;
}

header>div>span:nth-child(1){
    font-size: 18px;
}

.countries {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
}

.country, .countryDetails {
    border-radius: 0.5vw;
    display: flex;
    flex-direction: column;
    margin: 1vw;
    
}

.country {
    width: 20vw;
    box-shadow: 0 10px 50px #00000057;
}

.countryDetails{
    width: 80vw;
}

.flag {
    background-size: cover;
    width: 100%;
    height: 150px;
    border-radius: 0.5vw 0.5vw 0 0;
}

.flagDetails {
    border-radius: 0.5vw 0.5vw 0 0;
    width: 40%;
    margin-right: 10vw;
}
.flagDetails>img{
    width: 100%;
    
}

.name {
    
    font-size: 20px;
    font-weight: 600;
}

.country>p {
    margin-left: 2vw;
    
}


.country>p>span, .details span {
    color: hsl(0, 5%, 70%);
}

.infos {
    margin-top: 0.3vw;
    margin-bottom: 0.3vw;
}

.filters {
    
    width: 85vw;
    margin-left: auto;
    margin-right: auto;
    display: flex;
    justify-content: space-between;
    margin-top: 40px;
    margin-bottom: 40px;
}

input {
    font-family: 'Nunito Sans', sans-serif;
    
    font-weight: 600;
    border: 0;
    outline: none;
    margin-left: 10px;
    width: 90%;
}

select{
    font-family: 'Nunito Sans', sans-serif;
    font-weight: 400;
    padding: 10px;
    border-radius: 0.3vw;
    border: 0;
    outline: none;
    box-shadow: none;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-image: url("data:image/svg+xml;utf8,<svg fill='black' height='24' viewBox='0 0 24 24' width='24' xmlns='http://www.w3.org/2000/svg'><path d='M7 10l5 5 5-5z'/><path d='M0 0h24v24H0z' fill='none'/></svg>");
    background-repeat: no-repeat;
    background-position-x: 100%;
    background-position-y: 5px;
}


#search {
    padding: 10px;
    width: 30vw;
    border-radius: 0.5vw;
}

.far.fa-moon{
    margin-right: 1vw;
}

.country:hover, #search:hover, .themeSwitch:hover, .regions:hover, select:hover, #back:hover, .themeSwitcher:hover{
    cursor: pointer;
}

#back{
    margin-top: 3vw;
    width: 130px;
    height: 40px;
    border-radius: 0.5vw;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}


/* theme and colors */
.dark, #search.dark{
    background-color: hsl(209, 23%, 22%);
    color: hsl(0, 0%, 100%);
}

.light, #search.light{
    background-color: hsl(0, 0%, 100%);
    color: hsl(200, 15%, 8%);
}

input.dark, #back.back{
    background-color: hsl(209, 23%, 22%);
}

input.light, #back.light{
    background-color: hsl(0, 0%, 100%);
}

#vueContainer.dark{
    background-color: hsl(207, 26%, 17%);
}
#vueContainer.light{
    background-color: hsl(0, 0%, 98%);
}

.details{
    margin-top: 2vw;
    display: flex;
    flex-direction: row;
}

.infosDetails{
    display: flex;
    flex-direction: column;
}

.flexRow>div{
    
    margin-right: 3vw;
}

.flexRow{
    display: flex;
    flex-direction: row;
}
.flexColumn{
    display: flex;
    flex-direction: column;
}

.borders>span {
    background-color: hsl(209, 23%, 22%);
    padding: 0.6vw;
    margin-right: 0.5vw;
}

@media only screen and (max-width: 600px)  {
    .countries, .filters, .details{
        flex-direction: column!important;
        align-items: center;
    }


    .country{
        width: 85vw;
        margin-bottom: 20px;
        padding-bottom: 10px;
    }

    .regions{
        margin-top: 3vw;
        align-self: flex-start;
    }

    input{
        width: unset!important;
    }

    #search{
        width: 80vw;
    }

    .flagDetails{
        width: unset;
    }

    .details{
        margin-top: 30px;
    }

    .infos{
        margin-bottom: 10px;
    }

}

.fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }
  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
  }
</style>
