<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
  </div>
</template>



<template>
  <div id='app'>
  <ejs-schedule height='550px' width='100%' :selectedDate='selectedDate'
  :eventSettings= 'eventSettings'>
    <e-views>
      <e-view option='Week' startHour='08:00' endHour='20:00' ></e-view>
      <e-view option='WorkWeek' startHour='08:00' endHour='20:00' ></e-view>
      <e-view option='Month' showWeekend=false></e-view>
    </e-views>
  </ejs-schedule>
  </div>
</template>
<script>
  import Vue from 'vue';
  import { scheduleData } from './datasource.js';
  import { extend } from '@syncfusion/ej2-base';
  import { SchedulePlugin,  WorkWeek, Month, Week } from '@syncfusion/ej2-vue-schedule';
  Vue.use(SchedulePlugin);
  export default {
data () {
  return {
    eventSettings: { dataSource: extend([], scheduleData, null, true) },
    selectedDate: new Date(2018, 1, 15)
  }
},
provide: {
  schedule: [ WorkWeek, Month, Week]
}
  }
</script>

<style>
@import '/node_modules/@syncfusion/ej2-base/styles/material.css';
@import '/node_modules/@syncfusion/ej2-buttons/styles/material.css';
@import '/node_modules/@syncfusion/ej2-calendars/styles/material.css';
@import '/node_modules/@syncfusion/ej2-dropdowns/styles/material.css';
@import '/node_modules/@syncfusion/ej2-inputs/styles/material.css';
@import '/node_modules/@syncfusion/ej2-navigations/styles/material.css';
@import '/node_modules/@syncfusion/ej2-popups/styles/material.css';
@import '/node_modules/@syncfusion/ej2-vue-schedule/styles/material.css';

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
  font-weight: normal;
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
