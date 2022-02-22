<template>
  <div class="container">
    <div class="target" id="target">Vue Moveable</div>
    <Moveable
      className="moveable"
      v-bind:target="['.target']"
      v-bind:draggable="true"
      v-bind:scalable="true"
      v-bind:rotatable="true"
      @drag="onDrag"
      @scale="onScale"
      @rotate="onRotate"
    />
  </div>
</template>
<script>
import Moveable from "vue3-moveable";

export default {
  name: "app",
  components: {
    Moveable,
  },
  methods: {
    onDrag({ transform }) {
      document.getElementById("target").style.transform = transform;
    },
    onScale({ drag }) {
      document.getElementById("target").style.transform = drag.transform;
    },
    onRotate({ drag }) {
      document.getElementById("target").style.transform = drag.transform;
    },
  },
};
</script>
