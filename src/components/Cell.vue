<template>
<div class="cell">
    <!-- <div class="time">
        {{ time }} - {{ Number(time) + 1 }}
    </div> -->
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
export default {
  name: 'Cell',
  props: {
    exists: Boolean,
    name: String,
    code: String,
    teacher: String,
    room: String,
    time: Number
  }
}
</script>

<style scoped>
.cell {
  height: 1rem;
  width: 10rem;
  padding: 2px;
  border: 0.21rem solid rgb(95, 95, 95);
  margin: 0;
}
</style>
