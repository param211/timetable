<template>
<div class="cell" :class="classObject">
    <div class="time">
        {{ Number(time) }} - {{ Number(time) + 1 }}
    </div>
    <div class="name">
        <center> {{ code }} {{ name }} </center>
    </div>
    <!-- <div class="code">
        {{ code }}
    </div>
    <div class="teacher">
        {{ teacher }}
    </div>
    <div class="room">
        {{ room }}
    </div> -->
</div>
</template>

<script>
import moment from 'moment'

export default {
  name: 'Cell',
  props: {
    exists: Boolean,
    name: String,
    code: String,
    teacher: String,
    room: String,
    time: Number,
    day: String
  },
  methods: {
    moment: function () {
      return moment();
    }
  },
  computed: {
    classObject() {
      return {
        isNow: this.time == moment().format('H') && this.day == moment().format('ddd'),
        isDay: this.day == moment().format('ddd')
      }
    }
  },
}
</script>

<style scoped>

.isDay {
  background: #323232;
}

.isNow {
  background: #3B5249;
}

.cell {
  
  height: 50px;
  width: 150px;
  padding: 1px;
  border: 0.21px solid rgb(95, 95, 95);
  margin: 0;
  
}

.time {
  color: rgb(145, 145, 145);
}
</style>
