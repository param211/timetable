<template>

<center>
  {{ moment().format('Do MMM YYYY') }}
  <br>
  {{ moment().format('dddd') }}
  <br>
  {{ moment().format(' h:mm a') }}
</center>
<br>
<div class="wrapper">
  <!-- <div class="time">
    <br>
    <div class="time-slot">
      <center>8 - 9</center>
    </div>
    <div  class="time-slot">
      <center>9 - 10</center>
    </div>
    <div  class="time-slot">
      <center>10 - 11</center>
    </div>
    <div  class="time-slot">
      <center>11 - 12</center>
    </div>
    <div  class="time-slot">
      <center>12 - 1</center>
    </div>
    <div class="time-slot">
      <center>1 - 2</center>
    </div>
    <div  class="time-slot">
      <center>2 - 3</center>
    </div>
    <div  class="time-slot">
      <center>3 - 4</center>
    </div>
    <div  class="time-slot">
      <center>4 - 5</center>
    </div>
    <div  class="time-slot">
      <center>5 - 6</center>
    </div>
  </div> -->

  <div class="day" v-for="(Day, key) in Days" :key="Day">
    <center> {{ key }} </center>
    <div class="class" v-for="Class in Day" :key="Class.time">
      <Cell :day="Class.day" :time="Class.time" :exists="Class.exist" :name="Class.name" :code="Class.code" :teacher="Class.teacher" :room="Class.room"></Cell>
    </div>
  </div>

</div>



</template>

<script>
import Cell from './Cell.vue'

import moment from 'moment'

export default {
  name: 'Table',
  props: {
    // msg: String
  },
  components: {
    Cell
  },
  data() {
    return {
      Days: { 
        Monday: [
          {day: "Mon", time: "8", exists: false, name: "", code: "", teacher: "", room: "test"},
          {day: "Mon", time: "9", exists: true, name: "Neural Nets", code: "ITD23", teacher: "Priti Bansal", room: "VR75"},
          {day: "Mon", time: "10", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Mon", time: "11", exists: true, name: "Org. Dev.", code: "EO013", teacher: "Duru Arun Kumar", room: "NB(S-01)"},
          {day: "Mon", time: "12", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Mon", time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Mon", time: "14", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Mon", time: "15", exists: true, name: "A.I.", code: "ITD05", teacher: "Apoorvi Sood", room: "Room:VR75"},
          {day: "Mon", time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Mon", time: "17", exists: false, name: "", code: "", teacher: "", room: ""},
        ],
        Tuesday: [
          {day: "Tue", time: "8", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Tue", time: "9", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Tue", time: "10", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Tue", time: "11", exists: true, name: "A.I.", code: "ITD05", teacher: "Apoorvi Sood", room: "Room:VR75"},
          {day: "Tue", time: "12", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Tue", time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Tue", time: "14", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Tue", time: "15", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Tue", time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Tue", time: "17", exists: true, name: "Neural Nets", code: "ITD23", teacher: "Priti Bansal", room: "VR75"},
        ],
        Wednesday: [
          {day: "Wed", time: "8", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Wed", time: "9", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Wed", time: "10", exists: true, name: "A.I.", code: "ITD05", teacher: "Apoorvi Sood", room: "Room:VR75"},
          {day: "Wed", time: "11", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Wed", time: "12", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Wed", time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Wed", time: "14", exists: true, name: "Org. Dev.", code: "EO013", teacher: "Duru Arun Kumar", room: "NB(S-01)"},
          {day: "Wed", time: "15", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Wed", time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Wed", time: "17", exists: false, name: "", code: "", teacher: "", room: ""},
        ],
        Thursday: [
          {day: "Thu", time: "8", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Thu", time: "9", exists: true, name: "Neural Nets", code: "ITD23", teacher: "Priti Bansal", room: "VR75"},
          {day: "Thu", time: "10", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Thu", time: "11", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Thu", time: "12", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Thu", time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Thu", time: "14", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Thu", time: "15", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Thu", time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Thu", time: "17", exists: true, name: "Org. Dev.", code: "EO013", teacher: "Duru Arun Kumar", room: "NB(S-01)"},
        ],
        Friday: [
          {day: "Fri", time: "8", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Fri", time: "9", exists: true, name: "Neural Nets", code: "ITD23", teacher: "Priti Bansal", room: "VR75"},
          {day: "Fri", time: "10", exists: true, name: "Org. Dev.", code: "EO013", teacher: "Duru Arun Kumar", room: "NB(S-01)"},
          {day: "Fri", time: "11", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Fri", time: "12", exists: true, name: "A.I.", code: "ITD05", teacher: "Apoorvi Sood", room: "Room:VR75"},
          {day: "Fri", time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Fri", time: "14", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Fri", time: "15", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Fri", time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {day: "Fri", time: "17", exists: false, name: "", code: "", teacher: "", room: ""},
        ]
      }
    };
  },
  methods: {
  moment: function () {
    return moment();
  }
},

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.wrapper{
    padding: 10px;
    display: flex;
    /* justify-content: flex-start; */
}

/* .time-slot {
  
  height: 20px;
  width: 50px;
  padding: 1px;
  border: 0.21px solid transparent;
  margin: 0;
  
} */
/* .day {
  flex-basis: 30%;
  box-sizing: border-box;
  
} */

</style>
