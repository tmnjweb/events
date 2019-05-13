<template>
  <div id="app">
    <div class="float-my-children">
      <img v-bind:src="tmnjLogo" width="50" />
    </div>
    <div style='margin-left:60px;'>
      <h1>TMNJ Event Calendar</h1>
    </div>
    <vue-event-calendar
      :events="demoEvents"
      @day-changed="handleDayChanged"
      @month-changed="handleMonthChanged"
    ></vue-event-calendar>
  </div>
</template>

<script>
let today = new Date()
export default {
  name: 'app',
  data () {
    return {
      tmnjLogo: './../assets/pp.jpeg',
      demoEvents: [{
        date: '2019/05/21',
        title: 'Sri Lankan Masjid Iftaar',
        desc: 'Iftar sponsored by TMNJ brothers - 157 Plainfield Ave, Edison, NJ 08817'
      },{
        date: `2019/05/24`,
        title: 'சித்திக் பாய் வீடு ;-)'
      }]
    }
  },
  methods: {
    handleDayChanged (data) {
      console.log('date-changed', data)
    },
    handleMonthChanged (data) {
      console.log('month-changed', data)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 30px;
}

h1, h2, h3 {
  font-weight: normal;
  margin: 0;
  padding: 0;
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
.t-center{
  text-align: center;
  margin: 20px;
}

/* tell the container's children to float left: */
.float-my-children > * {
  float:left;
  margin-right:5px;
}

.mt150{
  margin-top: 150px;
}
</style>
