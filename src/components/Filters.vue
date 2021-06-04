<template>

        <div class="filters" v-show="isShow">
            <div id="search" :class="theme">
                <em class="fas fa-search"></em>
                <input type="text" :class="theme" data-type="name" v-on:keyup="name"
                    placeholder="Search for a country..." >
            </div>
            <div class="regions">
                <select name="regions" id="region-select" data-type="region" v-on:change="region" :class="theme">
                    <option disabled value="all">Filter By regions</option>
                    <option value="all">All</option>
                    <option value="region/africa">Africa</option>
                    <option value="region/americas">America</option>
                    <option value="region/asia">Asia</option>
                    <option value="region/europe">Europe</option>
                    <option value="region/oceania">Oceania</option>
                </select>
            </div>
        </div>
        
</template>

<script>
export default {
  name: 'Filters',
  props: {
    isShow: { type: Boolean, default: true }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
