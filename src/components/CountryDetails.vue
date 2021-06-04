<template>
             <div>
<div id="countryDetails" class="countryDetails theme" v-for="(countryDetails,index) in country"
                :key="index">
                <div id="back" :class="theme" @click="all">
                    <span><em class="fas fa-long-arrow-alt-left"></em> Back</span>
                </div>

                <div class="details">

                    <div class="flagDetails">
                        <img :src="countryDetails.flag" alt="">
                    </div>
                    <div class="flexColumn">
                        <p class="name">{{ countryDetails.name }}</p>

                        <div class="flexRow">
                            <div>
                                <p class="infos">Native Name : <span>{{ countryDetails.nativeName }}</span></p>
                                <p class="infos">Population : <span>{{ countryDetails.population }}</span></p>
                                <p class="infos">Region : <span>{{ countryDetails.region }}</span></p>
                                <p class="infos">Sub Region : <span>{{ countryDetails.subregion }}</span></p>
                                <p class="infos">Capital : <span>{{ countryDetails.capital }}</span></p>
                            </div>
                            <div>
                                <div v-for="(topLevelDomain, index) in countryDetails.topLevelDomain" :key="index">
                                    <p class="infos">TLD : <span>{{ topLevelDomain }}</span></p>
                                </div>
                                <div v-for="(currency, index) in countryDetails.currencies" :key="index">
                                    <p class="infos">currency : <span>{{ currency.name }}</span></p>
                                </div>
                                <div>
                                    <p class="infos">Language(s) : <span
                                            v-for="(language, index) in countryDetails.languages" :key="index">{{ language.name }}  </span>
                                    </p>
                                </div>
                            </div>

                        </div>


                        <div>
                            <p v-if="countryDetails.borders.length" class="infos borders"> Border Countries : <span
                                    v-for="(borderCountry, index) in countryDetails.borders" :key="index">{{ borderCountry }} </span></p>
                            <p v-else > No border countries</p>
                        </div>
                    </div>
                </div>
            </div>
             </div>
</template>

<script>
export default {
  name: 'ContryList',
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
