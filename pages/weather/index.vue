<template lang="pug">
  .weather-wrap
    form(@submit.prevent="getWeather")
      input.card.card-search(
        type="text"
        placeholder="請輸入國家或城市的英文名稱"
        v-model="query"
      )
    .card.card-container
      .noContent(v-if="weatherData === ''")
        span(v-if="isError") 找不到這個地區
        span(v-else) 尚未查詢任何城市或國家
      .card-content(v-else)
        .title-wrap
          h2.title-text {{ weatherData.name }}
          span.description {{ weatherData.weather[0].description }}
        .content-detail
          .detail.detail-temp
            img.temp-img(:src="icon")
            span.temp-text {{ temp(weatherData.main.temp) }} &#176;C
          .detail.detail-other
            span.wind 風速：{{ weatherData.wind.speed }} 公尺/秒
            span.humidity 濕度：{{ weatherData.main.humidity }} %
            span.humidity 大氣壓：{{ weatherData.main.pressure }} hpa
</template>

<script>
export default {
  name: 'Weather',
  data () {
    return {
      loading: false,
      query: '',
      weatherData: '',
      isError: ''
    }
  },

  computed: {
    icon () {
      return `https://openweathermap.org/img/w/${this.weatherData.weather[0].icon}.png`
    }
  },

  methods: {
    getWeather (val) {
      this.loading = true
      let api = `${process.env.weatherUrl}?q=${this.query}&appid=${process.env.weatherApiKey}`
      this.$axios.$get(api).then((res) => {
        this.weatherData = res
      }).catch((err) => {
        this.isError = err
      })
      this.loading = false
    },
    temp (val) {
      // 將華氏轉為攝氏
      return Math.round(val - 273)
    }
  }
}
</script>

<style lang="scss" scoped>
  @import "./style";
</style>
