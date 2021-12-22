<template>
  <div id="app">
    <draggable v-model="list">
      <transition-group tag="div" class="grid" name="grid">
        <div class="cell" v-for="item in list" :key="item">{{item}}</div>
      </transition-group>
    </draggable>
  </div>
</template>

<script>
import draggable from "vuedraggable";

export default {
  name: "App",
  components: {
    draggable
  },
  data() {
    return {
      list: [1, 2, 3, 4, 5, 6, 7, 8, 9]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(3, 100px);
  grid-template-rows: repeat(3, 100px);
  grid-gap: 0.2em;
}

.grid-move {
  transition: all 0.3s;
}

.cell {
  background-color: lightblue;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
