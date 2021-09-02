<template>
<!-- <div>
<div class="day Monday">
  <div class="cell 8">
  </div>
  <div class="cell 9">
  </div>
  <div class="cell 10">
  </div>
  <div class="cell 11">
  </div>
  <div class="cell 12">
  </div>
  <div class="cell 13">
  </div>
  <div class="cell 14">
  </div>
  <div class="cell 15">
  </div>
  <div class="cell 16">
  </div>
  <div class="cell 17">
  </div>
</div>

<div class="day Tuesday">
  <div class="cell 8">
  </div>
  <div class="cell 9">
  </div>
  <div class="cell 10">
  </div>
  <div class="cell 11">
  </div>
  <div class="cell 12">
  </div>
  <div class="cell 13">
  </div>
  <div class="cell 14">
  </div>
  <div class="cell 15">
  </div>
  <div class="cell 16">
  </div>
  <div class="cell 17">
  </div>
</div>

<div class="day Wednesday">
  <div class="cell 8">
  </div>
  <div class="cell 9">
  </div>
  <div class="cell 10">
  </div>
  <div class="cell 11">
  </div>
  <div class="cell 12">
  </div>
  <div class="cell 13">
  </div>
  <div class="cell 14">
  </div>
  <div class="cell 15">
  </div>
  <div class="cell 16">
  </div>
  <div class="cell 17">
  </div>

</div>

<div class="day Thursday">
  <div class="cell 8">
  </div>
  <div class="cell 9">
  </div>
  <div class="cell 10">
  </div>
  <div class="cell 11">
  </div>
  <div class="cell 12">
  </div>
  <div class="cell 13">
  </div>
  <div class="cell 14">
  </div>
  <div class="cell 15">
  </div>
  <div class="cell 16">
  </div>
  <div class="cell 17">
  </div>

</div>

<div class="day Friday">
  <div class="cell 8">
  </div>
  <div class="cell 9">
  </div>
  <div class="cell 10">
  </div>
  <div class="cell 11">
  </div>
  <div class="cell 12">
  </div>
  <div class="cell 13">
  </div>
  <div class="cell 14">
  </div>
  <div class="cell 15">
  </div>
  <div class="cell 16">
  </div>
  <div class="cell 17">
  </div>

</div>
</div> -->
<center>
  {{ moment().format('Do MMM YYYY') }}
  <br>
  {{ moment().format('dddd') }}
  <br>
  {{ moment().format(' h:mm a') }}
</center>
<br>
<div class="wrapper">
  <div class="time">
    <br>
    <div class="time-slot">
      8 - 9
    </div>
    <div  class="time-slot">
      9 - 10
    </div>
    <div  class="time-slot">
      10 - 11
    </div>
    <div  class="time-slot">
      11 - 12
    </div>
    <div  class="time-slot">
      12 - 1
    </div>
    <div class="time-slot">
      1 - 2
    </div>
    <div  class="time-slot">
      2 - 3
    </div>
    <div  class="time-slot">
      3 - 4
    </div>
    <div  class="time-slot">
      4 - 5
    </div>
    <div  class="time-slot">
      5 - 6
    </div>
  </div>

  <div class="day" v-for="(Day, key) in Days" :key="Day">
    <center> {{ key }} </center>
    <div class="class" v-for="Class in Day" :key="Class.time">
      <Cell :time="Class.time" :exists="Class.exist" :name="Class.name" :code="Class.code" :teacher="Class.teacher" :room="Class.room"></Cell>
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
          {time: "8", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "9", exists: true, name: "Neural Nets", code: "ITD23", teacher: "Priti Bansal", room: "VR75"},
          {time: "10", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "11", exists: true, name: "Org. Dev.", code: "EO013", teacher: "Duru Arun Kumar", room: "NB(S-01)"},
          {time: "12", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "14", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "15", exists: true, name: "A.I.", code: "ITD05", teacher: "Apoorvi Sood", room: "Room:VR75"},
          {time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "17", exists: false, name: "", code: "", teacher: "", room: ""},
        ],
        Tuesday: [
          {time: "8", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "9", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "10", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "11", exists: true, name: "A.I.", code: "ITD05", teacher: "Apoorvi Sood", room: "Room:VR75"},
          {time: "12", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "14", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "15", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "17", exists: true, name: "Neural Nets", code: "ITD23", teacher: "Priti Bansal", room: "VR75"},
        ],
        Wednesday: [
          {time: "8", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "9", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "10", exists: true, name: "A.I.", code: "ITD05", teacher: "Apoorvi Sood", room: "Room:VR75"},
          {time: "11", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "12", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "14", exists: true, name: "Org. Dev.", code: "EO013", teacher: "Duru Arun Kumar", room: "NB(S-01)"},
          {time: "15", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "17", exists: false, name: "", code: "", teacher: "", room: ""},
        ],
        Thursday: [
          {time: "8", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "9", exists: true, name: "Neural Nets", code: "ITD23", teacher: "Priti Bansal", room: "VR75"},
          {time: "10", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "11", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "12", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "14", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "15", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "17", exists: true, name: "Org. Dev.", code: "EO013", teacher: "Duru Arun Kumar", room: "NB(S-01)"},
        ],
        Friday: [
          {time: "8", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "9", exists: true, name: "Neural Nets", code: "ITD23", teacher: "Priti Bansal", room: "VR75"},
          {time: "10", exists: true, name: "Org. Dev.", code: "EO013", teacher: "Duru Arun Kumar", room: "NB(S-01)"},
          {time: "11", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "12", exists: true, name: "A.I.", code: "ITD05", teacher: "Apoorvi Sood", room: "Room:VR75"},
          {time: "13", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "14", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "15", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "16", exists: false, name: "", code: "", teacher: "", room: ""},
          {time: "17", exists: false, name: "", code: "", teacher: "", room: ""},
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
    display: flex;
    justify-content: center;
}

.time-slot {
  height: 1rem;
  width: 3;
  padding: 2px;
  border: 0.21rem solid transparent;
  margin: 0;
}
/* .day {
  flex-basis: 30%;
  box-sizing: border-box;
  
} */

</style>
