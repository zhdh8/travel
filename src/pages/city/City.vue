<template>
    <div>
      <city-header></city-header>
      <city-search></city-search>
      <city-list :cities="cities" :hot="hotCities" :letter="letter"></city-list>
      <city-alphabet :cities="cities" @change="handleMove"></city-alphabet>
    </div>
</template>
<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'City',
  data () {
    return {
      hotCities: [],
      cities: {},
      letter: ''
    }
  },
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(res => {
        res = res.data
        // console.log(res.data.cities)
        if (res.ret && res.data) {
          this.hotCities = res.data.hotCities
          this.cities = res.data.cities
        }
      }).catch(error => {
        console.log(error)
      })
    },
    handleMove (con) {
      // console.log(con)
      this.letter = con
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>
<style>

</style>
